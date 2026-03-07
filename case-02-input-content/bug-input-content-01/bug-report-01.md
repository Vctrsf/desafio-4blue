# Bug Report — Campo Telefone Aceita Caracteres Não-Numéricos

## Resumo
O campo TELEFONE do formulário de cadastro não possui restrição de entrada, permitindo que letras e caracteres especiais sejam inseridos livremente, sem qualquer validação ou bloqueio.

## Impacto
Permite o envio de valores inválidos para o backend, compromete a integridade dos dados coletados e introduz inconsistência de validação no formulário de cadastro.
**Severidade:** Média — falha de validação com impacto direto na integridade dos dados, sem quebra crítica do sistema.  
**Impacto:** Médio — permite o envio de dados inválidos ao backend, comprometendo a integridade dos registros  
**Prioridade**: Média  


## Escopo
**Afeta:** 
 1. Campo TELEFONE no formulário de cadastro
 2. Envio de dados incorretos para API e Banco de Dados
**Plataformas:** Web (desktop e visualizações responsivas)
**Navegadores:** Reproduzível em navegadores modernos (baseados em Chromium e WebKit)
**Usuários:** Todos os usuários que acessam a tela de criação de conta

## Ambiente
**Ambiente:** Ambiente similar ao de produção

## Passos para Reproduzir
1. Dado que estou na tela de login
2. Quando clico na opção "Criar conta"
3. E localizo o campo TELEFONE.
4. Quando insiro letras ou caracteres especiais (ex: `AA111`, `abc!@#`).
5. Então o campo aceita os valores sem restrição ou mensagem de erro.

## Resultado Esperado
O campo TELEFONE deve aceitar apenas caracteres numéricos, bloqueando qualquer entrada de letras ou símbolos e exibindo uma mensagem de validação caso o valor inserido seja inválido.
