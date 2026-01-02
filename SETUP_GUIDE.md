# ⚙️ Technical Deep-Dive: Implementation Guide

This guide covers advanced configuration, security best practices, and fine-tuning for the **Rayyan AI Product Sales Manager**.

---

## 🏗 Sub-Node Architecture Overview
To maintain professional standards, ensure the following nodes are configured exactly as described:

### 1. Omni-Channel Processor (The Switchboard)
*   **Purpose:** Sanitizes incoming JSON from FB, IG, and WA into a single format.
*   **Format:** `{ platform: string, senderId: string, senderName: string, message: string }`.
*   **Fine-tuning:** If using Instagram, make sure your Meta App has "Messaging" permissions enabled.

### 2. Google Gemini AI Node (The Brain)
*   **Model:** Use `gemini-1.5-flash` for speed or `gemini-1.5-pro` for complex logic.
*   **Temperature:** Set to `0.7`. (High enough for human-like variety, low enough to stay accurate).
*   **System Prompt:** Always include the "Operational Boundaries" (e.g., "Do not offer discounts more than 5% without asking").

### 3. Tool Inventory (The Hands)
*   **Get Catalog:** Needs to be configured with `Read` permission.
*   **Add Order/Customer:** Needs `Append` permission.
*   **Update/Cancel:** Needs `Update` permission using `Order ID` as the unique key.

---

## 🚀 Advanced Setup Steps

### 🔐 Security & Access Control
1.  **n8n Encryption:** Enabled by default. Do not share your n8n export file without removing sensitive credentials.
2.  **API Key Management:** 
    *   Rotate your Google API Key every 90 days.
    *   Use a **Meta Permanent System User Token** to avoid the 24-hour expiration of temporary tokens.
3.  **Google Sheet Protection:** Protect the first row (Headers) and the `Config` sheet so only admins can edit.

### 📊 Professional Data Structuring
Ensure your Google Sheet headers are exactly:
*   **Customers:** `customer_id`, `whatsapp_number`, `name`, `address`, `email`.
*   **Orders:** `order_id`, `customer_id`, `whatsapp_number`, `product_name`, `quantity`, `status`.
*   **Config:** `product_name`, `price`, `description`, `stock_status`.

### 🌐 Webhook Verification (Meta Portals)
*   **Verification Token:** Create a random string (e.g., `Rayyan_AI_2026`).
*   **Verification URL:** Use the Production URL from n8n (not the Test URL).
*   **Subscription:** You must subscribe to the `messages` field in the Meta Webhook settings.

---

## 📈 Scaling Instructions
As your business grows:
1.  **Move to SQL:** Replace Google Sheets with PostgreSQL or MySQL if handles >10,000 orders.
2.  **Add Media Support:** Update the `Get Catalog` node to fetch image URLs and send them as WhatsApp "Image" messages.
3.  **Human Handoff:** Implement a "Talk to Human" node that triggers an email if the AI cannot resolve an issue.

---

## 🆘 Critical Troubleshooting List
1.  **"No response from AI":** Usually a Rate Limit issue on Google Cloud or an empty system prompt.
2.  **"Order not saving":** Check if the Google Sheet reached its 10 million cell limit.
3.  **"Wrong Currency":** The AI guesses currency based on location. Explicitly state `BDT` or `USD` in the System Message.

---
**Technical Support:**
Rayyan Quantum Labs Integration Team.  
*Expertise in High-Performance Agentic Workflows.*
