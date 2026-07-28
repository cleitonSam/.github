# Guia de Contribuição

> Padrão único de contribuição aplicado a todos os repositórios de **@cleitonSam**.

Toda mudança entra por pull request. Não há commit direto na branch principal.

## 1. Fluxo de trabalho

```
main            produção, sempre estável e deployável
 |
 +-- develop    integração (apenas em projetos com release programada)
       |
       +-- feat/<escopo>-<descricao-curta>
       +-- fix/<escopo>-<descricao-curta>
       +-- chore/<escopo>-<descricao-curta>
       +-- hotfix/<escopo>-<descricao-curta>   (sai de main)
```

Regras de branch:

- Nomes em minúsculo, separados por hífen, sem acento e sem espaço.
- Uma branch resolve um problema. Branch grande é sinal de escopo mal definido.
- Rebase na branch base antes de pedir revisão. Histórico linear.
- Branch mergeada é excluída automaticamente.

## 2. Conventional Commits (obrigatório)

```
<tipo>(<escopo>): <resumo no imperativo, minusculo, sem ponto final>

[corpo opcional: o porque da mudanca, nao o que foi feito]

[rodape opcional: BREAKING CHANGE, Refs #123, Closes #123]
```

| Tipo | Uso | Efeito no SemVer |
| ---- | --- | ---------------- |
| feat | nova funcionalidade | MINOR |
| fix | correção de bug | PATCH |
| perf | ganho de performance | PATCH |
| refactor | mudança interna sem alterar comportamento | nenhum |
| docs | documentação | nenhum |
| test | testes | nenhum |
| build | build, dependências, empacotamento | nenhum |
| ci | pipelines e automação | nenhum |
| chore | tarefas de manutenção | nenhum |
| revert | reversão de commit | contexto |

`BREAKING CHANGE:` no rodapé (ou `!` após o escopo) gera MAJOR.

Exemplos aceitos:

```
feat(auth): adiciona refresh token com rotacao
fix(checkout): corrige calculo de frete para CEP nulo
refactor(api)!: remove endpoint v1 de pedidos
```

Exemplos recusados: `update`, `ajustes`, `wip`, `alteracoes finais`, `commit`.

## 3. Antes de abrir o pull request

- [ ] Build passa localmente.
- [ ] Lint e formatação sem erros.
- [ ] Testes novos cobrindo a mudança e suite completa verde.
- [ ] Nenhum segredo, token, credencial ou dado real no diff.
- [ ] Auditoria de dependências sem vulnerabilidade alta ou crítica.
- [ ] Documentação e CHANGELOG atualizados quando aplicável.
- [ ] Migrações de banco reversíveis e testadas.

## 4. Padrão do pull request

- Título no formato Conventional Commits.
- Descrição usando o template do repositório, com contexto, solução e evidência.
- Preferir PR pequeno: até 400 linhas alteradas revisa bem, acima disso a revisão perde qualidade.
- Marcar como Draft enquanto estiver em andamento.
- Vincular a issue correspondente.
- Merge apenas por **squash and merge**, mantendo histórico limpo.

## 5. Critérios de revisão

O revisor avalia, nesta ordem: correção, segurança, legibilidade, testes, performance e estilo.
Comentários prefixados com `nit:` são sugestões não bloqueantes.
Discussão técnica é sobre o código, nunca sobre a pessoa.

## 6. Qualidade de código esperada

- Nome revela intenção. Sem abreviação obscura.
- Função curta, com uma responsabilidade clara.
- Erro tratado de forma explícita; nunca engolir exceção.
- Configuração vem de variável de ambiente, nunca fixa no código.
- Log estruturado, sem dado pessoal ou credencial.
- Dependência nova precisa de justificativa no PR.

## 7. Ambiente local

```
git clone <repo>
cp .env.example .env
npm ci
npm run dev
```

## 8. Reportando problemas

Bugs e melhorias: use os templates de issue.
Vulnerabilidades: siga o [SECURITY.md](SECURITY.md), nunca em issue pública.
