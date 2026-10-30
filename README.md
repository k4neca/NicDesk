# NicDesk

Aplicação desktop para Windows 11 desenvolvida para a Nic-Labs, com foco em apoiar rotinas de suporte técnico.

> **Status:** projeto em preparação. Ainda não existe implementação de produto nesta base.

## Objetivo e escopo

A visão do produto, os problemas prioritários, as personas e os limites da versão 1.0 serão estabelecidos e validados na demanda **ND-001**. O escopo funcional é governado pelo backlog; tarefas planejadas não representam funcionalidades implementadas.

## Diretrizes técnicas propostas

- Windows 11 x64, C#/.NET e WinUI 3 (Windows App SDK).
- Interface com MVVM e separação entre domínio, infraestrutura e integrações com Windows.
- Testes, segurança, acessibilidade e privacidade considerados desde cada issue.
- Versões de SDK e dependências somente serão fixadas após validação técnica.

Essas diretrizes **não** significam que uma solução .NET ou uma estrutura de projetos já tenha sido criada.

## Desenvolvimento e governança

- Repositório público: **não publicar dados de clientes, segredos, logs privados, perfis reais de VPN/SAP ou certificados**.
- Uma issue por vez, na ordem das dependências do backlog; a próxima começa após o aceite e encerramento da anterior.
- Branches: `<tipo>/<numero-real-da-issue>-<slug>`; PRs para `main`, com revisão e evidências de validação.
- O bootstrap inicial de `main` é uma exceção operacional, executada **manualmente** pelo mantenedor.
- Codex CLI é o agente principal; Claude Code pode auxiliar na revisão. **Agentes não executam commit, push, criação de PR nem merge.**
- Consulte [AGENTS.md](AGENTS.md) antes de iniciar qualquer tarefa com agentes.

## Referências de planejamento

- `NicDesk_Prompt_Mestre.md` — instruções e controles do projeto.
- `NicDesk_Backlog_Completo.xlsx` — fases, IDs, dependências e critérios de aceite.

Esses documentos foram disponibilizados ao planejamento fora desta base. Eles só devem ser versionados depois de revisão de confidencialidade e decisão explícita do responsável. Caso um agente não consiga lê-los, solicitar conteúdo sanitizado em vez de presumir seu conteúdo.

## Estado atual

Primeira demanda planejada: **ND-001 — Definir visão e problemas prioritários**. Nenhuma conclusão de issue, teste, build ou CI é presumida neste README.
