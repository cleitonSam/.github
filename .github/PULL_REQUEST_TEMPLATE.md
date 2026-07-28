<!--
  Título do PR no padrão Conventional Commits.
  Ex.: feat(checkout): adiciona pagamento via pix
-->

## Contexto

<!-- Qual problema this PR resolve e por que agora. -->

Closes #

## O que foi feito

- 

## Tipo de mudança

- [ ] feat - nova funcionalidade
- [ ] fix - correção de bug
- [ ] refactor - mudança interna sem alterar comportamento
- [ ] perf - performance
- [ ] docs - documentação
- [ ] test - testes
- [ ] build / ci - infraestrutura de build ou pipeline
- [ ] chore - manutenção
- [ ] BREAKING CHANGE - quebra compatibilidade

## Como validar

<!-- Passo a passo para o revisor reproduzir o resultado. -->

1. 
2. 

## Evidência

<!-- Print, GIF, log ou saída de teste. Remova qualquer dado sensível. -->

## Checklist de qualidade

- [ ] Título do PR segue Conventional Commits
- [ ] Build local passa
- [ ] Lint e formatação sem erro
- [ ] Testes adicionados ou atualizados e suite completa verde
- [ ] Documentação atualizada (README, docs/, comentários públicos)
- [ ] Sem código morto, `console.log` ou TODO esquecido
- [ ] PR com escopo pequeno e revisável

## Checklist de segurança

- [ ] Nenhum segredo, token, chave ou credencial no diff
- [ ] Entradas externas validadas e sanitizadas
- [ ] Consultas ao banco parametrizadas
- [ ] Autorização verificada nos novos endpoints
- [ ] Dependências novas justificadas e sem vulnerabilidade conhecida
- [ ] Logs sem dado pessoal ou sensível

## Impacto

- [ ] Requer migração de banco (reversível e testada)
- [ ] Requer nova variável de ambiente (adicionada em `.env.example`)
- [ ] Requer ação manual no deploy
- [ ] Nenhum impacto operacional

## Plano de rollback

<!-- Como desfazer com segurança caso algo falhe em produção. -->
