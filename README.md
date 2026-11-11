# Hevy Workout Architect

**Screenshot-to-Hevy routine translation with set-by-set fidelity and an approval gate.**

Hevy Workout Architect is a reusable ChatGPT skill/instruction workflow for taking a workout program shown in screenshots and preparing a structured Hevy routine preview. It aims to **reproduce, not redesign**, the source program.

> [!IMPORTANT]
> This repository is an instruction skill, **not an official Hevy product** and not a standalone Hevy API integration. It cannot access or save to a Hevy account without a separately available, authorized Hevy connection. ChatGPT skill installation and invocation options depend on the product and account.

## Features

- Reviews every supplied screenshot for exercise order and continuation across images.
- Tracks **each individual set** (reps, ranges, durations, normal/warm-up/failure/AMRAP/drop/double-drop) rather than flattening mixed set prescriptions.
- Retains supersets, rounds and screenshot-stated rest intervals.
- Matches exercises against the Hevy catalog when access is available, and shows all replacements with their limitations.
- Adds **notes only where meaningful**: special instructions, substitutions or unsupported representations.
- **Only suggests weights on explicit request**, using accessible actual Hevy history if available; no invented historical loads.
- For unsupported special-set structures, uses the closest supported native Hevy representation, documents the instructions in notes and calls out any loss of fidelity.
- Displays a complete preview and **requires explicit approval before any Hevy write**.
- By default saves a **new routine copy**, not an overwrite, after approval.
- Follows a series naming convention such as `M5 - D2 Back`, only when the source or user confirms that name.

## Example workflow

1. Attach the screenshots in your ChatGPT conversation.
2. Ask: **“Use Hevy Workout Architect. Show the complete preview and differences. Do not save.”**
3. Check the per-exercise set detail, groupings, proposed substitutions, notes, and limitations.
4. Request edits if needed. To receive suggested starting weights, explicitly ask: **“Check my Hevy history and suggest weights.”**
5. Approve the final preview explicitly before allowing a new Hevy routine to be created.

For an entirely fabricated illustration of the expected output, see [examples/synthetic-preview.md](examples/synthetic-preview.md).

## Install or reuse

### As a ChatGPT skill (if supported)

Download the ZIP asset from the latest GitHub Release. It contains `SKILL.md` at the archive root. In your ChatGPT skill-management interface, choose the available create/import/upload flow, review the instructions, and install. The precise controls and skill support may vary by account and product version.

### As Project instructions

If your ChatGPT setup does not support importing skills, paste the contents of [`SKILL.md`](SKILL.md) into your Hevy-focused project's instructions (respecting any size limit), or attach it as a project reference and explicitly instruct ChatGPT to follow it.

### Without installation

Paste the skill instructions into a conversation before attaching screenshots. The skill's behavior is an instruction policy, not an executable app.

## File layout

```text
hevy-workout-architect/
├── SKILL.md                       # Complete skill definition
├── README.md                      # This guide
├── CHANGELOG.md                   # Version history
├── LICENSE                        # Proposed MIT license
├── CONTRIBUTING.md                # Public contribution guidance
├── SECURITY.md                    # Privacy and reporting policy
├── .gitignore
├── .github/
│   └── PULL_REQUEST_TEMPLATE.md
└── examples/
    └── synthetic-preview.md      # Invented, non-personal example
```

## Accuracy and boundaries

- Screenshot instructions are the source of truth; missing or obscured details are **unknown**, not assumed defaults.
- A catalog match, past-weight lookup or successful Hevy save must never be claimed without a real result from the relevant integration.
- Estimates (for example workout duration) are clearly labeled and may be impossible without complete rest/time data.
- Notes do not restore unsupported native set capabilities; the difference is reported before and after saving.
- Nothing is written to Hevy until **specific, explicit approval** of the displayed routine preview.

## Privacy

**Never commit:** actual workout screenshots without permission, personal exercise histories, private Hevy exports, access tokens, account identifiers, or sensitive details. This repository contains only generic instructions and a synthetic example. See [SECURITY.md](SECURITY.md) and [CONTRIBUTING.md](CONTRIBUTING.md).

## License and trademark

The included `LICENSE` file proposes the **MIT License** for this public project. Before publishing, the repository owner should confirm that the copyright-holder attribution in that file correctly represents the rights holder(s). MIT is permissive, allowing reuse and modification with preservation of the license and attribution. If you prefer reciprocal sharing of modifications, consider GPL-3.0; if you want distinct patent-grant terms, consider Apache-2.0. This is a practical recommendation, not legal advice.

Hevy and ChatGPT are trademarks of their respective owners. This independent project is **not affiliated with, endorsed by, or sponsored by Hevy or OpenAI**.

## Releases and changes

Version `v1.0.0` is documented in [CHANGELOG.md](CHANGELOG.md). Publish changes via pull requests and document meaningful modifications there. Use a new versioned ZIP for each release so users can reinstall or update the skill intentionally.
