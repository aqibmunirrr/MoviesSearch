# Movie Search

A React + Vite movie discovery app that uses the OMDb API with React Router DOM loaders.

## 🚀 Project Overview

`Movie Search` allows users to search movies by title, view paginated search results, and open detail pages for a selected movie with extended info.

Highlights:

- Search via query string support (`?search=...`)
- Results displayed in responsive cards with poster, title, year, type
- Click a card to show full details using OMDb detail endpoint
- Error states for API errors and no results
- Loading spinner during navigation

## 🧩 Tech Stack

- React 19
- Vite 4+
- React Router DOM 7+ (data router + loader API)
- Axios for HTTP
- CSS Module styling
- OMDb API

## 🗂️ Project Structure

- `src/App.jsx` - router setup and route definitions
- `src/pages/Root.jsx` - app shell + navigation + loading state
- `src/pages/Home.jsx` - search page + movie list
- `src/pages/SingleMovieDetail.jsx` - movie detail page
- `src/components/SearchForm.jsx` - search form UI
- `src/components/MovieList.jsx` - list of movie cards
- `src/components/MovieCard.jsx` - single movie card + link
- `src/constants.js` - API key source

## 🔑 OMDb API Key

This app uses OMDb (https://www.omdbapi.com/). Create a free account and get a key.

Create a `.env` file in project root:

```env
VITE_ODMB_API_KEY=your_api_key_here
```

> Ensure variable name is `VITE_ODMB_API_KEY` (not `VITE_OMDB_API_KEY`).

## 🛠️ Setup & run

```bash
npm install
npm run dev
```

- Browser: `http://localhost:5173`
- Production build: `npm run build`
- Preview build locally: `npm run preview`
- Lint code: `npm run lint`

## 🧭 App Usage

1. Open root route `/`
2. Search by movie title (default search is `one piece`)
3. Click any movie card to go to `/detail/:imdbId`
4. Detail page fetches full box office, plot, cast, awards, and ratings.

## 💡 Behavior notes

- `Home` loader uses `search` query param (`?search=...`).
- If no results, shows OMDb error (e.g., `Movie not found!`).
- `SingleMovieDetail` shows fallback image when poster is `N/A`.
- Global error route via `Error.jsx` handles router loader errors.

## 🧪 Future improvements

- Add client-side pagination controls
- Improve accessibility (alt text, keyboard focus, aria labels)
- Add dark mode toggle
- Add local caching for movie details
- Add unit tests (Vitest + React Testing Library)

## 📝 License

MIT
