# Guia e Modelo de Relatório de Impacto à Proteção de Dados Pessoais (RIPD / DPIA)

Conforme o **Art. 5º, XVII** e **Art. 38** da LGPD (Lei 13.709/2018), o Relatório de Impacto à Proteção de Dados Pessoais (RIPD) é a documentação que descreve os processos de tratamento de dados que podem gerar riscos às liberdades civis e aos direitos fundamentais, bem como medidas, salvaguardas e mecanismos de mitigação.

---

## 1. Quando o RIPD é Obrigatório no Desenho de Software?
O RIPD deve ser emitido nas seguintes hipóteses principais:
1. **Tratamento de Dados Pessoais Sensíveis em larga escala** (Art. 11 e Art. 38).
2. **Tratamento fundamentado no Legítimo Interesse do Controlador** (Art. 10, § 3º).
3. **Tomada de Decisão Automatizada e Perfilamento** de titulares (Art. 20).
4. **Tratamento de Dados de Crianças e Adolescentes** em larga escala (Art. 14).
5. **Determinação expressa da Autoridade Nacional de Proteção de Dados (ANPD)**.

---

## 2. Modelo Estruturado de RIPD para Engenharia de Sistemas

### I. Identificação do Projeto e Agentes de Tratamento
- **Nome do Sistema / Módulo**: [Ex.: Plataforma de Análise de Risco de Crédito]
- **Controlador**: [Nome da Empresa / Órgão Público]
- **Encarregado (DPO)**: [Nome e E-mail de Contato]
- **Operadores Envolvidos**: [Provedores Cloud, APIs de terceiros]

### II. Descrição da Operação e Ciclo de Vida dos Dados
- **Escopo do Sistema**: [Breve resumo funcional]
- **Dados Coletados**:
  - Dados Comuns: [Lista]
  - Dados Sensíveis: [Lista]
- **Fluxo de Dados**:
  - *Coleta*: [Ex.: Formulário Web / API REST]
  - *Processamento*: [Ex.: Algoritmo de ML / Regras de negócio]
  - *Armazenamento*: [Ex.: PostgreSQL AWS RDS com criptografia AES-256]
  - *Compartilhamento*: [Ex.: Transmissão via HTTPS para Bureau de Crédito]
  - *Retenção e Descarte*: [Ex.: Retenção por 5 anos (obrigação fiscal) e purge automático]

### III. Análise de Necessidade e Proporcionalidade
- **Base Legal Enquadrada**: [Ex.: Art. 7º, V - Execução de Contrato e Art. 7º, X - Proteção do Crédito]
- **Avaliação de Minimização**: [Os dados coletados são estritamente necessários para a finalidade declarada? Há excesso de coleta?]

### IV. Matriz de Identificação e Mitigação de Riscos
| ID do Risco | Descrição do Risco aos Titulares | Probabilidade | Impacto | Medida de Mitigação Técnica / Salvaguarda |
| :--- | :--- | :--- | :--- | :--- |
| **R-01** | Acesso não autorizado a dados de saúde por falha de autenticação | Média | Alto | Autenticação Múltiplo Fator (MFA) obrigatória + Controle de Acesso Baseado em Funções (RBAC). |
| **R-02** | Exfiltração de PII por vazamento em logs de servidor | Alta | Médio | Filtro automatizado de mascaramento de logs (*Scrubber*) no pipeline de logs. |
| **R-03** | Impossibilidade de atender solicitação de exclusão de dados | Média | Alto | Implementação de funcionalidade de exclusão lógica e anonimização assíncrona. |

### V. Parecer Final do Encarregado (DPO) e Aprovação
- **Conclusão**: [O nível de risco remanescente é aceitável após a implementação das salvaguardas?]
- **Data da Avaliação**: [AAAA-MM-DD]
- **Assinatura do DPO**: [Nome do Encarregado]
