# Coffee and Code At the Technical University Of Kenya

# 🧾 Product Requirements Prompt

Use the following prompt to generate a **Product Requirements Document (PRD)** for this project:

---

```
## 📌 Prompt for Backend

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
### Prompt for Frontend
```
Generate a detailed Product Requirements Document (PRD) for a React-based web application called **Coffee Kiosk** that enables users to purchase coffee using Safaricom M-PESA STK Push. The app features a simple UI for displaying coffee products and a modal payment form triggered on "Buy with M-PESA."

The PRD should include the following sections:

---

### 1. 📌 Overview
Provide a brief description of the app and its purpose.

### 2. 🎯 Goals and Objectives
Describe what this app aims to achieve.

### 3. ✨ Core Features
- Display coffee products with image, name, and price.
- Modal form to input Safaricom phone number.
- M-PESA STK Push payment triggered via API call to backend.
- Phone number validation (accepts 07XXXXXXXX, +2547XXXXXXXX, 2547XXXXXXXX formats).
- Responsive UI with header, navigation, product grid, and footer.

### 4. 🔄 User Flow
Explain the flow from selecting a product to completing a payment.

### 5. ⚙️ Technical Stack
- **Frontend:** React, Tailwind CSS
- **Backend:** Node.js (running on `localhost:3000`) with `/pay` endpoint
- **Networking:** Axios for HTTP requests

### 6. 🔌 API Interaction
- Endpoint: `POST /pay`
- Payload: `{ phone: string, amount: number }`
- Expected behavior: STK Push triggered and confirmation alert shown to user.

### 7. ❗ Validation & Error Handling
- Validate phone number input format.
- Display alerts for invalid input.
- Use try-catch blocks to catch and display API errors with friendly messages.

### 8. 🎨 UI/UX Requirements
- Clean and minimal interface.
- Modal popup for entering phone number.
- Loading indicator during API call.
- Consistent color theme (green for actions, gray for neutral elements).

### 9. 📌 Assumptions & Constraints
- Backend must be running and properly configured for M-PESA sandbox.
- Only Kenyan Safaricom numbers are supported.
- Product pricing is static and defined client-side.

```
Paste this prompt into your preferred AI writing tool to generate a comprehensive PRD tailored to this service architecture.
