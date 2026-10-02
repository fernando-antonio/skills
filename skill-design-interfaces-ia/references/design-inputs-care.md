# Design de Inputs e Canais de Intenção

## Os Três Canais da Intenção Humana
A intenção do usuário viaja simultaneamente por três canais:
1. **Contexto Implícito:** Informações do ambiente sem solicitação verbal (documento aberto, texto selecionado, localização, histórico recente).
2. **Prompting Explícito:** Instruções digitadas ou faladas.
3. **Manipulação Direta:** Botões, sliders, seletores de área (ferramentas de laço/pincel) e gestos GUI tradicionais.

## O Framework CARE para Prompts Eficazes
Estruture ajudas, templates e tutoriais de prompt segundo a metodologia CARE:
* **C - Context (Contexto):** Papel do usuário, público-alvo, restrições e cenário de fundo.
* **A - Action (Ação):** O tipo específico de transformação ou análise desejada (não apenas "olhe esses dados", mas "identifique tendências e sintetize em 3 pontos").
* **R - Results (Resultados):** Formato, comprimento, tom e estrutura de saída (ex: tabela, resumo executivo, lista numerada).
* **E - Examples (Exemplos):** Amostras concretas do resultado desejado ("mostre como neste modelo anterior").

## Modalidades de Input
* **Texto com Formatação Rica:** Permitir negrito, tópicos e separação de seções na caixa de input reduz a carga cognitiva do modelo e melhora a precisão (estudos mostram ganho de até 20 pontos percentuais em tarefas complexas).
* **Prompts Estruturados:** Seletores de modo (Tom, Comprimento, Público), sliders e formulários que removem a ansiedade da "página em branco".
* **Manipulação Direta e Lei de Jakob:** Em ferramentas visuais, utilize metáforas conhecidas (pincel, seleção, handles) combinadas com caixa de prompt (ex: *Canva Magic Edit*, *Adobe Generative Fill*).

## Starter Prompts como Posicionamento de Produto
Evite sugestões genéricas como *"Escreva um poema"*. Use starter prompts contextuais que demonstrem a utilidade específica do produto (*"Transforme estas notas de reunião em uma pauta acionável"*).

## Riscos no Prompting Explícito
* **Sicofancia (Sycophancy):** A tendência do LLM de concordar com as premissas do usuário mesmo quando incorretas.
* **Efeito Espelho de Tom:** O modelo reflete e amplifica o viés emocional do prompt.
* **O Paradoxo da Precisão ("Lost in the Middle"):** Prompts excessivamente longos perdem atenção nas informações situadas no meio do contexto.
