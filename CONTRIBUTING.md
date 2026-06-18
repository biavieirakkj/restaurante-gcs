# Guia de Contribuição

Este documento define os padrões que a equipe deve seguir ao trabalhar no repositório.

## Padrão de commits (Conventional Commits)

Use o formato: `tipo: descrição curta no infinitivo`

| Tipo | Quando usar | Exemplo |
|------|-------------|---------|
| `feat` | Nova funcionalidade | `feat: adiciona seção de cardápio` |
| `fix` | Correção de bug (não urgente) | `fix: corrige espaçamento do rodapé` |
| `hotfix` | Correção urgente em produção | `hotfix: corrige link quebrado do cardápio` |
| `style` | Mudança visual/CSS sem alterar lógica | `style: ajusta cores do cabeçalho` |
| `docs` | Documentação (README, login.md, etc.) | `docs: atualiza descrição do projeto` |
| `chore` | Tarefas de manutenção, configuração | `chore: configura .gitignore` |
| `refactor` | Reorganização de código sem mudar comportamento | `refactor: separa estilos em arquivo próprio` |
| `test` | Adição ou ajuste de testes (simulados) | `test: adiciona verificação simulada do formulário` |

Regras:
- Commits pequenos e atômicos (uma mudança lógica por commit).
- Mensagem no presente/infinitivo, sem ponto final.
- Sempre em português, para manter consistência no histórico.

## Padrão de branches

| Branch | Cenário | Uso |
|--------|---------|-----|
| `main` | Todos | Código sempre estável e implantável |
| `develop` | Git Flow | Integração das features antes da release |
| `feature/nome-da-feature` | Git Flow | Uma funcionalidade nova (ex.: `feature/login`) |
| `release/vX.Y` | Git Flow | Preparação de uma nova versão |
| `hotfix/vX.Y.Z` | Git Flow | Correção urgente direto a partir da `main` |
| `nova-funcionalidade-homepage` | GitHub Flow | Branch única para a entrega incremental da homepage |
| `feature-*` | Trunk-Based | Branch curta (vive no máximo 1 ciclo de commit) |

## Fluxo de Pull Request

1. Crie a branch a partir da branch base correta (veja a tabela acima).
2. Faça commits pequenos seguindo o padrão semântico.
3. Suba a branch e abra um Pull Request preenchendo o template (`.github/PULL_REQUEST_TEMPLATE.md`).
4. Peça a revisão de pelo menos um integrante da equipe (comentário + aprovação no GitHub).
5. Só faça o merge depois da aprovação.
6. Delete a branch após o merge (especialmente no Cenário 3, Trunk-Based).

## Tags

Use tags para marcar versões no Cenário 2 (Git Flow):

```
git tag -a v1.0 -m "Versão 1.0 - lançamento inicial"
git tag -a v1.0.1 -m "Hotfix - correção do link do cardápio"
git push origin --tags
```
