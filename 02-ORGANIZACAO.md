# SCOS — Documento 02 — Organização

| Campo | Valor |
|---|---|
| Identificador | SCOS-DOC-02 |
| Nome | Organização |
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

## 1. Natureza dos papéis

Papéis representam **responsabilidades**, não pessoas nem inteligências artificiais.

Disso decorrem quatro regras:

**1.1 — Papéis são ocupados por executores.** Um executor pode ser uma pessoa ou uma IA. O SCOS não distingue entre eles: exige de ambos as mesmas responsabilidades e os mesmos registros (Constituição, Artigos 7º e 8º).

**1.2 — Um executor pode acumular papéis.** O mesmo executor pode exercer mais de um papel, inclusive todos, desde que fique sempre registrado **em qual papel** cada ação foi realizada.

**1.3 — Especializações vivem dentro dos papéis.** Competências específicas (por exemplo: front-end, banco de dados, testes automatizados, redação técnica) são especializações internas de um papel, e não novos papéis. O SCOS possui exatamente seis papéis.

**1.4 — Todo papel tem titular.** Em todo projeto ativo, cada um dos seis papéis deve ter um executor designado, ainda que por acúmulo (Constituição, Artigo 7º).

## 2. Os seis papéis oficiais

### 2.1 CEO
**Define a estratégia.** É a autoridade final do SCOS e de seus projetos.
Responsabilidades: definir visão e prioridades; aprovar a Constituição e suas emendas; aprovar documentos oficiais; decidir quando as perspectivas registradas divergirem (Constituição, Artigo 6º); autorizar o início e o encerramento de projetos.

### 2.2 Steward
**Coordena.** É o centro operacional do SCOS.
Responsabilidades: intermediar toda a comunicação operacional entre papéis; garantir que o Fluxo Operacional (SCOS-DOC-04) seja seguido e que nenhum estado seja pulado; verificar que cada transição passe pelo Portão correspondente; acionar o papel responsável de cada estado; reportar o andamento ao CEO.

### 2.3 Produto
**Define requisitos.** Traduz intenção em especificação.
Responsabilidades: conduzir a Descoberta; escrever e manter as Capacidades; especificar o que deve ser construído e por quê; aceitar ou recusar, do ponto de vista de requisito, o que foi entregue.

### 2.4 Engenharia
**Implementa.** Transforma especificação em software.
Responsabilidades: projetar a solução técnica dentro dos Padrões de Engenharia (SCOS-DOC-06); implementar o Trabalho especificado; registrar as decisões técnicas com justificativa (Constituição, Artigo 4º); sinalizar ao Steward qualquer informação faltante em vez de assumi-la (Constituição, Artigo 2º).

### 2.5 Qualidade
**Valida.** É o guardião do estado de Validação.
Responsabilidades: verificar que a entrega corresponde à especificação; executar e registrar as validações definidas nos Padrões; aprovar ou reprovar a passagem pelo Portão de Validação; registrar defeitos como Conhecimento.

### 2.6 Conhecimento
**Registra e preserva.** É o guardião da Fonte Oficial da Verdade.
Responsabilidades: manter a Fonte Oficial da Verdade e o vocabulário oficial; garantir que decisões, justificativas e aprendizados sejam registrados; aplicar o ciclo de vida do conhecimento (Constituição, Artigos 9º a 13); garantir que nada seja apagado e que tudo seja pesquisável.

## 3. Regras de comunicação

**3.1 — Toda comunicação operacional passa pelo Steward.** Comunicação operacional é aquela relativa a Trabalhos em andamento: dúvidas, bloqueios, entregas, transições de estado. Papéis não negociam transições diretamente entre si.

**3.2 — A comunicação estratégica é exceção.** O CEO pode comunicar-se diretamente com qualquer papel para definir estratégia e prioridades. Ainda assim, os efeitos operacionais dessas conversas retornam ao Steward para coordenação.

**3.3 — Comunicação relevante vira registro.** Qualquer comunicação que produza decisão, mudança de requisito ou aprendizado deve ser registrada na Fonte Oficial da Verdade pelo papel Conhecimento (Constituição, Artigos 3º e 9º).

## 4. Relação com o Fluxo Operacional

Cada estado do Fluxo Operacional possui um papel responsável. O mapeamento oficial entre estados e papéis é definido no documento SCOS-DOC-04 — Fluxo, para que exista em um único lugar.

---

## Decisões registradas (Constituição, Artigo 4º)

**D-02-01 — Acúmulo de papéis é permitido.** Um executor pode exercer vários papéis, registrando em qual papel cada ação foi feita. *Justificativa:* na fase atual, poucos executores exercem todas as responsabilidades; proibir o acúmulo tornaria o SCOS inoperável. *Alternativa considerada:* exigir um executor por papel — rejeitada por inviabilidade prática.

**D-02-02 — Segregação entre Engenharia e Qualidade adiada.** A regra "quem implementa não valida" não integra a v1.0. *Justificativa:* seria um conceito novo e o escopo da Sprint 0 está congelado. *Alternativa considerada:* incluir a segregação desde já — adiada para versão futura, quando houver mais de um executor disponível.

**D-02-03 — Comunicação operacional definida como tudo que se refere a Trabalhos em andamento**, com exceção estratégica para o CEO (regra 3.2). *Justificativa:* sem essa definição, a regra "tudo passa pelo Steward" seria inaplicável por ambiguidade.

**D-02-04 — O mapeamento estado→papel vive apenas no SCOS-DOC-04.** *Justificativa:* manter o mesmo conteúdo em dois documentos cria risco de divergência e viola o espírito do Artigo 3º (fonte única).

