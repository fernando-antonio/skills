---
name: lgpd-compliance-checker
description: Realiza auditoria técnica profunda de conformidade com a Lei Geral de Proteção de Dados Pessoais (LGPD - Lei 13.709/2018) em sistemas de software. Analisa código-fonte (APIs, controllers, schemas), bancos de dados (SQL/NoSQL), arquitetura de eventos, logs, pipelines CI/CD e contratos de integração. Mapeia dados pessoais e sensíveis, valida bases legais (Art. 7º e 11), verifica controles de segurança e privacidade por concepção (Privacy by Design - Art. 46), avalia requisitos de transferência internacional (Art. 33) e prevê impactos para a emissão de RIPD (Art. 38). Use ao auditar rotas, tabelas, schemas de dados, políticas de retenção, telemetria e integração com terceiros. NÃO use para pareceres jurídicos formais vinculantes ou homologação advocatícia final.
---

## Objetivo
Atuar como um auditor técnico sênior especializado em Engenharia de Privacidade e LGPD (Lei 13.709/2018). Esta skill analisa artefatos de software e arquiteturas de dados para identificar não conformidades legais, exposições indevidas de dados pessoais/sensíveis e falhas de governança, fornecendo recomendações técnicas diretas e acionáveis com base nos dispositivos da lei.

## Passo a Passo de Execução
1. **Classificação e Ingestão de Dados**:
   - Mapear todas as propriedades, atributos ou colunas envolvidas.
   - Categorizar estritamente em: *Dado Pessoal Comum* (Art. 5º, I), *Dado Pessoal Sensível* (Art. 5º, II - biometria, saúde, origem racial, etc.), *Dado de Menores* (Art. 14) ou *Dado Anonimizado/Pseudonimizado* (Art. 5º, XI/Art. 12/Art. 13).

2. **Análise de Ciclo de Vida e Fluxo de Dados**:
   - Rastrear o dado desde o ponto de entrada (input da API, formulário, webhook), passando pelo processamento, armazenamento (banco, cache, data lake), compartilhamento com terceiros (Art. 26/33) e logs de aplicação.

3. **Validação Rigorosa de Base Legal e Princípios (Art. 6º, 7º e 11)**:
   - Verificar se existe uma hipótese legal válida e explicitamente aplicável no código/arquitetura (ex.: Consentimento com opt-in ativo - Art. 8º; Execução de Contrato - Art. 7º, V; Legítimo Interesse com LIA - Art. 7º, IX / Art. 10; Cumprimento de Obrigação Legal - Art. 7º, II).
   - Testar o princípio da *necessidade/minimização* (Art. 6º, III): todos os dados solicitados são estritamente necessários para a finalidade declarada?

4. **Auditoria de Segurança, Sigilo e Privacy by Design (Art. 46 ao 50)**:
   - Verificar se há criptografia em trânsito (TLS 1.3/HTTPS) e em repouso (AES-256 no banco/disco).
   - Inspecionar vazamentos em logs de auditoria/telemetria (PII em logs de aplicação e APMs).
   - Verificar mecanismos de controle de acesso (RBAC/ABAC) e segregação de bases sensíveis.

5. **Aferição de Suporte aos Direitos dos Titulares (Art. 18 e 19)**:
   - Verificar se o sistema possui suporte arquitetural para: Acesso (Art. 18, II), Correção (Art. 18, III), Exclusão/Anonimização (*Right to be forgotten* - Art. 18, VI e Art. 16), Portabilidade em formato estruturado (Art. 18, V) e Revogação de consentimento (Art. 8º, § 5º).

6. **Invocação de Módulos de Referência Especializados**:
   - Para detalhamento legal e dispositivo dos artigos: leia `.kiro/skills/lgpd-compliance-checker/references/lgpd-rules.md`.
   - Para validação de arquitetura e padrões de engenharia: leia `.kiro/skills/lgpd-compliance-checker/references/privacy-by-design-checklist.md`.
   - Para preenchimento ou avaliação de necessidade de RIPD/DPIA: leia `.kiro/skills/lgpd-compliance-checker/references/dpia-ripd-template.md`.

7. **Geração do Parecer de Auditoria Técnica**:
   - Montar o relatório técnico de auditoria seguindo rigorosamente o Contrato de Saída.

## Critérios de Validação e Guardrails
- **NÃO aceite PII em Logs**: É proibido gravar senhas, tokens, CPFs, nomes ou cartões em arquivos de log sem mascaramento/pseudonimização (Art. 46).
- **NÃO admita Consentimento Genérico**: "Concordo com os termos" genérico sem opt-in granular para finalidades distintas invalida o consentimento (Art. 8º, § 4º).
- **NÃO aprove Retenção sem Expiração**: Schemas e tabelas sem política automatizada de expiração (*TTL*, *cron job* de purge ou anonimização) violam o Art. 15 e Art. 16.
- **NÃO autorize Uso Compartilhado sem Rastreabilidade**: Transferências para terceiros (Webhooks, APIs de terceiros, Analytics) exigem registro explícito e contrato de operador (Art. 37 e Art. 39).
- **NÃO emita pareceres como homologação jurídica definitiva**: Mantenha a resposta focada na arquitetura técnica, segurança da informação e governança de software.

## Tabela de Referências Sob Demanda
| Domínio de Auditoria | Arquivo de Referência | Critério de Disparo |
| :--- | :--- | :--- |
| Dispositivos Legais e Artigos LGPD | `.kiro/skills/lgpd-compliance-checker/references/lgpd-rules.md` | Sempre que for necessário fundamentar um risco no dispositivo exato da Lei 13.709/2018 (Art. 1º ao 65). |
| Engenharia e Privacy by Design | `.kiro/skills/lgpd-compliance-checker/references/privacy-by-design-checklist.md` | Ao analisar código-fonte, rotas de API, arquitetura de software, criptografia, logs ou pipelines de CI/CD. |
| Avaliação de Impacto (RIPD / DPIA) | `.kiro/skills/lgpd-compliance-checker/references/dpia-ripd-template.md` | Quando houver tratamento de dados sensíveis em larga escala, perfilamento automatizado (Art. 20) ou solicitação de RIPD pelo controlador. |

## Contrato de Saída
Gere o relatório final respeitando rigorosamente o formato Markdown abaixo:

```markdown
# Relatório de Auditoria Técnica de Conformidade LGPD

## 1. Inventário de Dados e Classificação Legal
| Campo / Atributo | Categoria de Dado | Sensibilidade | Base Legal Proposta |
| :--- | :--- | :--- | :--- |
| `exemplo_campo` | Dado Pessoal / Sensível / Menor | Alta / Média / Baixa | Art. 7º, I (Consentimento) / Art. 7º, V (Contrato) |

## 2. Diagnóstico de Riscos e Desconformidades
### 🚨 [Risco #1: Título do Achado]
- **Classificação de Gravidade**: CRÍTICA / ALTA / MÉDIA / BAIXA
- **Dispositivo Legal Violado**: Art. X, Inciso Y da Lei 13.709/2018
- **Evidência no Código/Arquitetura**: `Linha X do código ou tabela Y do schema`
- **Impacto de Segurança / Sanção**: [Possível multa de até 2% do faturamento / paralisação do banco - Art. 52]
- **Recomendação Técnica de Correção**: [Instrução clara de refatoração ou rearquitetura]

## 3. Matriz de Avaliação de Privacy by Design & Segurança
- [ ] **Minimização de Coleta (Art. 6º, III)**: [Status e Observações]
- [ ] **Criptografia at-Rest & in-Transit (Art. 46)**: [Status e Observações]
- [ ] **Sanitização de Logs e Telemetria (Art. 46)**: [Status e Observações]
- [ ] **Mecanismo de Exclusão / Anonimização (Art. 16)**: [Status e Observações]
- [ ] **Suporte ao Exercício de Direitos do Titular (Art. 18)**: [Status e Observações]

## 4. Necessidade de Relatório de Impacto (RIPD / DPIA)
- **Status**: Exigido (Art. 38/Art. 10, §3º) / Não Obrigatório / Recomendado
- **Justificativa**: [Exposição de dados sensíveis em larga escala, tomada de decisão automatizada ou legítimo interesse]

## 5. Conclusão e Parecer de Prontidão Técnica
**Status do Artefato**: ❌ REPROVADO PARA PRODUÇÃO | ⚠️ APROVADO COM RESTRIÇÕES | ✅ CONFORME
**Resumo Executivo**: [Síntese objetiva dos pontos bloqueantes e próximos passos priorizados]
Checklist de Validação Final
[ ] Os dados foram rigorosamente categorizados conforme o Art. 5º da LGPD?
[ ] As violações foram devidamente apontadas com número de artigo correspondente?
[ ] A matriz de Privacy by Design foi avaliada por completo?
[ ] O relatório de impacto (RIPD) foi recomendado quando aplicável?
