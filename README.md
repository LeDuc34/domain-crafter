# Domain Crafter — Brandable AI Domain Name Generator with Options

[![Releases](https://img.shields.io/badge/Releases-download-blue?logo=github)](https://github.com/LeDuc34/domain-crafter/releases)

![Hero image](https://images.unsplash.com/photo-1498050108023-c5249f4df085?auto=format&fit=crop&w=1200&q=80)

Domain Crafter is a single-page web app that generates brandable, creative, and available domain names. It uses smart algorithms and customizable options to propose names that fit your brand voice, niche, and domain extension preferences.

Topics: ai, branding, creative, domain, domains, generator, name-generator, namecheap, tailwind, webapp

---

Table of contents

- Features
- Demo & Screenshots
- Quick start
- Releases (download and run)
- How it works
- Options & tuning
- CLI / API (local)
- Deploy
- Development
- Contributing
- License
- FAQ

---

Features

- Generates domain name ideas using AI-inspired algorithms and heuristic rules.
- Checks availability for common TLDs.
- Filters by length, syllables, and brandability score.
- Supports brand rules: keep, avoid, preferred suffix/prefix.
- Batch mode to generate hundreds of names per run.
- Export suggestions as CSV or copy to clipboard.
- Lightweight single-page app built with Tailwind CSS and plain JavaScript.
- Optional integrations: Namecheap lookup, WHOIS hints.

Quick highlights

- Single-page web app, no backend required for core generation.
- Lightweight UI built with Tailwind for fast interaction.
- Configurable presets for different brand tones (modern, playful, serious).

Demo & Screenshots

Live demo: Open the built release in a browser after download (see Releases below).

Screenshots
- Landing & hero: clean search bar and tone picker.
- Results grid: domain, TLD, score, action buttons.
- Filters panel: sliders for length, syllables, and score.

![Search screenshot](https://images.unsplash.com/photo-1521737604893-d14cc237f11d?auto=format&fit=crop&w=1200&q=80)
![Results screenshot](https://images.unsplash.com/photo-1515879218367-8466d910aaa4?auto=format&fit=crop&w=1200&q=80)

Releases (download and run)

Download the latest release asset from the releases page and run the contained file to use the app locally.

- Visit the releases page: https://github.com/LeDuc34/domain-crafter/releases
- Download the asset named domain-crafter-x.y.z.zip (or domain-crafter-latest.zip).
- Extract the archive.
- Open index.html in your browser to launch the single-page app.
- If the release includes an install script (install.sh or install.ps1), execute it to install optional helpers.

If you cannot reach the link above, check the Releases section on the repository page for available builds and instructions.

Usage guide

Start

- Open the app in your browser.
- Enter one or more seed words or a short description.
- Pick a brand tone: modern, playful, classic, technical.
- Set filters: max length, preferred TLDs, and minimum brand score.
- Click Generate.

Interpret results

- Each suggestion shows the full domain and its brand score.
- Score uses length, pronounceability, and memorability heuristics.
- Click Check to run a TLD availability check.
- Click Save to export selected names as CSV.

Advanced options

- Batch generation: run 100+ variations from a seed list.
- Suffix & prefix rules: enforce or block parts of names.
- Merge mode: combine multiple seed words with connectors.
- Phonetic tuning: prefer names with simpler syllable patterns.

How it works

Algorithm layers

- Seed normalization: lowercasing, diacritic stripping, stop-word removal.
- Variation engine: applies rules to create blends, contractions, and affixes.
- Heuristics filter: removes offensive or trademark-like terms.
- Scoring: weights include length (-), syllables (-), pronounceability (+), distinctiveness (+).
- Availability check: queries Namecheap API or uses DNS lookup for common TLDs.

Examples

- Seed: "green" + tone "modern" → greenly.com, greenco.io, greenuo.app
- Seed: "shift" + mode "technical" → shiftstack.com, shifts.io, shiftly.ai

Options & tuning (UI fields)

- Tone: modern, playful, classic, technical
- Domain length: integer (max characters)
- Max syllables: integer
- Preferred TLDs: list (.com, .io, .app, .ai)
- Blocklist: words to exclude
- Required: words that must appear
- Merge rules: how many seeds to combine
- Export: CSV or JSON

CLI / Local API

Domain Crafter includes a minimal local API for programmatic runs in development mode.

Start local server (dev)

- Clone the repo.
- Install dependencies: npm install
- Start dev server: npm run dev
- Open http://localhost:3000

Generate from CLI

- Use the provided script scripts/generate.js
- Example:
  node scripts/generate.js --seed "green,tech" --tone modern --count 50 --tlds ".com,.io"

Output: JSON array with suggestion, score, and availability hint.

Deploy

Static deploy options

- GitHub Pages: push the built site to gh-pages branch.
- Netlify / Vercel: point to the build folder and set a redirect to index.html for single-page routing.
- S3 + CloudFront: upload build artifacts and set index document to index.html.

Build steps

- npm run build
- Deploy contents of /dist (or /build) to your static host.

Development

Project structure

- src/ — source code
- public/ — static assets and index.html
- scripts/ — helpers and CLI tools
- dist/ or build/ — generated artifacts
- tests/ — unit tests for algorithm functions

Coding standards

- JavaScript (ES2020)
- Tailwind CSS for UI
- Minimal runtime dependencies
- Linting via ESLint
- Formatting via Prettier

Contributing

- Open an issue for bugs or feature requests.
- Fork the repo, create a feature branch, and open a pull request.
- Write tests for algorithm changes.
- Keep PRs focused and document configuration changes.

Suggested workflow

- Fork
- git checkout -b feat/name-improvement
- Implement feature and tests
- npm run test
- Open PR with issue reference and short changelog entry

License

- MIT License (a simple permissive license). See LICENSE file for details.

Community & support

- Open issues on GitHub for bugs and feature requests.
- Use PR comments for technical discussion.
- Tag maintainers for urgent fixes.

Roadmap

- Add deeper trademark checks and external API integration.
- Provide a paid API tier for volume generation.
- Add team collaboration features: shared lists, comments, voting.
- Improve scoring with user feedback and ML fine-tuning.

Security

- Keep API keys out of the client.
- Use environment variables for server-side integrations.
- Sanitize user-provided seeds before processing.

FAQ

Q: Do I need an API key to use availability checks?
A: The local app uses DNS for basic checks. For Namecheap or WHOIS APIs you must provide keys in the settings panel or environment variables on your host.

Q: Can I export large batches?
A: Yes. Use batch mode and the CSV export. For very large exports, run the CLI script to avoid browser memory limits.

Q: Does the app register domains?
A: The app suggests and checks availability. It does not register domains automatically. Use your registrar to complete registration.

Metrics & tests

- Unit tests cover the variation engine and scoring logic.
- Benchmarks measure generation time for 1,000 suggestions.
- Test commands:
  - npm test
  - npm run bench

Releases and builds badge

[![Download Release](https://img.shields.io/badge/Download%20Release-latest-green?logo=github)](https://github.com/LeDuc34/domain-crafter/releases)

The releases page contains compiled builds and installers. Download the appropriate asset and run the included index.html or the provided installer script to launch the app.

Acknowledgments

- Tailwind CSS for rapid UI styling.
- Open source name lists and word frequency datasets.
- Community feedback from branding professionals.

Contact

- File issues on GitHub.
- Create PRs for improvements.

