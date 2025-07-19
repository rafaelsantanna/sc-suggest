# /sc:suggest – SuperClaude Command Suggester

`/sc:suggest` lê o seu texto livre, identifica intenção, domínio técnico, nível de complexidade e requisitos de segurança, e devolve o **comando SuperClaude** ideal já preenchido com personas e flags. Assim você foca na tarefa e não em decorar sintaxes. :contentReference[oaicite:14]{index=14}

---

## ✨ Funcionalidades

- **Detecção de intenção**: mapeia verbos como *criar*, *analisar*, *melhorar* etc. para a família correta de comandos (`/sc:implement`, `/sc:analyze`, `/sc:improve` …) :contentReference[oaicite:15]{index=15}  
- **Identificação de domínio**: reconhece palavras‑chave de Frontend, Backend, Security, DevOps e sugere a *persona* apropriada (ex.: `--persona-frontend`) :contentReference[oaicite:16]{index=16}  
- **Avaliação de complexidade**: adiciona `--think`, `--think-hard`, `--ultrathink` ou `--wave-mode` conforme o tamanho da mudança :contentReference[oaicite:17]{index=17}  
- **Otimização de flags**: propõe `--validate`, `--safe-mode`, `--uc`, `--c7`, `--seq`, `--magic` e afins quando necessário :contentReference[oaicite:18]{index=18}  
- **Explicação didática**: cada sugestão vem com justificativas claras, ótimas para aprendizado interno. :contentReference[oaicite:19]{index=19}  

---

## 🔧 Instalação

```bash
# 1. Clone o repositório
git clone https://github.com/seu-usuario/sc-suggest.git
cd sc-suggest

# 2. Adicione o comando ao PATH (zsh/bash)
echo 'export PATH="$PATH:$(pwd)/bin"' >> ~/.zshrc
source ~/.zshrc
