# ConnectPro - Professional Networking Platform

## Overview

ConnectPro is a modern full-stack web application designed to facilitate professional networking and mentorship connections between senior and junior professionals. The platform allows users to create profiles, search for potential mentors or mentees, and establish meaningful professional relationships.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query (React Query) for server state management
- **UI Framework**: shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with CSS custom properties for theming
- **Form Handling**: React Hook Form with Zod validation
- **Build Tool**: Vite for development and production builds

### Backend Architecture
- **Runtime**: Node.js with Express.js server
- **Language**: TypeScript with ES modules
- **API Pattern**: RESTful API with conventional HTTP methods
- **Request Handling**: Express middleware for JSON parsing and logging
- **Error Handling**: Centralized error handling middleware

### Database Architecture
- **ORM**: Drizzle ORM with PostgreSQL dialect
- **Database**: PostgreSQL (configured for Neon serverless)
- **Schema Management**: Drizzle Kit for migrations and schema management
- **Data Storage**: Dual storage system with in-memory fallback and PostgreSQL production database

## Key Components

### Data Models
- **Profiles**: Core user profiles with professional information (name, title, bio, skills, experience level)
- **Connections**: Relationship tracking between users with status management (pending, accepted, rejected)
- **Users**: Authentication-ready user accounts (currently basic username/password structure)

### API Endpoints
- `GET /api/profiles` - Retrieve all profiles with optional filtering (search, industry, level)
- `GET /api/profiles/level/:level` - Get profiles by experience level (senior/junior)
- `GET /api/profiles/:id` - Retrieve individual profile details
- `POST /api/profiles` - Create new professional profiles
- `POST /api/connections` - Initiate connection requests between users

### UI Components
- **Profile Cards**: Responsive cards displaying professional information with connection actions
- **Search & Filter Bar**: Advanced filtering by skills, industry, and experience level
- **Profile Creation Modal**: Form-based profile creation with validation
- **Navigation**: Responsive header with route-based navigation
- **Hero Section**: Landing page with call-to-action elements

## Data Flow

1. **Profile Discovery**: Users browse profiles through filtered searches or level-specific pages
2. **Connection Initiation**: Users send connection requests through profile cards
3. **Data Persistence**: Profile and connection data stored via Drizzle ORM to PostgreSQL
4. **Real-time Updates**: TanStack Query manages cache invalidation and optimistic updates
5. **Form Validation**: Zod schemas ensure data integrity from client to database

## External Dependencies

### Core Dependencies
- **Database**: Neon serverless PostgreSQL for production data storage
- **Avatar Generation**: DiceBear API for automatic profile avatar generation
- **UI Components**: Extensive Radix UI component library for accessibility
- **Icons**: Lucide React for consistent iconography

### Development Tools
- **TypeScript**: Full type safety across client, server, and shared code
- **ESBuild**: Production bundling for server-side code
- **PostCSS**: CSS processing with Tailwind and Autoprefixer
- **Drizzle Kit**: Database schema management and migrations

## Deployment Strategy

### Development Environment
- **Port Configuration**: Frontend serves on port 5000 with Vite dev server
- **Hot Reloading**: Vite HMR for frontend, TSX for backend development
- **Database**: Automatic PostgreSQL provisioning in Replit environment

### Production Build
- **Frontend**: Vite builds optimized static assets to `dist/public`
- **Backend**: ESBuild bundles server code to `dist/index.js`
- **Deployment Target**: Autoscale deployment on Replit infrastructure
- **Environment Variables**: `DATABASE_URL` required for PostgreSQL connection

### File Structure
```
├── client/               # React frontend application
├── server/               # Express.js backend server
├── shared/               # Shared TypeScript schemas and types
├── migrations/           # Drizzle database migrations
└── dist/                 # Production build output
```

## Changelog

- June 24, 2025: Complete ConnectPro implementation with comprehensive GitHub documentation
- June 24, 2025: Initial setup

## User Preferences

Preferred communication style: Simple, everyday language.