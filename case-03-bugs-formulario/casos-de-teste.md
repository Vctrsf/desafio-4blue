# Casos de Teste — Bugs de Envio de Formulário


## Casos de teste para login

### CT-01 — Login com sucesso

| Campo | Valor esperado | 
|-------|-----------------------|
| EMAIL | emailcorreto@gmail.com|
| SENHA | Senha@123             |

**Passos:**
1. Dado que estou na tela de login
2. Quando preencho os campos de EMAIL e SENHA com dados existentes na base de dados
3. E clico no botão "Entrar"
4. Então o sistema deve redirecionar o usuário para a tela de confirmação de acesso

---

### CT-02 — Login com credenciais incorretas

**Casos de uso:**

| Campo | Valor esperado          | 
|-------|-----------------------  |
| EMAIL | emailincorreto@gmail.com|
| SENHA | Senhaincorreta          |

| Campo | Valor esperado          | 
|-------|-----------------------  |
| EMAIL | emailcorreto@gmail.com  |
| SENHA | Senhaincorreta          |

| Campo | Valor esperado          | 
|-------|-----------------------  |
| EMAIL | emailincorreto@gmail.com|
| SENHA | Senha@123               |

**Passos:**
1. Dado que estou na tela de login
2. Quando insiro dados nos campos EMAIL e SENHA que não estão na base de dados
3. E clico e entrar
4. Então o sistema não deve permitir que o usuário acesse o sistema e emitir uma mensagem de aviso.

---

### CT-03 — Login com campos em branco

| Campo | Valor esperado | 
|-------|----------------|
| EMAIL |                |
| SENHA |                |

**Passos:**
1. Dado que estou na tela de login
2. Quando mantenho os campos EMAIL e SENHA em branco
3. E clico no botão "Entrar"
4. Então o sistema não deve permitir que o usuário tenha seu acesso concedido e emitir uma mensagem de aviso

---


# Casos de teste para criação de contas


### CT-01 — Criação de conta com campos preenchidos corretamente
| NOME COMPLETO | TELEFONE  | EMAIL                |  SENHA  | CONFIRMAR SENHA |

| Victor Souza  |13400028922|emaildeteste@gmail.com|Senha@123|    Senha@123    |


**Passos:**
1. Dado que estou na tela de cadastro
2. Quando preencho os campos NOME COMPLETO, TELEFONE, EMAIL, SENHA, CONFIRMAR SENHA
3. E clico no botão "Criar conta"
4. Então o sistema deve realizar o cadastramento da conta do usuário com sucesso


---

### CT-02 — Criação de conta com dados inválidos
| NOME COMPLETO | TELEFONE  | EMAIL          |       SENHA          |    CONFIRMAR SENHA     |

| Victor Souza  |13400028922|emaildeteste.com| Senhasemmáscaraforte | Senhasemmáscaraforte   |
| Victor Souza  |13400028922|emaildeteste.com| Senhasemmáscaraforte | Senhasemmáscaraforte   |


| Campo          |  Valor inserido |
|----------------|-----------------|
| NOME COMPLETO  | Victor Souza    |
| TELEFONE       | 13400028922     |
| EMAIL          | emaildeteste.com|
| SENHA          | Senhafraca      |
| CONFIRMAR SENHA| Senhafraca      |

**Passos:**
1. Dado que estou na tela de cadastro
2. Quando insiro dados que não estão conformes aos campos EMAIL, SENHA e CONFIRMAR SENHA
3. Então deve ser exibido uma mensagem de erro nos campos com dados inválidos e a conta não deve ser cadastrada

---


### CT-03 — Criação de conta com campos em branco

| Campo          | Valor esperado |
|----------------|----------------|
| NOME COMPLETO  |                |
| TELEFONE       |                |
| EMAIL          |                |
| SENHA          |                |
| CONFIRMAR SENHA|                |

**Passos:**
1. Dado que estou na tela de cadastro de contas
2. E mantenho os campos NOME COMPLETO, TELEFONE, EMAIL, SENHA, CONFIRMAR SENHA em branco
3. Quando clico no botão "Criar conta"
4. Então o sistema não deve permitir que a conta seja criada e emita um aviso nos campos em branco que não há dados inseridos

---

## CT- — Mensagem de sucesso após cadastro

**Passos:**
1. Dado que estou na tela de cadastro
2. Quando preencho todos os campos corretamente e clico em "Criar conta"
3. Então deve ser exibida uma mensagem ou ícone de confirmação de cadastro realizado