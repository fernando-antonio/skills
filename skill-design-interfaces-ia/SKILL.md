---
name: skill-design-interfaces-ia
description: Guia prático e estruturado para projetar interfaces de IA (generativas, assistivas e agentivas) com foco em usabilidade, transparência, confiança e controle do usuário. Cobre o framework Input-Computacao-Output, descoberta e orquestracao de capacidades, design de inputs (framework CARE), tratamento de latencia e erros, verificabilidade de outputs, padrao Canvas e padroes de IA agentiva. Use ao projetar, revisar ou criticar UX de produtos de IA, chats, copilotos, agentes, geracao de conteudo, prompting ou fluxos human-in-the-loop. NÃO use para revisao de codigo, QA funcional ou arquitetura de backend nao relacionada a UX de IA.
---

> **Framework original:** Louise Macfadyen (*Designing AI Interfaces: Design Principles for Creative and Autonomous AI*, O'Reilly, 2026).

## Como usar esta skill

1. Enquadre o problema no **framework central** (abaixo) para identificar em qual estágio da interação você está atuando.
2. Carregue **apenas a referência do estágio relevante** (seção "Referências"). Não carregue todas de uma vez.
3. Ao final, valide o design contra o **Checklist de Quality Gates**.

## Framework central: Input ➔ Computação ➔ Output

Toda interação em IA se organiza em cinco estágios:

1. **Configuração / Orquestração (Pré-Input):** seleção de modelos, ferramentas, permissões e contexto. → `references/capacidades-orquestracao.md`
2. **Input:** onde a intenção humana entra (contexto implícito, prompt explícito, manipulação direta). → `references/design-inputs-care.md`
3. **Computação:** processamento, latência, guardrails e tratamento de erro (a "caixa-preta"). → `references/latencia-erros.md`
4. **Output:** apresentação clara, verificável, ancorada e ajustável do resultado. → `references/outputs-canvas.md`
5. **Ação & Interpretação (Pós-Output):** edição humana, integração ao workflow e ciclos de feedback. → `references/ia-agentiva.md` (quando o sistema planeja e age)

## Princípios que valem em todos os estágios

* **O design decide se a IA funciona.** A caixa de texto não é a interface final; o design determina se o sistema serve pessoas reais.
* **Desaprender hábitos de busca.** Usuários trazem 25 anos de hábito de busca determinística; a IA gera saídas probabilísticas. Onboarding precisa reconciliar essa diferença.
* **O output não é a resposta.** Todo resultado é um artefato proposto que convida à verificação e ação humana, nunca uma verdade incontestável.
* **Combine canais de intenção.** Contexto implícito + prompt explícito + manipulação direta juntos superam qualquer canal isolado.
* **Autonomia exige controle compartilhado.** Revele o plano antes de agir, priorize o que precisa de atenção humana e ofereça pausa/rollback.

## Referências (carregar sob demanda)

| Estágio / Tema | Arquivo | Quando consultar |
| :--- | :--- | :--- |
| Pré-Input: capacidades e orquestração | `references/capacidades-orquestracao.md` | Definir camada (base/tool/agent), descoberta de features (matriz 2x2), permissões em camadas. |
| Input: canais e prompting | `references/design-inputs-care.md` | Projetar caixa de input, templates de prompt (CARE), starter prompts, mitigar sicofancia. |
| Computação: latência e erros | `references/latencia-erros.md` | Estratégia de espera, progresso em tiers, tratamento de alucinações e falhas. |
| Output: qualidade e canvas | `references/outputs-canvas.md` | Estruturar saída verificável, evitar sobreconfiança, versionamento de canvas. |
| IA agentiva | `references/ia-agentiva.md` | Sistemas que planejam e agem: padrões agentivos, checkpoints, rollback. |

## Checklist de Quality Gates

Antes de aprovar uma interface de IA, verifique:
- [ ] O modelo mental do usuário está alinhado com as reais capacidades e limitações do sistema?
- [ ] A interface oferece canais combinados de intenção (contexto implícito + prompt + manipulação direta)?
- [ ] Os prompts e ajudas visuais seguem a estrutura CARE?
- [ ] A latência é tratada de forma transparente e adaptada ao tipo de tarefa?
- [ ] O progresso de tarefas longas/agentivas está estruturado em camadas (Tiers 1, 2 e 3)?
- [ ] O output é estruturado para leitura rápida (H2, H3, tópicos, parágrafos curtos)?
- [ ] As saídas objetivas incluem fontes verificáveis e hiperlinks?
- [ ] Há sinalização clara de conteúdo gerado por IA?
- [ ] Para tarefas agentivas, o plano é revelado antes da execução e existem checkpoints de controle compartilhado?
- [ ] O usuário pode editar, pausar ou reverter ações sem perder o contexto construído?
