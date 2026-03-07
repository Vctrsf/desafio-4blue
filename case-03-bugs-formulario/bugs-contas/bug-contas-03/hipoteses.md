## Hipóteses — Cadastro Permitido com Dados de Conta Já Existente

### Prováveis Causas
1. **Ausência de verificação de email duplicado no front**
   * Não existe nenhuma verificação no formulário de cadastro que consulte o backend antes do envio para checar se o email já está cadastrado, permitindo que o formulário seja enviado sem nenhuma restrição.

2. **Email não definido como chave única no banco de dados**
   * O campo de email pode não estar configurado como valor único no banco de dados, o que significa que o sistema aceita múltiplos cadastros com o mesmo email sem nenhum bloqueio a nível de banco.

3. **Ausência de validação no backend**
   * A API de cadastro pode não estar verificando se o email já existe antes de criar um novo registro, processando o cadastro normalmente mesmo com um email já utilizado.

4. **Sem testes para esse cenário**
   * Ninguém testou o que acontece quando o usuário tenta criar uma conta com um email já cadastrado, então o problema passou despercebido.

### Fatores Contribuintes
* Não existe uma regra de unicidade definida para o campo email, nem no front, nem no backend, nem no banco de dados.  
* O comportamento do formulário de cadastro para emails duplicados não foi verificado durante a revisão do código.

### Riscos de Regressão
1. Contas existentes podem ser sobrescritas por usuários mal-intencionados, comprometendo o acesso dos usuários legítimos.  
2. O banco de dados pode acumular registros duplicados, gerando inconsistências em outras partes do sistema que dependem do email como chave primária.

### Estratégia de Mitigação
* Adicionar verificação de email duplicado no frontend antes do envio do formulário.  
* Implementar validação no backend que retorne erro quando o email já estiver cadastrado.  
* Definir o campo email como chave única no banco de dados para garantir a restrição 
a nível de banco.  
* Criar testes que verifiquem o bloqueio do cadastro quando o email já está em uso.  
* Verificar durante o code review se o fluxo de cadastro está tratando corretamente 
a unicidade do email.