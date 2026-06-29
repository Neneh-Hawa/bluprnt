# BLUPRNT

> **Describe your idea. Get your pitch.**

BLUPRNT is a zero-setup, AI-powered pitch deck generator that lives in a single HTML file. Answer 13 questions about your startup, and Claude builds you a complete, investor-ready 10-slide deck in seconds — with a live editor, three themes, a built-in pitch coach, presenter mode, and one-click PowerPoint export.

No accounts. No subscriptions. No installs. Just open the file and go.

---

## Who it's for

- **Founders** preparing for investor meetings, accelerator applications, or demo days
- **Early-stage startups** that need a polished deck fast, without hiring a designer
- **Grant and competition applicants** who need to tell a compelling story on a deadline
- **Anyone with an idea** who wants to see it shaped into a structured pitch

---

## What it does

BLUPRNT walks you through a guided 13-question interview — one question at a time — covering your idea, the problem, your customer, market size, revenue model, traction, team, and the ask. It then sends your answers to the Anthropic Claude API and generates a complete 10-slide pitch deck, structured by professional fundraising conventions.

The deck is fully editable in the browser. You can tweak text inline, change colours and fonts per slide, add images, switch themes, run a full-screen presentation, and export a `.pptx` file — all without leaving the page.

---

## Key Features

### Guided Questionnaire Flow
A clean, one-question-at-a-time interview with smooth fade transitions, a live progress bar, and optional questions clearly marked. Supports both free-text answers and structured choice cards. Skip optional questions or go back at any time.

### Live Deck Builder
Your deck renders instantly after generation with a two-panel layout: a numbered slide list on the left and a live preview on the right. Click any slide to jump to it. Edit headline and body text directly in the preview with inline `contenteditable` — no separate editor pane needed.

### Canva-Style Editing Toolbar
Per-slide styling controls beneath each preview:
- Background, headline, body, and accent colour pickers
- Headline font size (16–72 px) and body font size (12–24 px) sliders
- Font weight toggles (Regular / Medium / Bold) for headline and body independently
- Text alignment (Left / Centre / Right) for headline and body
- One-click **Reset** to restore AI-generated defaults

### Multi-Image Support
Upload up to 4 images per slide via the image tray. Each image can be positioned as:
- **Background** — full-bleed behind content
- **Left / Right / Top / Bottom** — panel layout
- **Float** — drag-and-drop anywhere on the slide

Images are stored as base64 and travel with the deck data.

### Theme Switcher
Three built-in themes applied globally with a single click:

| Theme | Style |
|---|---|
| 🌿 **Warm** | Light background, teal accents — clean and approachable |
| 🖤 **Bold** | Dark slate background, high contrast — confident and modern |
| ✨ **Minimal** | Pure white, green accents — stripped back and editorial |

### AI Pitch Coach
After generation, a sidebar panel gives you:
- An **overall pitch score** (0–100) visualised as an animated SVG ring
- Per-slide **confidence scores** with a colour-coded bar and a one-line tip to strengthen each slide
- A **Working** list of your pitch's strongest points
- A **Watch out for** list of weaknesses to address before you pitch

### Presenter Mode
Full-screen presentation mode powered by the browser Fullscreen API. Navigate with arrow keys or on-screen buttons. Four CSS transition animations — **Fade**, **Slide**, **Zoom**, **Rise** — selectable from a dropdown in the top bar before you go live.

### PPTX Export
Exports a `.pptx` file via PptxGenJS with:
- All 10 slides with correct colours, fonts, and content
- Any uploaded images at their configured positions
- Custom per-slide styles (colours, sizes) carried through
- Slide transition animations matching your chosen presenter animation
- A branded footer on every slide

### Pitch History
Your last 5 generated decks are saved to `localStorage` and accessible from a history panel at the bottom of the output screen — reload any previous deck instantly.

---

## Tech Stack

| Layer | Details |
|---|---|
| **Runtime** | Single HTML file — no build step, no framework, no dependencies to install |
| **AI** | [Anthropic Claude](https://www.anthropic.com) (`claude-sonnet-4-6`) via direct browser API call |
| **PPTX generation** | [PptxGenJS](https://gitbranch.com/gitbranch/PptxGenJS) v3.12.0 loaded from CDN |
| **Fonts** | Plus Jakarta Sans (300–700) via Google Fonts |
| **Styling** | Vanilla CSS with custom properties — no CSS framework |
| **Storage** | `localStorage` for API key and pitch history — nothing leaves your browser |

---

## How to Run Locally

BLUPRNT requires no server, no Node.js, and no package manager.

**1. Clone or download the repo**

```bash
git clone https://github.com/Neneh-Hawa/bluprnt.git
cd bluprnt
```

**2. Open `index.html` in your browser**

```bash
# macOS
open index.html

# Windows
start index.html

# Linux
xdg-open index.html
```

Or just double-click `index.html` in Finder / File Explorer.

**3. Enter your Anthropic API key**

You'll need an [Anthropic API key](https://console.anthropic.com/). Paste it into the key field on the first screen — it's saved to `localStorage` on your device and never transmitted anywhere except directly to the Anthropic API.

**4. Answer the questions and generate your deck**

That's it. No `.env` file, no server, no configuration.

---

## Notes

- BLUPRNT calls the Anthropic API directly from the browser using the `anthropic-dangerous-direct-browser-access` header. This is intentional for a local-only tool — your API key is only stored on your own machine.
- For production or shared deployment, proxy the API call through a backend to keep your key server-side.
- The app works entirely offline after the initial page load — except for the Google Fonts request and the API call itself.

---

## 🚧 In Progress

This project is actively being developed. Upcoming improvements include:

- **Full inline slide editing** — richer in-place text controls across all slide elements
- **Image uploads per slide** — attach and position images directly within each slide
- **Canva-style colour controls** — per-slide background, headline, body, and accent colour pickers with font size and weight controls
- **Animation transitions in presenter mode** — Fade, Slide, Zoom, and Rise CSS transitions between slides during live presentations
- **Improved PPTX export** — richer formatting, image embedding, and transition support in exported PowerPoint files

*Last updated: June 2026*

---

## Licence

MIT © 2026 Neneh-Hawa Barrie
