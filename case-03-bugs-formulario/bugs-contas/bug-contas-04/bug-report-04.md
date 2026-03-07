# Bug Report — Cadastro Permitido com Campos de Senha Vazios

## Resumo
O formulário de cadastro permite a criação de conta sem que os campos SENHA e CONFIRMAR 
SENHA sejam preenchidos, sem exibir mensagem de erro ou bloquear o envio.

## Impacto
Permite a criação de contas sem senha definida, comprometendo diretamente a segurança 
do acesso do usuário e a integridade do fluxo de autenticação.  
**Severidade:** Crítica — falha crítica de segurança que permite a criação de contas sem senha.  
**Impacto:** Alto (contas criadas sem senha podem ser acessadas sem nenhuma credencial)  
**Prioridade:** Alta  

## Escopo
**Afeta:** Campos SENHA e CONFIRMAR SENHA no formulário de cadastro  
**Plataformas:** Web (desktop e visualizações responsivas)  
**Navegadores:** Reproduzível em navegadores modernos (baseados em Chromium e WebKit)  
**Usuários:** Todos os usuários que acessam a tela de cadastro  

## Ambiente
**Ambiente:** Ambiente similar ao de produção  

## Passos para Reproduzir
1. Dado que estou na tela de cadastro
2. Quando preencho os campos NOME COMPLETO, TELEFONE e EMAIL com valores válidos
3. E deixo os campos SENHA e CONFIRMAR SENHA em branco
4. Quando clico em "Criar conta"
5. E retorno para a tela de login
6. Quando insiro somente o e-mail da conta cadastrada no campo EMAIL
7. E clico no botão "Entrar" 
8. Então o sistema permite que o acesso seja bem-sucedido

## Resultado Esperado
Ao tentar criar uma conta com os campos SENHA e CONFIRMAR SENHA vazios, o sistema deve bloquear o envio e exibir mensagens de validação indicando que os campos são obrigatórios.