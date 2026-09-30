# AI Mock Interview Platform

A full-stack interview preparation application that helps candidates practice for technical and role-based interviews using AI. Users can upload their resume, select a job role and difficulty level, and start a simulated interview experience powered by Gemini AI. The app also tracks interview history, generates feedback, and scores responses.

## Features

- User authentication with JWT
- Resume upload and parsing from PDF files
- Role-based interview setup
- Difficulty selection for interview complexity
- AI-generated interview questions tailored to the resume and selected role
- Voice-enabled interview flow with transcription and audio support
- Interview history and performance tracking
- AI feedback and scoring after each interview
- Protected routes for authenticated users

## Tech Stack

### Frontend
- React
- Vite
- React Router
- Axios
- Monaco Editor
- React Hot Toast
- React Icons

### Backend
- Node.js
- Express.js
- MongoDB with Mongoose
- JWT authentication
- Multer for resume uploads
- Gemini AI integration
- AssemblyAI for speech transcription
- Murf for voice/audio delivery

## Project Structure

```bash
AI_Mock_Interview/
├── client/
│   ├── index.html
│   ├── package.json
│   ├── vite.config.js
│   └── src/
│       ├── App.jsx
│       ├── components/
│       ├── constants/
│       ├── context/
│       ├── pages/
│       └── services/
├── server/
│   ├── .env.example
│   ├── package.json
│   ├── server.js
│   └── src/
│       ├── app.js
│       ├── config/
│       ├── controllers/
│       ├── middleware/
│       ├── models/
│       ├── routes/
│       ├── services/
│       └── utils/
├── README.md
└── .gitignore
```

## Prerequisites

Before running this project, make sure you have:

- Node.js 18+ installed
- npm or yarn
- MongoDB Atlas account or a local MongoDB instance
- Gemini API key
- Murf API key
- AssemblyAI API key

## Environment Setup

### 1. Install dependencies

```bash
cd client
npm install

cd ../server
npm install
```

### 2. Create environment file

Copy the example file and update it with your own values:

```bash
cd server
copy .env.example .env
```

Then configure your variables in `server/.env`:

```env
PORT=5000
NODE_ENV=development
CLIENT_URL=http://localhost:5173
MONGODB_URI=mongodb+srv://<user>:<pass>@cluster.mongodb.net/ai-mock-interview
JWT_SECRET=your-secret-key
JWT_EXPIRES_IN=7d

GEMINI_API_KEY=your-gemini-api-key
MURF_API_KEY=your-murf-api-key
ASSEMBLYAI_API_KEY=your-assemblyai-api-key
```

If your frontend needs a custom backend URL, create a `.env` file in the `client` folder as well:

```env
VITE_API_URL=http://localhost:5000/api
```

## Run the Application

### Start the backend

```bash
cd server
npm run dev
```

### Start the frontend

```bash
cd client
npm run dev
```

Then open the URL shown by Vite in the browser, usually:

```bash
http://localhost:5173
```

## Typical Workflow

1. Register or log in to the app.
2. Upload a PDF resume.
3. Choose a target role and difficulty.
4. Start the mock interview.
5. Answer interview questions.
6. Review AI-generated feedback and overall score.
7. Revisit previous interview records in the history section.

## Notes

- Resume upload currently expects a PDF file.
- The server uses CORS to allow frontend communication from the configured client URL.
- The app is designed for local development and can be extended for deployment with environment-based settings.

## Scripts

### Client

```bash
npm run dev
npm run build
npm run preview
```

### Server

```bash
npm run dev
npm run start
```

## License

This project is intended for educational and portfolio use. Add your preferred license if you plan to distribute or deploy it publicly.
