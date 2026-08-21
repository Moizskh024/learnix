# Learnix — Your AI-Powered Learning Companion

A production-minded Next.js + TypeScript learning app with AI Tutor, PDF notes, AI quizzes, progress, settings, responsive navigation, and light/dark mode.

## Requirements
- Node.js 20+
- An API key for one supported AI provider

## Local setup

```bash
npm install
cp .env.example .env.local
```

Set:

```env
AI_PROVIDER=openai
AI_API_KEY=your_key_here
AI_MODEL=gpt-4.1-mini
```

Supported providers in the server-side abstraction: `openai`, `anthropic`, `google`.

Run:

```bash
npm run dev
```

Open http://localhost:3000.

## Notes
- AI routes run server-side. API keys are never exposed to client components.
- PDF upload extracts text in memory and does not persist documents.
- The app intentionally avoids fake AI responses. Missing/invalid AI configuration produces a visible setup/error state.
- Progress currently uses realistic sample values because persistent user accounts/database storage are outside the requested core scope.

## Vercel deployment
1. Push the project to GitHub.
2. Import the repository into Vercel.
3. Add `AI_PROVIDER`, `AI_API_KEY`, and `AI_MODEL` under Project Settings → Environment Variables.
4. Deploy.

No custom server is required; the Next.js API routes deploy as Vercel functions.
