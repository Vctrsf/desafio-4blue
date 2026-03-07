# Bug Report — Cadastro Permitido com Dados de Conta Já Existente

## Resumo
O formulário de cadastro permite a criação de uma nova conta utilizando o mesmo EMAIL de uma conta já cadastrada, sem exibir mensagem de erro ou bloquear o envio. Isso abre a possibilidade de um usuário mal-intencionado sobrescrever os dados de uma conta existente e assumir o acesso a ela.

## Impacto
Compromete diretamente a segurança das contas dos usuários, permitindo que qualquer pessoa crie uma conta com o email de outro usuário e potencialmente assuma o acesso a ela com uma nova senha definida por outro usuário.  

**Severidade:** Crítica — falha de segurança que permite a tomada de conta de outros usuários.  
**Impacto:** Alto (qualquer conta cadastrada no sistema pode ser comprometida por um usuário mal-intencionado)  
**Prioridade:** Crítica  

## Escopo
**Afeta:** Formulário de cadastro — campo EMAIL  
**Plataformas:** Web (desktop e visualizações responsivas)  
**Navegadores:** Reproduzível em navegadores modernos (baseados em Chromium e WebKit)  
**Usuários:** Todos os usuários com conta cadastrada no sistema  

## Ambiente
**Ambiente:** Ambiente similar ao de produção  
**Feature flags:** Padrões padrão, sem flags de validação de cadastro habilitadas  

## Passos para Reproduzir
1. Dado que existe uma conta cadastrada com o email `usuario@email.com`
2. Quando acesso a tela de login e clico em "Criar conta"
3. E preencho o campo EMAIL com `usuario@email.com`
4. E preencho os demais campos com dados válidos e uma senha diferente da original
5. Quando clico em "Criar conta"
6. Observo que o sistema realiza o cadastro sem informar que o email já está em uso

## Resultado Esperado
Ao tentar criar uma conta com um EMAIL já cadastrado, o sistema deve bloquear o envio e exibir mensagem de erro informando que já existe uma conta associada a esse email.