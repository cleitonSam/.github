# Política de Segurança

> Documento padrão aplicado a todos os repositórios de **@cleitonSam**.

## Versões suportadas

| Versão | Suportada | Observação |
| ------ | --------- | ---------- |
| Última release estável | Sim | Recebe correções de segurança |
| Última minor anterior | Parcial | Apenas vulnerabilidades críticas |
| Versões anteriores | Não | Atualize antes de reportar |

## Como reportar uma vulnerabilidade

**Não abra issues públicas para falhas de segurança.**

1. Use a aba **Security > Report a vulnerability** (Private Vulnerability Reporting) do repositório afetado.
2. Caso o recurso não esteja disponível, envie um relato privado ao mantenedor pelo perfil [@cleitonSam](https://github.com/cleitonSam).
3. Inclua no relato: versão afetada, ambiente, passos de reprodução, impacto estimado e, se possível, prova de conceito.

### Compromissos de resposta

| Etapa | Prazo alvo |
| ----- | ---------- |
| Confirmação de recebimento | 48 horas úteis |
| Triagem e classificação de severidade (CVSS v3.1) | 5 dias úteis |
| Correção de severidade crítica ou alta | 15 dias corridos |
| Correção de severidade média ou baixa | próximo ciclo de release |
| Divulgação coordenada | após a correção publicada |

## Escopo

No escopo: código-fonte deste repositório, pipelines de CI/CD, scripts de build e dependências declaradas nos manifestos do projeto.

Fora do escopo: serviços de terceiros, engenharia social, negação de serviço por volume, achados de scanners automáticos sem impacto demonstrado e vulnerabilidades já reportadas.

## Controles de segurança adotados

- Autenticação em dois fatores obrigatória na conta do mantenedor.
- Commits assinados (GPG ou SSH) e histórico verificado.
- Proteção da branch principal: revisão obrigatória, status checks obrigatórios e force-push bloqueado.
- Análise estática de código (CodeQL) e varredura de segredos em todo push e pull request.
- Atualização automatizada de dependências via Dependabot, com agrupamento e revisão humana.
- Segredos exclusivamente em GitHub Secrets ou cofre gerenciado. Nunca em código, arquivo .env versionado, logs ou issues.
- Princípio do menor privilégio: bloco permissions declarado em cada workflow e tokens de escopo restrito.

## Boas práticas esperadas de quem contribui

- Nunca commitar credenciais, chaves, tokens, certificados ou dados reais de clientes.
- Validar e sanitizar toda entrada externa; usar consultas parametrizadas.
- Manter o menor número possível de dependências, sempre na versão estável mais recente.
- Executar a auditoria de dependências da stack antes de abrir um pull request.

## Reconhecimento

Pesquisadores que reportarem falhas de forma responsável serão creditados nas notas da release, salvo pedido de anonimato. Este projeto não opera programa de recompensa financeira.
