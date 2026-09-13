<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/images/documentation.png">
    <source media="(prefers-color-scheme: light)" srcset="assets/images/documentation-mono.png">
    <img alt="The logo spells Documentation in cursive character." height="40" src="assets/images/documentation.png">
  </picture>

---

<small>Available at <https://documentation.vanillaos.org>.</small>

Powered by [Chronos](https://github.com/Vanilla-OS/chronos).

</div>

## Use of Generative AI

Maintainers may use generative AI tools as assistants while working on documentation. Non-trivial assisted commits disclose the tool, model, and scope of the work.

AI tools may assist with code comments, documentation, repetitive code, and issue triage. Maintainers make project decisions and review every assisted change before it is merged.

Use these trailers for non-trivial assisted commits:

```plain
Assisted-by: <tool>:<model-version>
AI-Scope: <what the tool generated and the prompt or a short prompt summary>
```

Single-line completions, renames, and formatting changes do not need trailers.

Coding agents must also follow [AGENTS.md](AGENTS.md) before changing files,
creating commits, or opening pull requests.
