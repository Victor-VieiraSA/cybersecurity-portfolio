# 01 — Auditoria de Segurança Interna: Botium Toys

> **Nota:** Esta atividade é um exercício prático do **Google Cybersecurity Certificate**, baseado no cenário fictício da empresa **Botium Toys**.

## Contexto

Auditorias de segurança internas garantem que verificações periódicas sejam realizadas para identificar e monitorar ameaças, riscos e vulnerabilidades que possam afetar a continuidade dos negócios e os ativos críticos de uma organização.

Neste cenário, fui responsável por conduzir uma auditoria interna no programa de segurança da **Botium Toys**, uma pequena empresa de varejo que atua com vendas presenciais e e-commerce (incluindo clientes nos EUA e na União Europeia). O relatório inicial de escopo, objetivos e avaliação de risco apontava um **nível de risco alto (8/10)**, motivado principalmente por:

- Gestão inadequada e falta de classificação/inventário dos ativos de TI (incluindo sistemas legados sem cronograma regular de manutenção);
- Ausência de controles essenciais de segurança administrativa e técnica;
- Possíveis não conformidades com normas e regulamentações aplicáveis (**PCI DSS**, **GDPR** e **SOC Type 1 / Type 2**), expondo dados de cartões de pagamento e informações pessoais identificáveis (PII/SPII) de clientes.

## O que eu fiz

1. **Análise de escopo, ativos e riscos:** Revisei o relatório [`Scope and goals of the audit.docx`](./references/Scope%20and%20goals%20of%20the%20audit.docx) para mapear o escopo completo do programa de segurança, os ativos gerenciados pelo departamento de TI e o perfil de risco da organização.
2. **Estudo das categorias de controles:** Consultei [`Control categories.docx`](./references/Control%20categories.docx) para classificar os controles entre **administrativos/gerenciais**, **técnicos** e **físicos/operacionais**, considerando suas funções (preventivos, corretivos, detectivos e dissuasivos).
3. **Avaliação de controles internos:** Preenchi o *Controls Assessment Checklist* verificando quais dos **14 controles avaliados** estavam implementados na Botium Toys.
4. **Verificação de conformidade:** Preenchi o *Compliance Checklist* avaliando a aderência da empresa a **12 boas práticas** distribuídas entre **PCI DSS**, **GDPR** e **SOC Type 1 / Type 2**.
5. **Elaboração de recomendações priorizadas:** Estruturei um resumo de recomendações práticas e priorizadas por risco para o gerente de TI apresentar aos stakeholders, alinhado à função **Identify** do **NIST CSF**.

## Resultado

O entregável concluído está disponível em [`Controls and compliance checklist.pdf`](./Controls%20and%20compliance%20checklist.pdf).

### Resumo quantitativo da auditoria

| Área avaliada | Em conformidade / Implementado | Lacunas identificadas | Total |
| :--- | :---: | :---: | :---: |
| **Controles de segurança** | 7 | 7 | 14 |
| **Conformidade — PCI DSS** | 0 | 4 | 4 |
| **Conformidade — GDPR** | 2 | 2 | 4 |
| **Conformidade — SOC Type 1 & 2** | 2 | 2 | 4 |

### Principais achados

- **Pontos fortes identificados:**
  - Controles físicos bem estabelecidos (fechaduras em escritórios, loja e depósito; CFTV atualizado; detecção e prevenção contra incêndio).
  - Controles técnicos básicos em operação (firewall com regras definidas e antivírus monitorado regularmente), além de integridade e disponibilidade de dados mantidas pela equipe de TI.
  - Plano de notificação em até 72 horas para clientes da União Europeia em caso de violação e políticas de privacidade documentadas.
- **Principais lacunas e riscos críticos:**
  - **Controle de acesso:** Ausência de princípio do menor privilégio (*Least Privilege*), segregação de funções (*Separation of Duties*) e políticas formais de acesso — todos os colaboradores podem acessar dados armazenados internamente, incluindo dados de cartão e PII/SPII.
  - **Proteção de dados:** Falta de criptografia para dados de cartão de crédito aceitos, processados, transmitidos e armazenados localmente.
  - **Continuidade de negócios:** Inexistência de plano de recuperação de desastres (*Disaster Recovery Plan*) e de backups de dados críticos.
  - **Detecção e autenticação:** Falta de sistema de detecção de intrusão (IDS), política de senhas abaixo dos requisitos mínimos atuais de complexidade e ausência de sistema centralizado de gerenciamento de senhas.
  - **Gestão de ativos:** Falta de inventário e classificação formal de dados e ativos, além de manutenção sem cronograma regular para sistemas legados.

### Recomendações entregues ao gerente de TI

1. **Prioridade imediata (Acesso e Criptografia):** Implementar menor privilégio, segregação de funções e políticas de controle de acesso, além de criptografar dados de cartão e de clientes em repouso e em trânsito para mitigar os maiores riscos de exposição e multas (PCI DSS, GDPR e SOC).
2. **Continuidade de negócios:** Criar um plano de recuperação de desastres e implantar backups regulares e testados dos dados críticos.
3. **Detecção e autenticação:** Instalar um IDS, atualizar a política de senhas para os requisitos mínimos atuais de complexidade (mínimo de 8 caracteres, letras, ao menos um número e caracteres especiais) e adotar um gerenciador centralizado de senhas.
4. **Gestão de ativos (NIST CSF — *Identify*):** Inventariar e classificar todos os ativos da organização, avaliando o impacto da perda de cada um na continuidade dos negócios, incluindo sistemas legados.

## Arquivos desta atividade

- [`Controls and compliance checklist.pdf`](./Controls%20and%20compliance%20checklist.pdf) — Checklist de controles, conformidade e recomendações preenchido.
- [`references/Scope and goals of the audit.docx`](./references/Scope%20and%20goals%20of%20the%20audit.docx) — Documento de escopo, objetivos e avaliação de risco da Botium Toys.
- [`references/Control categories.docx`](./references/Control%20categories.docx) — Referência das categorias e tipos de controles de segurança.
- [`references/Controls-and-compliance-checklist.docx`](./references/Controls-and-compliance-checklist.docx) — Modelo original do checklist utilizado na atividade.
