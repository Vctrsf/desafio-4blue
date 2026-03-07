# Bug Report — Formulário de Cadastro Permite Envio com Campos Vazios

## Resumo
O formulário de cadastro permite que o usuário clique em "Criar conta" sem preencher nenhum campo, sem exibir mensagens de validação ou bloquear envio.

## Impacto
Permite o envio de um formulário completamente vazio, comprometendo a integridade dos dados enviados ao backend e quebrando o fluxo esperado de cadastro. 

**Severidade:** Crítica — falha de validação crítica que compromete diretamente o fluxo de cadastro e a integridade dos dados.  
**Impacto:** Alto (permite criação de registros inválidos ou incompletos no sistema)  
**Prioridade**: Crítica  

## Escopo
**Afeta:** Formulário de cadastro completo (NOME COMPLETO, TELEFONE, EMAIL, SENHA, CONFIRMAR SENHA)  
**Plataformas:** Web (desktop e visualizações responsivas)  
**Navegadores:** Reproduzível em navegadores modernos (baseados em Chromium e WebKit)  
**Usuários:** Todos os usuários que acessam a tela de cadastro  

## Ambiente
**Ambiente:** Ambiente similar ao de produção

## Passos para Reproduzir
1. Dado que estou na tela de login
2. Quando clico na opção "Criar conta"
3. E não preencho nenhum campo do formulário
4. Quando clico em "Criar conta"
5. Observo que o sistema não exibe mensagens de validação e permite a envio

## Resultado Esperado
Ao tentar submeter o formulário com campos vazios, o sistema deve bloquear a envio e exibir mensagens de validação indicando quais campos são obrigatórios.