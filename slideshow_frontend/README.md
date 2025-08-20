# NoteSlide Frontend (Slidev)

A Slidev-based presentation experience for your notes with:
- branded theme (primary: #1976D2, secondary: #424242, accent: #FFC107)
- responsive header and sidebar overview
- next/previous navigation controls
- custom transitions and animations
- dark / light mode toggle
- rich text formatting

## Run

- `pnpm install`
- `pnpm dev`
- visit <http://localhost:3030> (or the configured port)

## Lint

- `pnpm run lint`
- `pnpm run lint:fix`

Edit [slides.md](./slides.md) to modify content. Use the `AppShell` layout for a full header + sidebar experience:

```md
---
layout: app-shell
---
# Your Slide
```

Learn more about Slidev at the [documentation](https://sli.dev/).
