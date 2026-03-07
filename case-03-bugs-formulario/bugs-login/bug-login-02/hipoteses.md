## Hipóteses — Login Permitido Sem Inserção de Credenciais

### Prováveis Causas
1. **Campos sem validação de obrigatoriedade**
   * Os campos EMAIL e SENHA não têm nenhuma verificação que impeça o envio do formulário 
   quando estão vazios — nem o atributo `required` no HTML.

2. **Botão de login não verifica os campos antes de enviar**
   * O botão "Entrar" está disparando a requisição de login independente de os campos estarem preenchidos ou não, sem nenhuma verificação anterior ao envio.

3. **Sem testes para esse cenário**
   * Ninguém testou o que acontece quando o usuário clica em "Entrar" sem preencher nenhum campo, então o problema passou despercebido.

### Fatores Contribuintes
* O componente de input do shadcn/ui não faz validação de campos obrigatórios automaticamente — ela precisa ser feita manualmente no código React.  
* O comportamento do formulário de login não foi verificado com cuidado durante a revisão do código.

### Riscos de Regressão
1. Qualquer pessoa que acesse a tela de login consegue entrar no sistema sem precisar de uma conta, expondo os dados de todos os usuários.  
2. Outros formulários do projeto podem ter o mesmo problema de ausência de validação de campos obrigatórios.

### Estratégia de Mitigação
* Implementar validação de campos obrigatórios com `react-hook-form`, bloqueando o envio quando EMAIL ou SENHA estiverem vazios.  
* Exibir mensagens de erro individuais por campo ao tentar enviar o formulário vazio.  
* Criar testes que verifiquem o bloqueio do login quando os campos estão vazios.  
* Verificar durante o code review se todos os formulários estão validando campos obrigatórios antes do envio.