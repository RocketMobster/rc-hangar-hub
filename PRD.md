# Product Requirements Document (PRD) – RC Hangar Hub

## 1. Overview

**App Name:** RC Hangar Hub  
**Target Audience:** Remote control (RC) hobbyists – airplane, drone, car, boat enthusiasts  
**Platform:** Mobile-first web app (React, Tailwind CSS, Firebase)  

RC Hangar Hub is an all-in-one garage and social app for RC hobbyists. It allows users to track their vehicles, log flight/run sessions, manage maintenance, and connect with other enthusiasts through events and shared build logs.

---

## 2. Goals

- Allow users to register/login with Firebase Authentication
- Let users add, edit, and manage their RC vehicles
- Log maintenance, battery cycles, and run/flight sessions
- View historical data in a searchable logbook
- Join and create meetups/events
- View other user builds and share updates in a community feed

---

## 3. Features

### Core MVP Features

- **Garage View**
  - Displays cards for each RC vehicle
  - Shows key stats: last run, battery cycles, model info
  - Button to add/edit vehicles

- **Flight Log / Run Tracker**
  - Log date, location, duration, notes, and vehicle used
  - Filter logs by vehicle/date

- **Vehicle Detail View**
  - View full specs, maintenance logs, images
  - Track battery usage and maintenance intervals

- **User Authentication**
  - Email/password login via Firebase
  - Persistent user-specific data

- **Bottom Navigation**
  - Garage | Logbook | Events | Community | Profile

### Optional Features

- **Event Calendar**
  - View or create public/private events
  - RSVP and comment
- **Community Feed**
  - Share build photos, updates, ask questions
  - Like, comment, and follow other users

- **Notifications**
  - Reminders for maintenance due
  - Event invites

---

## 4. Personas

**Tinker Tom** – Custom RC builder who wants to share mods and logs every test run  
**Weekend Warrior** – Casual flyer/driver logging flights and social meetups  
**Club Manager Carla** – Organizes community events, races, and gatherings  

---

## 5. UX/UI Design Principles

- Mobile-first, card-based layout  
- Large tap targets, clean navigation  
- Tag-based logbook filtering  
- Light and dark themes optional  
- Use vivid but minimal color palette (e.g., black, charcoal, red, accent yellow)

---

## 6. Tech Stack

- **Frontend**: React + Vite  
- **Styling**: Tailwind CSS  
- **Routing**: React Router  
- **State Management**: Zustand  
- **Forms**: React Hook Form + Zod  
- **Backend**: Firebase (Auth + Firestore + Storage)

---

## 7. Component Layout (React)

### Pages

- `GarageView`  
- `VehicleDetail`  
- `FlightLogList`  
- `EventList`  
- `CommunityFeed`  
- `UserProfile`  
- `SettingsPanel`

### Components

- `VehicleCard`  
- `AddVehicleModal`  
- `BottomNav`  
- `LogEntryCard`  
- `EventCard`  
- `PostCard`  
- `UserAvatar`  
- `NavTabs`  
- `MaintenanceReminder`

### Store

- `useGarageStore.js`  
- `useLogbookStore.js`  
- `useEventStore.js`  
- `useUserStore.js`

---

## 8. UI Wireframe Sketch (Text-Based)

### GarageView

[ + ] Add Vehicle

┌─────────────────────────────┐  
│ 🚁  DJI Mini 3 Pro          │  
│ Type: Drone                 │  
│ Battery Cycles: 14          │  
│ Last Flight: 07/10/2025     │  
└─────────────────────────────┘

┌─────────────────────────────┐  
│ 🚗  Traxxas Rustler         │  
│ Type: RC Car                │  
│ Battery Cycles: 22          │  
│ Last Run: 07/02/2025        │  
└─────────────────────────────┘

[ Bottom Nav: Garage | Logbook | Events | Community | Profile ]

---

## 9. Vibe Coding Section

### Summary Prompt (Use in Copilot)

"Create a responsive GarageView component in React. It should use Zustand for state management, Tailwind CSS for styling, and display a list of RC vehicles as cards with vehicle image, name, type, last activity date, and battery cycle count. Include a floating action button for adding new vehicles. Use React Router for navigation and ensure mobile-friendly layout. Modularize components."

### Component Layout (Repeat)

See Section 7 above

### Text-Based UI Wireframe

See Section 8 above

---

## 10. Timeline / Roadmap (Optional)

- Week 1: Scaffold GarageView, setup Zustand/Firebase/Auth  
- Week 2: Add Vehicle Detail view, logbook logging  
- Week 3: Add Event and Community views  
- Week 4: Polish UI, test, and deploy MVP

---

## 11. Future Expansion

- GPS integration (log flight paths)  
- Real-time chat or DMs  
- Parts inventory tracking  
- Battery management module  
- Offline mode with sync
