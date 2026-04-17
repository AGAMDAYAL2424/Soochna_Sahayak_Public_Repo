# Soochna_Sahayak_Public_Repo
# 🚔 Soochna Sahayak: Smart FIR & Transcription Ecosystem

[![Powered By Bhashini](https://img.shields.io/badge/Powered%20By-Bhashini-blue)](https://bhashini.gov.in/)
[![iOS](https://img.shields.io/badge/Platform-iOS%2018.4%2B-black?logo=apple)](https://developer.apple.com/ios/)
[![Backend](https://img.shields.io/badge/Backend-Spring%20Boot%20%7C%20Node.js-green)](#tech-stack)
[![Ecosystem](https://img.shields.io/badge/Ecosystem-Mobile%20%2B%20Web%20%2B%20API-orange)](#system-architecture)

**Soochna Sahayak** (सूचना सहायक - *Information Assistant*) is a state-of-the-art multi-platform solution designed for Indian law enforcement. It streamlines field documentation through AI-powered transcription, automated FIR generation, and a centralized management dashboard.

---

## 🌐 The Ecosystem

The Soochna Sahayak platform consists of three integrated components working in harmony:

1.  **📱 Mobile Application (iOS)**: A high-performance field tool for officers to record, transcribe, and draft FIRs in real-time using Bhashini AI.
2.  **🖥️ Central Web Dashboard (The Hub)**: A centralized command center for station heads to review cases, manage evidence vault, and analyze crime statistics.
3.  **🔐 Secure Auth Service**: A robust Java Spring Boot backend ensuring professional-grade authentication and secure access control.

---

## 📱 Mobile App (Field Operations)

Built for precision in the field, the iOS app transforms how officers document incidents.

### ✨ Highlights
- **12+ Indian Languages**: Native support for Hindi, Bengali, Tamil, Telugu, and more.
- **Hybrid Transcription**: Intelligent switching between **Bhashini (GOI)** and Apple Speech Recognition.
- **Smart FIR Generation**: Automated drafting using Named Entity Recognition (NER) to extract suspects, locations, and dates.
- **Offline Mode**: Record now in remote areas, transcribe later when connectivity returns.
- **Video Processing**: Extract and transcribe audio directly from evidence videos.

> [!TIP]
> Use the **Live Waveform** view for visual confirmation of recording quality in high-noise environments.

---

## 🖥️ Central Web Dashboard (The Hub)

The Hub acts as the brain of the operation, ingesting data from multiple field devices into a unified oversight interface.

### 🌟 Key Features
- **Unified Intake**: Dedicated API endpoints to ingest FIRs and transcriptions from external field apps.
- **Evidence Vault**: Secure storage for audio, video, and image evidence linked to specific cases.
- **Case Management**: Create, track, and update FIR statuses across the entire station.
- **Advanced Analytics**: Interactive visualizations of crime trends and station performance.
- **Vercel Cloud Ready**: Scaleable serverless architecture for high availability.

---

## 🛠️ Tech Stack

### Mobile Frontend
- **Language**: Swift 6 (SwiftUI)
- **Frameworks**: Speech, AVFoundation, Natural Language (NER), CoreData

### Web Hub & API
- **Frontend**: Vanilla JS, CSS3 (Modern Glassmorphism Design)
- **Server**: Node.js & Express.js (v4.x)
- **Deployment**: Vercel (Edge Functions & Blob Storage)

### Security Backend
- **Framework**: Java 17 (Spring Boot 3.2)
- **Security**: Spring Security + JWT (JJWT 0.12.5)
- **Database**: PostgreSQL (Production) / H2 (Development)

---

## 📡 External App Integration (API)

The Hub is designed as an **API-First** platform. Third-party field recording apps can push data using our standard REST API.

### **Endpoint: POST `/api/external/fir`**
Push a full FIR entry with optional transcription.
```json
{
  "complainant": "Officer Sharma",
  "phone": "9988776655",
  "incidentType": "Theft",
  "transcription": "Mobile phone snatched near Gateway of India..."
}
```

### **Endpoint: POST `/api/external/transcription`**
Push standalone witness statements or field recordings.
```json
{
  "caseId": "FIR-2025-00042",
  "transcription": "Witness reports seeing a black SUV at 11:30 PM.",
  "language": "hi"
}
```
*Note: Requires `x-api-key` header for authentication.*

---

## 🚀 Getting Started

### 1. Prerequisites
- **Mobile**: Xcode 16.0+, macOS Sonoma
- **Web**: Node.js v18+, MongoDB Atlas
- **Auth**: Java 17, Maven

### 2. Environment Setup
Create a `.env` for the Web Hub:
```env
BHASHINI_ULCA_API_KEY=your_key
MONGODB_URI=your_mongodb_connection
API_KEY=your_hub_secret_key
```

### 3. Installation
**Web Hub:**
```bash
npm install
npm run dev
```

**Auth Service:**
```bash
cd soochna-sahayak-backend
mvn spring-boot:run
```

---

## 🛡️ Security & Privacy
- **AES-256 Encryption**: All evidence stored in the vault is encrypted at rest.
- **JWT Authentication**: Secure stateless authentication for all cross-platform interactions.
- **Compliance**: Adheres to the Digital India platform guidelines and Indian Evidence Act standards.

---

## 👨‍💻 Development Team
- **Agam Dayal**
- **Avani Sehgal**
- **Aryaman Sharma**
- **Rajani Kant Jha**

---
© 2026 Soochna Sahayak - *Modernizing Public Safety through Intelligent Documentation.*
