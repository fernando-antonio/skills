# IA Agentiva: Sistemas que Planejam, Agem e Se Adaptam

## Os Cinco Padrões Agentivos
1. **Reflexão (Reflection):** Ciclo interno de *Gerar ➔ Criticar ➔ Refinar* antes de entregar o resultado final ao usuário.
2. **Uso de Ferramentas (Tool Use):** Capacidade de chamar APIs, bancos de dados e comandos para executar ações no mundo real.
3. **Planejamento (Planning):** Decomposição de metas complexas em sequências de tarefas com dependências e ramificações condicionais.
4. **Colaboração Multiagente (Multiagent Collaboration):** Coordenação entre agentes especializados (ex: pesquisador + analista + redator) com resolução de conflitos.
5. **ReAct (Reason + Act):** Ciclo iterativo adaptativo de *Pensar ➔ Agir ➔ Observar ➔ Reavaliar*.

## Os Três Princípios do Design Agentivo
Para manter a autonomia compreensível e confiável:
1. **Revele o Plano (Reveal the Plan):** Apresente a interpretação do objetivo e a sequência de passos *antes* de iniciar a execução, permitindo ajustes prévios.
2. **Priorize o que Mais Importa (Prioritize What Matters Most):** Evite sobrecarregar o usuário com todas as operações internas; filtre e apresente alertas apenas quando a atenção humana for necessária.
3. **Projete para Controle Compartilhado (Design for Shared Control):** Garanta pontos de interrupção (*pausa/retomada*), checkpoints de confirmação e capacidade de ajuste contínuo sem perder o trabalho já realizado.

## Pontos de Contato na UI Agentiva
* **Estágio de Processamento:** Decomposição visível da meta, sequenciamento de dependências e esclarecimento rápido de ambiguidades.
* **Checkpoints:** Momentos estratégicos de pausa para aprovação de permissões, revisão de saídas intermediárias e edições de rota.
* **Rollback e Histórico:** Capacidade de reverter o estado do projeto para um checkpoint anterior caso a execução agentiva tome um caminho indesejado.
