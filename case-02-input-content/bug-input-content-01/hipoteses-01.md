## Hipóteses — Campo Telefone Aceita Caracteres Não-Numéricos

### Prováveis Causas
1. **Restrição de tipo insuficiente**
   * O campo possui `type="tel"`, que restringe a entrada apenas em dispositivos móveis. Em desktop, browsers como Chrome e Firefox não bloqueiam caracteres não-numéricos via teclado físico. Faltam os atributos complementares `inputmode="numeric"` e `pattern="[0-9]*"`.

2. **Validação client-side não implementada**
   * Não há lógica no front bloqueando a entrada de caracteres não-numéricos em tempo real via `oninput`, tornando o `type="tel"` insuficiente como única restrição.

3. **Falta de cobertura de testes de validação**
   * Não há testes automatizados verificando o comportamento do campo TELEFONE para entradas 
   inválidas, o que permitiu que a ausência de validação passasse despercebida.

### Fatores Contribuintes
* Não existe um componente de input de telefone pronto no projeto que já venha com as regras de validação incluídas.
* O comportamento do campo não foi verificado com cuidado durante a revisão do código.

### Riscos de Regressão
1. Dados inválidos podem ser persistidos no backend caso não haja validação server-side complementar.
2. Outros campos numéricos do produto podem replicar o mesmo padrão sem restrição de entrada.

### Estratégia de Mitigação
* Adicionar casos de teste automatizados para entradas inválidas no campo TELEFONE.
* Incluir verificação explícita de comportamento de validação durante o code review.