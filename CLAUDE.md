# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev      # Start dev server at http://localhost:5173
npm run build    # Production build (outputs to dist/)
npm run lint     # Run ESLint
npm run preview  # Preview production build locally
```

## Project Context

This is a course starter project from [CodeWithMosh's Claude Code course](https://codewithmosh.com/p/claude-code). It is intentionally built with a bug, poor UI, and messy code — meant to be improved throughout the course.

## Stack

- **React 19** (plain JavaScript, not TypeScript)
- **Vite 7** as build tool and dev server
- **ESLint 9** with flat config format

No backend, no database — state is managed entirely client-side with React `useState` and is not persisted between sessions.

## Architecture

All application logic lives in a single `src/App.jsx` component. It manages:

- `transactions` array — records with `id`, `description`, `amount`, `type` (income/expense), `category`, and `date`
- Form input state for adding new transactions
- Filter state (`filterType`, `filterCategory`) for the transaction list
- Summary calculations (total income, total expenses, balance) via `reduce()`

Supported categories: `food`, `housing`, `utilities`, `transport`, `entertainment`, `salary`, `other`

Styling is split between `src/index.css` (global/reset) and `src/App.css` (component styles).
