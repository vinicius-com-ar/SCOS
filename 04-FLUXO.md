# SCOS — Documento 04 — Fluxo Operacional

| Campo | Valor |
|---|---|
| Identificador | SCOS-DOC-04 |
| Nome | Fluxo Operacional |
| Versão | 1.0 |
| Estado | Aprovado |
| Responsável | CEO |
| Criado em | 2026-07-06 |
| Atualizado em | 2026-07-06 |

## Histórico de versões

| Versão | Data | Alteração | Justificativa |
|---|---|---|---|
| 1.0 | 2026-07-06 | Primeira versão oficial | Consolidação da fase de descoberta da Sprint 0 |

---

## 1. Regra geral

Existe **um único fluxo** para qualquer Trabalho no SCOS, seja ele de produto, técnico ou de evolução do próprio sistema:

`Ideia → Descoberta → Especificação → Desenvolvimento → Validação → Concluído`

Quatro regras invioláveis:

1. Nenhum estado pode ser pulado.
2. Cada estado possui um papel responsável.
3. Cada estado gera uma saída obrigatória, registrada como Conhecimento.
4. Cada transição passa por um Portão.

## 2. Estados, responsáveis e saídas obrigatórias

| Estado | Responsável | Pergunta que o estado responde | Saída obrigatória |
|---|---|---|---|
| Ideia | Produto | O que está sendo proposto e por quê? | Registro da ideia: problema ou oportunidade, motivação, origem |
| Descoberta | Produto | Vale a pena? O que precisamos saber? | Contexto validado: problema confirmado, público, restrições, riscos e a recomendação de prosseguir ou não |
| Especificação | Produto | O que exatamente será construído? | Capacidade especificada, com critérios de aceitação verificáveis |
| Desenvolvimento | Engenharia | Como será construído? | Software implementado conforme os Padrões (SCOS-DOC-06) + decisões técnicas registradas com justificativa |
| Validação | Qualidade | Corresponde ao que foi especificado? | Relatório de validação com veredito (aprovado ou reprovado) e evidências |
| Concluído | Conhecimento | O que aprendemos? | Registro de conclusão: o que foi entregue, aprendizados e defeitos conhecidos |

## 3. Portões

Um Portão é a verificação formal que autoriza a transição entre dois estados.

**3.1 — Condições para abrir um Portão.** Um Portão só abre quando as três condições são verdadeiras:

1. A saída obrigatória do estado atual existe e está registrada na Fonte Oficial da Verdade.
2. O responsável pelo estado atual declara o estado concluído.
3. O Steward verifica as condições anteriores e registra a transição.

**3.2 — O Steward opera todos os Portões**, mas não julga conteúdo: ele verifica existência, registro e responsabilidade. O julgamento de mérito pertence ao responsável de cada estado.

**3.3 — Portão da Descoberta.** É o único Portão com poder de encerramento: se a Descoberta recomendar não prosseguir, o CEO decide entre seguir mesmo assim (com justificativa registrada) ou encerrar o Trabalho (ver 4.2).

**3.4 — Portão da Validação.** Se o veredito for **reprovado**, o Trabalho retorna ao estado Desenvolvimento, levando consigo o relatório de validação. Esse retorno é a única transição para trás permitida no fluxo, e cada ocorrência é registrada.

## 4. Situações especiais

**4.1 — Bloqueio.** Um Trabalho que não pode avançar por falta de informação ou dependência permanece no estado atual, com o bloqueio registrado e comunicado ao Steward. Bloqueio não é estado: é uma condição registrada dentro do estado.

**4.2 — Encerramento sem entrega.** Um Trabalho pode ser encerrado em qualquer estado por decisão do CEO, com justificativa registrada. O Trabalho é marcado como Obsoleto (SCOS-DOC-03, seção 4.2), preservando todo o histórico. Nada é apagado.

**4.3 — Trabalho urgente.** Não existe atalho. A urgência pode reduzir a profundidade de cada estado (uma Descoberta de trinta minutos é válida), mas nunca eliminar um estado ou um Portão.

## 5. Diagrama oficial

```
 Ideia ──▶ Descoberta ──▶ Especificação ──▶ Desenvolvimento ──▶ Validação ──▶ Concluído
              │                                    ▲               │
              │ (não prosseguir → CEO)             └── reprovado ──┘
              ▼
          Encerrado (Obsoleto)
```

---

## Decisões registradas (Constituição, Artigo 4º)

**D-04-01 — Mapeamento estado→papel:** Ideia, Descoberta e Especificação → Produto; Desenvolvimento → Engenharia; Validação → Qualidade; Concluído → Conhecimento. *Justificativa:* decorre diretamente das responsabilidades do SCOS-DOC-02. O CEO não é responsável por nenhum estado: ele decide prioridade e encerramento, e o Steward não é responsável por estados porque opera os Portões — ser juiz e parte violaria a separação de responsabilidades.

**D-04-02 — Reprovação na Validação devolve o Trabalho a Desenvolvimento.** É a única transição para trás. *Justificativa:* sem caminho de retorno, todo defeito exigiria um Trabalho novo, fragmentando o histórico. *Alternativa considerada:* criar estado "Correção" — rejeitada por adicionar estado sem adicionar significado.

**D-04-03 — Encerramento sem entrega usa o estado Obsoleto já existente**, não um estado novo do fluxo. *Justificativa:* respeita "nenhum objeto é apagado" sem inflar o fluxo; o histórico permanece pesquisável.

**D-04-04 — Bloqueio é condição, não estado.** *Justificativa:* qualquer estado pode bloquear; criar estados de bloqueio multiplicaria o fluxo por dois sem ganho de informação.

**D-04-05 — Urgência reduz profundidade, nunca elimina estados.** *Justificativa:* proteger a regra "nenhum estado pode ser pulado" contra sua morte mais comum na vida real, que é a exceção urgente.
