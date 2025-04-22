# ☕ Coffee Kiosk

A modern web application for ordering coffee and making payments via M-Pesa.

## 🚀 Features

- **🛍️ Shopping Experience**
  - Browse coffee products with images and descriptions
  - Responsive design for all devices

- **💸 Payment Integration**
  - M-Pesa STK Push integration
  - Phone number validation
  - Real-time payment status updates
  - Secure transaction handling

- **🎨 Modern UI**
  - Clean, minimalist design
  - Smooth animations and transitions
  - Custom cursor effects
  - Warm, coffee-inspired color scheme

## 🛠️ Tech Stack

- **Frontend**
  - React.js
  - Tailwind CSS

- **Backend**
  - Node.js
  - Express.js
  - M-Pesa Daraja API

### environment variables:
```bash
# Backend (.env)
MPESA_CONSUMER_KEY=your_consumer_key
MPESA_CONSUMER_SECRET=your_consumer_secret
MPESA_PASSKEY=your_passkey
MPESA_SHORTCODE=your_shortcode
```

4. Start the development servers:
```bash
# Start backend server
cd backend
npm run dev

# Start frontend server
cd ../frontend
npm run dev
```

## 🌐 API Endpoints

- `POST /pay` - Initiate M-Pesa payment
  - Request body: `{ phone: string, amount: number }`
  - Response: Payment status and transaction details

## 🎯 Project Structure

```
kenyan-coffee-kiosk/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── routes/
│   │   ├── services/
│   │   └── utils/
│   ├── .env
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── public/
│   └── package.json
└── README.md
```

## 🔒 Security Considerations

- Phone number validation (254 prefix)
- Secure API key storage
- Input sanitization
- Error handling and logging

## 🎨 UI Components

- **Navigation Bar**
  - Logo and brand name
  - Navigation links
  - Cart counter
  - Login button

- **Hero Section**
  - Welcome message
  - Call-to-action buttons

- **Product Cards**
  - Product image
  - Name and description
  - Price with discount support
  - Add to cart button

- **Cart Modal**
  - Item list with quantity controls
  - Total price calculation
  - M-Pesa payment form
