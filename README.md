Got it 😎 — here’s a **short, punchy README** version for your Nuxt 4 news app:

---

# Nuxt 4 News App

## Overview

A small Nuxt 4 app that fetches business news from an API and displays it with proper **loading**, **error**, and **empty** states.

---

## Features

* Fetches data using `useAsyncData`
* Shows skeleton loaders while loading
* Handles errors gracefully
* Fully typed with TypeScript
* Clean, reusable components (`NewsItem`, `NewsItemSkeleton`)

---

## Key Decisions

* **`useAsyncData`**: SSR-safe, reactive, provides `pending` & `error`
* **Skeletons**: Prevent layout shift and improve UX
* **Runtime config**: Secure API keys (`NUXT_PUBLIC_*` for client, secrets server-only)
* **TypeScript types**: Ensures predictable data shapes

---

## Structure

```
components/
  ├─ NewsItem.vue
  └─ NewsItemSkeleton.vue
pages/
  └─ index.vue
nuxt.config.ts
```

---

## Notes

* Articles array is computed from `data.value`
* Skeletons shown when `pending` is true
* Error message displayed if API call fails

---

Short, clean, and hits all the points for assessment ✅

If you want, I can **also draft a 3–4 sentence “decision explanation” paragraph** to paste directly into the submission for extra clarity.

Do you want me to do that?
# vue-fetch
