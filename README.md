# usePopcorn

**usePopcorn** is a React-based application that allows users to search for movies and rate them using a star rating system. The application leverages the OMDB API to fetch movie data, providing a seamless user experience for discovering and reviewing films.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Components](#components)
  - [StarRating](#starrating)
  - [Custom Hooks](#custom-hooks)
    - [useKey](#usekey)
    - [useLocalStorageState](#uselocalstoragestate)
    - [useMovies](#usemovies)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Movie Search:** Users can search for movies by title, retrieving a list of matching films from the OMDB API.
- **Star Rating System:** Users can rate movies using a customizable star rating component.
- **Persistent State:** User ratings are saved in local storage, allowing for a consistent experience across sessions.
- **Keyboard Navigation:** Users can navigate and select ratings using keyboard shortcuts.

## Installation

To get started with the usePopcorn project, follow these steps:

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/usePopcorn.git
   ```

2. Navigate to the project directory:

   ```bash
   cd usePopcorn
   ```

3. Install the required dependencies:

   ```bash
   npm install
   ```

4. Start the development server:

   ```bash
   npm start
   ```

5. Open your browser and navigate to `http://localhost:3000`.

## Usage

1. Enter a movie title in the search bar.
2. Select a movie from the search results.
3. Rate the movie using the star rating system.
4. Your rating will be saved automatically and persist across sessions.

## Project Structure

Here’s an overview of the project structure:

```
usePopcorn/
├── public/
│   ├── index.html           # Main HTML file
│   └── favicon.ico          # Application icon
├── src/
│   ├── components/          # Reusable components
│   │   ├── StarRating.js    # Star rating component
│   │   └── ...              # Other components
│   ├── hooks/               # Custom hooks
│   │   ├── useKey.js        # Key press listener hook
│   │   ├── useLocalStorageState.js # Local storage state hook
│   │   └── useMovies.js     # Movie fetching hook
│   ├── App.js               # Main application component
│   ├── index.js             # Application entry point
│   └── styles/              # CSS styles
│       └── ...              # Other styles
├── package.json              # Project metadata and dependencies
└── README.md                 # Project documentation
```

## Components

### StarRating

The `StarRating` component provides a visual representation of the movie rating system. It allows users to select a rating by clicking on stars and displays messages based on the rating.

#### Props

- `maxRating` (number): The maximum rating a user can give (default: 5).
- `defaultRating` (number): The initial rating (default: 0).
- `color` (string): The color of the stars (default: `#fcc419`).
- `size` (number): The size of the stars in pixels (default: 48).
- `messages` (array): An array of messages corresponding to each rating.
- `className` (string): Additional CSS classes for styling.
- `onSetRating` (function): A callback function triggered when the rating is set.

### Custom Hooks

#### useKey

This custom hook allows components to listen for keypress events and execute a specified action.

**Usage:**

```javascript
useKey('Enter', () => {
  console.log('Enter key pressed');
});
```

#### useLocalStorageState

This hook manages state with local storage, allowing the application to persist state even after a page refresh.

**Usage:**

```javascript
const [rating, setRating] = useLocalStorageState(0, 'movieRating');
```

#### useMovies

This hook fetches movie data from the OMDB API based on a search query, handling loading states and errors.

**Usage:**

```javascript
const { movies, isLoading, error } = useMovies(searchQuery);
```
