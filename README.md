# trustpadtrustpad-app/
├── public/
│   └── index.html
├── src/
│   ├── admin/
│   │   ├── AdminLogin.js
│   │   └── AdminDashboard.js
│   ├── user/
│   │   └── CreateRoom.js
│   ├── firebase-config.js
│   ├── App.js
│   └── index.js
├── package.json
└── tailwind.config.js
{
  "name": "trustpad-app",
  "version": "1.0.0",
  "private": true,
  "dependencies": {
    "firebase": "^9.0.0",
    "react": "^18.0.0",
    "react-dom": "^18.0.0",
    "react-router-dom": "^6.0.0"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build"
  }
}
module.exports = {
  content: ["./src/**/*.{js,jsx}", "./public/index.html"],
  theme: { extend: {} },
  plugins: []
};
import { initializeApp } from "firebase/app";
import { getAuth } from "firebase/auth";
import { getFirestore } from "firebase/firestore";

const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT_ID.appspot.com",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID"
};

const app = initializeApp(firebaseConfig);
export const auth = getAuth(app);
export const db = getFirestore(app);
import { useState } from "react";
import { auth } from "../firebase-config";
import {
  signInWithEmailAndPassword,
  RecaptchaVerifier,
  signInWithPhoneNumber
} from "firebase/auth";
import { Button } from "../components/ui/button";
import { Input } from "../components/ui/input";

export default function AdminLogin() { /* ... as above ... */ }
import { useState, useEffect } from "react";
import { auth, db } from "../firebase-config";
import { collection, query, onSnapshot } from "firebase/firestore";
import { Button } from "../components/ui/button";
import { Table, TableRow, TableCell } from "../components/ui/table";

export default function AdminDashboard() { /* ... as above ... */ }
import { useState } from "react";
import { db } from "../firebase-config";
import { collection, addDoc, serverTimestamp } from "firebase/firestore";
import { Input } from "../components/ui/input";
import { Button } from "../components/ui/button";

export default function CreateRoom() { /* ... as above ... */ }
import { BrowserRouter, Routes, Route } from "react-router-dom";
import AdminLogin from "./admin/AdminLogin";
import AdminDashboard from "./admin/AdminDashboard";
import CreateRoom from "./user/CreateRoom";

export default function App() { /* ... as above ... */ }
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";
import "./index.css"; // with Tailwind

ReactDOM.render(<App />, document.getElementById("root"));
