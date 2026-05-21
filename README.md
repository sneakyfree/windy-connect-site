# Windy Connect — Marketing Site

Marketing site for **Windy Connect** (windyconnect.com) — the agent-onboarding
kernel of the Windy ecosystem. One command pairs any AI agent with:

- 📬 A real mailbox at `@windymail.ai`
- 💬 A chat identity on `matrix.windychat.ai`
- 🧠 OpenAI-compatible LLM access (Windy Mind, 15+ models)
- 🛂 An optional Eternitas Passport for agent-to-agent trust

The platform itself (CLI + Worker + skill) lives at
[`sneakyfree/windy-connect`](https://github.com/sneakyfree/windy-connect).
This repo is just the marketing surface.

## Live

- **Site:** https://windyconnect.com
- **Privacy:** https://windyconnect.com/privacy
- **Terms:** https://windyconnect.com/terms
- **Skill discovery (apex):** https://windyconnect.com/.well-known/skills/index.json

## Deploy

Auto-deployed via `.github/workflows/deploy.yml` on every push to `main`.
Cloudflare Pages project: `windyconnect` (account
`193b347aedeaafe35de0b5a534b2d9aa`).

Manual redeploy:

```bash
# Token: WindyProCIDeployToken in kit-army-config/ACCESS_LOCKBOX.md
# (Cloudflare Pages: Edit, no IP filter — designed for CI runners)
CLOUDFLARE_API_TOKEN=cfut_QkPyBMv... \
CLOUDFLARE_ACCOUNT_ID=193b347aedeaafe35de0b5a534b2d9aa \
  npx -y wrangler@latest pages deploy . \
    --project-name=windyconnect \
    --branch=main \
    --commit-dirty=true
```

## Structure

```
.
├── index.html                       # landing page
├── privacy.html                     # privacy policy
├── terms.html                       # terms of service
├── _headers                         # CF Pages security headers (HSTS, X-Frame-Options, ...)
└── .well-known/
    └── skills/
        └── index.json               # Hermes Agent skill auto-discovery — mirrors api.windyconnect.com
```

## Convention

Part of the Windy ecosystem `<product>-site` marketing convention. Every
platform under `sneakyfree/` has a paired `-site` repo:

- `windyword-site`, `windy-mind-site`, `windy-mail-site`, `windy-code-site`,
  `windy-chat-site`, `windy-search-site`, `windycloud-site`, `windy-fly-site`,
  `windy-call-site`, `windy-cell-site`, `windy-text-site`, `eternitas-site`,
  `windy-mobile-site`, `windytraveler-site`, `windytranslate-site`,
  `Windy-Clone-site`, `windstorm-labs-site`, `windstorm-institute-site`,
  `nachocrunch-site` — and now `windy-connect-site`.

## License

MIT. See [`LICENSE`](LICENSE).

Site content © 2026 Windstorm Labs LLC.
