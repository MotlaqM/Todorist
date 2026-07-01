---
name: user-story-pattern-author
description: Author user story pattern library files.
disable-model-invocation: true
---

# User Story Pattern Author

## Steps

1. Load the authoring contract by reading:
   - `references/pattern-authoring-guide.md`
   - `references/index-template.md`
   - `references/flow-template.md`
   Completion: the canonical index shape, flow shape, and product-language rule are in context.

2. Locate the pattern library to edit.
   Completion: the root pattern folder is known. If the user names a library path, use it. If not, create or use a `patterns/` folder in the current working directory.

3. Identify the domain and files to author.
   Completion: the target `[pattern-root]/[domain]/` folder is known, and the requested `index.md` or flow file names are known.

4. Clarify overloaded product language before writing.
   Completion: terms that would change the pattern structure are settled, or the uncertainty is captured under `Do not assume`.

5. Author lazily.
   Completion: only needed files are created or changed; new domain folders get an `index.md`, and new flows get one flow file.

6. Prune against the templates.
   Completion: indexes are routing maps, flow files are product-behavior guidance, settled decisions are captured, and no product-irrelevant technical language or duplicate rule remains.

## References

- Use `references/examples/authentication-index.example.md` for index density and routing style.
- Use `references/examples/password-reset.example.md` for flow density and product-focused language.
- Templates are authoritative when examples differ.
