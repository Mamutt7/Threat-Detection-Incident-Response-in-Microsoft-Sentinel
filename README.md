# 🔐 Azure Security Operations: Threat Detection & Incident Response Using Microsoft Sentinel  

## 📌 Project Overview  
This project simulates a **real-world Security Operations Center (SOC) workflow** using **Microsoft Defender** and **Microsoft Sentinel** in Azure. You’ll learn to:  
- **Set up Microsoft Sentinel** to collect and analyze security logs.  
- **Connect Microsoft Defender to Sentinel** for centralized monitoring.  
- **Simulate security threats** to generate alerts.  
- **Analyze incidents and respond** like a cybersecurity analyst.  

🔹 **Why This Project?**  
- Hands-on experience with **Azure Sentinel (SIEM)**, a widely used security tool.  
- Demonstrates **threat detection, investigation, and response skills** relevant to SOC roles.  
- **Beginner-friendly** with step-by-step instructions and insights.  

---

## **🛠️ Step 1: Set Up Microsoft Sentinel**  
### **1️⃣ Log in to Azure**  
1. Go to **[Azure Portal](https://portal.azure.com)** and log in.  
2. Click on **☰ Menu** (top left) → **Microsoft Sentinel**.  

### **2️⃣ Create a Log Analytics Workspace (Required for Sentinel)**  
1. Click **"Create Microsoft Sentinel"**.  
2. Click **"Create a new Log Analytics workspace"**.  
3. **Fill in the details**:  
   - **Subscription**: Select your active Azure subscription.  
   - **Resource Group**: Click **"Create new"**, name it `Sentinel-RG`.  
   - **Workspace Name**: Enter `SOC-Workspace`.  
   - **Region**: Choose the closest one to you.  
   - Click **"Review + Create" → "Create"**.  

### **3️⃣ Enable Microsoft Sentinel**  
1. Once the **Log Analytics Workspace** is created, return to **Microsoft Sentinel**.  
2. Click **"Add"** → Select the `SOC-Workspace`.  
3. Click **"Add Microsoft Sentinel"** to activate it.  

### 📸 **Screenshot Point:**  
> *Take a screenshot of the Microsoft Sentinel homepage with your workspace visible.*

---

## **🛠️ Step 2: Connect Microsoft Defender to Sentinel**  
### **1️⃣ Enable Microsoft Defender**  
1. In **Azure Portal**, go to **Microsoft Defender for Cloud**.  
2. Click **"Environment settings"** → Select your **Subscription**.  
3. Click **"Enable Microsoft Defender for Cloud"**.  

### **2️⃣ Connect Defender to Sentinel**  
1. Return to **Microsoft Sentinel**.  
2. Click **"Data connectors"** (left panel).  
3. Search for **Microsoft Defender** → Click **"Open Connector Page"**.  
4. Click **"Connect"** to integrate Defender logs with Sentinel.  

### 📸 **Screenshot Point:**  
> *Take a screenshot of the Microsoft Sentinel Data Connectors page showing Defender connected.*

---

## **🛠️ Step 3: Simulate Security Threats**  
We’ll generate security events for Sentinel to detect.  

### **1️⃣ Simulate Failed Login Attempts**  
1. Open **PowerShell as Administrator**.  
2. Run the following command to create **failed login attempts**:
   ```powershell
   for ($i=1; $i -le 5; $i++) { 
       net use \\127.0.0.1\IPC$ /user:fakeuser wrongpassword 
   }
