# Hipóteses — Validação de Senha Não Bloqueia Cadastro com Senha Inválida
## Hipóteses

### Prováveis Causas
1. **Ausência de validação declarada no input**
   * O campo está implementado apenas como `type="password"` sem nenhum atributo de validação declarado — sem `required`, `pattern` ou `minlength`.

2. **Falta de cobertura de testes de validação de senha**
   * Não há testes automatizados verificando se o formulário bloqueia o envio quando a senha não atende às regras definidas, o que permitiu que a lacuna de validação passasse despercebida.

### Fatores Contribuintes
* A mensagem de regra exibida abaixo do campo foi adicionada apenas como texto informativo, sem a implementação correspondente da validação no formulário React.
* Revisão insuficiente do comportamento de validação de senha durante o code review.

### Riscos de Regressão
1. Contas com senhas fracas podem ser persistidas no backend caso não haja validação server-side complementar.
2. Contas criadas com senhas fracas (`123`) poderiam ser facilmente acessadas.
2. A política de segurança de senhas pode ser ignorada em outros formulários do produto que reapliquem o mesmo padrão.

### Estratégia de Mitigação
* Implementar validação de senha com `react-hook-form` e schema Zod, aplicando as regras de mínimo 8 caracteres e 1 caractere especial antes do envio.
* Exibir mensagem de erro inline no campo SENHA ao tentar submeter o formulário com senha inválida.
* Adicionar casos de teste automatizados verificando o bloqueio de envio para senhas que não atendem às regras.
* Incluir verificação explícita da política de senhas durante o code review.