#### Arquivo 2: `.kiro/skills/lgpd-compliance-checker/references/lgpd-rules.md`

```markdown
# Compêndio de Dispositivos Legais da LGPD (Lei 13.709/2018) para Engenharia de Software

Este documento fornece a base legal exaustiva da Lei Geral de Proteção de Dados Pessoais (LGPD) direcionada à auditoria técnica, arquitetura de sistemas e governança de dados.

---

## 1. Mapeamento de Conceitos e Classificação (Art. 5º)
- **Dado Pessoal (Art. 5º, I)**: Qualquer informação relacionada a pessoa natural identificada ou identificável. *Em software*: Nome, CPF, RG, e-mail, telefone, endereço IP, MAC Address, ID de dispositivo, cookies de rastreamento, geolocalização.
- **Dado Pessoal Sensível (Art. 5º, II)**: Origem racial ou étnica, convicção religiosa, opinião política, filiação a sindicato ou organização religiosa/filosófica/política, dado referente à saúde ou à vida sexual, dado genético ou biométrico. *Exige maior nível de controle e criptografia dedicada*.
- **Dado Anonimizado (Art. 5º, III e Art. 12)**: Dado relativo a titular que não possa ser identificado, considerando a utilização de meios técnicos razoáveis e disponíveis na ocasião do tratamento. *Atenção (Art. 12, § 2º)*: Se o dado for utilizado para perfilamento comportamental, pode ser reclassificado como dado pessoal.
- **Agentes de Tratamento (Art. 5º, IX)**:
  - **Controlador (Art. 5º, VI)**: A quem competem as decisões sobre o tratamento.
  - **Operador (Art. 5º, VII)**: Quem realiza o tratamento em nome do controlador (ex.: provedor de nuvem, SaaS terceiro, consultoria).
- **Encarregado / DPO (Art. 5º, VIII e Art. 41)**: Canal de comunicação entre controlador, titulares e ANPD.

---

## 2. Princípios Fundamentais do Tratamento (Art. 6º)
1. **Finalidade (I)**: Propósitos legítimos, específicos e informados.
2. **Adequação (II)**: Compatibilidade do tratamento com as finalidades informadas.
3. **Necessidade / Minimização (III)**: Limitação do tratamento ao mínimo necessário. *Payloads de API devem conter apenas os atributos estritamente exigidos*.
4. **Livre Acesso (IV)**: Consulta facilitada e gratuita sobre forma e duração do tratamento.
5. **Qualidade dos Dados (V)**: Exatidão, clareza, relevância e atualização.
6. **Transparência (VI)**: Informações claras e acessíveis sobre agentes e finalidades.
7. **Segurança (VII)**: Medidas técnicas e administrativas aptas a proteger dados contra acessos não autorizados ou acidentais.
8. **Prevenção (VIII)**: Adoção de medidas preventivas antes da ocorrência de danos.
9. **Não Discriminação (IX)**: Vedação de tratamento para fins discriminatórios abusivos (especialmente em algoritmos e decisões automatizadas - Art. 20).
10. **Responsabilização e Prestação de Contas (X)**: Demonstração da eficácia das medidas adotadas.

---

## 3. Hipóteses Legais para Tratamento (Art. 7º e Art. 11)

### Dados Comuns (Art. 7º)
- **Art. 7º, I - Consentimento**: Livre, informado e inequívoco. Deve ser fornecido por escrito ou meio equivalente com cláusula destacada (Art. 8º, § 1º). Proibidas autorizações genéricas (Art. 8º, § 4º). Pode ser revogado a qualquer momento (Art. 8º, § 5º).
- **Art. 7º, II - Obrigação Legal/Regulatória**: Ex.: Retenção de logs de acesso à aplicação pelo Marco Civil da Internet (Lei 12.965/2014) ou obrigações fiscais.
- **Art. 7º, V - Execução de Contrato**: Quando necessário para a prestação do serviço solicitado pelo titular.
- **Art. 7º, IX - Legítimo Interesse**: Para apoio a atividades do controlador. Exige teste de proporcionalidade (*LIA - Legitimate Interest Assessment*) e respeito às legítimas expectativas do titular (Art. 10).

### Dados Sensíveis (Art. 11)
- **Art. 11, I - Consentimento Destacado**: Exige manifestação específica e destacada para finalidades determinadas.
- **Art. 11, II, g - Prevenção à Fraude e Segurança**: Indispensável para autenticação e identificação do titular em sistemas eletrônicos.
- **Vedação de Vantagem Econômica com Dados de Saúde (Art. 11, § 4º)**: É proibida a comunicação/uso compartilhado de dados de saúde entre controladores visando vantagem econômica, salvo exceções de assistência à saúde e portabilidade.

---

## 4. Dados de Crianças e Adolescentes (Art. 14)
- Deve ser realizado em seu **melhor interesse**.
- Dados de crianças (até 12 anos incompletos) exigem **consentimento específico e em destaque dado por pelo menos um dos pais ou responsável legal** (Art. 14, § 1º).
- **Vedação de Condicionamento (Art. 14, § 4º)**: Não condicionar a participação em jogos ou aplicações ao fornecimento de dados além dos estritamente necessários.

---

## 5. Término do Tratamento e Retenção (Art. 15 e Art. 16)
O tratamento encerra-se quando a finalidade foi alcançada, os dados deixarem de ser necessários, o prazo expirar ou o titular revogar o consentimento (Art. 15).
Após o término, os dados **devem ser eliminados**, autorizada a conservação apenas para (Art. 16):
1. Cumprimento de obrigação legal ou regulatória.
2. Estudo por órgão de pesquisa (garantida a anonimização).
3. Transferência a terceiro (respeitados os requisitos da LGPD).
4. Uso exclusivo do controlador, vedado acesso por terceiro, **desde que anonimizados os dados**.

---

## 6. Direitos dos Titulares (Art. 18 ao 20)
O software deve ser projetado para atender às seguintes requisições do titular:
- Confirmação de existência e acesso simplificado/completo em até 15 dias (Art. 18, I/II e Art. 19, II).
- Correção de dados inexatos (Art. 18, III).
- Anonimização, bloqueio ou eliminação de dados excessivos (Art. 18, IV).
- Portabilidade de dados em formato estruturado e interoperável (Art. 18, V e Art. 40).
- Revogação de consentimento e eliminação de dados (Art. 18, VI e IX).
- **Revisão de Decisões Automatizadas (Art. 20)**: Direito de solicitar revisão de decisões tomadas unicamente com base em tratamento automatizado (ex.: scoring de crédito, perfilamento).

---

## 7. Transferência Internacional de Dados (Art. 33 ao 36)
Permitida apenas para países com nível de proteção adequado reconhecido pela ANPD (Art. 33, I) ou mediante comprovação de garantias através de:
- Cláusulas contratuais-padrão (*Standard Contractual Clauses - SCCs*).
- Normas corporativas globais (*Binding Corporate Rules - BCRs*).
- Consentimento específico e destacado informando o caráter internacional da operação (Art. 33, VIII).

---

## 8. Segurança, Sigilo e Incidentes (Art. 46 ao 48)
- **Privacy by Design (Art. 46, § 2º)**: Adotar medidas de segurança desde a fase de concepção do produto ou serviço.
- **Comunicação de Incidentes (Art. 48)**: Obrigatoriedade de comunicar à ANPD e aos titulares a ocorrência de incidente de segurança relevante que possa acarretar risco ou dano.

---

## 9. Sanções Administrativas pela ANPD (Art. 52)
Infrações sujeitam os agentes a:
- Advertência com indicação de prazo corretivo.
- Multa simples de **até 2% do faturamento** no Brasil, limitada a **R$ 50.000.000,00 por infração**.
- Multa diária.
- Publicização da infração.
- **Bloqueio ou eliminação** dos dados pessoais afetados.
- Suspensão/proibição parcial ou total das atividades de tratamento.
Arquivo 3: .kiro/skills/lgpd-compliance-checker/references/privacy-by-design-checklist.md
# Checklist de Engenharia de Privacidade e Privacy by Design (Art. 46)

Este guia prático direciona a verificação técnica de arquitetura, código-fonte e bancos de dados para garantir o cumprimento dos requisitos de *Privacy by Design* e *Privacy by Default*.

---

## 1. Arquitetura de APIs e Payloads
- [ ] **Minimização de Entrada (Input Minimization)**: Os endpoints recebem apenas os atributos estritamente necessários para a operação? (Ex.: Não aceitar objeto `User` completo no `POST /orders` se apenas `userId` for necessário).
- [ ] **Minimização de Saída (Output Minimization)**: As respostas da API filtram campos sensíveis/pessoais? (Ex.: Proibido retornar `password_hash`, `cpf`, `rg` ou `cartao` em rotas públicas de busca ou listagem).
- [ ] **Validação e Sanitização de Entrada**: Entradas do usuário são sanitizadas contra SQL Injection, NoSQL Injection e XSS, prevenindo vazamento indireto de dados?

---

## 2. Banco de Dados e Armazenamento
- [ ] **Criptografia em Repouso (Encryption at-Rest)**: Bancos de dados relacionais e NoSQL utilizam criptografia de disco/volume (ex.: AES-256) e criptografia em nível de coluna/campo para dados sensíveis (`Column-Level Encryption`).
- [ ] **Segregação de Dados Sensíveis**: Dados pessoais sensíveis (biometria, saúde, dados financeiros) são mantidos em tabelas/coleções segregadas com controle de acesso restrito?
- [ ] **Estratégia de Pseudonimização**: Chaves primárias expostas em URLs ou APIs utilizam UUIDv4 / ULID em vez de IDs sequenciais numéricos (`Auto-Increment`) que permitam enumeração de titulares.
- [ ] **Mecanismo de Expiração e Purga (TTL)**: Tabelas temporárias, tokens de sessão, caches Redis e logs de auditoria possuem política ativa de expiração (*Time To Live*).

---

## 3. Sanitização de Logs, Telemetria e APM
- [ ] **Mascaramento em Loggers (Log Scrubbing)**: Middlewares de log (Winston, Morgan, Log4j, Serilog, etc.) possuem filtros de regex configurados para interceptar e mascarar PII:
  - *CPF*: `\d{3}\.\d{3}\.\d{3}-\d{2}` -> `***.***.***-**`
  - *Cartão*: `\d{4}\s?\d{4}\s?\d{4}\s?\d{4}` -> `****-****-****-1234`
  - *E-mail*: `[^@]+@[^@]+\.[^@]+` -> `u***@domain.com`
- [ ] **Proibição de PII em Query Parameters**: URLs não contêm dados pessoais em query strings (ex.: `GET /search?email=user@test.com`), pois URLs são gravadas em logs de proxies, Nginx e navegadores.

---

## 4. Gestão de Consentimento e Direitos do Titular
- [ ] **Consentimento Granular (Opt-In Ativo)**: Telas de cadastro e formulários não possuem checkboxes pré-marcados. Cada finalidade (Marketing, Analytics, Compartilhamento) possui opt-in separado.
- [ ] **Trilhas de Auditoria de Consentimento (Audit Trail)**: O sistema armazena a evidência de consentimento contendo: `userId`, `timestamp`, `ip`, `versão do termo` e `finalidade aprovada` (Art. 8º, § 2º).
- [ ] **Automação de Exclusão (Soft/Hard Delete)**:
  - Exclusão a pedido do titular revoga o acesso e marca o registro como excluído logicamente (`deleted_at`).
  - Rotinas em background executam a limpeza definitiva (*Hard Delete*) ou anonimização irreversível após o prazo legal de retenção (Art. 16).

---

## 5. Integrações com Terceiros e Pipelines CI/CD
- [ ] **Auditoria de Webhooks e SaaS Terceiros**: Dados transmitidos para APIs parceiras (CRMs, Analytics, Gateways) contêm apenas os campos acordados em Contrato de Operador.
- [ ] **Sanitização de Ambientes de Staging e Dev**: Ambientes de desenvolvimento e homologação utilizam dados totalmente sintéticos (*Faker*) ou bases de produção mascaradas/anonimizadas. É terminantemente proibido clonar dumps de produção com dados reais para máquinas de desenvolvedores.
- [ ] **Gerenciamento de Segredos em CI/CD**: Chaves de criptografia, tokens de API e credenciais de banco não estão *hardcoded* no código-fonte nem em arquivos de configuração versionados no Git.
