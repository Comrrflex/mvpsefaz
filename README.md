# MVP SaaS: Decision Intelligence Record

## Objetivo

Transformar o conceito de Decision Intelligence Record em um SaaS funcional para registrar, organizar, auditar e exportar decisões importantes com apoio de IA.

## Produto

Nome provisório: **TCRIA Decisions**

Proposta:

> Um SaaS para estruturar decisões críticas em fatos, evidências, hipóteses, alternativas, riscos, recomendação, plano de execução e trilha de auditoria.

## Jornada principal do MVP

1. Usuário cria conta.
2. Usuário cria ou acessa um workspace.
3. Usuário cria uma nova decisão.
4. Preenche problema, objetivo e contexto.
5. Adiciona fatos e evidências.
6. Adiciona alternativas e riscos.
7. Usa IA para gerar diagnóstico, gaps, plano de execução e resumo executivo.
8. Define recomendação e decisão final.
9. Exporta o registro em JSON, Markdown ou PDF.

## Funcionalidades essenciais

### Autenticação

- login;
- cadastro;
- logout;
- sessão segura.

### Workspace

- criar workspace;
- listar workspaces;
- definir owner;
- permitir membros futuramente.

### Decision Record

Campos principais:

- id;
- workspaceId;
- title;
- status;
- mode;
- problem;
- objective;
- diagnosis;
- recommendationSummary;
- recommendationRationale;
- decisionStatus;
- selectedAlternativeId;
- createdBy;
- createdAt;
- updatedAt.

Status:

- DRAFT;
- UNDER_REVIEW;
- APPROVED;
- REJECTED;
- ARCHIVED.

### Fatos

- criar fato;
- editar fato;
- remover fato;
- registrar nível de confiança;
- associar evidências.

### Evidências

- registrar documento, link ou arquivo;
- campos: type, title, reference, url, filePath, checksum, verified.

### Alternativas

- nome;
- descrição;
- prós;
- contras;
- riscos.

### Critérios

- nome;
- peso;
- score por alternativa;
- justificativa do score.

### Riscos

- descrição;
- impacto;
- probabilidade;
- mitigação.

### Plano de execução

- ordem;
- ação;
- responsável;
- prazo;
- status;
- dependências.

### IA assistida

Endpoints sugeridos:

```text
POST /api/ai/structure
POST /api/ai/diagnosis
POST /api/ai/risks
POST /api/ai/gaps
POST /api/ai/execution-plan
POST /api/ai/executive-summary
```

A IA deve ajudar a organizar e sugerir, mas a decisão final deve continuar humana.

### Auditoria

Registrar eventos:

- CREATED;
- UPDATED;
- AI_GENERATED;
- APPROVED;
- REJECTED;
- EXPORTED;
- ATTACHMENT_ADDED;
- STATUS_CHANGED.

### Exportação

Formatos:

- JSON;
- Markdown;
- PDF simples.

## Stack recomendada

- Frontend: Next.js
- Backend: Next.js API Routes ou NestJS
- Banco: PostgreSQL
- ORM: Prisma
- Auth: Supabase Auth, Clerk ou Auth.js
- Storage: Supabase Storage ou S3
- IA: OpenAI API
- Deploy: Vercel + Supabase

## Telas do MVP

1. Landing page
2. Login/cadastro
3. Dashboard
4. Lista de decisões
5. Nova decisão
6. Editor estruturado de decisão
7. Painel de IA
8. Tela de exportação
9. Auditoria da decisão

## Backlog por sprint

### Sprint 1 — Fundação

- iniciar projeto Next.js;
- configurar TypeScript;
- configurar banco PostgreSQL;
- configurar Prisma;
- criar autenticação;
- criar modelo User/Workspace/DecisionRecord;
- criar dashboard básico.

### Sprint 2 — CRUD principal

- criar decisão;
- listar decisões;
- editar decisão;
- excluir/arquivar decisão;
- alterar status;
- registrar audit trail básico.

### Sprint 3 — Estrutura decisória

- facts;
- evidence;
- alternatives;
- criteria;
- risks;
- gaps;
- execution steps.

### Sprint 4 — IA assistida

- estruturar texto livre;
- gerar diagnóstico;
- sugerir riscos;
- encontrar gaps;
- gerar plano de execução;
- registrar AIContribution.

### Sprint 5 — Exportação e busca

- exportar JSON;
- exportar Markdown;
- exportar PDF;
- busca por título/texto/status;
- filtros.

### Sprint 6 — Produto vendável

- landing page;
- planos Free/Pro/Team;
- limites por plano;
- onboarding;
- templates iniciais;
- deploy produção.

## Modelo de monetização

### Free

- até 5 decisões;
- exportação JSON/Markdown;
- IA limitada.

### Pro

- decisões ilimitadas;
- exportação PDF;
- IA assistida;
- anexos;
- busca;
- templates.

### Team

- workspace compartilhado;
- membros;
- auditoria;
- responsáveis;
- relatórios.

### Enterprise futuro

- SSO;
- API;
- integrações;
- logs avançados;
- retenção customizada;
- deploy privado;
- compliance.

## Critérios de sucesso do MVP

- usuário cria primeira decisão em menos de 10 minutos;
- usuário exporta uma decisão estruturada;
- usuário registra pelo menos 3 decisões no primeiro mês;
- usuário entende claramente o valor de auditoria e memória operacional.

## Fora do MVP

- knowledge graph completo;
- integrações profundas;
- SSO;
- permissões complexas;
- marketplace;
- automações avançadas;
- fine-tuning.

## Próximas tarefas técnicas

1. Criar `prisma/schema.prisma`.
2. Criar JSON Schema do DecisionRecord.
3. Criar rotas CRUD.
4. Criar layout do dashboard.
5. Criar prompts versionados de IA.
6. Criar exportação Markdown.
7. Criar exportação PDF simples.

## Resultado esperado

Um MVP SaaS simples, funcional e vendável, capaz de transformar decisões soltas em registros estruturados, auditáveis e reutilizáveis por pessoas e agentes de IA.
