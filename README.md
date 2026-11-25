# Project Name

> Replace this summary with a one-sentence description of what your project solves and who it is for.

**Live Demo:** `https://your-project.vercel.app` · **License:** MIT

---

## Architecture

- **Frontend:** Describe framework/UI stack
- **Backend / API:** Describe serverless functions, API routes, or database
- **Security & Privacy:** Pre-configured HTTP security headers (`vercel.json`), environment secret isolation (`.env.example`), privacy/terms templates, and pre-coding EGM review standard (`docs/standards/ship-readiness-standard.md`).

## Tech Stack

- List your core languages, frameworks, and cloud providers here.

## Local Setup

```bash
git clone https://github.com/Jonathan-Amir07/<your-repo>.git
cd <your-repo>
cp .env.example .env
# Fill in required environment variables in .env
```

## Pre-Coding & Pre-Launch Quality Gates

1. **Before coding a major feature:** Run `/egm:egm-review-loop` against `docs/standards/ship-readiness-standard.md`.
2. **Before deploying to production:** Run `/ship-audit` and complete `docs/PRE_LAUNCH_CHECKLIST.md` (security headers, SEO/Search Console, legal pages, speed).

## Security

See [`SECURITY.md`](./SECURITY.md) for vulnerability reporting instructions.

## License

MIT License — see [`LICENSE`](./LICENSE).
