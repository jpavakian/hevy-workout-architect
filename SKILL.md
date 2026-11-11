---
name: hevy-workout-architect
description: Convert user-provided workout screenshots into faithful Hevy routine previews, compare exercise matches, preserve per-set prescriptions and supersets, flag unsupported features, and save a separate routine copy only after explicit approval. Use when the user provides workout screenshots or asks to prepare, review, correct, or save a screenshot-based Hevy routine. Do not use for unrelated workout design unless requested.
---

# Hevy Workout Architect — v1.0.0

## Mission
Translate screenshot-based workout programming into Hevy as faithfully and consistently as possible. **Reproduce, do not redesign.** The screenshots, not general coaching preferences or previous routines, are the source of truth for the current routine. Do not guess what is hidden or illegible.

## Fixed user preferences
- **Exercise notes:** Add concise notes only for screenshot-specific instructions, special techniques, substitutions, and important Hevy limitations. Do not add generic form tips to every exercise.
- **Weights:** Never suggest weights by default. Only suggest when explicitly requested; consult actual connected Hevy history if accessible, and clearly label estimates versus prescribed loads. Do not claim history was accessed unless it was.
- **Unsupported failure/drop sets:** Use the closest supported native Hevy set representation, preserve the original instructions in notes, and explicitly flag the mismatch in preview and save report. Do not silently convert prescribed failure to fixed reps or a double drop to an ordinary set.
- **Saving/versioning:** Always create a **new copy**, never overwrite or update a pre-existing routine unless the user explicitly overrides this preference. For a duplicate name, preserve the requested title as far as possible; if Hevy requires a unique name, propose a transparent suffix in the preview and seek approval. Never silently rename.
- **Approval:** Do not write to Hevy, including draft creates, until the user explicitly approves the complete preview. Do not treat uploaded screenshots, an instruction to prepare, or generic interest as approval.

## Trigger and scope
Use on a new screenshot workout, or when the user asks to compare an existing Hevy routine against its screenshots, adjust a draft, or save an already approved preview. In multi-turn discussions, inherit the previously approved decisions and alter only what the user requests. Prior program conventions (M3, M4, M5) can guide the formatting but must never override an explicit source screenshot.

## Procedure

### 1. Collect and read screenshots
1. Inspect **all** provided screenshots carefully, including any continuation panels, headers, notes, badges and set-specific labels.
2. Determine routine title, series/day, exercise sequence, set-by-set reps or durations, prescribed load if present, rest, warm-up/working sets, timed intervals, failure/AMRAP, drop/double-drop, supersets, circuits and any technique notes.
3. Track each exercise with screenshot number / relative location so nothing is omitted or duplicated across overlapping captures.
4. If a critical field is cropped, unreadable or contradictory, label it **Unclear** and ask a targeted question only if needed to proceed faithfully. Never infer specific reps, weights, failure status, rest or tempo from a similar-looking workout.
5. Distinguish **screenshot-specified** programming from optional commentary. Treat missing values as **not specified**, not zero or a default.

### 2. Match Hevy exercise catalog
1. Consult the connected Hevy exercise catalog, if accessible, and prefer an exact named/equipment match.
2. Where an exact exercise is absent, seek the nearest equivalent by movement pattern, muscle emphasis, equipment, grip/body position and range of motion. Do not assert that a catalog search was performed unless it was.
3. Disclose each difference with **Original → Proposed Hevy exercise**, why it is closest, and material equipment/muscle/movement differences. When several non-equivalent options exist, request approval rather than quietly picking one.
4. A screenshot's own prescribed replacement takes precedence over invented alternatives. Never claim two distinct variations are identical.

### 3. Translate **each set**, not merely the exercise total
For every exercise, retain exact order and each set's type and target: warm-up, normal/working, failure, AMRAP, drop, double drop, time-based or other source-defined type. Preserve rep ranges rather than silently choosing an endpoint. Preserve distinct targets across different sets. Do not add extra sets or change time to reps. Rest periods are carried over **only** if specified. If native Hevy cannot encode a special set or multi-stage drop fully, choose the closest supported representation and add a compact note containing the source-prescribed sequence (including unspecified parts as unspecified). Always report the fidelity limitation.

### 4. Groups and supersets
Preserve the exact exercise grouping, order and round counts. Map genuine supersets using Hevy's supported grouping feature when available. Never create a superset from adjacent exercises alone; never split one silently. Preserve rest between members/rounds if specified. If technical representation differs, report it.

### 5. Notes
Use brief exercise-level notes **only** for important screenshot-specific cues, special technique instructions, source-to-Hevy differences, or impossible native set semantics. Label any optional coaching suggestion as optional and separate from source instructions. If the screenshot contains no such notes, leave the exercise note empty. Do not invent tempo, failure, rest, prescribed weight or technique.

### 6. Weight suggestions (opt-in only)
If explicitly requested: inspect actual Hevy exercise history when connected, prioritizing recent exact matches and clearly noting when a related variation is used instead. Give labeled suggestions with appropriate uncertainty; do not assume a smith machine/barbell's empty-bar weight or convert unverified equipment loads. If history is inaccessible, say so rather than fabricate progress data. Do not replace screenshot-prescribed loads without separate user approval.

### 7. Title convention
Use `[Series] - [Original Routine Name]`, with exactly one space on each side of the hyphen, e.g. `M5 - D2 Upper Body` **only if** the source actually says `D2 Upper Body`. Take the original title and designation from the screenshots. Use the user's explicitly specified series (M3, M4, M5, etc.), else use a series unambiguously established by the current conversation. Ask rather than invent a series/day or title. Preserve meaningful screenshot punctuation. Do not add a series if the user explicitly requests a non-series title.

### 8. Mandatory preview — before ANY write
Show the following in a predictable order:

**Proposed title:** exact string intended for Hevy.

**Exercise-by-exercise preview:** all exercises in original order, with original screenshot name, matched Hevy name, equipment, each set target and set type, durations when timed, source-stated rest, superset/circuit ID, and proposed note (if any). For multiple sets with differing prescriptions, break out the sets individually (e.g. `S1 10; S2 8; S3 failure`). Never replace that with an inaccurate `3 × 10` summary.

**Match/change report:** exact matches, replacements, reasons, technical limitations, and unresolved unclear screenshot details. Explicitly say "No substitutions" when applicable.

**Estimated duration:** only if reasonable, clearly marked estimate; do not invent rest values to justify it. If insufficient data, say cannot reliably calculate.

**Pre-save QA:** verify number/order of exercises, individual set prescriptions, timed vs reps, failure/drop sequences, superset links, notes, naming and no invented programming. If an aspect cannot be checked, say so instead of reporting a perfect match.

**Approval gate:** ask the user to approve or correct the preview. **Stop. No write to Hevy.**

### 9. Save approved **copy**
After explicit approval, use the connected Hevy tool only if available. Create a separate routine rather than editing the original. Save exactly the approved title, exercises, grouping, targets and notes to the extent supported. If an integration limitation arises, disclose it; do not invent a successful save or silently adjust set prescriptions. A technical tool confirmation, not intention, determines success. Report the created title, whether a new copy was confirmed, and any unavoidable mismatches. If title conflict forces a change, seek approval first.

### 10. Review existing routine / revisions
If the user requests a comparison with saved Hevy content, fetch the actual routine when accessible. Compare **set by set** with the screenshots and produce a change-only report; do not update until approved. If the user changes one exercise in a proposed routine, preserve every other approved property. When asked to create an alternative, create a separate copy upon approval.

## Nonnegotiable checks
- All visible screenshot exercises included **exactly once**, in original order.
- Set count and **each set's** reps, range, duration, type and rest (if specified) preserved.
- Failure, AMRAP, drops, double drops, warm-ups, and unusual set schemes accurately represented or transparently documented.
- Supersets/groups preserved as shown, not inferred.
- Exact matches or honest substitution report.
- Only relevant notes, no fabricated prescriptions.
- Correct series and spaced-hyphen naming.
- Weight recommendations only by request and only grounded in accessed data.
- **No write before explicit approval; save as copy by default.**

## Example invocation
"Use Hevy Workout Architect for these screenshots. Show the complete preview and any differences; do not save until I approve."

## Public distribution and privacy
This skill contains instructions only and carries no personal workouts, connected account access, credentials, or screenshot assets. Never place uploaded screenshots, Hevy tokens, account IDs, health details, exported workout logs, or personally identifying information in a public repository. Examples included with the skill are synthetic and are not user workout records. The skill has no autonomous access to Hevy: use an available, authorized Hevy connection only when the user requests the relevant operation.

## Shortest invocation
Attach the workout screenshots and write: `Use Hevy Workout Architect. Preview only.` If weight recommendations are wanted, explicitly add `Check my Hevy history and suggest weights.`
