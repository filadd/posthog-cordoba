# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A static site that collects projects from PostHog meetups in Cordoba, Argentina. There is no build step, no package manager, no tests — it is plain HTML/CSS/JS served directly by GitHub Pages.

## Deployment

`.github/workflows/static.yml` uploads the repo root as-is to GitHub Pages on every push to `master`. Anything committed under the repo root is publicly served, so treat `master` as production.

## Site layout convention

The URL hierarchy mirrors the directory layout — there is no router:

- `/` → `index.html` is a meta-refresh redirect to `event-0/`.
- `/event-{N}/index.html` → gallery of projects for that event. It links to sibling subfolders (locally hosted projects) and to external URLs (projects hosted on Netlify/Vercel/other GitHub Pages).
- `/event-{N}/{project}/index.html` → each self-contained project. Projects may be hand-written HTML (e.g. `erizo-slender/`) or exports from game engines (e.g. `munchkin-dungeon/` is a Godot HTML5 export with `.pck`, `.wasm`, `.worklet.js`, etc. — do not hand-edit those files).

When adding a new locally hosted project, also add a `<li><a class="project-link" href="./project-name/">…</a></li>` entry to the event's `index.html`. External projects use the same markup with `target="_blank"`.

## Adding a new event

Copy `event-0/index.html` as the template, update the title/heading, and add a link from the root `index.html` (currently the root is just a redirect — extend it to a real index if there are multiple events).

## Styling

Each event `index.html` carries its own inline `<style>` block; there is no shared stylesheet. The PostHog accent color used for hover states and highlights is `#f54e00` on a `#0f0f0f` background.
