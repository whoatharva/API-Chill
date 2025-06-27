# API-Chill

This project walks you through building and deploying a custom AI chatbot using your own data, powered by Azure AI Foundry, and hosted via *Azure Web Apps. It also includes **Google Authentication* integration for secure access.

---

## 📦 Project Overview

* Platform: Azure AI Foundry
* Frontend Hosting: Azure Web App (App Services)
* Data Storage: Azure Blob Storage
* Search Engine: Azure AI Search (Semantic Search)
* Authentication: Google OAuth + Microsoft Entra ID (optional)
* Optional: Azure Cosmos DB for chat history storage

---

## 🚀 Getting Started

### 1. Set Up Azure Environment

Make sure you have an [Azure account](https://portal.azure.com) and access to the following services:

* Azure AI Studio
* Azure Blob Storage
* Azure AI Search
* Azure Web App (App Services)
* Azure Cosmos DB (if you want chat history)

---

### 2. Create a Copilot in Azure AI Foundry

1. Go to [https://ai.azure.com](https://ai.azure.com)
2. Click "Create a Copilot"
3. Choose a model (GPT-4 or GPT-3.5)
4. Configure:

   * Token rate
   * Filters
   * Safety messages (optional)
5. Open it in the Playground to start testing prompts

---

### 3. Add Your Own Data

1. Click “Add Data Source”
2. Upload documents (PDF, DOCX, etc.)
3. Choose:

   * Subscription
   * Create and select a Blob Storage account
   * Create and configure AI Search resource
4. Set:

   * Search type: Semantic
   * Chunk size: 1536
   * Data connection type: API Key
5. Save and close

> ✅ Tip: Make sure your documents are clean and well-formatted for best results.

---

### 4. Test in Playground

* Interact with the model using your uploaded data
* Validate the results and tweak prompts or documents as needed

---

### 5. Deploy as Web App

1. Click Deploy > Deploy as Web App
2. Fill in:

   * App name
   * Subscription & Resource Group
   * Location
   * Pricing plan
   * ✅ Enable chat history (stores in Cosmos DB)
3. Deploy and wait for the setup to complete

---

### 6. Configure Web App Authentication (with Google)

1. Go to Azure Portal → App Services → Your App → Authentication
2. Click “Add Identity Provider”
3. Choose Google
4. In a new tab, visit [Google Cloud OAuth Credentials](https://console.cloud.google.com/apis/credentials)
5. Create a new OAuth 2.0 Client ID

   * Application type: Web Application
   * Name: Anything (e.g., My Azure Chatbot)
   * Under Authorized redirect URIs, add:

     https\://<your-app-name>.azurewebsites.net/.auth/login/google/callback

     ✅ Example: [https://apichill01.azurewebsites.net/.auth/login/google/callback](https://apichill01.azurewebsites.net/.auth/login/google/callback)
6. Once created, copy the Client ID and Client Secret
7. Return to Azure → Authentication → Google
8. Paste the credentials and Save
9. Wait a minute or two for propagation

> ⚠ The redirect URI must match exactly — no trailing slashes, no spaces, no missing segments.

---

### 7. Launch & Use Your Chatbot

* Visit: https\://<your-app-name>.azurewebsites.net
* Authenticate with Google login
* Start chatting with your AI, grounded in your custom data 🎯

---

## 🔐 Optional Enhancements

| Feature           | Benefit                      |
| ----------------- | ---------------------------- |
| Cosmos DB       | Stores chat history          |
| Azure Key Vault | Secure API keys/secrets      |
| Custom Domain   | Personal branding            |
| Monitoring      | Add App Insights for metrics |

---

## 🧠 Tech Stack

* Azure AI Foundry – Copilot and data-grounded chat
* Azure Blob Storage – Document storage
* Azure AI Search – Semantic document search
* Azure Web Apps – Frontend hosting
* Azure Cosmos DB – Chat log storage (optional)
* Google OAuth – User authentication

---

## 🧪 Testing Tips

* ✅ Test in the Foundry Playground before deploying
* ✅ Ensure file format and structure are clean (PDFs with selectable text work best)
* ✅ Wait 1–2 minutes after OAuth config for the app to reflect changes

---

## 🎮 Bonus: Build Your Own Toy AI Project (Hosted by Vishvam Moliya)

While the above guide is for building a full-fledged Copilot using Azure AI Foundry, the second half of the *API & Chill* session is about creativity and fun with just HTML + JS + Azure OpenAI APIs.

You’ll learn how to:

* Call Azure OpenAI API with plain JavaScript
* Build quirky interactive UIs using Tailwind CSS
* Use creative prompts to make toy apps like MoodMate, GPT Pickup Line Generator, Startup Roaster, and Prompt Playground

🎯 *Live Demo:* [https://toys.vishvam.dev](https://toys.vishvam.dev)
💻 *Code Repository:* [https://github.com/0xvish/mlsa-api-and-chill](https://github.com/0xvish/mlsa-api-and-chill)

> ✨ This section of the session will be hosted by *Vishvam Moliya*, Co-Lead at MLSA LDCE.

---

## 📄 License

This project is licensed for educational and non-commercial use. Please ensure any use of third-party models or APIs complies with their respective licenses.

---

## ✨ Credits

Built with 💙 using Azure AI technologies and a passion for meaningful AI experiences.

Led by [Atharva Chitre](https://github.com/whoatharva) (Lead, MLSA LDCE) and [Vishvam Moliya](https://vishvam.dev/) (Co-Lead, MLSA LDCE)
