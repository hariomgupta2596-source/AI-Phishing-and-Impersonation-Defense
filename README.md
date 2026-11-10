# 🛡️ SENTINEL — AI Phishing & Impersonation Defense

**Multi-vector cybersecurity intelligence that unites machine learning, deterministic URL heuristics and authoritative brand-registry verification into one explainable 0–100 risk score.**

This repository is the entry point for the project. The full source lives in the TechAstra Hackathon organisation repo, where it was built and deployed as a team:

➡️ **[github.com/TECHASTRA-2026/AI-Phishing-and-Impersonation-Defense](https://github.com/TECHASTRA-2026/AI-Phishing-and-Impersonation-Defense)**

| | |
| --- | --- |
| **Live platform** | https://ai-phishing-and-impersonation-defen.vercel.app |
| **Interactive API docs** | https://ai-phishing-and-impersonation-defen.vercel.app/docs |
| **Health endpoint** | https://ai-phishing-and-impersonation-defen.vercel.app/health |

---

## The problem

Real credential-harvesting campaigns don't use one vector. They stack three at once:

1. **Psychological manipulation** — fabricated urgency, account-lockout threats, extortion.
2. **Structural obfuscation** — typo-squatted domains, abusive TLDs (`.top`, `.xyz`, `.cfd`), hidden `@` redirects.
3. **Identity spoofing** — impersonating banks and brands (State Bank of India, PayPal, Microsoft, Amazon) from unverified sender domains.

A single black-box classifier sees a string and guesses. SENTINEL scores each vector and then shows its working.

## How it answers

```
message / URL / brand
        ↓
┌───────────────────┬────────────────────┬─────────────────────┐
│  ML classifier    │  URL heuristics    │  Brand registry     │
│  (scikit-learn)   │  (deterministic)   │  verification       │
└───────────────────┴────────────────────┴─────────────────────┘
        ↓
normalised 0–100 risk score  +  diagnostic evidence  +  countermeasure playbook
```

The design decision that shaped everything: **the model never gets the final word alone.** Statistical NLP probability is synthesised with deterministic heuristics and registry checks, so a result is explainable to a non-specialist and auditable by a reviewer. Explainable AI isn't a feature here, it's the product.

## Stack

`Python 3.13` · `FastAPI` · `scikit-learn` · `XAI` · `Vercel` — with a full test suite (`test_e2e_api.py`, `test_integration.py`), a `security-layer` module and a QA/optimisation report in the source repo.

## Try it

Open the [live demo](https://ai-phishing-and-impersonation-defen.vercel.app) and paste in a suspicious message or URL. The best way to judge the project is to try to fool it.

---

<sub>Built for the **TechAstra Hackathon**. Team project — see the org repo for contributors, commit history and documentation.</sub>
