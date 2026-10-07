# Breakpoint — A Hands-On Security Testing Course

An interactive, browser-based course that teaches web application security testing from scratch: ten chapters with four **live, in-browser vulnerability labs**. No install, no backend, no setup — one self-contained HTML file.

**▶ Live site:** `[https://<your-username>.github.io/breakpoint-security-course/](https://suba-learning.github.io/breakpoint-security-course/)`

---

## About this project

I built Breakpoint as an **AI-assisted learning project**. I set the goal, shaped the curriculum and the design direction, and iterated on it with **Claude (Anthropic)**, which generated the implementation. It's two things at once: my own structured on-ramp into security testing, and a showcase of building a real, working tool by directing an AI — curriculum design, product decisions, and several rounds of iteration, end to end.

I'm a senior QA engineer (12+ years, focused on API and automation testing). This is my deliberate entry point into application security, built to precede a formal certification course rather than replace one.

## What's inside

**Foundations → the OWASP Top 10 → API security → doing the work.**

| # | Chapter |
|---|---------|
| 00 | The Security Mindset — CIA triad, threat vs. vulnerability vs. exploit vs. risk, trust boundaries |
| 01 | The Web, Attacker's View — HTTP as attack surface, client vs. server trust, authN vs. authZ, sessions |
| 02 | Broken Access Control — IDOR, privilege escalation |
| 03 | SQL Injection — the mechanism, the injection family, parameterized queries |
| 04 | Cross-Site Scripting (XSS) — reflected / stored / DOM, contextual output encoding |
| 05 | Auth & Session Failures — rate limiting, enumeration, session fixation, encoding ≠ encryption |
| 06 | The Rest of the Top 10 — misconfig, crypto failures, vulnerable components, SSRF, and more |
| 07 | API Security Testing — BOLA, mass assignment, rate limiting (with a `pytest`/`requests` starter) |
| 08 | Method & Reporting — scope → recon → discover → prove → report → retest; CVSS; a finding template |
| 09 | Your Lab & Next Steps — building a legal home lab, where to go deeper |

## The labs are real simulations

Each lab is a deterministic, in-browser model of a vulnerable endpoint — nothing connects to a network:

- **SQL Injection** — runs a small real boolean-expression evaluator over an in-memory user table, so classic payloads (`' OR '1'='1`, `admin'--`) actually resolve to a login bypass. Toggle "parameterized" to watch the fix work.
- **Broken Access Control (IDOR)** — change an ID to read records you don't own; toggle the ownership check to see the `403` fix.
- **Reflected XSS** — a safe simulation of unescaped reflection; toggle output-escaping.
- **JWT Token Inspector** — decode the Base64 payload, tamper the role, and see the signature check catch (or miss) the forgery.

Progress (completed chapters) is saved in the browser via `localStorage`.

## Ethics

Every technique here is taught against **safe, legal, purpose-built targets**. The course's own ground rule: only ever test systems you own or have **written permission** to test. Nothing in this project touches a real third-party system.

## Built with

- A single self-contained **HTML / CSS / JavaScript** file — no dependencies to install
- **Claude (Anthropic)** for AI-assisted design and implementation
- Hosted free on **GitHub Pages**

## License

Personal learning project — feel free to learn from it.
