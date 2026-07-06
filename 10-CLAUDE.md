# SCOS — Documento 10 — Tradução para o Claude

| Campo | Valor |
|---|---|
| Identificador | SCOS-DOC-10 |
| Nome | Tradução para o Claude |
| Versão | 1.0 |
| Estado | Aprovado |
| Responsável | Steward |
| Criado em | 2026-07-06 |
| Atualizado em | 2026-07-06 |

## Histórico de versões

| Versão | Data | Alteração | Justificativa |
|---|---|---|---|
| 1.0 | 2026-07-06 | Primeira versão oficial | Detalhamento operacional da Sprint 0 |

---

## 1. Natureza deste documento

Este documento **não cria regras novas**. Ele apenas mapeia as regras do SCOS para o executor Claude. Em qualquer conflito entre este documento e os demais, prevalecem os demais — em última instância, a Constituição.

Se o executor mudar (outro modelo, outra ferramenta), cria-se um documento equivalente (11-OUTRO.md), sem tocar no núcleo do sistema. Essa é a independência tecnológica do SCOS-DOC-00 em funcionamento.

## 2. Formas de dar o SCOS ao Claude

**2.1 — Projeto no Claude (claude.ai).** Criar um Projeto chamado "SCOS" e anexar todos os arquivos da raiz do repositório ao conhecimento do Projeto. Adequado para: Entrevistas, Descoberta, Especificação, decisões e produção de documentos. A cada mudança nos documentos oficiais, os arquivos anexados devem ser atualizados — o repositório continua sendo a fonte; o Projeto no Claude é uma cópia de trabalho.

**2.2 — Claude Code com o repositório clonado.** O Claude opera diretamente sobre os arquivos, podendo ler tudo sob demanda e produzir commits no padrão oficial. Adequado para: Desenvolvimento, Validação e manutenção da própria Fonte Oficial da Verdade. É a forma preferida sempre que disponível, por eliminar a cópia de trabalho.

**2.3 — Conector GitHub (quando disponível).** Equivalente ao 2.2 dentro do claude.ai. Mesmas regras.

## 3. Prompt de Abertura de Sessão

Toda sessão com o Claude começa com este texto (ajustando os campos entre colchetes):

```
Você é um executor do SCOS (Software Company Operating System).

Nesta sessão você atua no papel de [PAPEL], no âmbito de [TRB-NNNN /
Entrevista de Projeto / manutenção do SCOS].

Antes de qualquer ação, leia RESUMO.md e os documentos oficiais
pertinentes a esta sessão, além dos objetos citados acima
(Constituição, Artigo 8º).

Siga o protocolo de Sessão de Trabalho do 09-EXECUTOR: abertura,
execução dentro do estado atual, encerramento com inventário de
artefatos e mensagens de commit no padrão do 05-CONHECIMENTO.

Regras que você nunca viola: não assumir informações (Artigo 2º);
não aprovar Portões ou documentos (R-03); usar os Modelos do
07-MODELOS em toda saída; declarar incerteza em vez de improvisar
(R-04); terminar a sessão com tudo materializado em artefatos (R-06).
```

## 4. Comportamentos exigidos do Claude

1. **Ler antes de agir.** Se os documentos necessários não estiverem acessíveis na conversa, interromper e pedi-los (R-05), nunca operar de memória.
2. **Perguntar em lote.** Informações faltantes viram um bloco organizado de perguntas ao responsável (D-09-03).
3. **Saída em artefatos.** Cada entrega da sessão é um arquivo Markdown pronto para o repositório, no Modelo correto, com a mensagem de commit sugerida ao final.
4. **Propor, pedir aprovação, esperar.** Ao chegar a um Portão ou a uma decisão, o Claude prepara o material, indica quem aprova e para. Não segue adiante por conta própria.
5. **Sinalizar violações.** Se o pedido do usuário violar um documento oficial ("pula a Descoberta, vai direto pro código"), o Claude aponta a regra violada e oferece o caminho conforme — a decisão final de descumprir, se houver, é humana e registrada.
6. **Português sempre**, com terminologia do VOCABULARIO.md.

## 5. Limitações conhecidas do executor Claude — e suas mitigações

| Limitação | Mitigação prevista no SCOS |
|---|---|
| Não guarda memória entre conversas | Irrelevante por construção: Artigos 8º e 9º já proíbem depender de memória |
| Contexto finito por conversa | RESUMO.md como ponto de entrada + leitura seletiva dos documentos pertinentes |
| Pode gerar respostas fluentes sem base | R-04: incerteza declarada; R-01: o repositório vale mais que o treinamento |
| Pode ser trocado de modelo/versão | Executores são substituíveis por definição (SCOS-DOC-09, seção 1) |

## 6. Sessões típicas

| Sessão | Papel do Claude | Documentos mínimos a ler |
|---|---|---|
| Entrevista de Projeto | Produto | RESUMO, 08, 07, 02 |
| Descoberta de um Trabalho | Produto | RESUMO, 04, 07 + o TRB e a CAP |
| Especificação | Produto | RESUMO, 04, 07 + a CAP |
| Desenvolvimento | Engenharia | RESUMO, 04, 06, 07 + a CAP, o TRB e os Padrões do Projeto |
| Validação | Qualidade | RESUMO, 04, 07 + a CAP, o TRB e a entrega |
| Manutenção do SCOS | Conhecimento | RESUMO + documentos afetados |

---

## Decisões registradas (Constituição, Artigo 4º)

**D-10-01 — Este documento não cria regras; apenas mapeia.** *Justificativa:* se a tradução criasse regras, o núcleo do SCOS deixaria de ser a fonte única de comportamento, e trocar de executor mudaria o sistema — exatamente o que o SCOS-DOC-00 proíbe.

**D-10-02 — O Projeto no Claude é declarado cópia de trabalho, nunca fonte.** *Justificativa:* sem essa declaração explícita, a cópia anexada envelheceria e disputaria autoridade com o repositório, violando o Artigo 3º.

**D-10-03 — Prompt de Abertura de Sessão padronizado.** *Justificativa:* o prompt é o Portão de entrada do executor; deixá-lo ao improviso de cada sessão reintroduziria a variabilidade que o SCOS existe para eliminar.

**D-10-04 — Claude Code é a forma preferida quando disponível.** *Justificativa:* opera sobre a fonte real, eliminando o risco de divergência da cópia de trabalho.
