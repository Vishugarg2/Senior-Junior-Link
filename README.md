# ConnectPro 🌐

A modern professional networking platform that bridges the gap between experienced professionals and emerging talent, fostering meaningful mentorship connections.

## ✨ Features

- **Professional Profiles**: Create detailed profiles with skills, experience, and bio
- **Smart Search & Filtering**: Find professionals by skills, industry, and experience level
- **Connection System**: Send and manage connection requests for mentorship
- **Dual Experience Levels**: Separate views for senior (5+ years) and junior (0-5 years) professionals
- **Responsive Design**: Mobile-first approach with modern UI components
- **Real-time Updates**: Optimistic UI updates and cache management

## 🚀 Tech Stack

### Frontend
- **React 18** with TypeScript
- **Wouter** for lightweight routing
- **TanStack Query** for server state management
- **shadcn/ui** components built on Radix UI
- **Tailwind CSS** for styling
- **React Hook Form** with Zod validation
- **Vite** for build tooling

### Backend
- **Node.js** with Express.js
- **TypeScript** with ES modules
- **Drizzle ORM** for database operations
- **PostgreSQL** (with in-memory fallback for development)
- **Zod** for schema validation

## 📦 Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/connectpro.git
cd connectpro
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables:
```bash
# Create .env file (optional for development)
DATABASE_URL=your_postgresql_url
```

4. Start the development server:
```bash
npm run dev
```

The application will be available at `http://localhost:5000`

## 🏗️ Project Structure

```
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/          # Route pages
│   │   ├── lib/            # Utilities and types
│   │   └── hooks/          # Custom React hooks
├── server/                 # Express backend
│   ├── index.ts           # Server entry point
│   ├── routes.ts          # API route definitions
│   ├── storage.ts         # Data storage layer
│   └── vite.ts            # Vite integration
├── shared/                 # Shared TypeScript schemas
│   └── schema.ts          # Database schema and types
└── components.json         # shadcn/ui configuration
```

## 🎯 API Endpoints

### Profiles
- `GET /api/profiles` - Get all profiles with optional filtering
- `GET /api/profiles/level/:level` - Get profiles by experience level
- `GET /api/profiles/:id` - Get single profile
- `POST /api/profiles` - Create new profile
- `PUT /api/profiles/:id` - Update profile

### Connections
- `POST /api/connections` - Create connection request
- `GET /api/profiles/:id/connections` - Get profile connections
- `PUT /api/connections/:id` - Update connection status

## 🎨 Design System

The application uses a professional blue and green color scheme optimized for networking:

- **Primary**: Blue (#4F7FF0) - Trust and professionalism
- **Accent**: Green (#10B981) - Growth and success
- **Background**: Light gray (#F9FAFB) - Clean and modern

## 📱 Screenshots

### Home Page
Features a hero section, search functionality, and featured profiles from both senior and junior professionals.

### Profile Browsing
Clean card-based layout with filtering options by industry, experience level, and skills.

### Profile Creation
Comprehensive form with validation for creating professional profiles.

## 🔧 Development

### Available Scripts
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build

### Database Schema

The application uses three main tables:
- **profiles** - Professional user profiles
- **connections** - Relationship tracking between users
- **users** - Basic authentication (ready for future auth implementation)

## 🌟 Sample Data

The application comes with sample data including:
- 3 Senior professionals (Product Manager, Software Engineer, Marketing Director)
- 3 Junior professionals (Frontend Developer, Marketing Analyst, UX Designer)

## 🚀 Deployment

The application is configured for deployment on Replit with automatic scaling:

1. Push to your repository
2. Connect to Replit
3. The application will auto-deploy with PostgreSQL database

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **Your Name** - *Initial work* - [YourGitHub](https://github.com/yourusername)

## 🙏 Acknowledgments

- Built with modern web technologies
- UI components from shadcn/ui
- Icons from Lucide React
- Avatars from DiceBear API

---

**ConnectPro** - Building bridges between experience and ambition 🌉