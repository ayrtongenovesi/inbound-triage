# Setup

1. Import `workflow.json` into n8n.
2. Create credentials for the LLM provider, Google Sheets, Gmail, and internal notifications.
3. Copy `.env.example` values into your n8n credentials or environment.
4. Create a Google Sheet with columns: lead_id, created_at, source, name, email, phone, company, message, intent, priority, status, owner_notes.
5. Test with `demo-data/input-example.json`.
6. Confirm the output matches `demo-data/output-example.json`.

## Safe Deployment

Start with Gmail draft mode. Switch to automatic sending only after reviewing at least 20 generated responses.
