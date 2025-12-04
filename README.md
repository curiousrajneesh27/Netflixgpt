# 🎬 NetflixAI - AI-Powered Movie Recommendation Platform

A Netflix-inspired web application built with React that combines the power of AI (OpenAI/Gemini) with TMDB API to provide intelligent movie recommendations and an immersive browsing experience.

![React](https://img.shields.io/badge/React-18.3.1-blue)
![Redux](https://img.shields.io/badge/Redux-Toolkit-purple)
![Firebase](https://img.shields.io/badge/Firebase-11.1.0-orange)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.4.14-cyan)

## ✨ Features

### 🔐 Authentication

- **Sign Up / Sign In** with email and password
- **Firebase Authentication** integration
- Profile management with display name and avatar
- Protected routes and auto-redirect
- Persistent login sessions

### 🎥 Browse Movies

- **Main Container** with featured movie trailer playing in background
- **Video Title & Description** overlay
- **Secondary Container** with multiple movie categories:
  - Now Playing Movies
  - Popular Movies
  - Trending Movies
  - Upcoming Movies
  - Horror Movies
- **Responsive Movie Cards** with hover effects
- Smooth horizontal scrolling for movie lists

### 🤖 AI-Powered GPT Search

- **Intelligent Movie Search** using OpenAI or Google Gemini AI
- **Multi-language Support** (English, Hindi, Spanish)
- Natural language query processing
- AI-generated movie recommendations based on your search
- Real-time movie suggestions with posters and details

### 🎨 UI/UX

- Netflix-inspired design with Tailwind CSS
- Fully responsive layout for all devices
- Smooth animations and transitions
- Dark theme with gradient overlays
- Professional navigation header

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v14 or higher)
- **npm** or **yarn**
- **Git**

### Required API Keys

You'll need to obtain API keys from the following services:

1. **TMDB API** (The Movie Database)

   - Visit: https://www.themoviedb.org/settings/api
   - Sign up and request an API key
   - You'll need the **Bearer Token** (Read Access Token)

2. **Firebase**

   - Visit: https://console.firebase.google.com/
   - Create a new project
   - Enable Email/Password authentication
   - Get your Firebase configuration

3. **OpenAI API** (Optional - for GPT Search)

   - Visit: https://platform.openai.com/api-keys
   - Create an API key
   - Note: This is a paid service

4. **Google Gemini API** (Alternative to OpenAI)
   - Visit: https://makersuite.google.com/app/apikey
   - Create an API key
   - Free tier available

## 📦 Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/curiousrajneesh27/NetflixAI.git
cd NetflixAI
```

### Step 2: Install Dependencies

```bash
npm install
```

### Step 3: Set Up Environment Variables

1. Create a `.env` file in the root directory:

```bash
# Copy the example file
cp .env.example .env
```

2. Open `.env` and add your API keys:

```env
# TMDB API (Required)
REACT_APP_TMDB_KEY=your_tmdb_bearer_token_here

# OpenAI API (Optional - for GPT Search)
REACT_APP_OPENAI_KEY=your_openai_api_key_here

# Google Gemini API (Alternative to OpenAI)
REACT_APP_GEMINI_KEY=your_gemini_api_key_here
```

### Step 4: Configure Firebase

1. Open `src/Utils/firebase.js`
2. Replace the Firebase configuration with your own:

```javascript
const firebaseConfig = {
  apiKey: "your-api-key",
  authDomain: "your-auth-domain",
  projectId: "your-project-id",
  storageBucket: "your-storage-bucket",
  messagingSenderId: "your-messaging-sender-id",
  appId: "your-app-id",
};
```

### Step 5: Run the Application

```bash
npm start
```

The app will open in your browser at `http://localhost:3000`

## 🏗️ Project Structure

```
netflix-gpt2/
├── public/
│   ├── index.html
│   ├── manifest.json
│   └── robots.txt
├── src/
│   ├── Components/
│   │   ├── Body.js              # Main routing component
│   │   ├── Browse.js            # Browse page with movies
│   │   ├── Header.js            # Navigation header
│   │   ├── Login.js             # Login/Signup page
│   │   ├── MainContainer.js     # Featured movie section
│   │   ├── SecondaryContainer.js # Movie lists section
│   │   ├── VideoBackground.js   # Trailer player
│   │   ├── VideoTitle.js        # Movie title overlay
│   │   ├── MovieList.js         # Horizontal movie list
│   │   ├── MovieCard.js         # Individual movie card
│   │   ├── GptSearch.js         # AI search page
│   │   ├── GptSearchBar.js      # Search input with language
│   │   └── GptMovieSuggestion.js # AI results display
│   ├── hooks/
│   │   ├── useNowPlayingMovies.js
│   │   ├── usePopularMovies.js
│   │   ├── useTrendingMovies.js
│   │   ├── useUpcomingMovies.js
│   │   ├── useHorrorMovies.js
│   │   └── useMovieTrailer.js
│   ├── Utils/
│   │   ├── appstore.js          # Redux store
│   │   ├── userSlice.js         # User state
│   │   ├── moviesSlice.js       # Movies state
│   │   ├── gptSlice.js          # GPT search state
│   │   ├── configSlice.js       # App config
│   │   ├── constant.js          # API constants
│   │   ├── firebase.js          # Firebase config
│   │   ├── openai.js            # OpenAI config
│   │   ├── validate.js          # Form validation
│   │   └── languageConstants.js # Multi-language text
│   ├── App.js
│   ├── index.js
│   └── index.css
├── .env                         # Environment variables (not in git)
├── .env.example                 # Environment template
├── .gitignore
├── package.json
├── tailwind.config.js
└── README.md
```

## 🔧 Available Scripts

### `npm start`

Runs the app in development mode at `http://localhost:3000`

### `npm run build`

Builds the app for production to the `build` folder

### `npm test`

Launches the test runner in interactive watch mode

## 🛠️ Technologies Used

- **React 18.3.1** - Frontend library
- **Redux Toolkit** - State management
- **React Router DOM** - Navigation
- **Firebase 11.1.0** - Authentication & hosting
- **Tailwind CSS 3.4.14** - Styling
- **TMDB API** - Movie database
- **OpenAI API** - GPT-powered search
- **Google Gemini AI** - Alternative AI search
- **Axios** - HTTP requests

## 🎯 Key Features Implementation

### Custom Hooks

- **useNowPlayingMovies**: Fetches currently playing movies
- **usePopularMovies**: Fetches popular movies
- **useTrendingMovies**: Fetches trending movies
- **useUpcomingMovies**: Fetches upcoming releases
- **useHorrorMovies**: Fetches horror genre movies
- **useMovieTrailer**: Fetches trailer for a specific movie

### Redux Slices

- **userSlice**: Manages user authentication state
- **moviesSlice**: Stores all movie data
- **gptSlice**: Manages AI search state
- **configSlice**: Handles app configuration (language, etc.)

### Form Validation

- Email format validation
- Password strength requirements
- Real-time error messages
- Display name validation for signup

## 🔐 Security

- ✅ API keys stored in environment variables
- ✅ `.env` file excluded from git
- ✅ Firebase security rules implemented
- ✅ Protected routes with authentication
- ⚠️ **Important**: Never commit your `.env` file to version control

## 🚢 Deployment

### Firebase Hosting

1. Install Firebase CLI:

```bash
npm install -g firebase-tools
```

2. Login to Firebase:

```bash
firebase login
```

3. Initialize Firebase:

```bash
firebase init
```

4. Build and deploy:

```bash
npm run build
firebase deploy
```

### Other Platforms

- **Vercel**: Connect your GitHub repo and deploy
- **Netlify**: Drag and drop the `build` folder
- **GitHub Pages**: Use `gh-pages` package

## 🐛 Troubleshooting

### Common Issues

**1. API Keys not working**

- Ensure `.env` file is in the root directory
- Restart the development server after adding environment variables
- Verify all keys are prefixed with `REACT_APP_`

**2. Firebase Authentication Error**

- Check if Email/Password authentication is enabled in Firebase Console
- Verify Firebase configuration in `firebase.js`

**3. Movies not loading**

- Verify your TMDB API key is valid
- Check network tab for API errors
- Ensure you're using the Bearer Token, not just API Key

**4. Build folder not created**

- Run `npm install` to ensure all dependencies are installed
- Clear cache: `npm cache clean --force`
- Delete `node_modules` and `package-lock.json`, then reinstall

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👤 Author

**Rajneesh Verma**

- GitHub: [@curiousrajneesh27](https://github.com/curiousrajneesh27)

## 🙏 Acknowledgments

- [TMDB](https://www.themoviedb.org/) for the movie database API
- [OpenAI](https://openai.com/) for GPT API
- [Google](https://ai.google.dev/) for Gemini AI
- [Firebase](https://firebase.google.com/) for authentication
- Netflix for design inspiration

---

⭐ **If you find this project useful, please consider giving it a star!** ⭐
