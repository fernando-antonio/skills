# Capacidades, Descoberta e Orquestração (Pré-Input)

## A Pilha de Capacidades (Capability Stack)
Ao projetar, identifique em qual camada da pilha sua funcionalidade se encontra:
1. **Base Model (Modelo Base):** Reativo, responde a prompts sem perseguir metas autonomamente (ex: sugestão de texto inline).
2. **Tool-Enabled Model (Modelo com Ferramentas):** Modelo base estendido com APIs externas, busca web ou leitura de arquivos.
3. **Agent (Agente):** Modelo + Ferramentas + Planejamento autônomo e execução de metas em múltiplas etapas.

## Matriz de Descoberta de Funcionalidades (2x2 Matrix)
Cruze a **Intenção do Usuário** com a **Iniciativa do Sistema** para escolher o padrão de interface adequado:

| | Baixa Iniciativa do Sistema | Alta Iniciativa do Sistema |
| :--- | :--- | :--- |
| **Alta Intenção do Usuário** | **Deixe o usuário liderar:** Triggers de comando (`/`, `@`), atalhos de contexto, ações baseadas em localização. | **Aceleração direta:** Análise automática de conteúdo, ferramentas contextuais sugeridas proativamente. |
| **Baixa Intenção do Usuário** | **Apresentação gradual:** Graduação de funcionalidades (*feature graduation*), tutoriais contextuais no tempo certo. | **Intervenção sutil:** Ativação em estados vazios (*empty states*), detecção de anomalias, tradução/sugestão preditiva. |

## Taxonomia de Padrões de Descoberta
* **Baseados em Input:** Menus de comando (ex: *Notion AI Palette* acionada por espaço), menus de contexto ao selecionar texto.
* **Contextuais:** Botões/bolhas de ação baseados em análise de conteúdo ou comportamento repetitivo.
* **Ambientes / Proativos:** Alertas de conflito de agenda ou lembretes de anexos (ex: Gmail/Google Calendar).
* **Progressivos:** Modos avançados liberados conforme o uso e consolidação do modelo mental do usuário.

## Princípios de Orquestração
* **Orquestração Intencional:** Apresente escolhas de modelo/ferramenta em momentos significativos.
* **Transparência na Metrificação:** Torne limites de uso/tokens visíveis e compreensíveis (ex: indicação de "Volts" ou saldo de pesquisas profundas).
* **Gerenciamento de Permissões em Camadas:** Gradue permissões por nível de risco (leitura vs. modificação de arquivos vs. execução de comandos).
