# Bug Report — Ausência de Máscara no Campo Telefone

## Resumo
O campo TELEFONE do formulário de cadastro não aplica máscara de formatação durante a digitação.
Apesar do placeholder indicar visualmente o formato `(00) 00000-0000`, o valor é exibido como 
uma sequência de dígitos sem formatação, como `13999999999`.

## Impacto
Quebra o alinhamento entre a expectativa visual criada pelo placeholder e o comportamento real 
do campo, dificulta a leitura e conferência do número pelo usuário e entrega um dado não 
formatado ao backend.
 **Severidade:** Média (inconsistência funcional e visual com impacto 
direto na experiência do usuário e na integridade do formato dos dados.)
 **Impacto:** Baixo (não compromete a funcionalidade ou uso do campo)
 **Prioridade:** Baixa
## Escopo
**Afeta:** Campo TELEFONE no formulário de cadastro
**Plataformas:** Web (desktop e visualizações responsivas)
**Navegadores:** Reproduzível em navegadores modernos (baseados em Chromium e WebKit)
**Usuários:** Todos os usuários que acessam a tela de cadastro

## Ambiente
**Ambiente:** Ambiente similar ao de produção


## Passos para Reproduzir
1. Dado que estou na tela de login
2. Quando clico na opção "Criar conta"
3. E localizo o campo TELEFONE.
4. Quando insiro um número válido (ex: `13999999999`).
5. Observe que o valor é exibido sem formatação, ignorando o padrão `(00) 00000-0000` indicado pelo placeholder.

## Resultado Esperado
O campo TELEFONE deve aplicar máscara de formatação em tempo real durante a digitação, 
exibindo o valor no formato `(13) 99999-9999` conforme indicado pelo placeholder.