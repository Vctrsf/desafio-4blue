## Hipóteses — Cadastro Permitido com Senhas Divergentes

### Prováveis Causas
1. **Comparação entre os campos não implementada**
   * Não existe nenhuma verificação no código que compare o valor digitado em SENHA com o valor digitado em CONFIRMAR SENHA antes de enviar o formulário.

2. **Validação não vinculada ao botão de envio**
   * Pode existir alguma lógica de comparação no código, mas ela não está bloqueando o envio do formulário quando os valores são diferentes.

3. **Sem testes para esse cenário**
   * Não houve mapeamnto de testes para quando o usuário digita senhas diferentes nos dois campos, então o problema passou despercebido.

### Fatores Contribuintes
* O comportamento dos campos de senha não foi verificado com cuidado durante 
a revisão do código.

### Riscos de Regressão
1. O usuário pode criar uma conta e não conseguir fazer login por não saber 
qual senha foi cadastrada de fato.
2. Outros formulários do projeto que tenham campos de confirmação podem 
ter o mesmo problema.

### Estratégia de Mitigação
* Adicionar uma verificação que compare os dois campos antes de permitir o envio, exibindo uma mensagem de erro caso sejam diferentes.
* Criar testes que verifiquem o que acontece quando o usuário digita senhas diferentes nos dois campos.
* Verificar durante o code review se formulários com campos de confirmação estão validando corretamente.