# Project Structure

## Directory Organization

```
├── app/                    # Next.js App Router pages
│   ├── (auth)/            # Authentication routes (grouped)
│   ├── (chat)/            # Chat interface routes (grouped)
│   ├── globals.css        # Global styles with CSS variables
│   └── layout.tsx         # Root layout with providers
├── ai/                    # AI model configuration
│   ├── index.ts           # Model exports (geminiProModel, geminiFlashModel)
│   ├── actions.ts         # Server actions for AI operations
│   └── custom-middleware.ts # AI middleware wrapper
├── components/            # React components
│   ├── ui/               # shadcn/ui base components
│   ├── custom/           # Project-specific components
│   └── flights/          # Flight booking components
├── db/                   # Database layer
│   ├── schema.ts         # Drizzle schema definitions
│   ├── queries.ts        # Database query functions
│   └── migrate.ts        # Migration runner
├── lib/                  # Utility libraries
│   ├── drizzle/         # Generated migration files
│   └── utils.ts         # Shared utility functions
└── public/              # Static assets
    ├── fonts/           # Font files
    └── images/          # Image assets
```

## Naming Conventions

- **Files**: kebab-case for regular files, PascalCase for React components
- **Directories**: lowercase with hyphens for route groups `(auth)`, `(chat)`
- **Components**: PascalCase exports, co-located with related files
- **Database**: camelCase for fields, PascalCase for table names in schema

## Import Patterns

- Use `@/` path alias for absolute imports from project root
- Import UI components from `@/components/ui`
- Import utilities from `@/lib/utils`
- Server-only imports use `server-only` package

## Route Organization

- Route groups `(auth)` and `(chat)` for logical separation without URL nesting
- API routes in `app/api/` following REST conventions
- Middleware applies to all routes via `middleware.ts` in root

## Component Architecture

- Server Components by default (React 19 RC)
- Client Components marked with `"use client"` directive
- shadcn/ui components in `components/ui/` (auto-generated)
- Custom components in `components/custom/`
- Feature-specific components in dedicated folders (e.g., `components/flights/`)

## Database Patterns

- Schema definitions in `db/schema.ts` using Drizzle ORM
- Type inference with `InferSelectModel` for TypeScript safety
- Migrations auto-generated in `lib/drizzle/`
- Query functions centralized in `db/queries.ts`
