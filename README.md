# Forge Learn - Educational Platform with AI-Powered IDE

A comprehensive learning management system featuring an integrated IDE, AI chatbot mentor (BODHIT), progress tracking, and project submission capabilities.

## 🚀 Features

### Core Functionality
- **AI-Powered Chatbot (BODHIT)** - Project-skill guidance with mentor report generation
- **Integrated IDE** - Monaco-based code editor with file system, terminal, and AI assistance
- **Role-Based Dashboards** - Separate interfaces for Students, Mentors, and Admins
- **Project Submissions** - GitHub integration for project tracking and evaluation
- **Progress Tracking** - Milestone-based learning with automated progress reports
- **Conversation Persistence** - Save and resume chat sessions across devices
- **Google OAuth + OTP** - Secure authentication with email verification

### User Roles
- **Students** - Access IDE, submit projects, track progress, chat with AI mentor
- **Mentors** - Review submissions, view mentor reports, provide feedback
- **Admins** - Full system access, user management, analytics

## 🛠️ Tech Stack

### Frontend
- **React 18** with TypeScript
- **Vite** - Fast build tool and dev server
- **React Router** - Client-side routing
- **TanStack Query** - Server state management
- **shadcn/ui** - Component library built on Radix UI
- **Tailwind CSS** - Utility-first styling
- **Monaco Editor** - VS Code-powered code editor
- **Lucide React** - Icon library

### Backend
- **Supabase** - PostgreSQL database, authentication, real-time subscriptions
- **Express** - OTP server for email verification
- **Supabase Edge Functions** - Serverless functions for AI chat and milestone generation

### Development Tools
- **TypeScript** - Type safety
- **ESLint** - Code linting
- **tsx** - TypeScript execution for backend

## 📋 Prerequisites

- **Node.js** 18+ and npm (or use [nvm](https://github.com/nvm-sh/nvm))
- **Supabase Account** - [Create one here](https://supabase.com)
- **Google Cloud Project** - For OAuth and Gmail API (optional)

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone <YOUR_GIT_URL>
cd forge-learn
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Environment Setup

Copy the example environment file:

```bash
copy .env.example .env
```

Configure your `.env` file with:

```env
# Supabase Configuration
VITE_SUPABASE_PROJECT_ID="your-project-id"
VITE_SUPABASE_URL="https://your-project.supabase.co"
VITE_SUPABASE_PUBLISHABLE_KEY="your-anon-key"

# Google OAuth (Optional)
VITE_GOOGLE_CLIENT_ID="your-client-id.apps.googleusercontent.com"

# OTP Settings
VITE_OTP_EXPIRY_MINUTES="10"
VITE_OTP_LENGTH="6"

# API Keys
LOVABLE_API_KEY="your-lovable-api-key"
```

### 4. Database Setup

Follow the complete setup guide in `DATABASE_SETUP_CHECKLIST.md`:

```bash
# Execute the complete schema
# 1. Open Supabase Dashboard → SQL Editor
# 2. Copy contents of COMPLETE_DATABASE_SCHEMA.sql
# 3. Paste and execute
```

### 5. Deploy Supabase Functions

```bash
# Install Supabase CLI
npm install -g supabase

# Login to Supabase
supabase login

# Deploy functions
supabase functions deploy bodhit-chat --project-ref <YOUR_PROJECT_REF>
supabase functions deploy generate-milestones --project-ref <YOUR_PROJECT_REF>

# Set secrets
supabase secrets set LOVABLE_API_KEY=<YOUR_KEY> --project-ref <YOUR_PROJECT_REF>
```

### 6. Start Development Servers

```bash
# Terminal 1: Frontend dev server
npm run dev

# Terminal 2: OTP backend server (optional)
npm run otp-server
```

Visit `http://localhost:5173` to see the application.

## 📁 Project Structure

```
forge-learn/
├── src/
│   ├── components/          # React components
│   │   ├── ide/            # IDE-specific components
│   │   └── ui/             # shadcn/ui components
│   ├── pages/              # Route pages
│   ├── hooks/              # Custom React hooks
│   ├── services/           # API and business logic
│   ├── integrations/       # Third-party integrations
│   └── lib/                # Utility functions
├── supabase/
│   ├── functions/          # Edge functions
│   └── migrations/         # Database migrations
├── public/                 # Static assets
└── docs/                   # Documentation (*.md files)
```

## 🎯 Key Features Guide

### AI Chatbot (BODHIT)

The BODHIT chatbot provides project-skill guidance:

1. **Intake Flow** - Collects project details (idea, tech stack, skill level, timeline)
2. **Milestone Guidance** - Helps students work through project milestones
3. **Code Refusal** - Refuses to provide direct code, encourages learning
4. **Mentor Reports** - Generates structured feedback for mentors

See `DEPLOYMENT_GUIDE.md` for detailed setup.

### Integrated IDE

Features include:
- Monaco code editor with syntax highlighting
- File explorer with CRUD operations
- Terminal emulator
- AI chat panel for coding assistance
- GitHub integration for project imports

See `IDE_FILE_SYSTEM_GUIDE.md` for implementation details.

### Authentication

Multiple authentication methods:
- Email/Password with OTP verification
- Google OAuth with OTP
- Session management via Supabase Auth

See `GOOGLE_AUTH_OTP_SETUP.md` and `OTP_SETUP_GUIDE.md`.

## 📚 Documentation

Comprehensive guides are available:

- `DEPLOYMENT_GUIDE.md` - Complete deployment instructions
- `DATABASE_SETUP_CHECKLIST.md` - Database configuration
- `REQUIREMENTS.md` - Detailed feature requirements
- `API_ENDPOINTS_REFERENCE.ts` - API documentation
- `CONVERSATION_PERSISTENCE_GUIDE.md` - Chat persistence
- `CSV_DATA_IMPORT_GUIDE.md` - Data migration
- `GOOGLE_AUTH_OTP_SETUP.md` - OAuth setup
- `OTP_IMPLEMENTATION_GUIDE.md` - OTP system details

## 🧪 Testing

```bash
# Run linter
npm run lint

# Build for production
npm run build

# Preview production build
npm run preview
```

## 🚢 Deployment

### Option 1: Lovable Platform

1. Visit your [Lovable Project](https://lovable.dev/projects/REPLACE_WITH_PROJECT_ID)
2. Click Share → Publish
3. Your app is live!

### Option 2: Manual Deployment

```bash
# Build the project
npm run build

# Deploy dist/ folder to your hosting provider
# (Vercel, Netlify, AWS S3, etc.)
```

See `DEPLOYMENT_GUIDE.md` for detailed instructions.

## 🔒 Security

- Row Level Security (RLS) enabled on all database tables
- JWT-based authentication via Supabase
- Environment variables for sensitive data
- CORS configuration for API endpoints
- OTP verification for account creation

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 Available Scripts

```bash
npm run dev          # Start development server
npm run otp-server   # Start OTP backend server
npm run build        # Build for production
npm run build:dev    # Build in development mode
npm run lint         # Run ESLint
npm run preview      # Preview production build
```

## 🐛 Troubleshooting

### Common Issues

**Database connection errors:**
- Verify Supabase credentials in `.env`
- Check RLS policies are enabled
- Ensure migrations are applied

**OTP not sending:**
- Check Gmail API is enabled
- Verify OAuth credentials
- Check backend server is running

**IDE not loading:**
- Clear browser cache
- Check console for errors
- Verify file system permissions

See individual guide files for specific troubleshooting steps.

## 📄 License

This project is private and proprietary.

## 🙏 Acknowledgments

- Built with [Lovable](https://lovable.dev)
- UI components from [shadcn/ui](https://ui.shadcn.com)
- Code editor powered by [Monaco Editor](https://microsoft.github.io/monaco-editor/)
- Backend by [Supabase](https://supabase.com)

## 📞 Support

For issues or questions:
- Check the documentation in the project root
- Review Supabase function logs
- Check browser console for frontend errors
- Verify all environment variables are set correctly

---

**Built with ❤️ for education**
