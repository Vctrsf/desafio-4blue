## "Quais 2 bugs você corrigiria primeiro e por quê?"

1. **Login sem credenciais** — `case-03-bugs-formulario/bugs-login/bug-login-02/`  
   Falha crítica de autenticação que permite acesso ao sistema sem nenhuma credencial, expondo diretamente a segurança do produto e de todos os usuários.

2. **Cadastro Permitido com Dados de Conta Já Existente** — `case-03-bug-formulario/bugs-conta/bug-contas-03/`  
   Falha crítica de segurança que pode permitir a sobrescrita de contas existentes, expondo diretamente os dados e o acesso de todos os usuários já cadastrados no sistema.

## "Caso tenha, coloque suas sugestões de melhorias para essas telas."

### Melhorias Visuais

* Adicionar feedback visual nos campos quando o usuário digitar um valor inválido, como borda vermelha e mensagem de erro abaixo do campo.
* Exibir um indicador de força de senha no campo SENHA durante a digitação.
* Adicionar ícone de mostrar/ocultar senha nos campos SENHA e CONFIRMAR SENHA.
* Destacar visualmente o campo que está em foco com uma borda ou sombra mais evidente.
* Adicionar estado de loading no botão "Entrar" e "Criar conta" enquanto a requisição está sendo processada.
* Exibir um ícone de sucesso ou mensagem de confirmação após o cadastro realizado com sucesso.
* Melhorar o contraste entre o placeholder e o fundo dos campos para facilitar a leitura.

---

### Melhorias de Segurança

* Adicionar limite de tentativas de login para evitar ataques de força bruta.
* Implementar CAPTCHA após um número definido de tentativas de login sem sucesso.
* Adicionar expiração de sessão automática após período de inatividade.
* Ocultar mensagens de erro genéricas que possam revelar se um email está ou não cadastrado.
* Implementar autenticação em dois fatores como opção para o usuário.
* Garantir que a comunicação entre cliente e servidor seja feita exclusivamente via HTTPS.
* Adicionar validação de email com link de confirmação após o cadastro.
* Implementar opção de redefinição de senha em caso de comprometimento de segurança de conta ou esquecimento da senha