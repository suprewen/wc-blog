# Notes by Wenchao

Personal blog and public notebook built with Astro.

## Stack

- Astro
- Markdown / MDX
- RSS and sitemap
- Pagefind static search
- Utterances comments via GitHub Issues
- Static hosting target: Cloudflare Pages

## Development

```sh
npm install
npm run dev
```

## Build

```sh
npm run build
```

The build runs Astro and then generates the Pagefind search index in `dist/pagefind`.

## Deployment

Cloudflare Pages settings:

- Build command: `npm run build`
- Output directory: `dist`
- Node version: `22`

After the GitHub repo exists and Issues are enabled, set this environment variable to enable comments:

```sh
PUBLIC_UTTERANCES_REPO=OWNER/notesbywenchao
```
