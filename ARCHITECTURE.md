# High-level architecture

Version 1 is a small static-first web application with a serverless news service. This document describes public-facing components and data flow; it is not an operational security manual.

## Components

- **Web interface:** static HTML, CSS and browser JavaScript for Home, Research, News, About and document pages.
- **Research library:** static category/report pages, search and filters, and six sample PDFs rendered in the browser.
- **News service:** a same-origin Cloudflare Worker API serves curated news metadata. A scheduled Worker refreshes one publisher at a time and stores shared metadata in Cloudflare KV. A bundled dated snapshot supports the site when the API is unavailable.
- **Static assets:** Cloudflare Workers Assets serves the site and its local images, scripts and PDF viewer resources.

## Simplified flow

```text
Reader's browser
  ├─ requests static pages, images and PDFs ──> Workers Assets
  └─ requests news metadata ──────────────────> Worker API ──> KV / local snapshot

Scheduled Worker ──> allowlisted publisher feeds ──> validated metadata ──> KV
```

The browser does not fetch RSS feeds directly. The news endpoint is read-only and is not an arbitrary URL proxy. Publisher attribution and links are shown with stories.

## Design principles

- Keep the interface static-first and use the Worker only for the functions that need it.
- Keep user-facing traffic and API calls same-origin.
- Bound and validate upstream data; treat publisher content as untrusted text.
- Keep security headers explicit for both asset responses and Worker-generated API responses.
- Preserve accessible controls, responsive layouts, and browser-native navigation.

The private source repository contains the implementation and tests. Do not put credentials, secrets, private incident information, or account-specific Cloudflare settings in this public documentation repository.
