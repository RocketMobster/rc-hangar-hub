# 🚀 RC Hangar Hub

**Build. Fly. Log. Repeat.**  
A mobile-first app for RC hobbyists to track vehicles, log flights, plan events, and share builds with the community.

---

## 📦 Tech Stack

- **React + Vite** – Fast, modern frontend framework  
- **Tailwind CSS** – Utility-first styling for clean UI  
- **Zustand** – Lightweight state management  
- **Firebase** – Authentication, Firestore database, storage  
- **React Router** – Client-side routing  
- **React Hook Form + Zod** – Form handling and validation  
- **Shadcn/UI** *(optional)* – Headless UI primitives

---

## 🚀 Getting Started (Vibe Coding Style)

### 1. Clone + Install

Clone the repository and install dependencies:

git clone https://github.com/your-username/rc-hangar-hub.git  
cd rc-hangar-hub  
npm install

### 2. Start the Dev Server

Run the following to launch Vite:

npm run dev

The development server will start at http://localhost:5173.

### 3. Kickstart the Garage View (Vibe Coding Prompt)

Create a file at `src/pages/GarageView.jsx`. Use your code assistant (like Copilot or ChatGPT) to scaffold a view that:

- Displays a list of RC vehicles as cards  
- Each card includes: thumbnail image, vehicle name, type (e.g., drone, car), battery cycles, and last flight/run date  
- Uses Zustand for local state  
- Includes a floating action button to add a new vehicle  
- Styles the page with Tailwind CSS  

This is your MVP's core screen — start here and build outward.

### 4. Suggested Folder Structure

Organize your app with this layout:

src/  
├── components/  
│   ├── VehicleCard.jsx  
│   ├── AddVehicleModal.jsx  
│   ├── BottomNav.jsx  
├── pages/  
│   ├── GarageView.jsx  
│   ├── VehicleDetail.jsx  
├── store/  
│   └── useGarageStore.js  
├── lib/  
│   └── firebase.js  
├── App.jsx  
└── main.jsx

### 5. Firebase Setup

Create a `.env` file in the root directory and add your Firebase project values:

VITE_FIREBASE_API_KEY=your_key  
VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com  
VITE_FIREBASE_PROJECT_ID=your_project_id  
VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com  
VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id  
VITE_FIREBASE_APP_ID=your_app_id

Then in `src/lib/firebase.js`, initialize Firebase:

import { initializeApp } from "firebase/app";  
import { getFirestore } from "firebase/firestore";  
import { getAuth } from "firebase/auth";

const firebaseConfig = {
  apiKey: import.meta.env.VITE_FIREBASE_API_KEY,
  authDomain: import.meta.env.VITE_FIREBASE_AUTH_DOMAIN,
  projectId: import.meta.env.VITE_FIREBASE_PROJECT_ID,
  storageBucket: import.meta.env.VITE_FIREBASE_STORAGE_BUCKET,
  messagingSenderId: import.meta.env.VITE_FIREBASE_MESSAGING_SENDER_ID,
  appId: import.meta.env.VITE_FIREBASE_APP_ID,
};

const app = initializeApp(firebaseConfig);  
export const db = getFirestore(app);  
export const auth = getAuth(app);

---

## 🧱 Component Map

| Route         | Component         | Purpose                          |
|---------------|-------------------|----------------------------------|
| `/garage`     | `GarageView`      | Main dashboard for RC vehicles   |
| `/vehicle/:id`| `VehicleDetail`   | Detailed view of one vehicle     |
| `/logbook`    | `FlightLogList`   | Flight/run history and logging   |
| `/events`     | `EventList`       | Local events, races, meetups     |
| `/community`  | `CommunityFeed`   | Build logs, image sharing, chat  |
| `/profile`    | `UserProfile`     | User info, saved vehicles        |
| `/settings`   | `SettingsPanel`   | App preferences and Firebase auth|

---

## ✅ Vibe Coding Goals

- Scaffold pages and components using Copilot or ChatGPT  
- Manage global app state via Zustand  
- Use Tailwind CSS for consistent, responsive layout  
- Integrate Firebase authentication and Firestore for data  
- Use modular UI: reusable cards, tabs, modals, and bottom nav  
- Prioritize a working GarageView first, then expand to logs/events  

---

## 🧪 Testing Strategy

Start with basic manual testing:

- Add RC vehicle  
- View and edit vehicle details  
- Log flights  
- Switch tabs (Garage, Logbook, Events)

When ready, scale up to:

- `react-testing-library` for interaction tests  
- `vitest` for component and state testing  
- Firebase emulator suite for simulating backend

---

## 📎 Helpful Resources

- [Tailwind CSS Docs](https://tailwindcss.com/docs)  
- [Zustand Docs](https://docs.pmnd.rs/zustand)  
- [Firebase Docs](https://firebase.google.com/docs)  
- [React Hook Form](https://react-hook-form.com)  
- [Shadcn UI](https://ui.shadcn.com/)

---

**💡 Tip:** Start with `GarageView`, wire it up with Zustand + Tailwind, and expand with confidence — vibe code the platform you’d want as an RC hobbyist.
