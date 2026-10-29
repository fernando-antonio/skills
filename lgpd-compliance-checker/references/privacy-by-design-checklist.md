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
