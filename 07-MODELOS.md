# SCOS — Documento 07 — Modelos

| Campo | Valor |
|---|---|
| Identificador | SCOS-DOC-07 |
| Nome | Modelos |
| Versão | 1.0 |
| Estado | Aprovado |
| Responsável | Conhecimento |
| Criado em | 2026-07-06 |
| Atualizado em | 2026-07-06 |

## Histórico de versões

| Versão | Data | Alteração | Justificativa |
|---|---|---|---|
| 1.0 | 2026-07-06 | Primeira versão oficial | Detalhamento operacional da Sprint 0 |

---

## 1. Regra geral

Todo artefato do SCOS nasce de um Modelo deste documento. Modelos são **normativos**: seções podem ser marcadas como "não se aplica" com justificativa, mas nunca omitidas em silêncio (Constituição, Artigo 2º).

Este documento é a única fonte dos Modelos. Não existe pasta de templates: copia-se daqui.

Campos entre colchetes `[assim]` são preenchidos; o restante é fixo.

## 2. M-01 — Cabeçalho Padrão

Base de todos os artefatos. Já definido no SCOS-DOC-05, seção 4; reproduzido aqui por ser o Modelo raiz:

```markdown
# [ID] — [Título]

| Campo | Valor |
|---|---|
| Identificador | [PRJ/MOD/CAP/TRB/CON]-[NNNN] |
| Tipo | [apenas para Conhecimento] |
| Versão | [apenas para Conhecimento] |
| Estado | [conforme SCOS-DOC-03, seção 4] |
| Responsável | [papel] |
| Criado em | [AAAA-MM-DD] |
| Atualizado em | [AAAA-MM-DD] |
| Relacionamentos | [IDs relacionados] |
```

## 3. M-02 — Projeto (PROJETO.md)

```markdown
[M-01]

## Propósito
[Que problema este projeto resolve, para quem, e por que agora]

## Resultado esperado
[Como saberemos que o projeto está cumprindo seu propósito]

## Fronteiras
[O que este projeto explicitamente NÃO é]

## Módulos
[Lista de MODs com uma linha de descrição cada]

## Padrões do Projeto
[ID do item de Conhecimento com os Padrões — SCOS-DOC-06, seção 4]
```

## 4. M-03 — Módulo

```markdown
[M-01]

## Propósito
[Que área funcional este módulo cobre]

## Capacidades
[Lista de CAPs deste módulo]

## Dependências
[Outros módulos de que este depende, se houver]
```

## 5. M-04 — Capacidade

```markdown
[M-01]

## Enunciado
[Quem] é capaz de [fazer o quê] para [obter qual resultado].

## Contexto
[Por que esta capacidade importa; origem da necessidade]

## Critérios de aceitação
1. [Critério verificável — julga "pronto ou não pronto" sem ambiguidade]
2. [...]

## Fora de escopo
[O que esta capacidade explicitamente não cobre]
```

A Especificação (estado do fluxo) não possui modelo próprio: **especificar é preencher completamente o M-04**, sobretudo os critérios de aceitação (ver D-07-01).

## 6. M-05 — Trabalho

```markdown
[M-01]

## Objetivo
[O que este trabalho entrega quando concluído]

## Capacidade servida
[CAP-NNNN, ou "evolução do SCOS"]

## Linha do tempo do fluxo
| Estado | Entrada | Saída (registro) | Portão em |
|---|---|---|---|
| Ideia | [data] | [CON-NNNN] | [data] |
| Descoberta | | | |
| Especificação | | | |
| Desenvolvimento | | | |
| Validação | | | |
| Concluído | | | |

## Bloqueios registrados
[Data, descrição, resolução — ou "nenhum"]
```

## 7. Modelos de Registro de Fluxo

### M-06 — Ideia
```markdown
[M-01 · Tipo: Registro de Fluxo]

## Proposta
[O que está sendo proposto]

## Problema ou oportunidade
[O que motiva a proposta]

## Origem
[De onde veio a ideia: pessoa, papel, observação, dado]
```

### M-07 — Descoberta
```markdown
[M-01 · Tipo: Registro de Fluxo]

## Problema confirmado
[O problema, validado — ou a constatação de que não se confirma]

## Público
[Quem é afetado e como]

## Restrições e riscos
[Técnicos, de negócio, legais, de prazo]

## Perguntas respondidas
[Pergunta → resposta → fonte]

## Recomendação
[Prosseguir / não prosseguir, com justificativa]
```

### M-08 — Relatório de Validação
```markdown
[M-01 · Tipo: Registro de Fluxo]

## Veredito
[APROVADO / REPROVADO]

## Critérios verificados
| Critério (do M-04) | Resultado | Evidência |
|---|---|---|

## Defeitos encontrados
[IDs dos CONs de Defeito, ou "nenhum"]
```

### M-09 — Conclusão
```markdown
[M-01 · Tipo: Registro de Fluxo]

## Entregue
[O que existe agora que não existia antes]

## Aprendizados
[IDs dos CONs de Aprendizado gerados, ou "nenhum"]

## Defeitos conhecidos aceitos
[Defeitos que se decidiu conviver, com a decisão que os aceitou]
```

## 8. Modelos de Conhecimento

### M-10 — Decisão
```markdown
[M-01 · Tipo: Decisão]

## Decisão
[O que foi decidido, em uma frase]

## Contexto
[A situação que exigiu a decisão]

## Alternativas consideradas
[Cada alternativa e por que foi rejeitada]

## Decisor
[Papel que decidiu; perspectivas ouvidas — Constituição, Artigo 6º]

## Consequências
[O que passa a valer; o que fica mais difícil]
```

### M-11 — Aprendizado
```markdown
[M-01 · Tipo: Aprendizado]

## O que aprendemos
[O aprendizado, direto]

## Como aprendemos
[O evento ou evidência que o gerou]

## O que muda
[Prática, padrão ou documento afetado, se houver]
```

### M-12 — Defeito
```markdown
[M-01 · Tipo: Defeito]

## Comportamento incorreto
[O que acontece]

## Comportamento esperado
[O que deveria acontecer, com referência ao critério do M-04]

## Como reproduzir
[Passos]

## Severidade
[Impede uso / degrada uso / cosmético]
```

### M-13 — Termo
```markdown
**[Termo]** — [Definição em uma ou duas frases]. *Ver também:* [termos relacionados].
```
Termos vivem como entradas dentro de `VOCABULARIO.md`, em ordem alfabética, não como arquivos individuais.

---

## Decisões registradas (Constituição, Artigo 4º)

**D-07-01 — Especificação não tem modelo próprio: é o M-04 completamente preenchido.** *Justificativa:* um documento de especificação separado da Capacidade criaria duas fontes para o mesmo requisito, violando o Artigo 3º. O estado Especificação transforma a Capacidade de esboço em contrato.

**D-07-02 — Seções nunca são omitidas em silêncio.** Marcar "não se aplica" exige justificativa. *Justificativa:* a omissão silenciosa é a forma mais comum de assumir informação (Artigo 2º); o custo de escrever "não se aplica porque X" é mínimo e auditável.

**D-07-03 — Os Modelos vivem apenas neste documento**, sem pasta de templates. *Justificativa:* fonte única (Artigo 3º); uma pasta de templates inevitavelmente divergiria do documento normativo.

**D-07-04 — Termos do vocabulário são entradas em um arquivo único, não arquivos individuais.** *Justificativa:* um dicionário se consulta por varredura alfabética; centenas de microarquivos dificultariam exatamente o uso que o vocabulário quer servir.

**D-07-05 — O M-05 (Trabalho) carrega a linha do tempo do fluxo dentro de si.** *Justificativa:* dá ao Steward um único lugar para verificar Portões e datas, e torna cada Trabalho autoexplicativo para qualquer executor que o abra.
