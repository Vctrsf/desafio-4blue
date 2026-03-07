## Arquitetura de Pastas — Bug Reports 4blue
```
desafio-4blue/
├── case-01-bugs-visuais/
    └── casos-de-teste
├── case-02-bugs-inputs/
│
└── case-03-formulario/
|   ├── bugs-contas/
|   └── bugs-login/
|
└── case-04-bugs-mobile
```

### Descrição das Pastas

**`case-01-bugs-visuais/`**
Contém bugs relacionados a inconsistências visuais dos campos, como espaçamento interno, alinhamento e divergências entre o layout implementado e o definido na prototipagem.

**`case-02-bugs-inputs/`**
Contém bugs relacionados ao comportamento de preenchimento dos campos, como ausência de validação de tipo, falta de máscara de formatação e restrições de entrada.

**`case-03-formulario/`**
Contém bugs relacionados ao envio do formulário, como ausência de validação de campos obrigatórios, envio indevido e comportamentos incorretos ao clicar em "Criar conta" e "Entrar"

- **`bugs-contas/`** — Relatórios relacionados ao envio do formulário na tela de criação de conta
- **`bugs-login/`** — Relatórios relacionados ao envio do formulário na tela de login

**`case-04-bugs-mobile/`**
Contém bugs relacionados à validação do portal em ambiente mobile.

---

## Descrição dos Arquivos

### **`bug-report`** — Documentação que descreve um comportamento incorreto encontrado no portal, detalhando o problema, seu impacto e os passos para reproduzi-lo.

#### Estrutura do Bug Report

- **Resumo** — descrição objetiva do problema observado e onde ele ocorre.
- **Impacto** — consequências do bug, com Severidade (gravidade técnica) e Impacto (abrangência funcional).
- **Escopo** — o que é afetado, em quais plataformas, navegadores e para quais usuários.
- **Ambiente** — ambiente de reprodução e estado das feature flags.
- **Passos para Reproduzir** — sequência de ações que leva ao comportamento incorreto.
- **Resultado Esperado** — comportamento correto que o sistema deveria apresentar.

---

### **`hipoteses`** — Documentação que levanta as possíveis causas técnicas de um bug, os riscos associados e as ações recomendadas para corrigi-lo.

#### Estrutura das Hipóteses

- **Prováveis Causas** — causas técnicas mais prováveis para o bug.
- **Fatores Contribuintes** — lacunas de processo ou arquitetura que permitiram o bug chegar à produção.
- **Riscos de Regressão** — riscos de o problema se agravar ou se replicar em outras partes do produto.
- **Estratégia de Mitigação** — ações recomendadas para corrigir o bug e prevenir recorrências.

---

### **`casos-de-teste`** — Documentação que descreve cenários de uso das funcionalidades do portal, verificando se o comportamento real corresponde ao esperado.

#### Estrutura dos Casos de Teste

- **Dado que** — contexto inicial, a situação em que o usuário se encontra antes de executar o teste.
- **Quando** — ação realizada pelo usuário que desencadeia o comportamento a ser testado.
- **E** - adição de condicionais adicionais ao cenário
- **Então** — resultado esperado após a ação ser executada.



