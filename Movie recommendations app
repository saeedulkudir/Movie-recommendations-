# Navigate to your desired parent directory
# For example, if you want your project in a folder called 'movie-recommendation-app'
# mkdir movie-recommendation-app
# cd movie-recommendation-app

# 1. Create a new React project using Vite
# Choose 'react' as the framework and 'javascript' or 'typescript' as the variant.
npx create-vite@latest movie-recommendation-frontend -- --template react

# 2. Navigate into the new frontend project directory
cd movie-recommendation-frontend

# 3. Install dependencies
npm install

# 4. Start the development server to verify setup
npm run dev

# You should see a message like:
# 'Vite vX.X.X dev server running at:
# > Local: http://localhost:5173/' (or similar port)
# Open this URL in your browser to see the default Vite + React app.
```

**After running the commands above, modify `movie-recommendation-frontend/src/App.jsx` to display a simple message:**

```jsx
// movie-recommendation-frontend/src/App.jsx

import React from 'react';
import './index.css'; // Assuming you have a basic index.css or will create one

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <h1>Welcome to Movie Recommendation App!</h1>
        <p>Frontend is up and running.</p>
      </header>
    </div>
  );
}

export default App;
```

**And ensure `movie-recommendation-frontend/src/main.jsx` looks like this (standard Vite setup):**

```jsx
// movie-recommendation-frontend/src/main.jsx

import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App.jsx';
import './index.css'; // Import your global CSS

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
);
```

**You might also want a basic `movie-recommendation-frontend/src/index.css` for initial styling:**

```css
/* movie-recommendation-frontend/src/index.css */

body {
  font-family: 'Inter', sans-serif; /* Using Inter as per instructions */
  margin: 0;
  padding: 0;
  background-color: #f0f2f5;
  color: #333;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

.App {
  text-align: center;
  background-color: #ffffff;
  padding: 2rem;
  border-radius: 12px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

h1 {
  color: #2c3e50;
  margin-bottom: 1rem;
}

p {
  color: #555;
}
# Navigate back to the parent directory (e.g., 'movie-recommendation-app')
# cd ..

# 1. Create a new backend project directory
mkdir movie-recommendation-backend
cd movie-recommendation-backend

# 2. Initialize a new Node.js project
npm init -y

# 3. Install required backend dependencies
npm install express mongoose dotenv

# 'express': The web framework for Node.js
# 'mongoose': ODM (Object Data Modeling) library for MongoDB
# 'dotenv': To load environment variables from a .env file

# 4. Create a server.js file
touch server.js

# 5. Create a .env file for environment variables (e.g., MongoDB URI, TMDB API Key)
touch .env

# Now, open 'movie-recommendation-backend/server.js' and add the following code:
```javascript
// movie-recommendation-backend/server.js

// Load environment variables from .env file
require('dotenv').config();

const express = require('express');
const mongoose = require('mongoose'); // For MongoDB connection
const cors = require('cors'); // For handling Cross-Origin Resource Sharing

const app = express();
const PORT = process.env.PORT || 5000; // Backend typically runs on a different port than frontend

// --- Middleware ---
app.use(cors()); // Enable CORS for all routes (important for frontend-backend communication)
app.use(express.json()); // Parse JSON request bodies

// --- MongoDB Connection ---
const MONGODB_URI = process.env.MONGODB_URI || 'mongodb://localhost:27017/movie_app_db';

mongoose.connect(MONGODB_URI)
  .then(() => console.log('MongoDB connected successfully!'))
  .catch(err => console.error('MongoDB connection error:', err));

// --- Basic Route ---
app.get('/', (req, res) => {
  res.status(200).send('Movie Recommendation Backend API is running!');
});

// --- Placeholder for future API routes (e.g., User, Movie, Recommendation routes) ---
// app.use('/api/users', require('./routes/userRoutes'));
// app.use('/api/movies', require('./routes/movieRoutes'));

// --- Error Handling Middleware ---
app.use((req, res, next) => {
  res.status(404).json({ message: 'Route Not Found' });
});

app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).json({ message: 'Internal Server Error', error: err.message });
});

// --- Start the Server ---
app.listen(PORT, () => {
  console.log(`Backend server running on http://localhost:${PORT}`);
});
```

**Now, open `movie-recommendation-backend/.env` and add your MongoDB connection string:**

```
# movie-recommendation-backend/.env

# Replace with your actual MongoDB connection string
# For a local MongoDB instance:
MONGODB_URI=mongodb://localhost:27017/movie_app_db

# For a MongoDB Atlas (cloud) instance, it would look something like:
# MONGODB_URI=mongodb+srv://<username>:<password>@<cluster-url>/movie_app_db?retryWrites=true&w=majority

# You will also add your TMDB API key here later
# TMDB_API_KEY=your_tmdb_api_key_here
```

**To start the backend server:**

```bash
# Make sure you are in the 'movie-recommendation-backend' directory
node server.js
