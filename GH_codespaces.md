# 🧪 Foundry Agents Workshop – Setup Guide for SHVE Participants

This guide walks you through all the necessary steps to prepare for the Agents Workshop using GitHub Codespaces and Azure AI.

---

## 👤 1. Create a GitHub Account

If you don’t already have one, sign up here with your personal account:  
🔗 https://github.com/join

---

## 💻 2. Launch GitHub Codespaces

1. Go to the workshop repo:  
   🔗 https://github.com/Heenanl/azure-ai-agents-labs  
2. Click the **`<> Code`** button.  
3. Select the **`Codespaces`** tab.  
4. Click **`Create codespace on main`**.

---

## 🔐 3. Authenticate with Azure CLI

Since you're using Codespaces via a personal GitHub account, via the terminal within codespaces run:

```bash
az login
```

Follow the browser prompt to authenticate with your SHVE Azure credentials.  
For subscription, choose **`alz-nl-hq-s-copilot-training`**


## 🧰 4. Install Azure CLI

Depending on your OS:

**Windows (via Winget):**
```powershell
winget install Microsoft.AzureCLI
```

**Linux (Debian-based):**
```bash
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```

� **Reference:** https://learn.microsoft.com/cli/azure/install-azure-cli

## 🐍 5. Set Up Python Virtual Environment

Inside your Codespace terminal:

```bash
python3 -m venv venv
```


## 📦 6. Install Dependencies

```bash
pip install -r ./requirements.txt
```

## 🔐 7. Rename Environment File

Rename the sample environment file to `.env`:

```bash
mv sample.env .env
```

## 🧠 8. Update .env with Azure AI Foundry Values

1. Navigate to https://ai.azure.com, locate the AI project and copy the project endpoint and key from **Overview**.

2. Update your `.env` file with the project details:

```bash
# Your AI Foundry Project endpoint, found in the Foundry Project Overview page
AIPROJECT_ENDPOINT="https://<your-ai-services-account-name>.services.ai.azure.com/api/projects/<your-project-name>"
API_KEY=<key>
```

3. Next, navigate to **Models + Endpoints** → Click on **gpt-4o deployment** → Copy **Target URI**.

4. Update your `.env` file with the chat model configuration:

```bash
# Your AI Foundry project chat model
CHAT_MODEL_ENDPOINT=https://<AI-services-name>.openai.azure.com/openai/deployments/<model-name>/chat/completions?api-version=<api-version>
CHAT_MODEL=gpt-4o
```

---

## 🧪 9. Test Your Environment

To verify that everything is set up correctly, open and run the **`Lab 0 - Environment Test.ipynb`** notebook.

This interactive notebook will:
- ✅ Check that all required packages are installed
- ✅ Verify your `.env` file configuration
- ✅ Test Azure authentication
- ✅ Validate connection to your AI Foundry project
- ✅ Send a test message to your deployed GPT-4o model

Simply open the notebook and run all cells. If everything passes, you're ready to start the workshop! 🎉

---

## ✅ Ready to Go!

You're now ready to begin the workshop labs! 🚀




