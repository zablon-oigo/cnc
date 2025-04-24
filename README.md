# Coffee and Code At the Technical University Of Kenya

# 🧾 Product Requirements Prompt

Use the following prompt to generate a **Product Requirements Document (PRD)** for this project:

---

```
## 📌 Prompt

Create a detailed Product Requirements Document (PRD) for a minimalistic Node.js-based API service that integrates with the **Safaricom M-PESA STK Push** payment gateway in a **sandbox environment**.

### 🔒 Constraints
- All application logic must reside in a single `index.js` file.
- Dependencies and scripts must be defined exclusively in the `package.json` file.

### 🚀 Features to Include

1. **Token Generation Middleware**  
   Securely fetch and inject the OAuth access token required by the Safaricom API using basic authentication.

2. **Payment Endpoint (`/pay`)**  
   Accepts `POST` requests with `phone` and `amount`. Uses environment variables for credentials, constructs a timestamp and password, and initiates a payment request via M-PESA.

3. **Callback Handler (`/callback`)**  
   Handles M-PESA payment confirmations, logs relevant transaction data (Amount, PhoneNumber, MpesaReceiptNumber), and responds to the API.

4. **Environment Configuration**  
   Utilizes `dotenv` for managing credentials like `CONSUMER_KEY`, `SECRET`, `PAYBILL`, and `PASSKEY`.

5. **CORS and Express Middleware**  
   Configured to handle JSON and URL-encoded body data.

6. **Security & Error Handling**  
   Logs and gracefully handles failed token or payment requests.

---

### 🛠️ Technical Stack

- Node.js  
- Express  
- Axios  
- dotenv  
- cors  

---

### 📄 Output Requirements

- Overview of the application and its purpose
- Functional specifications of each endpoint
- Environment variables used and their role
- Description of the payment flow
- Key dependencies and required versions
- Example request/response for each endpoint
- Expected deployment and usage scenario (e.g., using Ngrok for callbacks in development)

---

```

Paste this prompt into your preferred AI writing tool to generate a comprehensive PRD tailored to this service architecture.
