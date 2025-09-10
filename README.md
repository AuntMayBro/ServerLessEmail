# 📧 Serverless Email Sender (AWS Lambda + Python)

This project is a **serverless email sending service** built using the **Serverless Framework**, **AWS Lambda**, and **Python 3.12**.  
It allows you to send emails via Gmail SMTP by making an HTTP POST request to an AWS API Gateway endpoint.  

---

## 🚀 Features
- Send emails through a secure **SMTP (Gmail)** connection.
- Serverless deployment with **AWS Lambda**.
- Credentials managed securely using a `.env` file.
- Local development support with **serverless-offline**.

---

## ⚙️ Setup

### 1. Clone Repository
```bash
git clone <your-repo-url>
cd sendEmail
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Create `.env` File
Add your Gmail credentials to a `.env` file:
```dotenv
EMAIL=your-email@gmail.com
EMAIL_PASSWORD=your-app-password
```

⚠️ For Gmail, you must use an **App Password** (not your normal Gmail password).  
Generate one from your Google Account → **Security → App Passwords**.

---

## 🏃 Run Locally
You can test locally using `serverless-offline`:
```bash
sls offline
```

---

## ☁️ Deployed Endpoint
The API is deployed on AWS and can be tested here:

**POST**  
```
https://brfgz8pb99.execute-api.us-east-1.amazonaws.com/dev/send-email
```

### Headers
```
Content-Type: application/json
```

### Request Body
```json
{
  "receiver_email": "bagriaditya00@gmail.com",
  "subject": "Hello from Serverless!",
  "body_text": "This is a test email."
}
```

---

## 📬 Test the Email
You can test the email sending using **Postman** or **cURL**.

### Example: Using cURL
```bash
curl -X POST "https://brfgz8pb99.execute-api.us-east-1.amazonaws.com/dev/send-email" \
  -H "Content-Type: application/json" \
  -d '{
    "receiver_email": "bagriaditya00@gmail.com",
    "subject": "Hello from Serverless!",
    "body_text": "This is a test email."
  }'
```

If successful, the receiver will get the email in their inbox.

---

## 🛠️ Tech Stack
- **AWS Lambda**
- **API Gateway**
- **Serverless Framework**
- **Python (smtplib, email.mime)**
- **Gmail SMTP**

---

## 📖 License
MIT License – feel free to use, modify, and share.
