# Contributing to eAg-HFMS-AgroTutor

This guide defines the contribution protocol for all repositories in the `eAg-HFMS-AgroTutor` GitHub organization.

For detailed engineering standards, environment setup, testing protocol, architecture decisions, and release process, refer to the `engineering-playbook` repository.

## 1. Repository map

The organization has six repositories: two governance repositories and four product/module repositories.

| Repository             | Responsibility                                                            |
| ---------------------- | ------------------------------------------------------------------------- |
| `.github`              | GitHub defaults, issue templates, PR template, contribution policy        |
| `engineering-playbook` | Engineering standards, setup, testing, governance, release protocol, ADRs |
| `e-agrology`           | Agronomic data, forms, ETL, metadata, FAIR/Dataverse workflows            |
| `hfms`                 | High-frequency monitoring pipelines, indicators, data cube, store         |
| `agrotutor`            | Advisory product, user workflows, recommendation rules, content, frontend |
| `ai-orchestration`     | LLM orchestration, agents, prompts, evaluations, guardrails               |

## 2. Start from an issue

Every contribution must start from a GitHub issue.

The issue must define:

- Problem or objective
- Target repository
- Expected output
- Acceptance criteria
- Assignee
- Labels

Do not mix unrelated work across repositories.

## 3. Repository boundaries

Use the correct repository.

| Work type                                                        | Repository             |
| ---------------------------------------------------------------- | ---------------------- |
| Survey forms, agronomic datasets, metadata, Dataverse publishing | `e-agrology`           |
| Monitoring indicators, dashboards, external time-series data     | `hfms`                 |
| Advisory UI, rules, user journeys, localized advisory content    | `agrotutor`            |
| Agents, tools, prompts, LLM evaluation, guardrails               | `ai-orchestration`     |
| Coding rules, setup standards, release process, ADRs             | `engineering-playbook` |
| GitHub templates and defaults                                    | `.github`              |

Cross-repository changes require coordination with the owners of all affected repositories.

## 4. Branch naming

Use:

```text
<type>/<issue-number>-short-description
```

Allowed types:

```text
feature
fix
docs
refactor
test
chore
ci
```

Examples:

```text
feature/24-add-dataverse-metadata-schema
fix/31-correct-hfms-rainfall-aggregation
docs/42-update-agrotutor-user-flow
refactor/55-clean-ai-agent-tool-routing
```

## 5. Commit messages

Use Conventional Commits.

Examples:

```text
feat: add e-agrology metadata validation schema
fix: correct hfms rainfall aggregation
docs: update agrotutor advisory workflow
test: add ai orchestration retrieval tests
ci: add linting workflow
```

## 6. Pull request requirements

Every pull request must include:

- Summary of the change
- Linked issue
- Testing performed

Do not merge if:

- CI fails
- Review is missing
- Secrets are committed
- Documentation is outdated
- Tests are missing for core logic
- The change affects another repository without coordination

## 7. Required checks before review

For Python repositories:

```bash
ruff check .
pytest
```

For frontend repositories:

```bash
npm run lint
npm test
npm run build
```

For AI workflows:

```bash
pytest
```

Also verify:

- `.env` is not committed
- `.env.example` is updated
- Data schemas are documented
- Breaking changes are described

## 8. Environment files

Never commit real environment files.

Allowed:

```text
.env.example
```

Not allowed:

```text
.env
.env.local
credentials.json
secrets.json
private_key.pem
```

Each repository must document required environment variables in `.env.example`.

## 9. Documentation requirements

Update documentation when changing:

- APIs
- Data schemas
- Pipeline behavior
- Indicator definitions
- Advisory rules
- Prompt templates
- Environment variables
- Deployment steps

Documentation belongs in the repository where the change happens.

## 10. AI rules

For `ai-orchestration`, every AI workflow must document:

- Input schema
- Output schema
- Prompt version
- Retrieval source
- Evaluation method
- Known limitations
- Guardrails
- Human review requirement, if applicable

Do not add undocumented prompts, agents, or tools.

## 11. Merge policy

Merge only when:

- Issue is linked
- At least one review is approved
- CI passes
- Documentation is updated
- Tests are sufficient
- No secrets or sensitive data are included

The `main` branch must be protected in all active repositories.
