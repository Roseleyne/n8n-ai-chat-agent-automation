# Passo a passo para executar o Chat Agent no n8n

## 1. Criar ou abrir o n8n

Você pode usar o n8n local, desktop, cloud ou via Docker.

## 2. Importar workflow

No menu lateral do n8n:

1. Clique em **Workflows**.
2. Clique em **Import from File**.
3. Selecione `workflows/chat-agent-atendimento.json`.
4. Clique em **Save**.

## 3. Entender o fluxo

O workflow possui os seguintes passos:

1. **Webhook - Receber mensagem**  
   Recebe a mensagem enviada pelo cliente.

2. **Validar dados recebidos**  
   Confere se nome, e-mail e mensagem foram enviados.

3. **Classificar intenção**  
   Identifica se a mensagem é sobre agendamento, suporte, orçamento ou dúvida geral.

4. **Gerar resposta automática**  
   Monta uma resposta personalizada.

5. **Responder ao usuário**  
   Retorna a resposta via Webhook.

## 4. Testar pelo Postman ou terminal

Exemplo com curl:

```bash
curl -X POST "http://localhost:5678/webhook/chat-agent-atendimento" \
  -H "Content-Type: application/json" \
  -d @examples/payload-teste.json
```

## 5. Subir no GitHub

```bash
git init
git add .
git commit -m "Add n8n chat agent workflow"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/n8n-chat-agent-project.git
git push -u origin main
```

## 6. Sugestão de nome do repositório

```text
n8n-chat-agent-atendimento
```

## 7. Sugestão de descrição do repositório

```text
Agente de chat automatizado em n8n para atendimento inicial, classificação de intenção e resposta via Webhook.
```
