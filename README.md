# 🛡️ Aegis-OS: Industrial Intelligence HUD

> **Google AI Challenge Submission** - Multi-Modal AI Portfolio  
> Powered by Gemini 2.5-Flash

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Vercel-black?style=for-the-badge&logo=vercel)](https://agent-command-center-xi.vercel.app)
[![Google AI](https://img.shields.io/badge/Google%20AI-Gemini%202.5--Flash-blue?style=for-the-badge&logo=google)](https://ai.google.dev)
[![Next.js](https://img.shields.io/badge/Next.js-15-black?style=for-the-badge&logo=next.js)](https://nextjs.org)

### 🛠️ Tech Stack

![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)
![Cloud Run](https://img.shields.io/badge/Cloud_Run-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
![Gemini AI](https://img.shields.io/badge/Gemini_AI-8E75B2?style=for-the-badge&logo=google&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)


## 🎯 Overview

Aegis-OS is an industrial-grade command center that transforms static engineering documentation into interactive AI intelligence. Built for high-stakes operational environments like refineries, power plants, and manufacturing facilities.

**Live Demo**: [https://agent-command-center-xi.vercel.app](https://agent-command-center-xi.vercel.app)

## ✨ Features

### 1. 📊 P&ID Diagram Analysis (Vision AI)
Upload engineering blueprints and receive instant:
- Component identification (valves, sensors, pumps)
- Flow logic analysis
- Risk assessment and safety recommendations

### 2. 📚 Ask The Manual (RAG AI)
RAG-powered search through thousands of pages:
- Query equipment manuals in natural language
- Instant retrieval of relevant procedures
- Context-aware responses

### 3. 💬 24/7 Industrial Assistant
AI persona trained for industrial environments:
- Safety protocol guidance
- Best practice recommendations
- Operational support

## 🚀 Tech Stack

- **Frontend**: Next.js 15 (App Router) + TypeScript
- **Styling**: Tailwind CSS + Custom HUD Animations
- **AI Engine**: Google Gemini 2.5-Flash (Vision + RAG + Chat)
- **Deployment**: Docker + Google Cloud Run + Vercel
- **Architecture**: Dual-key API management with 5-tier retry logic

## 🎨 Industrial HUD Design

- **Tactical Borders**: Polygon-clipped frames mimicking physical hardware
- **Biometric Scanlines**: Continuous monitoring animations
- **Digital Grain**: SVG noise overlay for authentic industrial feel
- **RGB Glitch Effects**: Subtle interference on interaction

## 🏗️ Getting Started

### Prerequisites

- Node.js 20+ 
- npm or pnpm
- Google Gemini API key ([Get one here](https://ai.google.dev))

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/Tahir-yamin/aegis-os-challenge.git
cd aegis-os-challenge
```

2. **Install dependencies**
```bash
npm install
# or
pnpm install
```

3. **Set up environment variables**

Create a `.env.local` file in the root directory:

```env
NEXT_PUBLIC_GEMINI_API_KEY=your_gemini_api_key_here
NEXT_PUBLIC_RAG_API_KEY=your_rag_api_key_here
```

> **Note**: Never commit your `.env.local` file. It's already in `.gitignore`.

4. **Run the development server**
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## 🐳 Docker Deployment

### Build the Docker image

```bash
docker build -t aegis-os .
```

### Run the container

```bash
docker run -p 8080:8080 \
  -e NEXT_PUBLIC_GEMINI_API_KEY=your_key \
  -e NEXT_PUBLIC_RAG_API_KEY=your_key \
  aegis-os
```

## ☁️ Cloud Run Deployment

### Prerequisites
- Google Cloud SDK installed
- Cloud Run, Cloud Build, and Secret Manager APIs enabled

### Deploy

```bash
# Create secrets
echo -n "your_gemini_key" | gcloud secrets create GEMINI_API_KEY --data-file=-
echo -n "your_rag_key" | gcloud secrets create RAG_API_KEY --data-file=-

# Grant permissions
gcloud secrets add-iam-policy-binding GEMINI_API_KEY \
  --member="serviceAccount:PROJECT_NUMBER-compute@developer.gserviceaccount.com" \
  --role="roles/secretmanager.secretAccessor"

# Build and deploy
gcloud builds submit --tag gcr.io/PROJECT_ID/aegis-os

gcloud run deploy aegis-os \
  --image gcr.io/PROJECT_ID/aegis-os \
  --platform managed \
  --region us-east1 \
  --allow-unauthenticated \
  --port 8080 \
  --set-secrets="NEXT_PUBLIC_GEMINI_API_KEY=GEMINI_API_KEY:latest,NEXT_PUBLIC_RAG_API_KEY=RAG_API_KEY:latest" \
  --labels dev-tutorial=devnewyear2026
```

## 🔒 Security

- ✅ API keys stored in environment variables (never committed)
- ✅ Google Secret Manager integration for production
- ✅ `.env.local` in `.gitignore`
- ✅ No hardcoded credentials

## 🛠️ API Resilience

Built for 24/7 industrial uptime:

- **Dual-Key Architecture**: Separate keys for chat vs. resource-intensive operations
- **5-Tier Retry Logic**: Smart exponential backoff with daily vs. minute-limit detection
- **Error Recovery**: Graceful degradation and user feedback

## 📁 Project Structure

```
├── app/                    # Next.js App Router
│   ├── page.tsx           # Home page with HUD interface
│   └── api/               # API routes
├── components/            # React components
├── services/             # Gemini service layer
├── public/               # Static assets
├── Dockerfile            # Production container
└── tailwind.config.ts    # Styling configuration
```

## 🤝 Contributing

This is a challenge submission project, but feedback and suggestions are welcome!

## 📄 License

MIT License - see LICENSE file for details

## 👨‍💻 Author

**Tahir Yamin**
- GitHub: [@Tahir-yamin](https://github.com/Tahir-yamin)

## 🏆 Google AI Challenge

This project is a submission for the [New Year, New You Portfolio Challenge](https://dev.to/challenges/new-year-new-you-google-ai-2025-12-31) presented by Google AI.

**Challenge Requirements Met:**
- ✅ Deployed to Google Cloud Run
- ✅ Uses Gemini 2.5-Flash multimodal capabilities
- ✅ Production-ready with proper error handling
- ✅ Live demo available

---

**Built with ❤️ using Google Gemini AI**
