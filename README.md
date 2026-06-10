# 🛺 SwiftRide — AI-Powered Ride Hailing App

> *Ride Smart. Arrive Faster.* — Built with React, ML fare prediction, GPay/Paytm integration & full dark/light mode.

---

## 📁 Project Structure

```
swiftride/
├── public/
│   └── index.html
├── src/
│   ├── context/
│   │   ├── ThemeContext.js      ← Dark/Light mode
│   │   └── AuthContext.js       ← User login/register
│   ├── components/
│   │   ├── Navbar.js            ← Navigation + avatar menu
│   │   ├── RideMap.js           ← Leaflet live map
│   │   └── ProtectedRoute.js    ← Auth guard
│   ├── pages/
│   │   ├── Landing.js           ← Hero + features
│   │   ├── Login.js             ← Sign in
│   │   ├── Register.js          ← Create account
│   │   ├── Dashboard.js         ← User home
│   │   ├── BookRide.js          ← Full booking flow + payment
│   │   ├── Analytics.js         ← ML insights + charts
│   │   ├── History.js           ← Ride history
│   │   ├── Wallet.js            ← Add money + security
│   │   └── Profile.js           ← User settings
│   ├── ml/
│   │   └── mlService.js         ← Fare prediction, ETA, driver ranking
│   ├── services/
│   │   ├── rideService.js       ← Ride lifecycle, history
│   │   └── paymentService.js    ← Paytm/GPay, tokens, buffer
│   ├── App.js                   ← Routes
│   ├── index.js                 ← Entry point
│   └── index.css                ← Global styles + themes
└── package.json
```

---

## ⚡ Quick Start (Recommended: VS Code)

### Step 1 — Install Node.js
Download from: https://nodejs.org (choose LTS version)
Verify: open terminal and run `node -v`

### Step 2 — Open the project in VS Code
1. Open VS Code
2. File → Open Folder → select `swiftride/`
3. Open terminal: `Ctrl + `` ` (backtick)

### Step 3 — Install dependencies
```bash
npm install
```
Wait ~2-3 minutes for packages to install.

### Step 4 — Start the app
```bash
npm start
```
Browser opens automatically at **http://localhost:3000** 🎉

---

## 🖥️ CMD / Command Prompt Setup

```cmd
# Navigate to project
cd path\to\swiftride

# Install packages
npm install

# Start development server
npm start
```

---

## 🔑 Demo Login
After app starts, click **Sign In** and use:
- **Email:** `demo@swiftride.in`
- **Password:** anything (any text works)

---

## ✨ Features

### 🤖 ML / AI Features (mlService.js)
| Feature | Description |
|---------|-------------|
| **Fare Prediction** | Distance × base rate × surge multiplier × demand noise |
| **ETA Estimation** | Speed model with peak-hour traffic factors |
| **Driver Ranking** | Composite score: proximity (40%) + rating (35%) + acceptance (25%) |
| **Surge Detection** | Automatic 1.3–1.7× multiplier during 7–10 AM and 5–9 PM |
| **Demand Forecast** | Hourly bar chart with ML-predicted demand percentages |
| **Cancellation Risk** | Probability model based on distance, hour, driver rating |

### 💳 Payment Security (paymentService.js)
| Feature | Description |
|---------|-------------|
| **Token Encryption** | Base64 + reversal token with 10-min expiry |
| **Payment Buffer** | localStorage backup before payment; recovers on retry |
| **Duplicate Protection** | Clears buffer only on successful txn confirmation |
| **GPay / Paytm Sim** | UPI/wallet flow simulation with realistic delay |
| **95% Success Rate** | 5% simulated failure to test recovery flow |

### 🌗 Dark / Light Mode
- Toggled via sun/moon icon in navbar
- Persisted in `localStorage`
- Full purple gradient aesthetic in both modes
- CSS variables for seamless transition

---

## 🗺️ Map Integration

Uses **Leaflet** + **CartoDB tiles** (dark/light auto-switch):
- Pickup marker (purple dot)
- Drop marker (green dot)
- Dashed route polyline
- Driver markers with emoji icons
- Auto-fit bounds to show full route

**Note:** Map loads after booking a ride in the `/book` page.

---

## 🛡️ Security Highlights

1. **No raw passwords stored** — demo auth only (production would use JWT)
2. **Payment tokens expire** in 10 minutes
3. **Payment buffer recovery** — if browser crashes during payment, retrying completes the order
4. **Cancel anytime** — free before driver accepts; ₹15 fee if driver is arriving
5. **Masked UPI/card** display in UI (e.g., `ar***@upi`)

---

## 🎨 Design System

- **Fonts:** Syne (display/headings) + DM Sans (body)
- **Colors:** Purple gradient `#7c3aed` → `#6d28d9`
- **Dark bg:** `#0d0720` → `#1a0f3d`
- **Light bg:** `#f8f5ff` → `#ede9fe`
- **Animations:** fadeUp, pulse-glow, shimmer
- **Glass morphism:** backdrop-filter blur on cards

---

## 📱 Pages

| Route | Page | Auth Required |
|-------|------|---------------|
| `/` | Landing page with hero & features | No |
| `/login` | Sign in | No |
| `/register` | Create account | No |
| `/dashboard` | User home + quick book | ✅ Yes |
| `/book` | Full ride booking flow | ✅ Yes |
| `/analytics` | ML insights + demand chart | ✅ Yes |
| `/history` | Past rides | ✅ Yes |
| `/wallet` | Add money, payment methods | ✅ Yes |
| `/profile` | User settings, security | ✅ Yes |

---

## 🚀 Build for Production

```bash
npm run build
```
Outputs to `build/` folder — ready to deploy on Netlify, Vercel, or any static host.

---

## 💡 Tips

- Use demo login `demo@swiftride.in` to see pre-loaded profile
- Book a ride end-to-end: Dashboard → Book → Select locations → Choose vehicle → Confirm → Pay
- Toggle 🌙/☀️ in navbar to switch themes anytime
- Wallet starts at ₹500; add more via Wallet page

---

*Built with ❤️ using React, Leaflet, ML fare models & Paytm/GPay payment simulation.*
