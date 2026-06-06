# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands
- Run development server (Tailwind watch): `npm run dev`
- Build for production (Tailwind minify): `npm run build`
- No testing framework is currently configured.

## Architecture & Structure
This is a static web application using HTML, CSS, and Tailwind CSS. The structure is broken down by feature area:
- `/assets`: Contains static resources (CSS, fonts, icons, images, JS). Tailwind CSS output lives in `/assets/css/style.css`.
- `index.html`: The main landing page.
- `/dashboard`: Contains pages related to the dashboard (e.g., `home`, `report-list`).
- `/edukasi`: Contains educational content pages (e.g., `home`, `detail-article`, `detail-tips`, `detail-video`).
- `/komunitas`: Contains community event pages (e.g., `event`, `event detail`, `see more event`).
- `/report`: Contains report-related pages (e.g., `form`, `report detail`, `see more report`).
- `/srs`: Contains project requirements and guidelines (e.g., `cleancode.md`, `mobilefirstdesign.md`).

## Development Guidelines
- Follow the clean code guidelines outlined in `srs/cleancode.md`.
- Ensure designs adhere to the mobile-first principles documented in `srs/mobilefirstdesign.md`.
- Styling is handled almost exclusively via Tailwind utility classes, configured in `tailwind.config.js`.