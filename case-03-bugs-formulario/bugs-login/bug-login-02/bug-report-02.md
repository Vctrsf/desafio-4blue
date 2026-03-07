# Bug Report — Login Permitido Sem Inserção de Credenciais

## Resumo
A tela de login permite que o usuário clique em "Entrar" sem preencher os campos EMAIL e SENHA, sem exibir mensagens de validação ou bloquear o envio, realizando o login sem nenhuma credencial inserida.

## Impacto
Compromete diretamente o fluxo de autenticação, permitindo acesso ao sistema sem 
nenhuma credencial válida e expondo o produto a riscos críticos de segurança.

**Severidade:** Crítica — falha crítica de autenticação com impacto direto na segurança do sistema.   
**Impacto:** Alto (permite acesso indevido ao sistema sem nenhuma credencial)  
**Prioridade:** Crítica  

## Escopo
**Afeta:** Tela de login (campos EMAIL e SENHA)  
**Plataformas:** Web (desktop e visualizações responsivas)  
**Navegadores:** Reproduzível em navegadores modernos (baseados em Chromium e WebKit)  
**Usuários:** Qualquer usuário que acesse a tela de login  

## Ambiente
**Ambiente:** Ambiente similar ao de produção


## Passos para Reproduzir
1. Dado que estou na tela de login
2. E não preencho nenhum dos campos EMAIL e SENHA
3. Quando clico em "Entrar"
4. Observo que o sistema não exibe mensagens de validação e permite o login

## Resultado Esperado
Ao tentar realizar o login sem preencher os campos EMAIL e SENHA, o sistema deve bloquear 
o envio e exibir mensagens de validação indicando que os campos são obrigatórios.