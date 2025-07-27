# Finpal – Your Personal Finance Assistant 💰

[![Next.js](https://img.shields.io/badge/Next.js-14-black?logo=next.js)](https://nextjs.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4-38B2AC?logo=tailwind-css)](https://tailwindcss.com/)
[![Firebase](https://img.shields.io/badge/Firebase-Authentication-FFCA28?logo=firebase)](https://firebase.google.com/)
[![Go](https://img.shields.io/badge/Go-1.23+-00ADD8?logo=go)](https://golang.org/)
[![Google ADK](https://img.shields.io/badge/Google_ADK-Agent_Framework-4285F4?logo=google)](https://ai.google.dev/)
[![Google Cloud](https://img.shields.io/badge/Google_Cloud-Platform-4285F4?logo=google-cloud)](https://cloud.google.com/)
[![Gemini AI](https://img.shields.io/badge/Gemini_AI-1.5_Flash_|_Pro-34A853?logo=google)](https://ai.google.dev/)
[![Vercel](https://img.shields.io/badge/Deployed_on-Vercel-000000?logo=vercel)](https://vercel.com)

Finpal is a modern personal finance assistant that combines cutting-edge AI technology with intuitive web interfaces to help you track, analyze, and manage your finances with ease. Built with a full-stack architecture featuring Next.js frontend and Go backend, powered by Google's advanced AI models.

## 🏗️ Architecture Overview

### Frontend Stack
- **Framework**: [Next.js 14](https://nextjs.org/) - React-based full-stack framework
- **Styling**: [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
- **Authentication**: [Firebase Authentication](https://firebase.google.com/docs/auth)
  - Google OAuth integration
  - Email/Password authentication
- **Deployment**: [Vercel](https://vercel.com) - Seamless deployment platform

### Backend & AI Agent
- **Backend Language**: Go 1.23+
- **AI Framework**: [Google ADK (Agent Developer Kit)](https://ai.google.dev/)
- **AI Models**: 
  - **Gemini 1.5 Flash** - Fast reasoning and quick responses
  - **Gemini 1.5 Pro** - Deep research and long-context processing
- **Data Integration**: [fi.money MCP Server](https://fi.money) via ADK MCPToolset
- **Cloud Infrastructure**:
  - [Firebase](https://firebase.google.com/) - Database and authentication
  - [Google Cloud Platform](https://cloud.google.com/) - Cloud services
  - [Cloud Speech-to-Text](https://cloud.google.com/speech-to-text) - Voice input processing

---

## 🚀 Quick Start

### Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v18.0.0 or later)
- **npm** or **yarn**
- **Go** (v1.23 or later)
- **Firebase account** with a configured project
- **Google Cloud API Key** with Gemini API access

---

## 📱 Frontend Setup

### 1. Clone and Navigate
```bash
git clone https://github.com/anisvsc/finpal.git
cd finpal/finpal-frontend
```

### 2. Install Dependencies
```bash
# Using npm
npm install

# Using yarn
yarn install
```

### 3. Environment Configuration
Create a `.env.local` file in the frontend root directory:

```env
# Firebase Configuration
NEXT_PUBLIC_FIREBASE_API_KEY=your_firebase_api_key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_firebase_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_messaging_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_firebase_app_id

# Backend API Configuration
NEXT_PUBLIC_API_URL=http://localhost:8080
```

> 💡 **Tip**: Get your Firebase configuration values from the [Firebase Console](https://console.firebase.google.com/) → Project Settings → General → Your apps

### 4. Start Development Server
```bash
# Using npm
npm run dev

# Using yarn
yarn dev
```

The frontend will be available at **http://localhost:3000**

---

## 🔧 Backend Setup

### 1. Navigate to Backend Directory
```bash
cd finpal/backend
```

### 2. Install Go Dependencies
```bash
go mod tidy
```

### 3. Environment Configuration
Set the required environment variables:

```bash
# MCP Server Port
export FI_MCP_PORT=8080

# Google API Key for Gemini models
export GOOGLE_API_KEY=your_google_api_key
```

### 4. Start Backend Server
```bash
FI_MCP_PORT=8080 go run .
```

The backend API will be available at **http://localhost:8080**

---

## 🤖 AI Agent Setup

### 1. Install Google ADK
```bash
pip install google-adk>=1.8.0
```

### 2. Configure API Access
```bash
export GOOGLE_API_KEY=your_google_api_key
```

### 3. Start AI Agent
Navigate to the project root directory and run:
```bash
adk web
```

---

## 🌐 Deployment

### Frontend Deployment (Vercel)

1. **Connect Repository**
   - Push your code to GitHub
   - Import your repository in [Vercel Dashboard](https://vercel.com/dashboard)

2. **Configure Environment Variables**
   - In Vercel Dashboard, go to Project Settings → Environment Variables
   - Add all the variables from your `.env.local` file

3. **Deploy**
   - Vercel will automatically build and deploy your application
   - Your app will be available at `https://your-project.vercel.app`

### Backend Deployment (Google Cloud)

```bash
# Build for production
go build -o finpal-backend .

# Deploy to Google Cloud Run (example)
gcloud run deploy finpal-backend --source . --region us-central1
```

---

## 🛠️ Development Workflow

### Running Full Stack Locally

1. **Start Backend Server**
   ```bash
   cd backend && FI_MCP_PORT=8080 go run .
   ```

2. **Start AI Agent**
   ```bash
   adk web
   ```

3. **Start Frontend Development Server**
   ```bash
   cd finpal-frontend && npm run dev
   ```

4. **Access Application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:8080
   - AI Agent: http://localhost:3001 (default ADK port)

---

## 🔐 Security & Authentication

- **Firebase Authentication** handles user registration and login
- **JWT tokens** for secure API communication
- **Environment variables** for sensitive configuration
- **CORS configuration** for cross-origin requests

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🐛 Troubleshooting

### Common Issues

**Frontend won't start:**
- Ensure all environment variables are set correctly
- Check Node.js version (v18+ required)
- Clear npm cache: `npm cache clean --force`

**Backend connection issues:**
- Verify Go version (1.23+ required)
- Check if port 8080 is available
- Ensure GOOGLE_API_KEY is set correctly

**Firebase authentication errors:**
- Verify Firebase project configuration
- Check that authentication methods are enabled in Firebase Console
- Ensure domain is added to authorized domains

---

## 📞 Support

For questions, issues, or contributions:
- **GitHub Issues**: [Create an issue](https://github.com/anisvsc/finpal/issues)
- **Documentation**: Check our [Wiki](https://github.com/anisvsc/finpal/wiki)

---

*Built with ❤️ using Next.js, Go, and Google AI*