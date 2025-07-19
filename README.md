# /sc\:suggest – Sugestões de Comandos SuperClaude

`/sc:suggest` analisa a sua descrição de tarefa, detecta domínio, complexidade e requisitos de segurança e devolve **o comando SuperClaude perfeito**, já preenchido com personas e flags. Foque na solução; deixe a sintaxe por conta do Suggester.

---

## 🚀 Instalação

```bash
# 1. Clone o repositório
 git clone https://github.com/seu-usuario/sc-suggest.git
 cd sc-suggest

# 2. Crie (se necessário) a pasta de comandos do Claude
 mkdir -p "$HOME/.claude/commands/sc"

# 3. Copie ou crie um link simbólico do script
 cp sc-suggest "$HOME/.claude/commands/sc/suggest"   # cópia
#   ou
 ln -s "$(pwd)/sc-suggest" "$HOME/.claude/commands/sc/suggest"  # symlink

# 4. Garanta permissão de execução
 chmod +x "$HOME/.claude/commands/sc/suggest"
```

> **Pré‑requisito**: SuperClaude CLI ≥ 0.9 já instalado e em `$PATH`.

---

## 💡 Uso rápido

```bash
# Sintaxe básica
/sc:suggest "descrição da tarefa"

# Exemplo
/sc:suggest "implementar API REST de produtos com CRUD completo"
```

Saída típica:

```text
Comando sugerido:
/sc:implement products-api --persona-backend --type api --with-tests --c7
```

---

## 📚 Exemplos adicionais

| Objetivo                            | Comando sugerido                                                                                                     |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Criar componente de login acessível | `/sc:implement login-component --persona-frontend --type component --with-tests --focus accessibility --magic`       |
| Auditar segurança de pagamentos     | `/sc:analyze payment-system --persona-security --ultrathink --focus security --validate --wave-mode --comprehensive` |
| Migrar monolito para microserviços  | `/sc:design microservices-migration --persona-architect --ultrathink --wave-mode --enterprise-waves`                 |

---

## 🧠 Pipeline resumido

1. **Detecção de intenção** → mapeia verbos (criar, analisar, melhorar…) para comandos base.
2. **Identificação de domínio** → seleciona persona apropriada (frontend, backend, security…).
3. **Avaliação de complexidade** → aplica `--think`, `--think-hard`, `--ultrathink` ou `--wave-mode`.
4. **Otimização de flags** → acrescenta `--validate`, `--safe-mode`, `--uc`, `--c7`, `--seq`, `--magic` quando necessário.
5. **Resposta** → retorna comando principal, alternativas e explicações claras.

---

## 🤝 Contribuição

1. Faça *fork* e `git clone`.
2. Crie sua branch: `git checkout -b feat/nova-heuristica`.
3. Rode testes: `./scripts/test.sh`.
4. Abra *pull request* com rationale + prints.

---

## 📅 Roadmap

* [ ] Suporte multilíngue automático
* [ ] Export JSON para CI bots
* [ ] Modo interativo para ajuste fino das flags

---

## 📄 Licença

MIT – veja `LICENSE`.

<!-- Conteúdo adaptado de suggest.md -->
