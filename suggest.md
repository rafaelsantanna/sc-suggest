---
allowed-tools: [Read, Grep, Glob]
description: "Analyze user input and suggest the most appropriate SuperClaude command with optimized flags and personas"
---

# /sc:suggest - SuperClaude Command Suggester

## Purpose
Analyze user input to recommend the most appropriate SuperClaude command, personas, and flags based on intent detection and context analysis.

## Usage
```
/sc:suggest [user_input]
```

## Arguments
- `user_input` - Your task description or what you want to accomplish

## Execution Process

1. **Intent Detection**
   - Analyze keywords and phrases to identify primary intent
   - Map to SuperClaude command categories (build, implement, analyze, etc.)

2. **Domain Identification**
   - Detect technical domain (frontend, backend, security, etc.)
   - Select appropriate personas based on context

3. **Complexity Assessment**
   - Evaluate task complexity
   - Recommend appropriate thinking flags (--think, --think-hard, --ultrathink)

4. **Flag Optimization**
   - Suggest performance flags (--uc for token optimization)
   - Add safety flags for critical operations (--validate, --safe-mode)
   - Include MCP server flags when needed (--c7, --seq, --magic)

5. **Generate Suggestions**
   - Primary recommendation with full command
   - Alternative approaches when applicable
   - Explanation of why each flag/persona was selected

## Analysis Patterns

### Intent Mapping
- "criar", "implementar", "build", "desenvolver", "construir" → `/sc:implement` or `/sc:build`
- "analisar", "debug", "investigar", "entender", "examinar" → `/sc:analyze` or `/sc:troubleshoot`
- "melhorar", "otimizar", "refatorar", "aprimorar", "enhance" → `/sc:improve`
- "documentar", "explicar", "descrever", "escrever docs" → `/sc:document` or `/sc:explain`
- "testar", "validar", "verificar", "QA" → `/sc:test`
- "design", "arquitetura", "planejar", "estruturar" → `/sc:design`
- "limpar", "organizar", "remover código morto" → `/sc:cleanup`
- "commit", "versionar", "git" → `/sc:git`

### Persona Detection Keywords
- **Frontend**: UI, interface, componente, React, Vue, CSS, responsive, acessibilidade, UX, design system, frontend
- **Backend**: API, servidor, database, endpoint, REST, GraphQL, microservice, backend, autenticação, JWT
- **Security**: segurança, vulnerabilidade, auth, encryption, OWASP, pentest, auditoria, compliance
- **Performance**: performance, otimização, speed, latência, bottleneck, cache, slow, rápido
- **Analyzer**: debug, investigar, problema, erro, bug, root cause, analisar, entender
- **QA**: teste, qualidade, cobertura, edge case, validação, QA, test suite
- **Architect**: arquitetura, design, estrutura, escalabilidade, padrões, sistema, solução
- **DevOps**: deploy, CI/CD, Docker, Kubernetes, infraestrutura, monitoring, pipeline
- **Refactorer**: refatorar, clean code, technical debt, simplificar, melhorar código
- **Scribe**: documentação, README, wiki, tutorial, guia, manual, escrever

### Complexity Indicators
- **Simple** (base command only):
  - Single file operations
  - Basic CRUD tasks
  - Straightforward implementations
  - Quick fixes

- **Moderate** (add --think):
  - Multi-file operations
  - Feature implementations
  - Bug investigations
  - API development

- **Complex** (add --think-hard or --ultrathink):
  - System-wide changes
  - Architecture decisions
  - Performance optimization
  - Security audits
  - Large refactoring

- **Enterprise** (add --wave-mode):
  - Files > 50
  - Multiple domains involved
  - Critical production systems
  - Comprehensive audits

### Safety and Validation Triggers
- Production mentions → Add `--safe-mode --validate`
- Security operations → Add `--validate`
- Database migrations → Add `--safe-mode`
- Critical systems → Add `--validate --safe-mode`

### MCP Server Selection
- Documentation needed → Add `--c7`
- Complex analysis → Add `--seq`
- UI components → Add `--magic`
- Testing/E2E → Add `--play`
- All comprehensive → Add `--all-mcp`

## Examples

### Example 1: Frontend Component Creation
**Input**: "preciso criar um componente de login com validação e acessibilidade"
**Output**:
```
Comando principal sugerido:
/sc:implement login-component --persona-frontend --type component --with-tests --focus accessibility --magic

Alternativa para design primeiro:
/sc:design login-component --persona-frontend --think --c7

Explicação:
- --persona-frontend: Detectado trabalho com UI/componentes
- --type component: Criação de componente específico
- --with-tests: Boa prática para componentes críticos como login
- --focus accessibility: Requisito explícito de acessibilidade mencionado
- --magic: MCP server especializado em geração de componentes UI modernos
```

### Example 2: Performance Analysis
**Input**: "analisar problemas de performance na API de autenticação"
**Output**:
```
Comando principal sugerido:
/sc:analyze auth-api --persona-performance --focus performance --think-hard --seq

Alternativa para troubleshooting específico:
/sc:troubleshoot "slow authentication API" --persona-analyzer --seq --validate

Explicação:
- --persona-performance: Foco explícito em otimização de performance
- --focus performance: Direciona análise para métricas de desempenho
- --think-hard: APIs de auth são complexas e requerem análise profunda
- --seq: Sequential MCP para análise sistemática de bottlenecks
- --validate: Importante validar mudanças em sistema crítico de auth
```

### Example 3: Security Audit
**Input**: "fazer auditoria de segurança completa no sistema de pagamentos"
**Output**:
```
Comando principal sugerido:
/sc:analyze payment-system --persona-security --ultrathink --focus security --validate --wave-mode --comprehensive

Alternativa mais rápida:
/sc:analyze payment-system --persona-security --think --focus security --validate

Explicação:
- --persona-security: Auditoria de segurança requer especialista em security
- --ultrathink: Sistema de pagamento é crítico, requer análise máxima (32K tokens)
- --focus security: Análise específica de vulnerabilidades e compliance
- --validate: Essencial para operações de segurança em produção
- --wave-mode: Auditoria completa se beneficia de análise em múltiplas ondas
- --comprehensive: Garante cobertura total do sistema de pagamentos
```

### Example 4: Bug Investigation
**Input**: "usuários reportam erro 500 ao fazer upload de arquivos grandes"
**Output**:
```
Comando principal sugerido:
/sc:troubleshoot "error 500 on large file uploads" --persona-analyzer --think --seq --validate

Alternativa com foco em performance:
/sc:analyze upload-system --persona-performance --focus performance --think

Explicação:
- --persona-analyzer: Investigação de bugs requer análise sistemática
- --think: Problema específico mas pode ter múltiplas causas
- --seq: Sequential MCP para investigação estruturada
- --validate: Importante validar correções antes de aplicar
```

### Example 5: Code Refactoring
**Input**: "refatorar código legado do módulo de relatórios para melhorar manutenibilidade"
**Output**:
```
Comando principal sugerido:
/sc:improve reports-module --persona-refactorer --focus quality --think-hard --validate --uc

Alternativa com cleanup primeiro:
/sc:cleanup reports-module --persona-refactorer --safe-mode

Explicação:
- --persona-refactorer: Especialista em melhoria de código e redução de dívida técnica
- --focus quality: Objetivo é melhorar qualidade e manutenibilidade
- --think-hard: Código legado geralmente requer análise cuidadosa
- --validate: Garantir que refatoração não quebra funcionalidades
- --uc: Refatoração pode gerar muito output, otimizar tokens
- --safe-mode: Importante em código legado para evitar breaking changes
```

### Example 6: API Implementation
**Input**: "implementar nova API REST para gerenciamento de produtos com CRUD completo"
**Output**:
```
Comando principal sugerido:
/sc:implement products-api --persona-backend --type api --with-tests --c7

Alternativa com design primeiro:
/sc:design products-api --persona-architect --think --type api

Explicação:
- --persona-backend: Desenvolvimento de API é domínio backend
- --type api: Especifica tipo de implementação
- --with-tests: APIs devem ter testes desde o início
- --c7: Context7 para melhores práticas e padrões de API REST
```

### Example 7: Documentation Writing
**Input**: "criar documentação completa do sistema para novos desenvolvedores"
**Output**:
```
Comando principal sugerido:
/sc:document --persona-scribe --comprehensive --focus onboarding

Alternativa em português:
/sc:document --persona-scribe=pt --comprehensive --focus onboarding

Explicação:
- --persona-scribe: Especialista em documentação técnica
- --comprehensive: Documentação completa do sistema
- --focus onboarding: Específico para novos desenvolvedores
- =pt: Versão em português se preferir (padrão é inglês)
```

### Example 8: Large System Improvement
**Input**: "melhorar arquitetura do sistema monolítico para microserviços"
**Output**:
```
Comando principal sugerido:
/sc:design microservices-migration --persona-architect --ultrathink --wave-mode --enterprise-waves

Alternativa para análise inicial:
/sc:analyze current-architecture --persona-architect --think-hard --comprehensive

Explicação:
- --persona-architect: Mudança arquitetural requer visão de arquiteto
- --ultrathink: Migração monolito→microserviços é extremamente complexa
- --wave-mode: Projeto grande se beneficia de abordagem em ondas
- --enterprise-waves: Estratégia específica para transformações enterprise
- --comprehensive: Necessário entender sistema completo antes de migrar
```

## Integration with ORCHESTRATOR.md

This command leverages the routing intelligence patterns:

1. **Master Routing Table**: Uses pattern matching for command selection
2. **Auto-Activation Rules**: Applies intelligent persona and flag selection
3. **Complexity Detection**: Evaluates task complexity for appropriate flags
4. **Wave/Delegation Scoring**: Suggests advanced orchestration when needed
5. **MCP Server Selection**: Recommends appropriate servers based on task

## Best Practices

1. **Be Specific**: Quanto mais detalhado seu input, melhor a sugestão
2. **Include Context**: Mencione tecnologias, urgência, e requisitos específicos
3. **Trust Auto-Selection**: O sistema geralmente acerta nas escolhas automáticas
4. **Learn Patterns**: Use as explicações para aprender quando usar cada comando

## Troubleshooting

Se o comando sugerido não parecer adequado:
1. Adicione mais contexto ao seu input
2. Especifique o tipo de tarefa (análise, implementação, etc.)
3. Mencione requisitos especiais (segurança, performance, etc.)
4. Considere usar a alternativa sugerida

Remember: SuperClaude é inteligente e muitas vezes ativa flags e personas automaticamente. Use este comando para aprender e otimizar, mas confie também na inteligência built-in do framework!