Web App - https://xgb-web-app-zxqsffcusegmbpcmepaekh.streamlit.app/

# calcitra-fe

Frontend (Next.js PWA) of **Calcitra** (daily movie-guess game + movie logging + XP/streaks). Split out of the original monorepo so it can be developed and started on its own.

- `apps/web` — Next.js app (frontend only, no DB or service keys)
- `packages/ui` — shared components + design tokens/styles
- `packages/shared` — zod schemas, game constants, error codes
- `packages/api-client` — typed API client generated from the API's OpenAPI document

The backend is the separate [calcitra-api] repo. This app talks to it only through `packages/api-client`.

## Setup

```bash
pnpm install  
  
# point NEXT_PUBLIC_API_URL at the running calcitra-api  
cp apps/web/.env.example apps/web/.env  
  
#Builds all packages (shared, api-client, ui)
pnpm build  
  
# web on http://localhost:3000  
pnpm dev                                  
```

Start [calcitra-api] first (it owns the database and the game logic).

## Commands

`pnpm dev` · `pnpm build` · `pnpm typecheck` · `pnpm lint` · `pnpm test` · `pnpm gen:client`
