## Hipóteses — Ausência de Máscara no Campo Telefone

### Prováveis Causas
1. **Ausência de biblioteca ou lógica de máscara**
   * O campo não utiliza nenhuma biblioteca de mascaramento (como `IMask`, `react-input-mask` ou similar), nem lógica própria via `oninput` que formate o valor durante a digitação.

2. **Placeholder usado como substituto de máscara**
   * O placeholder `(00) 00000-0000` foi adicionado apenas como indicação visual do formato 
   esperado, sem a implementação correspondente da máscara, criando uma expectativa não 
   atendida pelo comportamento real do campo.

3. **Falta de cobertura de testes de formatação**
   * Não há testes automatizados verificando se o campo aplica a formatação correta durante 
   a digitação, o que permitiu que a ausência de máscara passasse despercebida.

### Fatores Contribuintes
* Ausência de um componente centralizado de input de telefone no design system que já considere a máscara de formatação.
* Revisão insuficiente do comportamento de formatação do campo durante o code review.

### Riscos de Regressão
1. O dado entregue ao backend sem formatação podem gerar inconsistências na exibição do telefone em outras partes do produto.
2. Outros campos com formato esperado podem replicar o mesmo padrão de placeholder sem máscara correspondente.

### Estratégia de Mitigação
* Implementar máscara de formatação via `oninput` ou biblioteca dedicada (ex: `IMask`).
* Garantir que o formato aplicado pela máscara seja consistente com o placeholder definido.
* Adicionar casos de teste automatizados verificando a formatação em tempo real do campo.
* Incluir verificação explícita de comportamento de formatação durante o code review.   