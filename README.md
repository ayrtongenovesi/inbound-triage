# Speed to Lead Automation

Fast response automation for inbound leads. The workflow receives a new lead, classifies intent, generates a personalized first reply, stores the lead in a CRM-style table, and notifies the sales owner.

## Business Problem

Most small businesses lose leads because they respond too late. This workflow reduces time-to-first-response from hours to seconds while keeping a human owner in the loop for the actual sale.

## Who This Is For

- Local service businesses receiving form or WhatsApp leads
- Agencies handling inbound requests
- Real estate, clinics, education, consultants, and B2B services

## Stack

n8n, webhook trigger, LLM classification, Google Sheets CRM, Gmail draft/send, internal notification.

## How It Works

1. A lead arrives through a webhook.
2. The workflow normalizes the payload into a consistent lead schema.
3. An LLM classifies intent and priority.
4. The lead is saved to Google Sheets.
5. Gmail creates a fast first-response draft.
6. The owner receives an internal notification with the suggested next action.

## Demo

Input: `demo-data/input-example.json`  
Expected output: `demo-data/output-example.json`

## Business Impact

- Faster response time
- Higher lead conversion probability
- Cleaner CRM data
- Less manual triage for the business owner

## Production Improvements

- Add lead source attribution
- Add duplicate detection by email/phone
- Add meeting scheduler integration
- Add dashboard for response time and conversion rate

## Safety Notes

The workflow is designed to start in Gmail draft mode. A human can review generated replies before automatic sending is enabled.
