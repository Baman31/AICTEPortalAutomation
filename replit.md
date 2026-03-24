# AICTE Approval System - Portal Automation

## Overview
A comprehensive portal automation system that digitizes and automates the document verification process for AICTE (All India Council for Technical Education) institutional approvals. Uses AI, OCR, and a multi-platform architecture to replace manual validation.

## Architecture

### Services
- **InstituteFrontend** (port 5000) - React.js portal for educational institutes to register, submit documents and track applications
- **admin** - React.js dashboard for AICTE administrators to review applications and manage workflow
- **backend** (port 3000) - Node.js/Express server with MongoDB (Mongoose), handles business logic and API
- **api** - Python/FastAPI service for AI/OCR tasks (Tesseract, Google Cloud Vision, LangChain, Groq, FAISS)
- **mobile** - Expo React Native app for mobile access

### Key Technologies
- **Frontend:** React.js (Create React App), framer-motion, recharts, react-router-dom v7
- **Backend:** Node.js, Express, MongoDB/Mongoose, bcryptjs, AWS S3 for document storage
- **AI/ML:** Python FastAPI, Tesseract OCR, Google Generative AI (Gemini), LangChain, FAISS
- **Mobile:** React Native with Expo

## Workflows
- **Start application**: `cd InstituteFrontend && PORT=5000 HOST=0.0.0.0 DANGEROUSLY_DISABLE_HOST_CHECK=true npm start`
- **Backend Server**: `cd backend && PORT=3000 node server.js`

## Port Configuration
- InstituteFrontend runs on port 5000 (main webview)
- Backend API runs on port 3000
- Python AI API runs on port 8000 (via Docker in original setup)

## User Roles
1. **Institutes:** Submit applications, upload documents, track status
2. **Admins (Scrutiny/Expert Visit/Executive):** Review, verify and approve documents
3. **Super Admin:** Oversee all committees with charts and statistics
4. **Mobile Users:** Track applications on the go

## Environment Variables
The backend uses:
- `MONGO_URI` - MongoDB Atlas connection string (defaults to hardcoded Atlas URL)
- `AWSID` - AWS S3 Access Key ID
- `AWSKEY` - AWS S3 Secret Access Key

## Notes
- All merge conflicts from git history have been resolved (HEAD/feature branch versions retained where richer)
- Frontend API calls use `http://localhost:3000` to reach the backend
- `InstituteFrontend/package.json` has proxy set to `http://localhost:3000`
- MongoDB connection requires network access to Atlas cluster
