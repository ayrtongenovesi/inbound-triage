# Architecture

## Flow

1. Webhook receives a lead payload.
2. A normalization step maps raw fields into a consistent lead schema.
3. An LLM classification step assigns intent and priority.
4. The lead is appended to Google Sheets.
5. A personalized first response is drafted or sent.
6. The owner receives an internal notification with summary and next action.

## Failure Handling

- Missing email and phone: mark lead as `needs_contact_info` and notify owner.
- Empty message: classify as `unknown_intent` and send neutral acknowledgment.
- LLM failure: use a deterministic fallback message and still save the lead.
- Sheets failure: send internal alert with the full payload so the lead is not lost.

## Production Notes

For production, the send step can be configured as Gmail draft first instead of automatic send. This keeps humans in the loop while preserving speed.
