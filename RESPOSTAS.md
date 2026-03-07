## "Quais 2 bugs você corrigiria primeiro e por quê?"

1. **Cadastro Permitido com Campos de Senha Vazios** — `case-03-bugs-formulario/bugs-contas-04/bug-contas-04/bug-report-04`  
   Falha crítica de segurança que permite a criação de contas sem nenhuma senha definida. Em um cenário onde uma conta administrativa fosse criada dessa forma, qualquer pessoa poderia acessá-la sem nenhuma credencial, comprometendo todo o sistema.

2. **Login sem credenciais** — `case-03-bugs-formulario/bugs-login/bug-login-02/bug-report-02`  
   Falha crítica de autenticação que permite acesso ao sistema sem nenhuma credencial, expondo diretamente a segurança do produto e de todos os usuários.

Escolhi esses dois porque ambos comprometem diretamente a segurança do produto. O primeiro é o mais crítico pois abre uma brecha para que contas sejam criadas sem senha, incluindo possíveis contas administrativas e o segundo permite que qualquer pessoa entre no sistema sem precisar de uma conta cadastrada.


## "Caso tenha, coloque suas sugestões de melhorias para essas telas."

### Melhorias Visuais

* Adicionar feedback visual nos campos quando o usuário digitar um valor inválido, como borda vermelha e mensagem de erro abaixo do campo.
* Exibir um indicador de força de senha no campo SENHA durante a digitação.
* Adicionar ícone de mostrar/ocultar senha nos campos SENHA e CONFIRMAR SENHA tanto da tela de login, quanto da tela de cadastro de conta.
* Adicionar estado de loading no botão "Entrar" e "Criar conta" enquanto a requisição está sendo processada.
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
* Implementar opção de redefinição de senha em caso de comprometimento de segurança de conta ou esquecimento da senha.