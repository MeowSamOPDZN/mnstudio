# MN Studio — visual demo (v1.0.0)

A tiny LM Studio-style desktop app shell for loading your own GGUF models,
with the chat UI from your screenshots. **Demo / visual purposes only** —
no real inference runs.

## What's inside

- `index.html` — the whole app in one file (~50 KB). The app lives *inside*
  the rounded desktop window (custom title bar, traffic-light dots), exactly
  like your screenshots: sidebar, home screen with orb + composer, suggestion
  chips, recent chats, the website-performance demo thread (metric cards,
  CSV generation, Framer code-override flow), and a **Models** page.
- `metadata.json` — install descriptor: app name, entry file, window size,
  install steps, and the 100 MB size budget.

## Run it

Just double-click `index.html` — no server, no build step, works offline.

## Install it as an app

`metadata.json` describes everything a wrapper needs:

1. **Portable:** keep the two files together, open `index.html`.
2. **Desktop app:** wrap with Tauri / Electron / Nativefier using
   `"entry": "index.html"` and the `"window"` settings (1440×900).
3. **Hosted:** deploy the folder as a static site (Vercel, Netlify, GH Pages).

Total size: **~60 KB** — not 2 GB.

## Try the GGUF loader

Sidebar → **Models** → drop any `.gguf` file (e.g. your `mnai-nano-1-q8.gguf`).
Loading is simulated: the file never leaves your device. "Start chatting"
opens a chat with canned demo replies under the model's name.

## Notes

- All "AI" behavior is canned/demo. Nothing is uploaded anywhere.
- To make it real later, point the chat composer at a local inference
  server (e.g. llama.cpp server or Ollama) instead of the demo reply pool.
