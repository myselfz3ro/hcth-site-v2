# Reservation System Schema

## Google Form Fields
1. Name (Short answer)
2. WhatsApp/Phone Number (Short answer)
3. Email (Short answer)
4. Date (Date)
5. Time (Time)
6. Number of Guests (Number, max 45, max group 8)

## Google Sheet Structure (Output)
- Timestamp
- Name
- WhatsApp/Phone
- Email
- Date
- Time
- Guests
- Status (Pending/Confirmed)

## Logic (n8n Workflow)
1. **Trigger:** Google Form Submit
2. **Validator:** 
    - IF guests > 45 -> Reject
    - IF group > 8 -> Flag for manual check (or reject)
3. **Action:**
    - Insert to Sheet
    - Create Event in Google Calendar
    - Send Email (via Gmail)
    - Send WhatsApp (via API)
