Here's a detailed **Product Requirements Document (PRD)** for the **Coffee Kiosk** React-based web application:

---

# ☕ Coffee Kiosk — Product Requirements Document (PRD)

## 1. Overview
**Coffee Kiosk** is a lightweight React-based web application that allows users to browse and purchase coffee using Safaricom M-PESA STK Push. Designed for simplicity and speed, it provides a seamless payment experience directly from a modal interface triggered within the app.

---

## 2. Goals and Objectives
- Provide a user-friendly platform for purchasing coffee with mobile payments.
- Simplify M-PESA integration for fast, secure checkouts.
- Create a responsive and visually appealing UI accessible on all devices.
- Ensure reliable phone number validation and error handling to minimize failed transactions.

---

## 3. Core Features
- **Product Display**: Visual grid showcasing coffee products with:
  - Name
  - Price (KES)
  - High-quality image
- **Payment Modal**:
  - Triggered on clicking “Buy with M-PESA”
  - Input for Safaricom phone number
  - Submit button to initiate payment
- **M-PESA Integration**:
  - STK Push triggered via POST to backend `/pay` endpoint
  - Utilizes Safaricom sandbox credentials
- **Phone Number Validation**:
  - Accepts: `07XXXXXXXX`, `+2547XXXXXXXX`, or `2547XXXXXXXX`
  - Non-conforming numbers are rejected with feedback
- **Responsive UI**:
  - Includes: header, nav, product grid, modal, and footer
  - Tailored for mobile and desktop experiences

---

## 4. User Flow
1. User lands on homepage and sees a grid of coffee products.
2. User clicks **Buy with M-PESA** on a product.
3. Modal opens prompting user to enter their Safaricom number.
4. Upon submission:
   - Validates phone number
   - Initiates STK Push via backend API
5. User receives push prompt on their phone
6. Payment completes and success message is shown (or error if declined)

---

## 5. Technical Stack
- **Frontend**:
  - React.js
  - Tailwind CSS for styling
  - Axios for HTTP requests
- **Backend**:
  - Node.js with Express (running on `localhost:3000`)
  - Custom `/pay` endpoint handles M-PESA STK Push
- **M-PESA Integration**:
  - OAuth token middleware
  - Sandbox credentials configured via `.env`

---

## 6. API Interaction
- **Endpoint**: `POST http://localhost:3000/pay`
- **Payload**:
  ```json
  {
    "phone": "07XXXXXXXX",
    "amount": 50
  }
  ```
- **Response**:
  - On success: Show alert or message that STK Push has been initiated
  - On failure: Display error message to user

---

## 7. Validation & Error Handling
- **Phone Number Validation**:
  - RegEx-based check before submission
- **Errors Managed**:
  - Frontend alerts for invalid format
  - Try-catch around Axios request
  - Graceful fallback if backend is unavailable or returns an error

---

## 8. UI/UX Requirements
- **Design**:
  - Clean and modern, with ample spacing and intuitive layout
- **Modal**:
  - Centered with fade-in animation
  - Dismissible by clicking outside or close icon
- **Loading Indicator**:
  - Spinner or progress bar shown during API call
- **Color Scheme**:
  - **Green** (`#10B981`): primary CTA (Buy with M-PESA)
  - **Gray** (`#D1D5DB`): neutral text and borders

---

## 9. Assumptions & Constraints
- Backend service must be live at `localhost:3000` and correctly configured for the M-PESA sandbox.
- Only Kenyan phone numbers are supported.
- Product prices are fixed and defined in the frontend.
- No user login or cart functionality — each transaction is one-off and immediate.
