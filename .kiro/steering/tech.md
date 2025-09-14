# Technology Stack

## Core Framework

- **Next.js 15** (canary) with App Router
- **React 19** (release candidate) with Server Components
- **TypeScript** for type safety

## AI & Language Models

- **Vercel AI SDK** (v3.4.9) for LLM integration
- **Google AI SDK** (@ai-sdk/google) for Gemini models
- **Custom middleware** for AI model wrapping and enhancement

## Database & ORM

- **PostgreSQL** via Vercel Postgres (powered by Neon)
- **Drizzle ORM** for database operations and migrations
- **Vercel Blob** for object storage

## Authentication

- **NextAuth.js v5** (beta) for authentication
- **bcrypt-ts** for password hashing

## UI & Styling

- **Tailwind CSS** for styling with CSS variables
- **shadcn/ui** component library
- **Radix UI** primitives for accessibility
- **Framer Motion** for animations
- **Lucide React** for icons
- **Geist** font family

## Development Tools

- **ESLint** with Next.js and Prettier configs
- **Turbo** for faster development builds
- **tsx** for TypeScript execution

## Common Commands

```bash
# Development
pnpm dev              # Start development server with Turbo
pnpm build            # Run migrations and build for production
pnpm start            # Start production server
pnpm lint             # Run ESLint

# Database
tsx db/migrate        # Run database migrations
```

## Environment Setup

- Use `.env.local` for local development
- Required: `GOOGLE_GENERATIVE_AI_API_KEY`, `AUTH_SECRET`, `POSTGRES_URL`, `BLOB_READ_WRITE_TOKEN`
- Deploy via Vercel with automatic environment variable setup
