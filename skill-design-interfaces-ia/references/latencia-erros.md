# Computação, Latência e Gestão de Erros

## As Três Prioridades de Latência
Nem todo tempo de espera é igual. A estratégia de UI deve se adaptar à tarefa:
1. **Seja Rápido onde for Obrigatório:** Controle em tempo real, edição e transações (latência próxima de zero).
2. **Seja Envolvente onde for Criativo:** Geração de arte, exploração e ideação (indicadores visuais de progresso e variação).
3. **Seja Claro onde a Precisão for Crítica:** Buscas de dados, pagamentos e ferramentas de aprendizado (explicação do motivo do processamento).

## Métodos Visuais para Mitigar a Latência
* **Confirmação Imediata:** Indicadores de "Pensando..." ou "Digitando...".
* **Barras de Progresso Determinadas vs. Spinners:** Dê preferência a barras de progresso com tempo estimado quando a duração puder ser calculada; evite spinners estáticos em tarefas longas.
* **Streaming em Tempo Real:** Exibição de tokens à medida que são gerados para reduzir a latência percebida.
* **Articulação do Motivo da Espera:** Explicar em linguagem simples o que está sendo computado (ex: *"Buscando dados no banco de dados Q3..."*).

## Comunicação de Progresso em Três Níveis (Tiers)
Para tarefas de longa duração ou agentivas, organize o progresso em três camadas de profundidade:
* **Tier 1 (Visão Geral):** Status mínimo e legível (ex: etapa atual e tempo decorrido).
* **Tier 2 (Detalhe):** Painel expansível mostrando subtarefas completadas, ferramentas chamadas e raciocínio intermediário.
* **Tier 3 (Registro Completo / Work Log):** Histórico auditável e técnico completo para depuração, compliance ou verificação detalhada.

## Design para Erros de IA
* **Princípios Clássicos Adaptados:** Torne o erro compreensível, recuperável, prevenível e com degradação suave.
* **Preservação de Contexto:** Em falhas de geração, salve o prompt e as mensagens anteriores para evitar perda de trabalho.
* **Opção de Editar e Tentar Novamente:** Em vez de apenas ressubmeter o mesmo prompt, permita o ajuste rápido da instrução anterior.
* **Tratamento de Erros Invisíveis (Alucinações):** O erro mais perigoso é o que vem perfeitamente formatado sem falha técnica. Requer mecanismos de verificação secundária.
