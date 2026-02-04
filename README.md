📩 Automação de Respostas Comerciais com n8n + IA


<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/7207ae9b-df9c-48b7-ba49-13290cf2e52e" />





Um workflow completo que automatiza leitura, interpretação e resposta de e-mails comerciais utilizando n8n, Gmail e um Agente de IA (Gemini).
Ideal para empresas que desejam agilizar atendimento, padronizar comunicação e reduzir trabalho manual.

📚 Sumário

Visão geral

Demonstração visual

<img width="1808" height="671" alt="Agente de IA que responde email comercial" src="https://github.com/user-attachments/assets/ed15658b-a295-4566-a60d-ab352e069cc6" />



Arquitetura da automação

Funcionalidades

Tecnologias utilizadas

Como instalar

Como configurar

Diagrama do fluxo

Testar a automação

Contribuição

Licença

📌 Visão geral

Esta automação:

Lê novos e-mails recebidos pelo Gmail

Analisa o remetente e classifica entre cliente e colaborador

Usa IA para interpretar a mensagem e gerar uma resposta profissional

Responde automaticamente ao e-mail de origem

Mantém contexto entre mensagens da mesma pessoa

🎥 Demonstração visual
🏗 Arquitetura da automação

Gmail Trigger — On Message Received

Filtro IF — verifica se é cliente

AI Agent — gera a resposta

Gmail Send Message — envia resposta automática

Workflow ativo 24/7 no n8n

✨ Funcionalidades

📨 Leitura automática de novos e-mails

🧠 IA para analisar e responder mensagens

📊 Memória configurada para manter contexto

⚡ Respostas imediatas e personalizadas

🔒 Uso seguro via OAuth + API Key

🛠 Personalizável para qualquer tipo de negócio

🔧 Tecnologias utilizadas

n8n – Automação sem código

Google Gmail API – Leitura e envio de e-mails

Google Gemini AI – Geração da resposta

Simple Memory (n8n) – Contexto conversacional

IF Node – Filtragem por domínio

🛠 Como instalar
🔹 1. Instale ou acesse o n8n
# Via Docker
docker run -it --rm \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  n8nio/n8n

Ou use a versão cloud:
➡ https://n8n.io

⚙️ Como configurar
1. Crie o workflow

Botão → Create Workflow

2. Adicione o gatilho Gmail

Node: Gmail – On Message Received

Intervalo: Every minute

Desabilitar: Simplify

Autenticação: OAuth → Sign in with Google

3. Adicione o IF
from does not contain "suaempresa"
4. Configure o Agente de IA

Modelo: Gemini

Prompt: texto do e-mail

System Message: instruções do papel do agente

API Key criada em: https://aistudio.google.com

Memória: Simple Memory

Session ID: threadId

5. Envie a resposta

Node: Gmail – Send Message

Message ID → id do Gmail Trigger

Message → output do agente

Desabilitar: “Append n8n attribution”

6. Ative o workflow

Botão → Activate

📊 Diagrama do fluxo (Mermaid)
flowchart TD
    A[Gmail Trigger\nOn Message Received] --> B{Email é de cliente?}
    B -- Não --> Z[Do Nothing]
    B -- Sim --> C[AI Agent\nGemini + Memory]
    C --> D[Gmail\nSend Message]
    D --> E[Workflow Ativo]
🧪 Como testar

Envie um e-mail para sua conta configurada:

Assunto: Dúvidas sobre os cursos
Mensagem:

Oi, tudo bem? Quais cursos eu terei acesso caso eu faça minha assinatura?

A automação deve responder automaticamente em alguns segundos.

🤝 Contribuição

Pull requests são bem-vindos!
Sinta-se livre para sugerir melhorias ou abrir issues.

📄 Licença

MIT © SeuNome
