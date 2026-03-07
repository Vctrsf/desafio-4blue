# Bug Report — Inputs Possuem Layout Sobreposto

## Resumo
Os campos do formulário de cadastro apresentam padding interno inconsistente em todos os inputs. Os campos NOME COMPLETO, TELEFONE, EMAIL, SENHA e CONFIRMAR SENHA estão renderizando com espaçamento interno visivelmente maior do que o definido, resultando em uma inconsistência visual generalizada.

## Impacto
Quebra o alinhamento visual entre design e implementação, reduz a reconhecibilidade dos campos do formulário e introduz uma linguagem visual inconsistente na mesma superfície de UI.

**Severidade:** Baixa — inconsistência visual sem impacto funcional ou de segurança.  
**Impacto:** Baixo (afeta apenas a aparência dos campos, sem comprometer o funcionamento do formulário)  
**Prioridade:** Baixa  

## Escopo
**Afeta:** Formulário de cadastro  
**Plataformas:** Web (desktop e visualizações responsivas)  
**Navegadores:** Reproduzível em navegadores modernos (baseados em Chromium e WebKit)  
**Usuários:** Todos os usuários que acessam a tela de criação de conta  

## Ambiente
**Ambiente:** Ambiente similar ao de produção

## Passos para Reproduzir
1. Dado que estou na tela de login
2. Quando clico na opção "Criar conta"
3. E localizo os campos NOME COMPLETO, TELEFONE, EMAIL, SENHA e CONFIRMAR SENHA.
4. Então verifico que o padding definido para os campos do formulário estão fora do padrão de design, sobrepondo uns aos outros.

## Resultado Esperado
O padding dos campos do formulário de cadastro deve corresponder exatamente à definição de design prototipado, incluindo:

- **Espaçamento interno:** Mesmo padding horizontal e vertical em todos os campos
- **Proporções:** Mesma altura e área clicável em todos os inputs
- **Consistência:** Alinhamento uniforme entre todos os campos do formulário
- **Padrões visuais:** Conformidade com o grid e estilização.