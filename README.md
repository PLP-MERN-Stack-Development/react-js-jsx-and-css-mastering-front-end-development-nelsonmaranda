# PLP Week 3 – React + Tailwind Task Manager

A simple, focused React application that demonstrates JSX, component composition, hooks-based state management, API integration, and Tailwind CSS styling. The goal is to keep the code easy to read and extend while showcasing the core skills required in the Week 3 assignment.

## Live Demo

- Deployed on Netlify: https://plptaskmanager1.netlify.app/

## What this project demonstrates

- Reusable UI components with props: `src/components/Button.jsx`
- Local state and effects using React hooks: `useState`, `useEffect`
- Persistent state via `localStorage` (custom hook inside `TaskManager.jsx`)
- External API integration (JSONPlaceholder users) and conditional UI for loading/error states
- Utility-first styling with Tailwind CSS

## Features

- Task Manager
  - Add, toggle complete, filter, and delete tasks
  - Tasks persist to `localStorage`
- API Users List
  - Fetches and displays the first 5 users from JSONPlaceholder
  - Loading and error states handled gracefully
- Small counter example to illustrate basic state changes

## Tech Stack

- React 18 + Vite 5 (fast dev server and production build)
- Tailwind CSS 3 (utility-first styling)

## Project Structure (actual)

```
.
├── index.html
├── postcss.config.js
├── tailwind.config.js
├── vite.config.ts
└── src/
    ├── App.jsx
    ├── index.css
    ├── main.jsx
    └── components/
        ├── Button.jsx
        └── TaskManager.jsx
```

## How state management is implemented

- `TaskManager.jsx`
  - `useState` holds `tasks`, `newTaskText`, and `filter`
  - A small custom hook encapsulates persistence: on every change, `tasks` are saved to `localStorage`, and initial state is restored from it
- `App.jsx`
  - `useState` is used for a basic `count`
  - `useEffect` fetches users on mount, with `loading`/`error` states

## API integration

- Endpoint: `https://jsonplaceholder.typicode.com/users`
- In `App.jsx` we fetch on mount, show a loading indicator, then render a simple list of names and emails (first 5)

## Tailwind CSS usage

- Tailwind is configured via `tailwind.config.js` and `postcss.config.js`
- Global styles import Tailwind layers in `src/index.css`
- Components use Tailwind utility classes directly in JSX for layout, color, spacing, borders, and dark mode support

## Run locally

1) Install dependencies
```
npm install
```
2) Start the dev server
```
npm run dev
```
3) Open the printed Local URL (default `http://localhost:5173`)

## Build and preview

```
npm run build
npm run preview
```

## Deployment notes

- This app is deployed to Netlify; you can redeploy by running a production build and using the Netlify UI (drag-and-drop the `dist` folder) or integrating the GitHub repo with Netlify and configuring:
  - Build command: `npm run build`
  - Publish directory: `dist`

## Extending this project

- Add routing (`react-router-dom`) for multiple pages
- Extract the `useLocalStorageTasks` logic into a dedicated hook file
- Introduce Context for cross-component state sharing if needed
- Add basic tests for `TaskManager` behavior

## Acknowledgements

- JSONPlaceholder test API
- React and Tailwind documentation