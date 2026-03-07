# Bug Report — Cadastro Permitido com Senhas Divergentes

## Resumo
O formulário de cadastro permite a criação de conta mesmo quando os valores inseridos nos campos SENHA e CONFIRMAR SENHA são diferentes, sem exibir mensagem de erro ou bloquear o envio.

## Impacto
Compromete a integridade do cadastro, permitindo que o usuário crie uma conta sem saber qual senha foi efetivamente registrada no sistema.  
**Severidade:** Alta — falha de validação crítica que compromete diretamente o acesso futuro do usuário à conta recém-criada.  
**Impacto:** Alto (o usuário pode ficar sem acesso à conta por não saber qual senha foi cadastrada)
**Prioridade:** Alto

## Escopo
**Afeta:** Campos SENHA e CONFIRMAR SENHA no formulário de cadastro  
**Plataformas:** Web (desktop e visualizações responsivas)  
**Navegadores:** Reproduzível em navegadores modernos (baseados em Chromium e WebKit)  
**Usuários:** Todos os usuários que acessam a tela de cadastro

## Ambiente
**Ambiente:** Ambiente similar ao de produção  

## Passos para Reproduzir
1. Dado que estou na tela de login
2. Quando clico na opção "Criar conta"
3. E preencho os campos NOME COMPLETO, TELEFONE e EMAIL com valores válidos
4. Quando preencho o campo SENHA com um valor (ex: `123`)
5. E preencho o campo CONFIRMAR SENHA com um valor diferente (ex: `Senha@123`)
6. Quando clico em "Criar conta"
7. Observo que o sistema realiza o cadastro sem exibir mensagem de erro sobre a divergência

## Resultado Esperado
Ao tentar enviar o formulário com senhas divergentes, o sistema deve bloquear o envio e exibir mensagem de validação indicando que os campos SENHA e CONFIRMAR SENHA precisam ter o mesmo valor.