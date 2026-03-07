# Casos de Teste — Inputs

## CT-01 — Campo TELEFONE aceita apenas números

**Passos:**
1. Dado que estou na tela de cadastro
2. Quando digito apenas números no campo TELEFONE
3. Então o campo deve aceitar e exibir o valor corretamente

---

## CT-02 — Usuário insere letras e caracteres especiais no campo TELEFONE

**Passos:**
1. Dado que estou na tela de cadastro
2. Quando tento inserir letras ou caracteres especiais no campo TELEFONE
3. Então o sistema não deve permitir que o usuário realize a ação e não preencha nada no campo
---

## CT-03 — Campo EMAIL aceita formato válido

**Passos:**
1. Dado que estou na tela de cadastro ou login
2. Quando digito um email no formato `usuario@dominio.com`
3. Então o campo deve aceitar o valor sem exibir erro

---

## CT-04 — Usuário insere EMAIL com formato inválido

| Entrada | Resultado esperado |
|---------|-------------------|
| `usuarioemail.com` | Bloqueado |
| `usuario@` | Bloqueado |
| `@email.com` | Bloqueado |
| `usuario@email` | Bloqueado |

**Passos:**
1. Dado que estou na tela de cadastro ou login
2. Quando digito um email em formato inválido
3. Então o campo deve exibir mensagem de erro de formato

---

## CT-05 — Usuário insere senha fora do padrão de segurança estabelecido

| Entrada     | Resultado esperado     |           Cenário                |
|-------------|------------------------|----------------------------------|   
| `SenhaX!`   | Bloqueado              |  Menos de 8 caracteres           |   
| `SenhaXPTO` | Bloqueado              |  Sem caractere especial          |    
 

**Passos:**
1. Dado que estou na tela de cadastro ou login
2. Quando digito as senhas fora do padrão de segurança no campo SENHA
3. Então o sistema deve incluir um feedback visual ao usuário de que a senha não confere com o formato solicitado

---

## CT-06 — Usuário insere senha aceita com combinação de caracteres

| Entrada | Resultado esperado |
|---------|-------------------|
| `Abc@1234` | Aceito |
| `abc@1234` | Aceito |
| `ABC@1234` | Aceito |
| `Abc@!#$%` | Aceito |

**Passos:**
1. Dado que estou na tela de cadastro
2. Quando digito uma senha com letras, números e caracteres especiais
3. Então o campo deve aceitar o valor sem exibir erro

---

## CT-07 — Usuário insere senha diferente em campo CONFIRMAR SENHA 

|Campo                | Entrada       | Resultado esperado    |
|---------------------|---------------|-----------------------| 
|SENHA                | `Senha@123`   | Aceito                |
|CONFIRMAR SENHA      | `SenhaXPTO!`  | Bloqueado             |

**Passos:**
1. Dado que estou na tela de cadastro
2. Quando preencho todos os campos 
3. E preencho os campos SENHA e CONFIRMAR SENHA com valores diferentes 
4. Quando clico no botão "Criar conta"
5. Então o sistema deve informar ao usuário que os valores inseridos nos campos SENHA e CONFIRMAR SENHA não conferem

---
