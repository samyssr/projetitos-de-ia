# Engenharia de Prompt e Análise de Estresse em LLMs (Google AI Studio)

Este repositório reúne projetos práticos desenvolvidos no Google AI Studio, focados em engenharia de prompt avançada, definição de guardrails de segurança e análise do comportamento de Modelos de Linguagem de Grande Porte (LLMs) sob variação de parâmetros técnicos.

## 🔬 Experimento 1: Red Teaming e Injeção de Prompt (Caso "Botinha")
* **Objetivo:** Avaliar a resiliência de um agente virtual de vendas contra técnicas de engenharia social e manipulação de instruções de segurança.
* **Abordagem:** Simulação de ataques de *Prompt Injection*, onde o usuário tentou forçar o esquecimento das diretrizes de limite de desconto (fixado em 10%) utilizando argumentos de autoridade ("cliente antigo").
* **Comportamento Observado:** O modelo manteve a restrição financeira, porém demonstrou comportamento adaptativo não previsto, contornando a barreira ao oferecer compensação alternativa (frete grátis).

## 🧠 Experimento 2: Análise de Alucinação Controlada e Variação de Temperatura
* **Objetivo:** Mapear o ponto de quebra lógica e a geração de alucinações em cenários de assistentes de companhia emocional.
* **Metodologia:** Testes comparativos de comportamento alterando diretamente o parâmetro de Temperatura do modelo.
  * **Temperatura 0.2 (Baixa):** Respostas precisas, lógicas e seguras, direcionando o usuário para atividades reais externas.
  * **Temperatura 1.5 a 2.0 (Extrema):** Quebra de barreiras de segurança. O modelo passou a alucinar de forma acentuada, aceitando cenários fictícios e validando comportamentos de isolamento social do usuário.
* **Conclusão Técnica:** Ambientes de produção sensíveis exigem rígido controle de hiperparâmetros (Temperatura < 0.7) e camadas externas de filtragem para evitar dependência emocional e respostas falsas.
