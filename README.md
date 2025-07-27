# Finpal – Your Finance Buddy 💰

Finpal is your personal finance assistant, built using modern web technologies to help you track, analyze, and manage your finances with ease.

---

### 🖥 Frontend
- **Framework:** [Next.js](https://nextjs.org/)
- **Styling:** [Tailwind CSS](https://tailwindcss.com/)
- **Authentication:** [Firebase Authentication](https://firebase.google.com/docs/auth) (Google, Email/Password)
- **Deployment:** [Vercel](https://vercel.com)

### 🧠 Backend – AI Agent
- **LLM Agent Framework:** [Google ADK (Agent Developer Kit)](https://ai.google.dev/)
- **AI Models:** 
  - Gemini 1.5 Flash (for fast reasoning)
  - Gemini 1.5 Pro (for deeper research and long-context processing)
- **Data Source:** [fi.money MCP Server](https://fi.money) via ADK MCPToolset
- **Cloud Services:**
  - [Firebase](https://firebase.google.com/)
  - [Google Cloud](https://cloud.google.com/)
  - [Cloud Speech-to-Text](https://cloud.google.com/speech-to-text)

---

## 🛠️ Getting Started (frontend)

### 1. Clone the Repository

```bash
git clone https://github.com/anisvsc/finpal.git
cd finpal-frontend
```

### 2. Install Dependencies
```bash
npm install

# or

yarn install
```

### 3. Setup Environment Variables
Create a .env.local file in the root directory and add your config:
```env
NEXT_PUBLIC_FIREBASE_API_KEY=your_key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_bucket
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id
```
You can get these values from your [Firebase Project Settings](https://console.firebase.google.com/).

### 4. Run the Development Server
```bash
npm run dev

# or

yarn dev
```

Navigate to http://localhost:3000 to see Finpal Frontend with Firebase Auth in action.

---

## 🚀 Deployment

1. Push your code to GitHub.
2. Connect your repo to Vercel.
3. Set the same environment variables in Vercel Dashboard.

---

## 🛠️ Getting Started (backend)

### Running the server

#### Prerequisites
- Go 1.23 or later

### Install dependencies
```bash
go mod tidy```

### Start the server
```bash
FI_MCP_PORT=8080 go run .

```
The server will start on http://localhost:8080.

### Running the AI Agent
### Requirements
- google-adk(>=1.8.0) (`pip install google-adk`)
- export GOOGLE_API_KEY=YOUR_API_KEY
- Run `adk web` in parent directory