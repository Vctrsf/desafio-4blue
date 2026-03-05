## Hipóteses — Campo Telefone Aceita Caracteres Não-Numéricos

### Prováveis Causas
1. **Ausência de restrição de tipo no input**
   * O campo está implementado como `type="text"` genérico em vez de `type="tel"`, 
   ou sem atributo `inputmode="numeric"` e `pattern="[0-9]*"`, permitindo qualquer caractere.

2. **Validação não implementada**
   * Não há regra de validação JavaScript ou de formulário bloqueando a entrada de caracteres 
   não-numéricos, seja no evento `onchange`, `oninput` ou na submissão do formulário.

3. **Falta de cobertura de testes de validação**
   * Não há testes automatizados verificando o comportamento do campo TELEFONE para entradas 
   inválidas, o que permitiu que a ausência de validação passasse despercebida.

### Fatores Contribuintes
* Ausência de um componente centralizado de input de telefone no design system que já 
encapsule as regras de validação.
* Revisão insuficiente entre implementação e prototipagem para o comportamento esperado do campo.

### Riscos de Regressão
1. Dados inválidos podem ser persistidos no backend caso não haja validação server-side complementar.
2. Outros campos numéricos do produto podem replicar o mesmo padrão sem restrição de entrada.

### Estratégia de Mitigação
* Adicionar `inputmode="numeric"` e `pattern="[0-9]*"` ao campo.
* Implementar validação client-side bloqueando caracteres não-numéricos no evento `oninput`.
* Adicionar casos de teste automatizados para entradas inválidas no campo TELEFONE.
* Incluir verificação explícita de comportamento de validação durante o code review.