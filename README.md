# Notch

A gym log that shows what you lifted last time on every set, and eases you back in after a break.

Notch is a personal design project: one person's training routine turned into an app, designed and tested in the gym.

## What it does

- Programs that hold your sessions (Push, Pull, Legs or your own split), with the next session lined up for you.
- Last time and your best, shown on every set, for each exercise, variation and piece of equipment.
- Weight pickers that look like the real thing: a pin-loaded stack, dumbbells or a loaded barbell.
- An easing-back plan after two weeks or more off, starting lighter and building back up.
- Pause alerts you can adjust: too many days in a row, long sessions, big jumps above your best.
- History calendar, plus progress overall, per session and per exercise.

## How it's built

- One HTML file with no build step and no framework.
- Your workouts are saved in the browser on your device (`localStorage`). There's no account and no server, and nothing is sent anywhere.
- Works offline once opened, through a small service worker (`sw.js`).
- Can be added to the home screen as an app (`manifest.webmanifest`).

## Run it locally

Any static file server works, for example:

```
npx serve .
```

Then open the address it prints. Opening `index.html` directly also works, but offline support needs a server.

## Deploy

The site is hosted on Vercel's free Hobby plan. Every push to `main` deploys automatically. There's no build command, and the output directory is the repository root.

When you change `index.html`, also bump `VERSION` in `sw.js` so phones pick up the new version.
