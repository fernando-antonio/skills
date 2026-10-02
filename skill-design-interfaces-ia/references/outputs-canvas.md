# Design de Outputs, Verificabilidade e Canvas

## O Princípio Fundamental: "O Output Não É a Resposta"
O output gerado pela IA é um artefato proposto, não uma verdade incontestável. Deve ser entregue de forma a convidar à interpretação, verificação e ação humana.

## Princípios de Qualidade do Output
O output deve ser projetado para ser:
1. **Claro:** Estruturado com hierarquia visual explícita (Títulos, H2, H3, bullets, parágrafos curtos de no máximo 3 frases).
2. **Verificável:** Acompanhado de fontes rastreáveis, citações com hiperlinks e suporte à checagem humana.
3. **Ancorado (Grounded):** Transparente quanto ao contexto usado (jurisdição, versão do modelo, arquivos consultados, localização).
4. **Acionável:** Cercado por verbos de ação para o próximo passo (salvar, exportar, comprar, agendar, citar).
5. **Ajustável:** Fácil de refinar inline, alterar tom ou regenerar trechos específicos.

## Evitando a Sobreconfiança (AI Overreliance)
* **A Falácia das Percentagens de Confiança:** Mostrar "93% de confiança" baseado na probabilidade do próximo token cria uma falsa precisão e induz o usuário a erro.
* **Criação de Camadas de Verificação Humana (HITL):** Para decisões de alto impacto (médico, jurídico, financeiro), a interface deve exigir revisão humana ativa (*cognitive forcing functions*).
* **Declaração de Isenção e Transparência:** Indicação clara de conteúdo gerado por IA (conforme exigências regulatórias como California SB 1001 e EU AI Act).

## O Padrão Canvas (Espaço de Trabalho Interativo)
Quando a saída da IA evolui de uma simples mensagem para um artefato de trabalho:
* **Caraterísticas do Canvas:** Espaço persistente, editável, espacial e multimodal (texto, código, elementos visuais).
* **Gestão de Estados e Versões:** Oferecer alternância clara entre versões (v1, v2, v3), histórico de alterações e capacidade de restaurar (*rollback*).
