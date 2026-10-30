# Instruções para agentes — NicDesk

Estas regras se aplicam ao Codex CLI, ao Claude Code e a outros agentes que atuem nesta árvore de trabalho.

## Contexto e prioridade

- Repositório: `k4neca/NicDesk` (público); plataforma-alvo: Windows 11 x64.
- Referências: `NicDesk_Prompt_Mestre.md` e `NicDesk_Backlog_Completo.xlsx`, fornecidas pelo responsável. Não presumir que estão dentro deste repositório. Solicitar contexto sanitizado se indisponíveis.
- O planejamento exige **uma única demanda ativa por vez**, obedecendo às dependências do backlog e aos critérios de aceite da issue real.
- Antes de editar, inspecionar `README.md`, este arquivo, a issue informada, o estado Git e os arquivos efetivamente presentes. Não inventar estado de branch, número de issue, resultados ou arquitetura já implementada.

## Proibições obrigatórias de Git e GitHub

**Agentes NÃO devem executar, nem autonomamente nem após sugerir uma aprovação interativa:**

- `git commit`, `git push`, `git merge`, `git rebase`, `git reset`, `git cherry-pick`, `git tag` ou qualquer operação que publique, reescreva ou integre histórico.
- `git add`, `git switch`, `git checkout`, `git branch -d/-D`, criação de branches ou outras alterações de estado Git.
- `gh pr create`, `gh pr merge`, `gh issue create`, `gh issue edit`, `gh release create`, ou ações remotas de escrita equivalentes.
- Qualquer commit, push, pull request ou merge em nome do mantenedor, inclusive por scripts, aliases, APIs ou automações.

Agentes podem usar comandos de **leitura** como `git status`, `git diff`, `git log`, `git branch --show-current` e `gh issue view`. O mantenedor executa manualmente os comandos de Git/GitHub que alteram estado, depois de revisar seus efeitos.

**Nunca editar arquivos diretamente em `main`.** Se a branch atual não corresponder à issue autorizada, interromper edições e solicitar que o mantenedor prepare a branch. O bootstrap inicial de `main` é uma exceção **exclusivamente manual**, sem execução de agente.

## Escopo, implementação e validação

- Antes da mudança, declarar objetivos, impacto, dependências, plano e critérios de aceite. Implementar apenas o escopo da issue ativa.
- Base tecnológica planejada: C#/.NET, WinUI 3, MVVM; Clean Architecture quando apropriada. Não introduzir estrutura de projetos, bibliotecas ou versões sem confirmação ou necessidade da issue.
- Preferir lógica testável desacoplada da interface; pequenas mudanças, contratos claros, tratamento de erros, cancelamento e logs sanitizados.
- Definir cenários positivos, negativos e de borda. Executar os testes e verificações aplicáveis; nunca declarar sucesso sem evidência. Em demandas documentais, registrar por que build/test não se aplicam.
- Ao final, apresentar arquivos alterados, resumo, comandos/testes executados e resultados observados, riscos, pendências e instruções para revisão manual. **Parar antes de qualquer operação de commit/push/PR.**

## Segurança e privacidade

- Não incluir credenciais, tokens, certificados, chaves, dados de clientes, nomes de servidores internos, dumps, logs pessoais ou perfis reais de VPN/SAP em arquivos, prompts ou commits.
- Usar dados fictícios ou sanitizados. Tratar entradas, caminhos, processos e XML com validação; evitar execução de comandos arbitrários, download de binários não verificados e instalação ou elevação sem consentimento explícito.
- Diagnósticos são somente leitura por padrão. Remediação, instalação e conexões a sistemas externos exigem autorização do responsável, pré-checagens e rollback quando aplicável.
- Gravação de tela/áudio exige consentimento e indicador visível; não capturar silenciosamente.
- Não desabilitar controles, scanners ou restrições de segurança para obter sucesso aparente. Não executar flags de sandbox/permissão irrestrita.

## Entrega por issue

- Uma issue real, uma branch de nome `tipo/numero-slug`, um conjunto coeso de mudanças.
- Revisar `git diff --check`, arquivos não rastreados e possíveis segredos; registrar o que foi verificado e o que não foi.
- O mantenedor faz `git add`, `git commit`, `git push`, abertura do PR, aprovação e merge manualmente.
- Não iniciar a próxima demanda sem aceite documentado da anterior.
