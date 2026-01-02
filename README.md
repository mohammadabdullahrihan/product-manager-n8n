# 🚀 Rayyan AI Product Sales & Omni-Channel Manager (V2.0)

Welcome to the **Rayyan AI Product Sales Manager**, an enterprise-level conversational commerce solution. This project isn't just a chatbot; it's a complete autonomous sales workforce that manages your customer relations, sales pipe, and inventory logic across the world's most popular messaging platforms.

---

## 🎯 Project Vision
Our goal is to eliminate the "Waiting Time" for customers. In modern e-commerce, a 10-minute delay in replying can cost a sale. Rayyan AI ensures a **0-second response time** with the empathy and intelligence of a human sales representative.

---

## 🛠 High-Level Tech Stack
*   **Workflow Engine:** [n8n](https://n8n.io/) (Low-code automation with high-code flexibility).
*   **Core Intelligence:** Google Gemini 1.5 Pro / Flash (Advanced LLM with deep Bengali context understanding).
*   **Database Layers:** 
    *   **Google Sheets:** Primary database (easy for non-tech admins to manage).
    *   **Simple Memory Buffer:** Window-based memory for maintaining chat context.
*   **Integration Gateways:** 
    *   **WhatsApp:** Via Meta Cloud API.
    *   **Instagram & Facebook:** Via Meta Graph API Webhooks.
*   **Logic Processing:** Node.js / JavaScript (custom logic for data sanitization).

---

## 📉 Workflow Logic & Architecture
The system follows a proprietary **"Detect-Identify-Action"** logic:
1.  **Detection:** The Webhook captures an incoming message and identifies the platform (WA/FB/IG).
2.  **Identification:** The system queries the `Customers` sheet. 
    *   If found, it pulls the profile.
    *   If not, it triggers the "Onboarding Protocol".
3.  **Context Loading:** Loads the last 6 messages from memory to "know" what the customer was talking about.
4.  **AI Reasoning:** Gemini processes the user intent. Is it a purchase? A complaint? A tracking request?
5.  **Tool Execution:** The AI autonomously calls the necessary Google Sheets tool (Add Order, Get Catalog, etc.).
6.  **Response Generation:** A polite, persuasive Bengali response is sent back through the Response Router.

---

## 📂 Documentation Deep-Dive
For a 360-degree understanding, please read the following:

### 🇺🇸 English Documentation
*   [**Detailed Features**](./FEATURES.md) - Technical and business capabilities.
*   [**Full User Manual**](./USER_MANUAL.md) - Interaction guide for staff and buyers.
*   [**Technical Setup Guide**](./SETUP_GUIDE.md) - Developer instructions.

### 🇧🇩 বাংলা ডকুমেন্টেশন (Bengali)
*   [**বিস্তারিত ফিচারসমূহ**](./FEATURES_BN.md)
*   [**ইউজার ম্যানুয়াল**](./USER_MANUAL_BN.md)
*   [**পূর্ণাঙ্গ সেটআপ গাইড**](./SETUP_GUIDE_BN.md)

---

## 💎 Commercial Benefits
*   **90% Reduction in Support Cost:** No need for night-shift operators.
*   **Increased Conversion Rate:** Instant responses lead to higher purchase confidence.
*   **Error-Free Data:** No more manual mistakes in address or quantity entry.

---

## 📞 Business Inquiries
**Rayyan Quantum Labs**  
*The Pioneers of Agentic AI in Bangladesh.*  
📧 [support@rayyanqlabs.com](mailto:support@rayyanqlabs.com)  
🌐 [www.rayyanqlabs.com](http://www.rayyanqlabs.com)  

---
© 2026 Rayyan Quantum Labs. All rights reserved.
