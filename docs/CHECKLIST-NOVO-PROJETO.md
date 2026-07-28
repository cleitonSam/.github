# Checklist de Novo Projeto

> Use este checklist na criação de qualquer repositório. Enquanto houver item aberto, o projeto não está no padrão.

## 1. Criação

- [ ] Criado a partir do repositório template `template-base`
- [ ] Nome segue a nomenclatura (`api-`, `web-`, `dash-`, `lp-`, `app-`, `lib-`, `infra-`)
- [ ] Descrição preenchida em uma frase objetiva
- [ ] Topics adicionados (stack e domínio)
- [ ] Visibilidade correta definida (público apenas se pode ser público)
- [ ] LICENSE definida

## 2. Documentação

- [ ] README completo: propósito, stack, como rodar, como testar, deploy, variáveis
- [ ] `.env.example` com todas as variáveis, sem valores reais
- [ ] `docs/ARCHITECTURE.md` criado
- [ ] `docs/adr/0001-...` registrando as decisões iniciais
- [ ] `docs/RUNBOOK.md` com diagnóstico e rollback
- [ ] CHANGELOG inicializado

## 3. Qualidade

- [ ] Formatador e linter configurados e rodando no CI
- [ ] Tipagem em modo estrito quando a stack permitir
- [ ] Framework de teste configurado com pelo menos um teste real
- [ ] Limite mínimo de cobertura configurado
- [ ] `.editorconfig` presente
- [ ] Versão do runtime fixada (`.nvmrc`, `.tool-versions` ou equivalente)
- [ ] Hook de commit validando Conventional Commits

## 4. Automação

- [ ] `ci.yml` com lint, build e testes
- [ ] `codeql.yml` ativo
- [ ] `dependency-review.yml` ativo
- [ ] `secret-scan.yml` ativo
- [ ] `dependabot.yml` configurado para dependências e para GitHub Actions
- [ ] Workflow de release gerando tag, CHANGELOG e notas
- [ ] Todo workflow declara `permissions` mínimas
- [ ] Actions de terceiros fixadas por SHA

## 5. Segurança

- [ ] Branch `main` protegida com revisão e status checks obrigatórios
- [ ] Commits assinados exigidos
- [ ] Secret scanning e push protection habilitados
- [ ] Alertas do Dependabot habilitados
- [ ] Private vulnerability reporting habilitado
- [ ] CODEOWNERS definido
- [ ] Nenhum segredo no histórico (verificado com varredura)
- [ ] Environments de produção com aprovação manual

## 6. Operação

- [ ] Health check exposto
- [ ] Log estruturado configurado
- [ ] Monitoramento de erro conectado
- [ ] Backup e restore testados quando houver banco
- [ ] Deploy documentado e reproduzível

## 7. Encerramento de projeto

- [ ] Aviso no topo do README informando descontinuação
- [ ] Última release publicada
- [ ] Segredos e tokens revogados
- [ ] Repositório arquivado
