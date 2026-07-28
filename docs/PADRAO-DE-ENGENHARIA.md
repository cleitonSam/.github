# Padrão de Engenharia

> Documento normativo. Todo repositório de **@cleitonSam** segue este padrão, independentemente de linguagem ou tamanho.
> Versão 1.0.

## Princípios

1. **Código é lido muito mais do que escrito.** Clareza vence esperteza.
2. **Segurança não é etapa final.** É requisito de cada commit.
3. **Se não está automatizado, não é padrão.** Regra sem CI é só boa intenção.
4. **Repositório é documentação.** Quem chega precisa rodar o projeto em menos de 10 minutos.
5. **Reversibilidade acima de tudo.** Toda mudança precisa de caminho de volta.
6. **Menos dependências, menos superfície de ataque.**

## 1. Anatomia obrigatória de um repositório

```
.
|-- .github/
|   |-- workflows/          ci.yml, codeql.yml, dependency-review.yml, secret-scan.yml
|   |-- ISSUE_TEMPLATE/     herdado do repositorio .github
|   |-- CODEOWNERS          revisor obrigatorio por area
|   |-- dependabot.yml      atualizacao de dependencias
|-- docs/
|   |-- ARCHITECTURE.md     visao geral, diagrama e decisoes
|   |-- adr/                registros de decisao arquitetural
|   |-- RUNBOOK.md          operacao, incidentes e rollback
|-- src/                    codigo de producao
|-- tests/                  testes automatizados
|-- .editorconfig
|-- .env.example            todas as variaveis, sem valores reais
|-- .gitignore
|-- .nvmrc                  ou equivalente da stack
|-- CHANGELOG.md            gerado a partir dos commits
|-- LICENSE
|-- README.md
```

Arquivos herdados automaticamente de `cleitonSam/.github`: `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, `SUPPORT.md`, templates de issue e de pull request.

## 2. Nomenclatura

| Item | Regra | Exemplo |
| ---- | ----- | ------- |
| Repositório | minúsculo, hífen, prefixo por domínio | `dash-evoque`, `api-financa`, `lp-goodbe` |
| Branch | `tipo/escopo-descricao` | `feat/auth-refresh-token` |
| Variável de ambiente | MAIÚSCULO com underscore | `DATABASE_URL` |
| Tag de release | SemVer com prefixo v | `v2.3.1` |
| Arquivo de código | convenção da linguagem, sem acento | `user-service.ts` |

Prefixos recomendados de repositório: `api-`, `web-`, `dash-`, `lp-`, `app-`, `lib-`, `infra-`, `bot-`.

## 3. Versionamento semântico

`MAJOR.MINOR.PATCH`

- MAJOR: quebra de compatibilidade.
- MINOR: nova funcionalidade compatível.
- PATCH: correção compatível.

A versão é derivada dos commits. Ninguém edita CHANGELOG à mão.

## 4. Fluxo de branches

- `main`: sempre deployável. Protegida.
- `develop`: apenas em projetos com release programada.
- Branches de trabalho curtas, com um objetivo, rebase antes da revisão.
- Merge por squash. Histórico linear e legível.

## 5. Proteção de branch exigida em `main`

- Pull request obrigatório, com no mínimo 1 aprovação.
- Status checks obrigatórios: lint, build, testes, CodeQL, secret scan e dependency review.
- Conversas resolvidas antes do merge.
- Commits assinados obrigatórios.
- Histórico linear obrigatório.
- Force-push e exclusão de branch bloqueados.
- Regra vale também para o administrador. Padrão com exceção deixa de ser padrão.

## 6. Qualidade automatizada (pipeline mínimo)

| Etapa | Ferramenta típica | Bloqueia merge |
| ----- | ----------------- | -------------- |
| Formatação | Prettier / formatador da stack | Sim |
| Lint | ESLint / RuboCop / Credo | Sim |
| Tipagem | TypeScript strict | Sim |
| Testes | Vitest / Jest / RSpec / ExUnit | Sim |
| Cobertura | mínimo 70 por cento, meta 85 | Sim |
| Build | build de produção | Sim |
| SAST | CodeQL | Sim |
| Segredos | Gitleaks e secret scanning | Sim |
| Dependências | Dependency Review e Dependabot | Sim para alta e crítica |

## 7. Segurança como padrão

- 2FA na conta e chave de acesso com escopo mínimo.
- Commits assinados com GPG ou SSH.
- Segredos apenas em GitHub Secrets, Actions Environments ou cofre gerenciado.
- `.env` nunca versionado. `.env.example` sempre versionado, sem valores reais.
- `permissions: contents: read` como padrão em todo workflow, elevando apenas onde necessário.
- Actions de terceiros fixadas por SHA, não por tag móvel.
- Ambientes de produção com aprovação manual no deploy.
- Rotação de credenciais a cada 90 dias e revogação imediata em caso de exposição.
- Nenhum dado pessoal real em ambiente de desenvolvimento ou em issue.

## 8. Testes

Pirâmide: muitos testes unitários, alguns de integração, poucos de ponta a ponta nos fluxos críticos.

- Todo bug corrigido nasce com um teste que falharia antes da correção.
- Teste é determinístico. Teste instável é tratado como falha, não é ignorado.
- Nome do teste descreve comportamento esperado, não implementação.

## 9. Documentação mínima

- **README**: o que é, para que serve, stack, como rodar, como testar, como fazer deploy, variáveis de ambiente, status dos badges.
- **ARCHITECTURE.md**: diagrama, limites de contexto, fluxo de dados, integrações.
- **ADR**: uma decisão relevante por arquivo, com contexto, decisão e consequências.
- **RUNBOOK.md**: como monitorar, como diagnosticar, como reverter.

## 10. Observabilidade

- Log estruturado com nível adequado e correlation id.
- Endpoint de health check em todo serviço.
- Erro em produção rastreado por ferramenta de monitoramento.
- Nenhum dado sensível em log.

## 11. Higiene do portfólio

- Repositório sem descrição, sem README e sem topics não é portfólio, é rascunho.
- Nomes gerados automaticamente pelo GitHub devem ser renomeados ou arquivados.
- Projeto encerrado: arquivar, com aviso no topo do README.
- Experimento pessoal: manter privado ou marcar claramente como experimento.
- Todo repositório público precisa de LICENSE. Sem licença, ninguém pode usar legalmente.

## 12. Definição de pronto

Uma entrega só está pronta quando: código revisado e aprovado, pipeline verde, testes cobrindo o caso, documentação atualizada, sem débito de segurança conhecido, observabilidade em funcionamento e rollback definido.
