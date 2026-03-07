# Bug Report — Portal Não Centralizado em Dispositivos Móveis

## Resumo
Na versão mobile, o conteúdo da tela de login não está centralizado corretamente, 
fazendo com que o layout ultrapasse a borda esquerda da tela e fique deslocado 
para fora da área visível.

## Impacto
Compromete a experiência do usuário em dispositivos móveis, tornando parte do conteúdo 
inacessível e indicando que o layout não está adaptado corretamente para telas menores.

**Severidade:** Média — problema de responsividade com impacto direto na experiência do usuário em mobile.  
**Impacto:** Médio (afeta todos os usuários que acessam o portal via dispositivo móvel)  
**Prioridade:** Média  

## Escopo
**Afeta:** Tela de login  
**Plataformas:** Mobile (Android)  
**Navegadores:** Reproduzível em navegadores modernos mobile  
**Usuários:** Todos os usuários que acessam a tela de login via dispositivo móvel  

## Ambiente
**Ambiente:** Ambiente similar ao de produção

## Passos para Reproduzir
1. Dado que estou acessando o portal via dispositivo móvel
2. Quando acesso a tela de login
3. Observo que o conteúdo está deslocado para fora da área visível da tela, 
cortando parte do layout pela borda esquerda

## Resultado Esperado
O conteúdo da tela de login deve estar centralizado e completamente visível 
independente do tamanho da tela ou dispositivo utilizado.