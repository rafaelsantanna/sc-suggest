# /sc\:suggest – SuperClaude Command Suggestions

`/sc:suggest` analyzes your task description, detects domain, complexity, and security requirements, and returns **the perfect SuperClaude command**, already filled with personas and flags. Focus on the solution; leave the syntax to Suggester.

---

## 🚀 Installation

```bash
# 1. Clone the repository
git clone https://github.com/your-username/sc-suggest.git
cd sc-suggest

# 2. Create (if necessary) Claude's command folder
mkdir -p "$HOME/.claude/commands/sc"

# 3. Copy or create a symbolic link to the script
cp sc-suggest "$HOME/.claude/commands/sc/suggest" # copy
# or
ln -s "$(pwd)/sc-suggest" "$HOME/.claude/commands/sc/suggest" # symlink

# 4. Ensure execution permission
chmod +x "$HOME/.claude/commands/sc/suggest"
```

> **Prerequisite**: SuperClaude CLI ≥ 0.9 already installed and in `$PATH`.

---

## 💡 Quick Start

```bash
# Basic Syntax
/sc:suggest "task description"

# Example
/sc:suggest "implement products REST API with full CRUD"
```

Typical Output:

```text
Suggested Command:
/sc:implement products-api --persona-backend --type api --with-tests --c7
```

---

## 📚 Additional Examples

| Objective | Suggested Command |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Create Accessible Login Component | `/sc:implement login-component --persona-frontend --type component --with-tests --focus accessibility --magic` |
| Audit payment security | `/sc:analyze payment-system --persona-security --ultrathink --focus security --validate --wave-mode --comprehensive` |
| Migrate monolith to microservices | `/sc:design microservices-migration --persona-architect --ultrathink --wave-mode --enterprise-waves` |

---

## 🧠 Pipeline Summary

1. **Intent Detection** → maps verbs (create, analyze, improve…) to base commands.
2. **Domain Identification** → selects appropriate persona (frontend, backend, security…).
3. **Complexity Assessment** → applies `--think`, `--think-hard`, `--ultrathink`, or `--wave-mode`.
4. **Flag Optimization** → adds `--validate`, `--safe-mode`, `--uc`, `--c7`, `--seq`, `--magic` when necessary.
5. **Response** → returns the main command, alternatives, and clear explanations.

---

## 🤝 Contribution

1. Fork and git clone.
2. Create your branch: `git checkout -b feat/nova-heuristica`.
3. Run tests: `./scripts/test.sh`.
4. Open a pull request with rationale + prints.

---

## 📅 Roadmap

* [ ] Automatic multilingual support
* [ ] Export JSON for CI bots
* [ ] Interactive mode for fine-tuning flags

---

## 📄 License

MIT – see `LICENSE`.

<!-- Content adapted from suggest.md -->
