# MAGNON / ARCHIVE — not the live Hermes runtime

> [!CAUTION]
> **This GitHub repository (`syocum11/hermes-agent`) is a MIRROR / ARCHIVE.**
> It is **not** the Hermes that Magnon machines run.
> Do not clone it expecting live profiles, SOULs, HVAC state, or production config.

This file is the Magnon pointer for anyone (human or agent) who lands on this fork.
It does not replace live host docs. It exists so this archive is not mistaken for the runtime.

Matching stamps (banner / pointer only — they do not rewrite upstream product docs):

- [README.md](README.md) — CAUTION banner at the top
- [AGENTS.md](AGENTS.md) — LIVE STATUS stamp at the top; remainder is Nous Research contributor guidance

---

## Where the live runtime actually is

| What people assume | What is true |
| --- | --- |
| This `syocum11/hermes-agent` GitHub repo is what Magnon runs | **False.** This repo is archive / mirror only. |
| Cloning this fork gives you live profiles | **False.** Live profiles, SOULs, and host state are not in this tree. |
| Upstream `AGENTS.md` is Magnon Ops source of truth | **False.** That file is Hermes *product / contributor* guidance from Nous Research. |

**Live runtime on Magnon machines** is the managed checkout at:

```text
~/.hermes/hermes-agent
```

That checkout tracks **[NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent)** upstream — **not** this `syocum11` fork.

If you need to operate Magnon, work on the live host under `~/.hermes`. Do not treat a clone of this GitHub repo as a substitute.

---

## Forbidden on Magnon mini / Admins-iMac

These commands can replace or wipe `~/.hermes` (profiles, keys, sessions, skills, memory). They are **forbidden** on Magnon machines:

- `curl … | bash` against `install.sh` (including the upstream one-liner)
- PowerShell `iex` / `irm` installers (`install.ps1`)
- `hermes reinstall` or any reinstall path that wipes `~/.hermes`
- Any “fresh install” that overwrites the live home directory

Do not run them “to fix Hermes,” “to sync this fork,” or “because the README said so.” The install block in this repo’s README is **upstream product docs**, not a Magnon procedure.

---

## Profiles (live hosts only)

Named profiles live on the Magnon machines. They are **not** reconstructed by cloning this archive.

| Profile | Role | Host |
| --- | --- | --- |
| `nova` | PA | Magnon mini |
| `echo` | HVAC | Admins-iMac — see `echo-hvac-controller` and `CSW devices.md` |
| `forge` | as named | live Magnon host |
| `scout` | as named | live Magnon host |

Use the profile that matches the job. Do not invent extra profiles from this archive.

---

## Magnon Ops source of truth

For Magnon operations, read **in this order** on the live hosts (or the ops docs that live with them):

1. **`CSW devices.md`** — devices, which machine owns what, HVAC / CSW facts
2. **Profile SOULs** — identity, voice, and standing orders for `nova` / `echo` / `forge` / `scout`
3. **`echo-hvac-controller`** — HVAC controller context for `echo` on Admins-iMac

**Do not** treat upstream `AGENTS.md` (in this repo or in Nous Research’s tree) as Magnon Ops source of truth. That document is for Hermes contributors. It is not the Magnon runbook, device map, or profile constitution.

This archive's [`AGENTS.md`](AGENTS.md) opens with a LIVE STATUS / MAGNON ARCHIVE stamp so coding agents do not treat it as live Magnon Ops. Below that stamp the file is still upstream Hermes contributor guidance. That does not make it Magnon policy.

---

## Pin policy — no auto-pull / update without Scott

The live `~/.hermes/hermes-agent` checkout is **pinned**.

- Do **not** `git pull`, `hermes update`, `hermes reinstall`, or otherwise refresh the live checkout unless Scott explicitly authorizes it.
- Do **not** auto-update because upstream moved, because this archive moved, or because an agent “noticed a newer commit.”
- Pin stays until Scott says to bump.

If something looks stale, **ask Scott**. Do not “helpfully” sync.

---

## What this repo is for

- Historical / mirror copy of Hermes Agent source as forked at `syocum11/hermes-agent`
- This Magnon ARCHIVE notice so agents and humans do not confuse the two

## What this repo is not

- Not the process Magnon is running
- Not a source of live `~/.hermes` state
- Not a place to recover profiles, API keys, SOULs, or HVAC credentials
- Not authorization to reinstall or update Magnon hosts
