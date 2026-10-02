# Skill: Design de Interfaces de IA

Guia prático e estruturado para projetar interfaces de IA (generativas, assistivas e agentivas) com foco em usabilidade, transparência, confiança e controle do usuário.

Baseado no framework de Louise Macfadyen (*Designing AI Interfaces: Design Principles for Creative and Autonomous AI*, O'Reilly, 2026).

## Para que serve

Use esta skill ao **projetar, revisar ou criticar** a UX de produtos de IA: chats, copilotos, agentes, geração de conteúdo, prompting e fluxos human-in-the-loop.

**Não** use para revisão de código, QA funcional ou arquitetura de backend não relacionada à UX de IA.

## O framework central: Input ➔ Computação ➔ Output

Toda interação em IA se organiza em cinco estágios. Identifique em qual deles você está atuando e carregue apenas a referência correspondente.

| Estágio | Descrição | Referência |
| :--- | :--- | :--- |
| **1. Configuração / Orquestração** (Pré-Input) | Seleção de modelos, ferramentas, permissões e contexto. | [`capacidades-orquestracao.md`](references/capacidades-orquestracao.md) |
| **2. Input** | Onde a intenção humana entra: contexto implícito, prompt explícito, manipulação direta. | [`design-inputs-care.md`](references/design-inputs-care.md) |
| **3. Computação** | Processamento, latência, guardrails e tratamento de erro (a "caixa-preta"). | [`latencia-erros.md`](references/latencia-erros.md) |
| **4. Output** | Apresentação clara, verificável, ancorada e ajustável do resultado. | [`outputs-canvas.md`](references/outputs-canvas.md) |
| **5. Ação & Interpretação** (Pós-Output) | Edição humana, integração ao workflow e ciclos de feedback. | [`ia-agentiva.md`](references/ia-agentiva.md) |

## Princípios que valem em todos os estágios

- **O design decide se a IA funciona.** A caixa de texto não é a interface final; o design determina se o sistema serve pessoas reais.
- **Desaprender hábitos de busca.** Usuários trazem 25 anos de hábito de busca determinística; a IA gera saídas probabilísticas. O onboarding precisa reconciliar essa diferença.
- **O output não é a resposta.** Todo resultado é um artefato proposto que convida à verificação e ação humana, nunca uma verdade incontestável.
- **Combine canais de intenção.** Contexto implícito + prompt explícito + manipulação direta juntos superam qualquer canal isolado.
- **Autonomia exige controle compartilhado.** Revele o plano antes de agir, priorize o que precisa de atenção humana e ofereça pausa/rollback.

## Como usar

1. Enquadre o problema no framework central para identificar o estágio da interação.
2. Carregue **apenas** a referência do estágio relevante — não todas de uma vez.
3. Valide o design contra o Checklist de Quality Gates abaixo.

## Conteúdo das referências

### `capacidades-orquestracao.md` — Pré-Input
A pilha de capacidades (Base Model, Tool-Enabled Model, Agent), a matriz 2x2 de descoberta de funcionalidades (intenção do usuário × iniciativa do sistema), taxonomia de padrões de descoberta e princípios de orquestração e permissões em camadas.

### `design-inputs-care.md` — Input
Os três canais da intenção humana, o framework **CARE** (Context, Action, Results, Examples) para prompts eficazes, modalidades de input, starter prompts como posicionamento de produto e riscos do prompting explícito (sicofancia, efeito espelho de tom, "lost in the middle").

### `latencia-erros.md` — Computação
As três prioridades de latência, métodos visuais para mitigar a espera, comunicação de progresso em três níveis (Tiers 1, 2 e 3) e design para erros de IA, incluindo alucinações "invisíveis".

### `outputs-canvas.md` — Output
O princípio "o output não é a resposta", os cinco atributos de qualidade do output (claro, verificável, ancorado, acionável, ajustável), como evitar a sobreconfiança (AI overreliance) e o padrão Canvas com gestão de versões.

### `ia-agentiva.md` — Pós-Output
Os cinco padrões agentivos (Reflexão, Uso de Ferramentas, Planejamento, Colaboração Multiagente, ReAct), os três princípios do design agentivo (revele o plano, priorize o que importa, controle compartilhado) e os pontos de contato na UI agentiva.

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

## Estrutura do projeto

```
skill-design-interfaces-ia/
├── SKILL.md                              # Definição da skill e framework central
├── README.md                             # Este arquivo
└── references/
    ├── capacidades-orquestracao.md       # Pré-Input: capacidades e orquestração
    ├── design-inputs-care.md             # Input: canais de intenção e framework CARE
    ├── latencia-erros.md                 # Computação: latência e gestão de erros
    ├── outputs-canvas.md                 # Output: verificabilidade e canvas
    └── ia-agentiva.md                    # Pós-Output: padrões de IA agentiva
```
