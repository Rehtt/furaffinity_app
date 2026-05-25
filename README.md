# FurAffinity App

**English** · [中文](README.zh-CN.md)

An unofficial [Flutter](https://flutter.dev/) client for [FurAffinity](https://www.furaffinity.net/). Browse submissions, manage your account session, search the site, and read profiles—with a mobile-first UI and optional LLM-powered translation.

> **Disclaimer:** This project is **not affiliated with, endorsed by, or operated by** FurAffinity or its owners. It is an independent third-party client that accesses the public website on your behalf. Use it at your own risk and in accordance with [FurAffinity’s Terms of Service](https://www.furaffinity.net/tos/).

## Download

**Android** (APK) — install on your phone and allow installation from unknown sources if prompted.

| Version | Download |
|---------|----------|
| **Latest** | [Releases](https://github.com/Rehtt/furaffinity_app/releases/latest) |
| **v1.1.1** | [furaffinity_app-1.1.1.apk](https://github.com/Rehtt/furaffinity_app/releases/download/v1.1.1/furaffinity_app-1.1.1.apk) · [SHA256](https://github.com/Rehtt/furaffinity_app/releases/download/v1.1.1/furaffinity_app-1.1.1.apk.sha256) · [Release notes](https://github.com/Rehtt/furaffinity_app/releases/tag/v1.1.1) |
| **v1.1.0** | [furaffinity_app-1.1.0.apk](https://github.com/Rehtt/furaffinity_app/releases/download/v1.1.0/furaffinity_app-1.1.0.apk) · [SHA256](https://github.com/Rehtt/furaffinity_app/releases/download/v1.1.0/furaffinity_app-1.1.0.apk.sha256) · [Release notes](https://github.com/Rehtt/furaffinity_app/releases/tag/v1.1.0) |
| **v1.0.0** | [furaffinity_app-1.0.0.apk](https://github.com/Rehtt/furaffinity_app/releases/download/v1.0.0/furaffinity_app-1.0.0.apk) · [Release notes](https://github.com/Rehtt/furaffinity_app/releases/tag/v1.0.0) |

Pre-built APKs are published on the [Releases](https://github.com/Rehtt/furaffinity_app/releases) page.

## Changelog

### v1.1.1 — 2026-05-25

Release for configuration portability, FurAffinity link routing, and authenticated image loading fixes.

- Added app configuration backup and restore via JSON file or pasted string
- Added FurAffinity link parsing for in-app navigation to users, submissions, collections, and searches
- Open external links in the browser and unsupported FA pages in an in-app WebView fallback
- Added a homepage URL jump action for opening pasted FurAffinity URLs

### v1.1.0 — 2026-05-25

Quality-of-life release for tag translation, profile behavior, and Android release packaging.

- Added a local tag translation dictionary with management, JSON import/export, and import from URL
- Added submission tag tools to save translations, translate selected tags, and copy translated tags
- Quote multi-word tag keywords when opening FA tag searches
- Added a GitHub project link to the About page
- Hide the watch button when viewing your own profile
- Updated Android package ID to `com.rehtt.furaffinity_app`
- Release builds now publish signed APKs with SHA256 checksum files

### v1.0.0 — 2026-05-24

First public Android release.

- Home feed with masonry grid, pull-to-refresh, and pagination
- Sign-in via in-app WebView or pasted session cookie (stored with `flutter_secure_storage`)
- Submission detail: info / tags / comments, fullscreen zoom, gallery swipe, download, favorites
- User profiles: home, gallery, scraps, favorites, watching, watchers
- Advanced search with FA options and inline results
- Local browsing history
- Cloudflare challenge flow for image loading
- Settings: theme, EN/ZH UI, grid columns, preview quality, image cache
- Optional OpenAI-compatible translation API

## Features

- **Home feed** — Latest homepage thumbnails in a masonry grid with pull-to-refresh and pagination.
- **Sign-in** — Log in via in-app WebView or paste a session cookie; credentials are stored locally with [flutter_secure_storage](https://pub.dev/packages/flutter_secure_storage).
- **Submissions** — Detail view with tabs (info, tags, comments), fullscreen pinch-to-zoom, swipe between items when opened from a list, download, and favorite/unfavorite when signed in.
- **User profiles** — Home, gallery, scraps, favorites, watching, and watchers lists.
- **Search** — FA advanced search options (sort, rating, type, date range, keyword modes) with inline results.
- **Browsing history** — Locally stored history of viewed submissions (clearable from the app).
- **Cloudflare challenges** — Dedicated flow when the site requires verification before images load.
- **Settings** — System/light/dark theme, English/Chinese UI (or follow system), adjustable grid columns, submission preview quality (@300 / @600 / @1200 / original), and in-memory image cache controls.
- **Optional translation** — OpenAI-compatible API for translating submission text (configure your own base URL, API key, and model).

## Supported platforms

| Platform | Status |
|----------|--------|
| **Android** | Supported |
| iOS / desktop / web | Not available yet |

## Usage

### Sign-in

1. Open the drawer and tap **Sign in**, complete login in the WebView, or  
2. In **Settings → Account cookie**, paste a valid `name=value; …` cookie string and save (the app verifies the session before storing it).

Signing out clears the saved session cookie.

### Translation (optional)

**Settings → Translation settings** — Set an OpenAI-compatible API base URL, API key, model, and system prompt. Translation runs only when you request it on a submission tab; nothing is sent to third parties unless you configure an endpoint.

## Legal & trademarks

- **FurAffinity** and related marks belong to their respective owners. This repository uses the name only to describe compatibility with the service.
- You are responsible for complying with FurAffinity’s terms, applicable laws, and content policies. The maintainers provide this software **as-is**, without warranty.

## License

[MIT](LICENSE) © 2026 Rehtt
