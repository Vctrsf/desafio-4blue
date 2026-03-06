## Arquitetura de Pastas — Bug Reports 4blue
```
desafio-4blue/
├── case-01-input-layout/
│
├── case-02-input-content/
│
└── case-03-submit/
    ├── submit-login/
    └── submit-account/
```

### Descrição das Pastas

**`case-01-input-layout/`**
Contém bugs relacionados a inconsistências visuais dos campos, como espaçamento interno, alinhamento e divergências entre o layout implementado e o definido na prototipagem.

**`case-02-input-content/`**
Contém bugs relacionados ao comportamento de preenchimento dos campos, como ausência de validação de tipo, falta de máscara de formatação e restrições de entrada.

**`case-03-submit/`**
Contém bugs relacionados ao envio do formulário, como ausência de validação de campos obrigatórios, submissão indevida e comportamentos incorretos ao clicar em "Criar conta" e "Entrar"

- **`submit-login/`** — Relatórios relacionados ao envio do formulário na tela de login
- **`submit-account/`** — Relatórios relacionados ao envio do formulário na tela de criação de conta

**`suggestions/`**
Contém sugestões de melhoria para o portal.

---

## Descrição dos Arquivos

### **`bug-report`**

#### Estrutura do Bug Report

- **Resumo** — descrição objetiva do problema observado e onde ele ocorre.
- **Impacto** — consequências do bug, com Severidade (gravidade técnica) e Impacto (abrangência funcional).
- **Escopo** — o que é afetado, em quais plataformas, navegadores e para quais usuários.
- **Ambiente** — ambiente de reprodução e estado das feature flags.
- **Passos para Reproduzir** — sequência de ações que leva ao comportamento incorreto.
- **Resultado Esperado** — comportamento correto que o sistema deveria apresentar.

---

### **`hipoteses`**

#### Estrutura das Hipóteses

- **Prováveis Causas** — causas técnicas mais prováveis para o bug.
- **Fatores Contribuintes** — lacunas de processo ou arquitetura que permitiram o bug chegar à produção.
- **Riscos de Regressão** — riscos de o problema se agravar ou se replicar em outras partes do produto.
- **Estratégia de Mitigação** — ações recomendadas para corrigir o bug e prevenir recorrências.