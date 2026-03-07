# Bug Report — Validação de Senha Não Bloqueia Cadastro com Senha Inválida

## Resumo
O formulário de cadastro exibe a regra de que a senha deve conter no mínimo 8 caracteres e 1 caractere especial, porém não bloqueia o envio quando essa regra não é atendida, permitindo a criação de conta com uma senha fora do padrão definido.

## Impacto
Compromete a política de segurança de senhas do produto, permitindo o cadastro com senhas fracas e fora do padrão definido, expondo os usuários a riscos de segurança.

**Severidade:** Alta — falha de validação crítica.  
**Impacto:** Alto (permite criação de contas com senhas fracas)  
**Prioridade:** Alta  

## Escopo
**Afeta:** Campo SENHA no formulário de cadastro  
**Plataformas:** Web (desktop e visualizações responsivas)  
**Navegadores:** Reproduzível em navegadores modernos (baseados em Chromium e WebKit)  
**Usuários:** Todos os usuários que acessam a tela de cadastro  

## Ambiente
**Ambiente:** Ambiente similar ao de produção

## Passos para Reproduzir
1. Dado que estou na tela de login
2. Quando clico na opção "Criar conta"
3. E preencho os campos NOME COMPLETO, TELEFONE e EMAIL com valores válidos
4. Quando preencho o campo SENHA com um valor que não atende às regras (ex: `123`)
5. E preencho o campo CONFIRMAR SENHA com o mesmo valor
6. Quando clico em "Criar conta"
7. Observo que o sistema realiza o cadastro sem exibir mensagem de erro sobre a senha

## Resultado Esperado
Ao tentar enviar o formulário com uma senha que não atende às regras definidas, o sistema deve bloquear o envio e exibir uma mensagem de que os critérios de senha forte não foram cumpridos

