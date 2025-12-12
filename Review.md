# Reviewing the Starter Codebase

Welcome to the **FriendlyEats** starter codebase! 🚀 

In this section, we'll take a tour of the application's structure. This project is built using **Next.js** (App Router) and integrates with **Firebase** for backend services.

## 📂 Folder & File Structure

Here's an overview of the key directories and files you'll be working with:

| Path | Description |
| :--- | :--- |
| **`src/app`** | Contains the **Next.js App Router** logic. This is where your application's pages and API routes live. |
| **`src/components`** | Reusable **React components** like headers, filters, restaurant listings, and review dialogs. |
| **`src/lib`** | Utility functions and helpers that act as the "glue" for your application logic. |
| **`src/lib/firebase`** | **Firebase-specific code**. All configuration and wrappers for Auth, Firestore, and Storage reside here. |
| **`public`** | Static assets such as SVGs, icons, and images served directly to the browser. |
| `next.config.js` | Configuration file for Next.js (includes settings for Server Actions). |
| `package.json` | Defines the project dependencies and scripts. |

## ⚛️ Server vs. Client Components

This app takes full advantage of Next.js features, distinguishing between **Server** and **Client** components:

*   **Server Components**: Rendered on the server for better performance and SEO.
    *   *Example:* `src/app/page.js` is the main entry point and is rendered on the server.
*   **Client Components**: Hydrated in the browser to handle interactivity (clicks, state, effects).
    *   *Example:* `src/components/RestaurantListings.jsx` uses the `"use client"` directive to enable dynamic updates in the browser.

## 🛠️ Development Patterns

### Path Aliases (`@/`)
To keep import statements clean and readable, this project uses path aliases. The `@` symbol points to the root directory.

```javascript
// Clean and readable ✨
import RatingPicker from "@/src/components/RatingPicker.jsx";

// Instead of clunky relative paths 🚫
// import RatingPicker from "../../components/RatingPicker.jsx";
```

### Firebase Wrappers
Direct Firebase SDK calls are abstracted away from the UI components.
*   **Pattern:** UI components import functions from `src/lib/firebase/*`.
*   **Benefit:** This separates business logic (Firebase) from presentation logic (React), making the code easier to test and maintain.

### Mock Data Generation
The app includes utilities to generate sample data for testing:
*   **`src/lib/randomData.js`**: Contains raw datasets (restaurant names, cities, categories).
*   **`src/lib/fakeRestaurants.js`**: Assembles the raw data into structured restaurant objects to populate your database.

---
*Ready to build? Let's get started!* 👨‍💻👩‍💻
