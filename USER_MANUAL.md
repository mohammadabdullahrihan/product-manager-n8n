# 📖 Full User Manual: Operational Guardrails

This document provides detailed operational procedures for both customers and administrators using the **Rayyan AI Product Sales Manager**.

---

## 👤 1. The Customer Experience Journey

### Phase A: Greeting & Context
*   **Trigger:** Customer sends `Hi`, `Store info`, or `I want to buy`.
*   **AI Action:** Provides a customized welcome message based on the platform and time of day.
*   **Menu:** Presents 4 clear options.

### Phase B: Onboarding (New Customers Only)
*   **Scenario:** Customer chooses "New Order". System sees they are not in the `Customers` sheet.
*   **AI Protocol:** Polite data collection.
    *   *Prompt 1:* "May I know your full name for the delivery?"
    *   *Prompt 2:* "Please provide your detailed delivery address (Area, Street, House No)."
    *   *Prompt 3:* "Lastly, your email for the invoice (Optional)."
*   **Validation:** AI checks if the address looks like a real address before proceeding.

### Phase C: Selection & Checkout
*   **Catalog:** AI presents products with prices.
*   **Quantity Selection:** AI asks "How many units do you need?".
*   **Confirmation:** AI summarizes: "One *Smartphone Pro Max* for $999. Shipping to *Dhaka*. Should I confirm?".
*   **Final Step:** Once confirmed, AI creates the row and provides an `Order ID`.

### Phase D: Post-Purchase Support
*   **Status Inquiry:** Customer types "Status" or "Update".
*   **AI Action:** Lists all active orders. If the sheet says "Shipped", the AI adds: "Great news! Your package is with the courier."

---

## 👨‍💼 2. The Administrator Console (Google Sheets)

Administrators manage the system via three main tabs. **DO NOT change the column headers (Row 1), as the AI depends on them.**

### Tab 1: `Config` (Your Shop Backend)
| Column Name | Purpose | Example |
| :--- | :--- | :--- |
| `product_name` | Name shown to customers | Wireless Mouse v2 |
| `price` | Product cost | 1500 BDT |
| `description` | Sales pitch used by AI | Long battery life, ergonomic |
| `stock_status` | Filter for AI | In Stock / Out of Stock |

### Tab 2: `Orders` (Sales Monitoring)
*   **`status` Column:** The most important column. Update this regularly:
    *   `Pending`: Default state.
    *   `Processing`: When you are packing.
    *   `Shipped`: When the courier takes it.
    *   `Cancelled`: This will trigger a notification to the customer.

### Tab 3: `Customers` (CRM)
*   Use this for your marketing campaigns or to contact customers for delivery verification.

---

## 🆘 Troubleshooting for Admins
*   **AI stopped replying?** Check the `Credentials` tab in n8n. Most common issue: Meta Token expired.
*   **Wrong info in chat?** Check the `Config` sheet for typos in the price or product name.
*   **Orders not appearing?** Check if you accidentally reached the Google Sheets cell limit or if the API connection is disconnected.

---
*Next: Technical deep-dive in the [Setup Guide](./SETUP_GUIDE.md)*
