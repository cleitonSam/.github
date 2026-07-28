# Padrões de Engenharia — @cleitonSam

Este repositório é a **fonte única de verdade** dos padrões aplicados a todos os meus projetos.
Os arquivos aqui são herdados automaticamente pelo GitHub em qualquer repositório da conta que não tenha versão própria.

## O que está aqui

| Arquivo | Para que serve |
| ------- | -------------- |
| [CONTRIBUTING.md](CONTRIBUTING.md) | Fluxo de branches, Conventional Commits, checklist de PR e critérios de revisão |
| [SECURITY.md](SECURITY.md) | Política de segurança, como reportar vulnerabilidade e prazos de resposta |
| [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) | Código de conduta (Contributor Covenant 2.1) |
| [SUPPORT.md](SUPPORT.md) | Canais oficiais de suporte |
| [docs/PADRAO-DE-ENGENHARIA.md](docs/PADRAO-DE-ENGENHARIA.md) | Documento normativo: estrutura, nomenclatura, segurança, testes e definição de pronto |
| [docs/CHECKLIST-NOVO-PROJETO.md](docs/CHECKLIST-NOVO-PROJETO.md) | Checklist obrigatório de abertura e encerramento de projeto |
| [docs/MODELO-README.md](docs/MODELO-README.md) | Modelo único de README |
| [.github/PULL_REQUEST_TEMPLATE.md](.github/PULL_REQUEST_TEMPLATE.md) | Template de pull request com checklist de qualidade e segurança |
| [.github/ISSUE_TEMPLATE](.github/ISSUE_TEMPLATE) | Formulários de bug e de feature |

## Como aplicar em um projeto novo

1. Crie o repositório a partir do template `template-base`.
2. Preencha descrição, topics e licença.
3. Copie o [modelo de README](docs/MODELO-README.md) e preencha.
4. Ative proteção de branch, secret scanning e alertas do Dependabot.
5. Percorra o [checklist de novo projeto](docs/CHECKLIST-NOVO-PROJETO.md) até zerar os itens.

## Como aplicar em um projeto que já existe

1. Copie a pasta `.github/workflows` do `template-base`.
2. Adicione `.github/dependabot.yml` e `.github/CODEOWNERS`.
3. Reescreva o README no modelo padrão.
4. Ative proteção de branch e os alertas de segurança.
5. Rode uma varredura de segredos no histórico antes de tornar qualquer coisa pública.

## Regras que não se negociam

- Nada entra em `main` sem pull request revisado e pipeline verde.
- Nenhum segredo no repositório, em nenhuma hipótese.
- Commit segue Conventional Commits.
- Repositório público sem README, descrição e licença não existe: ou arruma, ou arquiva.
- Toda mudança precisa de caminho de rollback.
# .github
Padroes globais de engenharia, seguranca e qualidad aplicados a todos os repositorios de @cleitonSam
