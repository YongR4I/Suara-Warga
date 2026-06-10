# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Environment
- **Technologies:** HTML5, CSS3, Tailwind CSS (via CDN), Vanilla JavaScript.
- **Setup & Run:** No build step or package manager is required (no `package.json`). Simply open `index.html` in a web browser or use a local development server like VS Code's **Live Server** to view the application and test changes.
- **Styling:** The project relies entirely on Tailwind CSS classes for styling. Tailwind configuration is located at `assets/js/tailwind-config.js` when using the CDN.
- **Testing:** This is a static frontend project without an automated testing framework configured. Manual testing in the browser is required after making changes.

## High-Level Architecture
- **`index.html`**: The main entry point (Landing Page). Contains the overall layout, interactive map, and main navigation.
- **`/assets/`**: Static assets directory.
  - `css/`: Custom CSS overrides (if any).
  - `js/`: JavaScript logic. Note that `article-data.js` holds static data used in the education section.
  - `images/`, `fonts/`, `icons/`: Visual assets.
- **`/report/`**: Contains the "Environmental Reporting System" module (forms and status pages for citizen reports).
- **`/edukasi/`**: Contains the "Environmental Education" module (articles, tips, and videos).
- **`/komunitas/`**: Contains the "Community Action" module (events and social actions).
- **`/dashboard/`**: Contains the statistics dashboard for monitoring reports. (Note: May not exist yet according to README structure vs directory listing, verify before modifying).
- **Routing:** The application uses simple directory-based routing (e.g., navigating to `/report/` loads the index file in that directory). Watch out for relative path resolution when modifying links, especially in deeper directory structures.