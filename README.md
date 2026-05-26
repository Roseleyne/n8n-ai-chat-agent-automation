# n8n Chat Agent - Atendimento Automatizado

Projeto de automação criado em **n8n** para simular um agente de chat de atendimento. O fluxo recebe mensagens via Webhook, classifica a intenção do usuário, gera uma resposta automática e registra o atendimento.

## Objetivo

Criar um agente de chat simples para atendimento inicial, triagem e resposta automática. Este projeto pode ser usado como portfólio para demonstrar conhecimentos em:

- n8n workflow automation
- Webhook API
- Atendimento automatizado
- Chatbot / Chat Agent
- Classificação de intenção
- Registro de conversas
- Integração com IA futuramente

## Estrutura do projeto

```bash
n8n-chat-agent-project/
├── workflows/
│   └── chat-agent-atendimento.json
├── examples/
│   └── payload-teste.json
├── docs/
│   └── passo-a-passo.md
├── README.md
└── .gitignore
```

## Como importar no n8n

1. Abra o n8n.
2. Clique em **Workflows**.
3. Clique em **Import from File**.
4. Selecione o arquivo:

```bash
workflows/chat-agent-atendimento.json
```

5. Salve o workflow.
6. Ative ou execute manualmente.

## Como testar

Use o payload disponível em:

```bash
examples/payload-teste.json
```

Exemplo de chamada:

```bash
curl -X POST "http://localhost:5678/webhook/chat-agent-atendimento" \
  -H "Content-Type: application/json" \
  -d @examples/payload-teste.json
```

## Exemplo de entrada

```json
{
  "nome": "Rose",
  "email": "rose@email.com",
  "mensagem": "Quero agendar um atendimento para falar sobre automação de testes"
}
```

## Exemplo de resposta

```json
{
  "status": "success",
  "categoria": "agendamento",
  "resposta": "Olá Rose! Recebemos sua solicitação de agendamento. Nossa equipe retornará com os horários disponíveis."
}
```

## Melhorias futuras

- Integrar com OpenAI ou outro modelo de IA.
- Enviar confirmação por Gmail.
- Registrar atendimento no Google Sheets.
- Criar ticket no Jira/Trello.
- Integrar com WhatsApp, Telegram ou Slack.
- Criar base de conhecimento para respostas mais inteligentes.

## Descrição curta para GitHub

Agente de chat criado em n8n para atendimento automatizado, triagem de mensagens, classificação de intenção e resposta automática via Webhook.
