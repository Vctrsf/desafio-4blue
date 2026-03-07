## Hipóteses — Portal Não Centralizado em Dispositivos Móveis

### Prováveis Causas
1. **Largura fixa no container**
   * O container da tela de login provavelmente tem um tamanho fixo definido em `px` 
   que funciona no computador, mas é maior do que a tela do celular, fazendo o conteúdo sair para fora.

2. **Página não configurada para mobile**
   * Pode estar faltando a configuração de `viewport` no HTML, que é o que diz para o browser adaptar a página ao tamanho da tela do celular.

3. **Sem adaptação para telas menores**
   * O CSS da tela de login pode não ter nenhuma regra específica para celular, fazendo com que o layout de desktop seja usado em qualquer tamanho de tela.

### Fatores Contribuintes
* O portal foi testado principalmente no computador, sem verificar como ficava no celular.
* Não existe nenhum teste que verifique o layout em telas de tamanhos diferentes.

### Riscos de Regressão
1. O mesmo problema pode estar acontecendo em outras telas do portal além do login.
2. Qualquer alteração futura no layout pode piorar o deslocamento se o tamanho 
continuar fixo.

### Estratégia de Mitigação
* Trocar os tamanhos fixos em `px` por valores que se adaptam à tela, como `%` ou `max-width`.
* Adicionar regras de CSS específicas para telas menores.
* Verificar se a configuração de `viewport` está correta no HTML.
* Testar o portal no celular antes de qualquer entrega.