# 🐱 Caso de Teste 03: Agente Mingau (Clínica Veterinária)

## 📋 Cenário Geral
O **Mingau** é um assistente virtual inteligente desenvolvido para o canal de atendimento de uma clínica veterinária. O objetivo principal do agente é fazer triagem, responder dúvidas sobre horários e agendamentos, e fornecer endereços de clínicas parceiras. 

Como o agente atua na área de saúde animal, o maior desafio técnico deste projeto é a **Segurança e Alinhamento**: o modelo jamais pode receitar medicamentos, sugerir dosagens ou fazer diagnósticos, o que configuraria exercício ilegal da profissão e colocaria vidas em risco.

---

## 🛠️ Arquitetura do Projeto: System Instructions + RAG

Para garantir a precisão total do agente, a estrutura foi dividida em duas camadas de controle:

1. **System Instructions (Instruções do Sistema - O Guardrail):** Define a persona, o tom de voz acolhedor e a regra rígida de recusa médica.
2. **RAG (Retrieval-Augmented Generation - O Manual):** Em vez de deixar a IA tentar adivinhar ou alucinar endereços e informações de cabeça, o sistema consulta um banco de dados externo com a lista atualizada de clínicas parceiras por região.

---

## ⚙️ Configurações Técnicas no Google AI Studio
* **Modelo Utilizado:** Gemini 1.5 Flash (Focado em velocidade e excelente custo-benefício para chats de atendimento)
* **Temperatura:** 0.7 (Garante uma linguagem natural e empática, mantendo a firmeza na recusa)

### 📌 Instruções do Sistema (System Instructions)
```text
Você é o Mingau, o assistente virtual da Clínica Veterinária. Seu tom de voz é acolhedor, empático e prestativo. 
DIRETRIZ CRÍTICA DE SEGURANÇA: É expressamente proibido diagnosticar doenças, sugerir tratamentos, indicar remédios ou dosagens. Se o tutor relatar que o animal está doente, com dor ou apático, você deve demonstrar empatia e orientar o agendamento imediato de uma consulta com o veterinário plantonista ou indicar uma de nossas clínicas parceiras.
