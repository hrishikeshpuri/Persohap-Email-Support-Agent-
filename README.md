# Persohap (Email Support Agent)

n8n workflow that answers labeled Gmail messages using an AI agent grounded in a Pinecone knowledge base of Persohap GTM material.

## What it does

1. **Email replies** — A Gmail trigger polls a specific label every minute, sends the message text to an AI agent (`gpt-4.1`), retrieves Persohap GTM context from Pinecone, and replies on the original thread.
2. **Knowledge ingest** — A form (`GTMHRISHI`) accepts a file upload, loads it, embeds it with OpenAI, and inserts it into Pinecone index `gtm-hrishi-persohap-v2`.

## Import into n8n

1. Open n8n → **Workflows** → **Import from File**.
2. Select `workflows/persohap-email-support-agent.json`.
3. Reconnect credentials: Gmail, OpenAI, Pinecone.
4. Confirm the Gmail label filter and the Pinecone index name.
5. Publish when you are ready to run it.

## Credentials required

- Gmail OAuth
- OpenAI API
- Pinecone API (index: `gtm-hrishi-persohap-v2`)

Do not commit API keys. Map credentials in n8n after import.
