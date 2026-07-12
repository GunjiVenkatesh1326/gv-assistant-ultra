# gv-assistant-ultra

A clean, test-focused Python codebase for experimenting with assistant-like tooling, safety heuristics, and demoing UI flows.

[Live Demos](/) · [Tests](#running-tests) · [Contribute](#contributing)

---

## Quick overview

gv-assistant-ultra gathers unit tests and utilities used to validate and demonstrate behaviors for assistant systems (tool integration, safety heuristics, upload handling, web fetches, vision/TTS checks, and more). The repository also includes short demo videos (.webm) that showcase UI flows and example interactions.

Key highlights

- Test-first design: Dozens of pytest files (test_*.py) exercise behaviors and guardrails.
- Demo assets: chat.webm, gallery.webm, theme.webm, document.webm, notes.webm, research.webm, bg.webm.
- Small tooling/spec: `bombadil-spec.ts` — a concise TypeScript helper/spec.
- Standalone utilities: `build_oversized_test_split_plan.py` for experiment orchestration.

---

## Demo gallery (local)

Preview the demo files locally or serve them via a tiny static server.

Play a demo directly (choose one):

- chat.webm — core chat demo
- gallery.webm — gallery / thumbnails
- theme.webm — visual theme showcase
- document.webm — document handling flow
- notes.webm — note-taking demo
- research.webm — longer research walkthrough

Open with your OS default video player:

macOS: `open chat.webm`
Linux: `xdg-open chat.webm`
Windows (PowerShell): `Start-Process chat.webm`

Serve and view in browser:

```bash
python -m http.server 8000
# then open http://localhost:8000/chat.webm
```

Raw file links (direct download):
- https://raw.githubusercontent.com/GunjiVenkatesh1326/gv-assistant-ultra/main/chat.webm
- https://raw.githubusercontent.com/GunjiVenkatesh1326/gv-assistant-ultra/main/gallery.webm

If you want, I can add an attractive index.html gallery page that embeds these videos and publish it via GitHub Pages.

---

## Getting started (developer)

1. Clone:

```bash
git clone https://github.com/GunjiVenkatesh1326/gv-assistant-ultra.git
cd gv-assistant-ultra
```

2. Create a virtual environment and install test dependencies:

```bash
python -m venv .venv
source .venv/bin/activate   # macOS / Linux
.\.venv\Scripts\Activate.ps1  # Windows (PowerShell)
pip install -U pip
pip install pytest
```

3. Run the tests:

```bash
pytest -q
```

Notes: A `requirements.txt` is not present; add one if you want reproducible installs for CI.

---

## Project layout (top-level)

```
CNAME                         # optional GitHub Pages custom domain
README.md                     # this file (updated)
*.webm                        # demo media assets
bombadil-spec.ts              # small TypeScript spec/utility
build_oversized_test_split_plan.py  # standalone Python utility
test_*.py                     # pytest files (primary content)
```

---

## How this repo fits together

There is no packaged `src/` library — tests drive the work. The test files define expected assistant/tool behavior and safety checks; the demo videos show UI/UX flows that correspond to those behaviors. `build_oversized_test_split_plan.py` is a helper script used during experiment preparation.

---

## Contributing

Contributions are welcome. A good workflow:

1. Open an issue describing the change or feature.
2. Create a branch named `feat/<short-description>` or `fix/<short-description>`.
3. Add tests alongside any new behavior.
4. Submit a PR with a descriptive title and short summary.

Suggested checklist for PRs:
- Add or update tests for new features.
- Keep changes small and focused.
- Include screenshots or short GIFs for UI/demo changes when relevant.

---

## License

No license file is present. If you want permissive reuse, consider adding `LICENSE` with MIT or Apache-2.0.

---

## Want me to do this next?

- I can add an `index.html` gallery embedding the demo videos and commit it.
- I can create a `requirements.txt` and a GitHub Actions workflow that runs `pytest` on push.
- I can generate short preview GIFs for the demos and add them to the README.

Tell me which option you prefer and I'll implement it.