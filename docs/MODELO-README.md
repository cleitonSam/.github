# Modelo de README

> Copie o bloco abaixo para o README de cada projeto e substitua os campos entre chaves.

---

# {nome-do-projeto}

{Uma frase dizendo o que o projeto faz e para quem.}

[![CI](https://github.com/cleitonSam/{repo}/actions/workflows/ci.yml/badge.svg)](https://github.com/cleitonSam/{repo}/actions/workflows/ci.yml)
[![CodeQL](https://github.com/cleitonSam/{repo}/actions/workflows/codeql.yml/badge.svg)](https://github.com/cleitonSam/{repo}/actions/workflows/codeql.yml)
![License](https://img.shields.io/github/license/cleitonSam/{repo})
![Last commit](https://img.shields.io/github/last-commit/cleitonSam/{repo})

## Sumário

- [Visão geral](#visão-geral)
- [Stack](#stack)
- [Começando](#começando)
- [Variáveis de ambiente](#variáveis-de-ambiente)
- [Scripts](#scripts)
- [Testes](#testes)
- [Arquitetura](#arquitetura)
- [Deploy](#deploy)
- [Segurança](#segurança)
- [Contribuição](#contribuição)
- [Licença](#licença)

## Visão geral

{Problema resolvido, contexto de negócio e principais recursos em 3 a 6 linhas.}

## Stack

| Camada | Tecnologia |
| ------ | ---------- |
| Linguagem | {} |
| Framework | {} |
| Banco de dados | {} |
| Infraestrutura | {} |
| Testes | {} |

## Começando

Pré-requisitos: {runtime e versão}, {banco}, {outros}.

```bash
git clone https://github.com/cleitonSam/{repo}.git
cd {repo}
cp .env.example .env
npm ci
npm run dev
```

Aplicação disponível em http://localhost:3000

## Variáveis de ambiente

| Variável | Obrigatória | Descrição |
| -------- | ----------- | --------- |
| `DATABASE_URL` | sim | String de conexão do banco |
| `NODE_ENV` | sim | development, test ou production |

Nunca comitar `.env`. Toda variável nova entra também no `.env.example`.

## Scripts

| Comando | Função |
| ------- | ------ |
| `npm run dev` | Ambiente de desenvolvimento |
| `npm run build` | Build de produção |
| `npm test` | Testes |
| `npm run lint` | Análise estática |
| `npm run format` | Formatação |

## Testes

```bash
npm test
npm run test:coverage
```

Cobertura mínima aceita: 70 por cento.

## Arquitetura

Detalhes em [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) e decisões em [docs/adr](docs/adr).

## Deploy

{Ambiente, gatilho, passos e como reverter. Referência ao RUNBOOK.}

## Segurança

Vulnerabilidades devem ser reportadas conforme a [política de segurança](https://github.com/cleitonSam/.github/blob/main/SECURITY.md). Não abra issue pública.

## Contribuição

Leia o [guia de contribuição](https://github.com/cleitonSam/.github/blob/main/CONTRIBUTING.md) e o [padrão de engenharia](https://github.com/cleitonSam/.github/blob/main/docs/PADRAO-DE-ENGENHARIA.md).

## Licença

Distribuído sob a licença {MIT}. Veja [LICENSE](LICENSE).
