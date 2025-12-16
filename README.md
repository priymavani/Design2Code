# Design2Code 🚀


## 📋 Project Overview

**Design2Code** is a full-stack AI-powered web application that converts website design images and natural language prompts into clean, responsive HTML code. Built during a Hackathon, this project leverages **Google's Gemini AI API** to analyze visual designs and generate production-ready front-end code in seconds.

Whether you're a designer who wants quick prototypes, a developer looking to accelerate development, or a student learning web development, Design2Code eliminates repetitive coding and lets you focus on what matters.

### The Problem It Solves

- ⏳ **Slow Prototyping**: Converting design mockups to code manually takes hours
- 🎨 **Designer-Developer Gap**: Designers struggle to communicate exact styling to developers
- 📱 **Responsive Design**: Building responsive layouts requires extensive media queries and testing
- 💡 **Ideation Speed**: Rapid iteration and prototyping becomes a bottleneck

### Target Users

- 🎨 **UI/UX Designers** - Convert mockups to working prototypes instantly
- 👨‍💻 **Frontend Developers** - Generate boilerplate code and focus on complex logic
- 🏢 **Startups & Agencies** - Speed up project delivery and reduce development time
- 📚 **Students & Learning** - Understand HTML/CSS best practices through AI-generated code

---

## ✨ Core Features

### 1. **Image-to-Code Generation**
- Upload website design screenshots (PNG/JPEG)
- AI analyzes layout, colors, typography, and spacing
- Generates semantic HTML5 with embedded CSS
- Creates responsive designs automatically

### 2. **Prompt-to-Code Generation**
- Describe your website idea in natural language
- AI generates complete HTML structure with modern styling
- Supports complex design descriptions
- Produces pixel-perfect, responsive code

### 3. **Live Preview**
- Real-time HTML preview within the application
- Test generated code before downloading
- Visual validation of AI output
- Interactive component testing

### 4. **Multiple Creation Modes**
- 📸 **Upload Mode** - Convert design images to code
- 💬 **Prompt Mode** - Generate code from descriptions
- 📐 **Whiteboard Mode** - Sketch and convert
- 🎨 **Template Mode** - Start from pre-built templates

### 5. **Code Features**
- ✅ Semantic HTML5 structure
- ✅ Modern CSS with Flexbox/Grid
- ✅ Fully responsive (desktop, tablet, mobile)
- ✅ Smooth animations and transitions
- ✅ Professional styling (gradients, shadows, effects)
- ✅ Accessibility-ready

---

## 🛠️ Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| **React 18** | UI framework |
| **TypeScript** | Type-safe development |
| **Vite** | Fast build tool |
| **Tailwind CSS** | Utility-first styling |
| **Shadcn/ui** | High-quality component library |
| **Framer Motion** | Smooth animations |
| **GSAP** | Advanced animations |
| **React Three Fiber** | 3D graphics |
| **TanStack Query** | Data fetching & caching |
| **React Router** | Client-side routing |

### Backend
| Technology | Purpose |
|---|---|
| **Node.js** | JavaScript runtime |
| **Express.js** | Web framework |
| **Google Gemini AI API** | Code generation engine |
| **Multer** | File upload handling |
| **CORS** | Cross-origin support |
| **Dotenv** | Environment variables |

### Languages & Styling
- **TypeScript**: 85% of codebase
- **JavaScript**: 9.9% (backend scripts)
- **CSS**: 4.6% (custom styling)
- **HTML**: 0.5% (markup)

---

## 🏗️ System Architecture & Workflow

```
┌─────────────────────────────────────────────────────────────┐
│                      USER INTERFACE (React)                 │
│  ┌──────────────┬──────────────┬──────────────────────────┐ │
│  │ Landing Page │ Create Page  │ Preview & Download       │ │
│  └──────────────┴──────────────┴──────────────────────────┘ │
└────────────┬────────────────────────────────────────────────┘
             │
             ▼
┌─────────────────────────────────────────────────────────────┐
│              INPUT PROCESSING LAYER                          │
│  ┌──────────────┬──────────────┬──────────────────────────┐ │
│  │ Image Upload │ Text Prompt  │ File Management          │ │
│  │ (Multer)     │ Processing   │ (Validation)             │ │
│  └──────────────┴──────────────┴──────────────────────────┘ │
└────────────┬────────────────────────────────────────────────┘
             │
             ▼
┌─────────────────────────────────────────────────────────────┐
│              EXPRESS BACKEND SERVER                          │
│  ┌──────────────┬──────────────┬──────────────────────────┐ │
│  │ Image Route  │ Prompt Route │ Middleware (Error)       │ │
│  │  /upload     │  /generate   │ Handler, CORS            │ │
│  └──────────────┴──────────────┴──────────────────────────┘ │
└────────────┬────────────────────────────────────────────────┘
             │
             ▼
┌─────────────────────────────────────────────────────────────┐
│            AI PROCESSING LAYER (Controllers)                 │
│  ┌──────────────────────┬──────────────────────────────────┐ │
│  │ imageToCode.js       │ generationController.js          │ │
│  │ Process & Send to AI │ Handle Generation Requests       │ │
│  └──────────────────────┴──────────────────────────────────┘ │
└────────────┬────────────────────────────────────────────────┘
             │
             ▼
┌─────────────────────────────────────────────────────────────┐
│         SERVICES LAYER (External API Calls)                  │
│  ┌──────────────────────┬──────────────────────────────────┐ │
│  │ imageService.js      │ generationService.js             │ │
│  │ - Buffer to Base64   │ - Build API request              │ │
│  │ - Send to Gemini API │ - Parse Gemini response          │ │
│  └──────────────────────┴──────────────────────────────────┘ │
└────────────┬────────────────────────────────────────────────┘
             │
             ▼
┌─────────────────────────────────────────────────────────────┐
│       GOOGLE GEMINI AI (External Service)                    │
│         🤖 AI Code Generation Engine                         │
└─────────────────────────────────────────────────────────────┘
             │
             ▼
┌─────────────────────────────────────────────────────────────┐
│              GENERATED HTML RESPONSE                         │
│  ├─ Semantic HTML5 Structure                                │
│  ├─ Embedded CSS with Flexbox/Grid                          │
│  ├─ Responsive Media Queries                                │
│  └─ Modern Design Patterns                                  │
└─────────────────────────────────────────────────────────────┘
```

### Request Flow

1. **User Input** → Frontend captures image/prompt
2. **Upload/Send** → Data sent to Express backend via API
3. **Processing** → Backend validates and processes input
4. **AI Call** → Service layer sends to Google Gemini API
5. **Generation** → Gemini AI analyzes and generates code
6. **Response** → HTML code returned to frontend
7. **Preview** → Live preview rendered in iframe
8. **Download** → User downloads/uses generated code

---

## 📡 API Documentation

### Base URL
```
http://localhost:5000/api
```

### Endpoints

#### 1. **Generate Code from Image**
```http
POST /upload/image-to-code
Content-Type: multipart/form-data

Body:
  image: <File> (PNG or JPEG)
```

**Response (Success - 200)**
```json
{
  "code": "<!DOCTYPE html>\n<html>...",
  "timestamp": "2025-12-17T10:30:00Z"
}
```

**Response (Error - 400/500)**
```json
{
  "error": "Error message describing what went wrong"
}
```

**cURL Example:**
```bash
curl -X POST http://localhost:5000/api/upload/image-to-code \
  -F "image=@design.png" \
  -H "Accept: application/json"
```

#### 2. **Generate Code from Prompt**
```http
POST /generate/prompt-to-code
Content-Type: application/json

Body:
{
  "prompt": "Create a modern landing page with a hero section, features grid, and CTA button"
}
```

**Response (Success - 200)**
```json
{
  "code": "<!DOCTYPE html>\n<html>...",
  "timestamp": "2025-12-17T10:30:00Z"
}
```

**cURL Example:**
```bash
curl -X POST http://localhost:5000/api/generate/prompt-to-code \
  -H "Content-Type: application/json" \
  -d '{"prompt": "Create a modern dashboard"}'
```

### Request/Response Details

| Aspect | Details |
|---|---|
| **Max File Size** | 10 MB |
| **Supported Formats** | PNG, JPEG |
| **Timeout** | 30 seconds |
| **Rate Limit** | No limit (development) |
| **Authentication** | None (development) |

---

## 🚀 Installation & Setup Guide

### Prerequisites

Before installing, ensure you have:

- **Node.js** (v16.0.0 or higher)
  - Download: [nodejs.org](https://nodejs.org)
  - Verify: `node --version`

- **npm** (v7.0.0 or higher) - Comes with Node.js
  - Verify: `npm --version`

- **Git** - For cloning the repository
  - Download: [git-scm.com](https://git-scm.com)

- **Google Gemini API Key** - Required for AI functionality
  - Get it: [Google AI Studio](https://aistudio.google.com/app/apikey)

### Step 1: Clone the Repository

```bash
git clone https://github.com/priymavani/Design2Code.git
cd Design2Code
```

### Step 2: Set Up Backend

```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create .env file
echo "GEMINI_API_KEY=your_api_key_here" > .env
echo "PORT=5000" >> .env

# Verify .env
cat .env
```

**Backend Dependencies Installed:**
- `express` - Web server framework
- `cors` - Cross-origin resource sharing
- `multer` - File upload handling
- `dotenv` - Environment variables
- `nodemon` - Auto-reload server
- `uuid` - Unique ID generation

### Step 3: Start Backend Server

```bash
# Start with nodemon (auto-reload on changes)
npm run dev

# OR start normally
npm start
```

**Expected Output:**
```
Server is running on port 5000
```

### Step 4: Set Up Frontend (New Terminal)

```bash
# From project root, navigate to frontend
cd frontend

# Install dependencies
npm install

# Start development server
npm run dev
```

**Expected Output:**
```
Local: http://localhost:5173
```

### Step 5: Access the Application

1. Open browser: `http://localhost:5173`
2. Navigate to "Create" page
3. Choose mode (Upload Image or Enter Prompt)
4. Generate and preview your code!

### Common Setup Issues

| Issue | Solution |
|---|---|
| **Port already in use** | Change `PORT` in `.env` or kill process on that port |
| **Module not found** | Run `npm install` in the correct directory |
| **GEMINI_API_KEY error** | Ensure `.env` file exists in `backend/` with valid key |
| **CORS error** | Verify frontend URL in `server.js` matches your dev URL |
| **Build fails** | Delete `node_modules` and `.lock` files, run `npm install` again |

---

## 📁 Folder Structure Explanation

```
Design2Code/
├── README.md                          # Project documentation
│
├── backend/                           # Express.js server
│   ├── package.json                   # Backend dependencies
│   ├── server.js                      # Main server file with routes
│   │
│   ├── controllers/                   # Request handlers
│   │   ├── imageToCode.js             # Processes image uploads
│   │   ├── generationController.js    # Handles prompt generation
│   │   ├── chatController.js          # Chat functionality (future)
│   │   └── promptToCode.js            # Prompt processing
│   │
│   ├── routes/                        # API endpoints
│   │   ├── imageRoute.js              # POST /api/upload/image-to-code
│   │   ├── generationRoute.js         # POST /api/generate/prompt-to-code
│   │   ├── chatRoute.js               # Chat endpoints (future)
│   │   └── promptRoute.js             # Prompt-related routes
│   │
│   ├── services/                      # Business logic & API calls
│   │   ├── imageService.js            # Calls Gemini API for images
│   │   ├── generationService.js       # Calls Gemini API for prompts
│   │   ├── geminiService.js           # Shared Gemini utilities
│   │   └── conversationService.js     # Chat conversation logic
│   │
│   ├── middleware/                    # Express middleware
│   │   └── errorHandler.js            # Global error handling
│   │
│   └── .env                           # Environment variables (not in repo)
│
├── frontend/                          # React + TypeScript application
│   ├── package.json                   # Frontend dependencies
│   ├── vite.config.ts                 # Vite build configuration
│   ├── tsconfig.json                  # TypeScript configuration
│   ├── tailwind.config.ts             # Tailwind CSS config
│   ├── postcss.config.js              # PostCSS configuration
│   │
│   ├── src/
│   │   ├── main.tsx                   # React entry point
│   │   ├── App.tsx                    # Root component with routing
│   │   ├── index.css                  # Global styles
│   │   │
│   │   ├── pages/                     # Page components
│   │   │   ├── Index.tsx              # Landing page
│   │   │   ├── CreatePage.tsx         # Main code generation page
│   │   │   ├── StickersPage.tsx       # Stickers/decorations page
│   │   │   ├── RealisticRobot.tsx     # 3D robot component
│   │   │   └── NotFound.tsx           # 404 page
│   │   │
│   │   ├── components/                # Reusable components
│   │   │   ├── LandingPage.tsx        # Hero section
│   │   │   ├── CreatePage.tsx         # Creation workflow
│   │   │   ├── LivePreview.tsx        # Code preview iframe
│   │   │   ├── LoadingSpinner.tsx     # Loading animation
│   │   │   ├── LogoGenerator.tsx      # Logo creation tool
│   │   │   ├── OrbPreview.tsx         # 3D orb animation
│   │   │   ├── ParticleBackground.tsx # Animated particles
│   │   │   ├── ColorPaletteDisplay.tsx # Color picker
│   │   │   ├── ExampleLogos.tsx       # Example templates
│   │   │   ├── FeaturesTile.tsx       # Features showcase
│   │   │   ├── ThemeToggleTile.tsx    # Dark mode toggle
│   │   │   ├── ImpactTile.tsx         # Impact statistics
│   │   │   ├── PreviewTile.tsx        # Code preview section
│   │   │   ├── UploadTile.tsx         # File upload component
│   │   │   ├── StickersTile.tsx       # Stickers showcase
│   │   │   ├── FooterTile.tsx         # Footer component
│   │   │   ├── SmoothScrollProvider.tsx # Scroll animation provider
│   │   │   │
│   │   │   └── ui/                    # shadcn/ui components
│   │   │       ├── button.tsx         # Button component
│   │   │       ├── card.tsx           # Card component
│   │   │       ├── dialog.tsx         # Modal dialog
│   │   │       ├── input.tsx          # Input field
│   │   │       ├── textarea.tsx       # Text area
│   │   │       ├── tabs.tsx           # Tab component
│   │   │       ├── accordion.tsx      # Accordion
│   │   │       ├── dropdown-menu.tsx  # Dropdown menu
│   │   │       ├── skeleton.tsx       # Loading skeleton
│   │   │       └── [20+ more UI components]
│   │   │
│   │   ├── hooks/                     # Custom React hooks
│   │   │   ├── use-mobile.tsx         # Mobile detection hook
│   │   │   └── use-toast.ts           # Toast notification hook
│   │   │
│   │   ├── lib/                       # Utility functions
│   │   │   └── utils.ts               # Helper functions
│   │   │
│   │   └── vite-env.d.ts              # Vite type definitions
│   │
│   ├── public/                        # Static assets
│   │
│   └── index.html                     # HTML entry point
│
└── .gitignore                         # Git ignore rules
```

### Key Directory Purposes

| Directory | Purpose | Key Files |
|---|---|---|
| `backend/controllers` | Handle incoming requests | `imageToCode.js` |
| `backend/services` | Business logic & API calls | `imageService.js` |
| `backend/routes` | Define API endpoints | `imageRoute.js` |
| `frontend/pages` | Full page components | `CreatePage.tsx` |
| `frontend/components` | Reusable UI components | `LivePreview.tsx` |
| `frontend/components/ui` | Pre-built UI library | 30+ shadcn components |

---

## 🔐 Environment Variables

Create a `.env` file in the `backend/` directory:

```bash
# .env
GEMINI_API_KEY=your_actual_gemini_api_key_here
PORT=5000
```

### Variable Details

| Variable | Type | Required | Description |
|---|---|---|---|
| `GEMINI_API_KEY` | String | ✅ Yes | Google Gemini API key for code generation |
| `PORT` | Number | ❌ No | Server port (default: 5000) |

### How to Get GEMINI_API_KEY

1. Visit [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Click "Create API Key"
3. Copy the generated key
4. Paste into `.env` file

### Security Note
⚠️ **Never commit `.env` to Git!** It's already in `.gitignore`.

---

## 💻 How to Use the Application

### 1. **Landing Page**
- View project features and benefits
- See example logos and stickers
- Understand the technology stack
- Browse theme options

### 2. **Create Page - Main Workflow**

#### Option A: Image to Code
```
1. Click "Upload Design Image" button
2. Select PNG or JPEG file from computer
3. Click "Generate Code"
4. AI analyzes image and generates HTML
5. Preview generated code in live preview
6. Download or copy code
```

#### Option B: Prompt to Code
```
1. Click "Describe Your Website" button
2. Type detailed description:
   - "Create a modern e-commerce landing page with 
      hero section, product cards, and contact form"
3. Click "Generate Code"
4. AI generates responsive HTML
5. Preview and download
```

#### Option C: Template Mode
```
1. Browse pre-built templates
2. Select "Modern Dashboard" or others
3. View template preview
4. Use as starting point or modify
```

### 3. **Live Preview**
- Generated code displayed in live iframe
- See responsive design in real-time
- Test on different screen sizes
- Interactive component testing

### 4. **Download & Export**
- Copy code to clipboard
- Download as `.html` file
- Share preview link
- Edit in your editor

### 5. **Stickers Page**
- Browse decorative stickers
- Add to your designs
- Export as SVG/PNG

---

