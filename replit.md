# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Each package manages its own dependencies.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)
- **Frontend**: React + Vite + TailwindCSS + Shadcn/ui

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

## Artifacts

### Manomitra — Mental Wellness Companion

- **Frontend**: `artifacts/manomitra/` (React + Vite, previewPath: `/`)
- **API Server**: `artifacts/api-server/` (Express 5, path: `/api`)

#### Pages
- `/` — Home/Dashboard with wellness score, affirmations, recent moods/activity
- `/chat` — AI chatbot with sticker responses, mood selector, voice input
- `/mood` — Mood tracker with intensity, notes, recharts visualization, insights
- `/music` — Spotify/YouTube music by mood (filters: calm, stressed, anxious, etc.)
- `/speeches` — Telugu spiritual speeches: Chaganti, Garikapati, Tanikella Bharani
- `/stories` — Inspiring stories: Nick Vujicic, Sudha Chandran, etc.
- `/voice` — Voice assistant (SpeechRecognition API) + face detection (camera)
- `/feedback` — Star ratings + emoji reactions + comments
- `/settings` — Profile, language, notifications, privacy, voice toggle

#### API Endpoints
- `GET/POST /api/chat/messages` — Chat history + AI responses
- `GET/POST /api/mood/logs` — Mood tracking
- `GET /api/mood/summary` — Mood analytics
- `GET /api/music/recommendations` — Mood-filtered music
- `GET /api/music/playlists` — Curated playlists
- `GET /api/content/speeches` — Spiritual speeches (filter by speaker)
- `GET /api/content/stories` — Inspiring stories
- `GET /api/content/featured` — Featured daily content + affirmation
- `GET/POST /api/feedback` — Ratings and feedback
- `GET /api/insights/dashboard` — Personalized dashboard analytics

#### DB Tables
- `chat_messages` — Chat history (role, content, mood, sticker)
- `mood_logs` — Mood entries (mood, intensity, note)
- `music_tracks` — Music library
- `playlists` — Curated playlists
- `content_items` — Speeches and stories (type: speech|story)
- `feedback` — User ratings and comments

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.
