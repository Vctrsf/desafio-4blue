# Bug Report — Formulário de Cadastro Permite Envio com Campos Vazios

## Resumo
O formulário de cadastro permite que o usuário clique em "Criar conta" sem preencher nenhum campo, sem exibir mensagens de validação ou bloquear envio.

## Impacto
Permite o envio de um formulário completamente vazio, comprometendo a integridade dos dados enviados ao backend e quebrando o fluxo esperado de cadastro. 
**Severidade:** Alta — falha de validação crítica que compromete diretamente o fluxo de cadastro e a integridade dos dados. 
**Impacto:** Alto (permite criação de registros inválidos ou incompletos no sistema)

## Escopo
**Afeta:** Formulário de cadastro completo (NOME COMPLETO, TELEFONE, EMAIL, SENHA, CONFIRMAR SENHA)
**Plataformas:** Web (desktop e visualizações responsivas)
**Navegadores:** Reproduzível em navegadores modernos (baseados em Chromium e WebKit)
**Usuários:** Todos os usuários que acessam a tela de cadastro

## Ambiente
**Ambiente:** Ambiente similar ao de produção
**Feature flags:** Padrões padrão, sem flags de validação de formulário habilitadas

## Passos para Reproduzir
1. Dado que estou na tela de login
2. Quando clico na opção "Criar conta"
3. E não preencho nenhum campo do formulário
4. Quando clico em "Criar conta"
5. Observo que o sistema não exibe mensagens de validação e permite a envio

## Resultado Esperado
Ao tentar submeter o formulário com campos vazios, o sistema deve bloquear a envio e 
exibir mensagens de validação indicando quais campos são obrigatórios.

## Hipóteses

### Prováveis Causas
1. **Ausência de validação de campos obrigatórios**
   * Os campos do formulário não possuem o atributo `required` ou validação via React 
   (como `react-hook-form` com schema Zod), permitindo a envio sem qualquer verificação 
   de preenchimento.

2. **Componente shadcn/ui sem validação nativa**
   * Os inputs utilizam o componente base do shadcn/ui, que não inclui validação de 
   obrigatoriedade por padrão. A validação precisa ser implementada explicitamente 
   no componente React, o que não foi feito.

3. **Falta de cobertura de testes de validação de formulário**
   * Não há testes automatizados verificando o comportamento do formulário para envio 
   com campos vazios, o que permitiu que a ausência de validação passasse despercebida.

### Fatores Contribuintes
* O Tailwind CSS e o Radix UI, base do shadcn/ui, não fornecem validação de formulário 
nativamente — exigindo implementação explícita no componente React.
* Revisão insuficiente do comportamento de envio do formulário durante o code review.

### Riscos de Regressão
1. Registros incompletos ou inválidos podem ser persistidos no backend caso não haja 
validação server-side complementar.
2. Outros formulários do produto podem replicar o mesmo padrão sem validação de 
obrigatoriedade.

### Estratégia de Mitigação
* Implementar validação de formulário com `react-hook-form` e schema Zod, garantindo 
que todos os campos obrigatórios sejam verificados antes da envio.
* Exibir mensagens de erro individuais por campo ao tentar submeter o formulário vazio.
* Adicionar casos de teste automatizados verificando o bloqueio de envio com 
campos vazios.
* Incluir verificação explícita de validação de formulário durante o code review.