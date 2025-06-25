# Concurso de Tatuajes - Plataforma de Gestión

## Overview

This is a full-stack web application for managing tattoo contests. The system allows for artist registration, jury management, category assignment, evaluation scoring, and real-time results tracking with Excel export capabilities. The application is built with a modern stack using React, Express, and PostgreSQL with a focus on Spanish language support for the tattoo contest domain.

## System Architecture

The application follows a full-stack monorepo architecture with clear separation between client and server:

- **Frontend**: React with TypeScript, using Vite for development and building
- **Backend**: Express.js with TypeScript running on Node.js
- **Database**: PostgreSQL with Drizzle ORM for type-safe database operations
- **UI Framework**: Tailwind CSS with shadcn/ui components for consistent styling
- **State Management**: TanStack React Query for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Deployment**: Configured for Replit with autoscaling deployment

## Key Components

### Frontend Architecture
- **Client Structure**: Located in `/client` directory with standard React app structure
- **Component Library**: Extensive shadcn/ui component library in `/client/src/components/ui`
- **Pages**: Six main application pages for different contest management functions
- **Hooks**: Custom hooks for mobile detection and toast notifications
- **Utilities**: Contest data calculations and Excel export functionality

### Backend Architecture
- **Server Structure**: Express.js server in `/server` directory
- **Storage Layer**: Abstracted storage interface with PostgreSQL database implementation using Drizzle ORM
- **API Routes**: RESTful endpoints for artists, jurors, and evaluations
- **Middleware**: Request logging and error handling

### Database Schema
- **Artists Table**: Stores tattoo artist information with categories
- **Jurors Table**: Manages jury members with assigned categories (JSON array)
- **Evaluations Table**: Stores scoring data with JSON scores object and calculated totals
- **Relationships**: Foreign key relationships between evaluations and both artists/jurors

## Data Flow

1. **Registration Phase**: Artists and jurors are registered through dedicated forms
2. **Assignment Phase**: Jurors are assigned to specific tattoo categories
3. **Evaluation Phase**: Jurors score artists based on predefined subcriteria
4. **Results Phase**: Real-time calculation of rankings with export functionality

The application uses a centralized query client for API communication and maintains consistent state across components through React Query's caching system.

## External Dependencies

### Core Framework Dependencies
- **React Ecosystem**: React 18+ with TypeScript, React Hook Form, TanStack React Query
- **UI Components**: Radix UI primitives with custom styling via Tailwind CSS
- **Database**: Drizzle ORM with PostgreSQL adapter (@neondatabase/serverless)
- **Validation**: Zod for runtime type validation and schema generation

### Development Tools
- **Build Tools**: Vite for development server and building, esbuild for server bundling
- **Code Quality**: TypeScript for type safety across the entire codebase
- **Replit Integration**: Custom Replit plugins for development environment

### External Services
- **Excel Export**: XLSX library loaded via CDN for client-side spreadsheet generation
- **Database Provider**: Configured for Neon PostgreSQL (serverless PostgreSQL)

## Deployment Strategy

The application is configured for deployment on Replit's platform:

- **Development**: Hot reload development server on port 5000
- **Production Build**: Vite builds client assets, esbuild bundles server code
- **Auto-scaling**: Configured for Replit's autoscale deployment target
- **Environment**: Uses environment variables for database connection and configuration

The build process creates a `dist` directory with both client assets and server bundle, enabling single-command deployment.

## Changelog

- June 24, 2025: Initial setup
- June 24, 2025: Integrated PostgreSQL database with Drizzle ORM, replaced in-memory storage with persistent database storage

## User Preferences

Preferred communication style: Simple, everyday language.