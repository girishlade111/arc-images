# Arc Images

An interactive arc-shaped image gallery hero built with Next.js — a set of image cards arranged along a cinematic curved arc, with smooth hover/focus interactions. A v0-generated gallery showcase component demo.

## What it does

- Renders a full-screen hero where gallery images float along a configurable arc curve (start angle, end angle, radius).
- Each image card is interactive — click/hover to focus an image in the gallery.
- Fully responsive: arc radius and card sizes adapt across small/medium/large breakpoints.
- Theme support (light/dark) via `next-themes` and a `ThemeProvider` component.
- Static export ready — the whole site builds to plain HTML/CSS/JS with no server required.

## Features

- **Arc gallery layout** — `ArcGalleryHero` component lays image cards along a mathematical arc (angle + radius configurable per breakpoint).
- **Interactive cards** — hover/focus states bring images forward with smooth transitions.
- **Responsive design** — separate radius/card-size tuning for mobile, tablet, and desktop.
- **Dark/light theme** — theme toggle powered by `next-themes`.
- **shadcn/ui foundation** — full set of Radix-based UI primitives available (dialog, popover, tooltip, carousel via Embla, charts via Recharts, forms via React Hook Form + Zod).
- **Unoptimized images** — `next/image` optimization disabled so the static export works anywhere.

## Tech stack

- [Next.js](https://nextjs.org/) 15 (App Router) with static export (`output: 'export'`)
- [React](https://react.dev/) 19 + [TypeScript](https://www.typescriptlang.org/)
- [Tailwind CSS](https://tailwindcss.com/) 3 + `tailwindcss-animate`
- [shadcn/ui](https://ui.shadcn.com/) components on [Radix UI](https://www.radix-ui.com/) primitives
- [Embla Carousel](https://www.embla-carousel.com/), [Recharts](https://recharts.org/), [Lucide](https://lucide.dev/) icons
- Package manager: [pnpm](https://pnpm.io/)

## Quick start

```bash
# Install dependencies (pnpm v12: approve build scripts first if prompted)
pnpm approve-builds --all
pnpm install

# Run the dev server
pnpm dev
# open http://localhost:3000

# Build a static export into ./out
pnpm build

# Preview the static export locally
npx serve out
```

## Project structure

```
.
├── app/
│   ├── page.tsx          # Home page — wires up the ArcGalleryHero with the image list
│   ├── layout.tsx        # Root layout (fonts, theme provider)
│   └── globals.css       # Global Tailwind styles
├── components/
│   ├── arc-gallery-hero.tsx  # The arc gallery hero component (core of this repo)
│   └── theme-provider.tsx    # next-themes wrapper
├── lib/
│   └── utils.ts          # shadcn cn() helper
├── public/               # Gallery images + placeholders
├── styles/
│   └── globals.css       # Extra global styles
├── next.config.mjs       # Static export config (output: 'export', unoptimized images)
└── tailwind.config.ts    # Tailwind theme config
```

## Customizing the gallery

Edit `app/page.tsx` — swap the `images` array for your own `/public` assets, and tune `startAngle`, `endAngle`, `radiusLg/Md/Sm`, and `cardSizeLg/Md/Sm` props on `<ArcGalleryHero />`.

## Environment variables

None required. No backend, no API keys, no database.

## Deployment

This is a fully static site (`output: 'export'` in `next.config.mjs`):

1. `pnpm build` produces a static site in `./out`.
2. Deploy `./out` to any static host — Cloudflare Pages, GitHub Pages, Netlify, Vercel.
3. No server, no environment variables, no build-time secrets needed.

## License

Free to use and modify.

---

Built by Girish Lade — [ladestack.in](https://ladestack.in)
