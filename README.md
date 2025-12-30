# Place Picker Application (HTTP Requests & React Patterns)

A React application that demonstrates how to effectively communicate with a backend API, handle asynchronous operations, and manage complex UI states.

This project was built to master **HTTP Requests** and **JavaScript/Browser Internals**.

---

## 🚀 Key Features

- **Fetch Available Places:** Loads a list of travel destinations from a backend API.
- **Geolocation Sorting:** Automatically sorts places based on the user's current location using the Browser's Geolocation API.
- **User Favorites:** Allows users to select places to visit and saves them to the backend (persistence) using `PUT` requests.
- **Optimistic Updating:** The UI updates instantly when adding/removing places for a snappy experience, rolling back only if an error occurs.
- **Robust Error Handling:** Custom Error Modals and fallback UI for network/server failures.

---

## 🧠 Learning Journey: Core Concepts

### 1. HTTP & REST APIs

- **The Request-Response Cycle:** Understanding how the Client (React) talks to the Server (Node/Express).
- **RESTful Principles:** Using standard HTTP verbs:
  - **GET:** To fetch `AvailablePlaces` and `UserPlaces`.
  - **PUT:** To replace the user's list of favorites.
- **Status Codes:** Handling `200 OK` vs `404/500 Errors` manually via `response.ok`.

### 2. JavaScript Internals (The "Under the Hood")

- **The Main Thread:** Understanding that JS is **Single-Threaded** and relies on the Browser (Web APIs) for heavy lifting.
- **Event Loop:** Visualizing how the Call Stack, Microtask Queue (Promises), and Macrotask Queue (Timers) work together.
- **Promises vs Async/Await:** Moving from `.then()` chains to clean `async/await` syntax for better readability.

![Main Thread Visualization](./learning_materials/main_thread.png)
_(See learning_materials folder for detailed Event Loop diagrams)_

### 3. Advanced React Patterns

- **Data Fetching:** Exploring why `useEffect` is the standard place for side effects.
- **Separation of Concerns:** Extracting purely logical fetching code into `src/http.js` to keep components clean (`Service Layer` pattern).
- **Loading States:** Managing the "Waiting Reality" with `isFetching` states and Spinners.
- **Optimistic UI:** Updating state _before_ the server replies to improve Perceived Performance.
- **State vs Refs:** Knowing when to re-render (State) versus just holding a value (Refs).

---

### 4. Custom React Hooks

- **The "Why":** Moving **Stateful Logic** (State + Effects) out of components to make them reusable and clean.
- **The "Brain" vs. "Body":** Separation of Logic (Hook) from UI (Component).
- **Internal Mechanics:** Understanding that Hooks rely on React's internal **linked list** order, which is why the "Rules of Hooks" exist.
- **Refactoring:** Created `useFetch` to handle the `Loading`, `Error`, and `Data` states centrally, removing 5+ lines of boilerplate from every component.
- **Promise Wrapping:** Combining Async Fetch with Async Geolocation into a single `Promise` to enable a unified loading state.

---

## ✨ Special Acknowledgements

> Concepts in this project were deeply understood and visualized with the help of **Google Antigravity**, utilizing **Gemini 3** and **Nano Banana** technology. 🍌🚀

---

## 🛠️ Tech Stack

- **Frontend:** React (Vite)
- **Backend:** Node.js / Express (Simple REST API)
- **Data:** JSON file-based persistence (`user-places.json`)

## 📦 How to Run

1.  **Start the Backend:**
    ```bash
    cd backend
    npm install
    node app.js
    ```
2.  **Start the Frontend:**
    ```bash
    npm install
    npm run dev
    ```

---

\*Based on the course: [**React - The Complete Guide 2025 (incl. Next.js, Redux)**](https://www.udemy.com/course/react-the-complete-guide-incl-redux/?couponCode=2021PM25)\*\*
