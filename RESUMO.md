# SCOS — Resumo Oficial

| Campo | Valor |
|---|---|
| Identificador | SCOS-RESUMO |
| Nome | Resumo Oficial |
| Versão | 1.0 |
| Estado | Aprovado |
| Responsável | Conhecimento |
| Criado em | 2026-07-06 |
| Atualizado em | 2026-07-06 |

> Este arquivo é o **ponto de entrada** de qualquer executor. Leia-o primeiro, sempre (Constituição, Artigo 8º). Ele substitui o resumo original da Sprint 0, agora obsoleto.

---

## O que é o SCOS em três frases

O SCOS é um Sistema Operacional para Engenharia de Software: organiza pessoas, IAs e conhecimento em um único processo padronizado, do surgimento de uma ideia à entrega validada. Ele é independente de qualquer ferramenta, linguagem ou modelo de IA — essas coisas são executores substituíveis. Sua missão é transformar conhecimento em software de forma organizada, rastreável, previsível e contínua.

## As cinco regras de ouro

Nenhuma ação no SCOS viola estas regras, que resumem a Constituição:

1. Só existe o que está registrado na Fonte Oficial da Verdade — este repositório.
2. Nunca assuma informações: pergunte, registre a dúvida.
3. Toda decisão importante tem justificativa registrada.
4. Nada é apagado; tudo é versionado e pesquisável.
5. Toda ação tem um papel responsável, e nenhum estado do fluxo é pulado.

## Mapa de leitura

| Preciso de... | Leia |
|---|---|
| Entender o que o SCOS é | 00-VISAO.md |
| Saber o que nunca pode ser violado | 01-CONSTITUICAO.md |
| Saber quem faz o quê | 02-ORGANIZACAO.md |
| Entender os cinco objetos e seus IDs | 03-OBJETOS.md |
| Seguir o fluxo Ideia → Concluído e seus Portões | 04-FLUXO.md |
| Registrar qualquer coisa (estrutura, tipos, commits) | 05-CONHECIMENTO.md |
| Fazer engenharia (os 10 padrões e a Definição de Pronto) | 06-PADROES.md |
| Preencher qualquer artefato (os 13 modelos) | 07-MODELOS.md |
| Iniciar um projeto novo (Entrevista de Projeto) | 08-INICIALIZACAO.md |
| Atuar como executor (Sessão de Trabalho, regras de IA) | 09-EXECUTOR.md |
| Operar o SCOS especificamente no Claude | 10-CLAUDE.md |
| Conferir um termo | VOCABULARIO.md |

## Estado atual

- **Sprint 0:** documentação oficial completa (documentos 00 a 10, Vocabulário e este Resumo), aguardando apenas as aprovações finais do CEO.
- **Fonte Oficial da Verdade:** repositório Git com Markdown, estrutura definida no 05-CONHECIMENTO.
- **Próximo marco:** Entrevista de Projeto do **PRJ-001 — MiPet**, primeiro projeto do SCOS, conforme o 08-INICIALIZACAO. O MiPet valida o SCOS; não o define.

## Como abrir uma sessão

Use o Prompt de Abertura de Sessão do 10-CLAUDE.md (seção 3), informando o papel e o âmbito da sessão. A sessão segue o protocolo do 09-EXECUTOR e termina com tudo materializado em artefatos e mensagens de commit no padrão `[Papel] ação: descrição (IDs)`.
