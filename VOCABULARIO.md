# SCOS — Vocabulário Oficial

| Campo | Valor |
|---|---|
| Identificador | SCOS-VOCABULARIO |
| Nome | Vocabulário Oficial |
| Versão | 1.0 |
| Estado | Aprovado |
| Responsável | Conhecimento |
| Criado em | 2026-07-06 |
| Atualizado em | 2026-07-06 |

Regra: nenhum documento oficial usa termo próprio que não esteja aqui (SCOS-DOC-05, seção 8). Novos termos entram apenas por registro do papel Conhecimento.

---

**Aprendizado** — Item de Conhecimento que registra algo que o SCOS ou um projeto aprendeu e não quer reaprender. *Ver também:* Conhecimento, Defeito.

**Capacidade** — Objeto fundamental: algo que o software é capaz de fazer para alguém, descrito do ponto de vista de quem usa. É a unidade de requisito do SCOS. *Ver também:* Módulo, Trabalho.

**Conhecimento (objeto)** — Objeto fundamental: qualquer informação registrada com valor duradouro. Único objeto com versionamento interno. *Ver também:* Fonte Oficial da Verdade, Tipo de Registro.

**Conhecimento (papel)** — Papel responsável por registrar e preservar; guardião da Fonte Oficial da Verdade e do Vocabulário. *Ver também:* Papel.

**Constituição** — Documento de autoridade máxima do SCOS (SCOS-DOC-01). Nenhuma prática ou documento prevalece sobre ela.

**Decisão** — Item de Conhecimento que registra o que foi decidido, por quê, alternativas consideradas e quem decidiu. Exigida pelo Artigo 4º.

**Defeito** — Item de Conhecimento que registra um comportamento incorreto identificado, com contexto e reprodução.

**Descoberta** — Segundo estado do Fluxo Operacional: investiga se a ideia vale a pena e o que é preciso saber. Único estado cujo Portão pode recomendar encerramento.

**Documento Oficial** — Item de Conhecimento normativo do SCOS ou de um projeto (os arquivos da raiz e os PROJETO.md).

**Entrevista de Projeto** — Procedimento obrigatório de nascimento de todo Projeto, conduzido pelo papel Produto em quatro blocos (Propósito, Estrutura, Técnica, Operação). Definida no SCOS-DOC-08.

**Especificação** — Terceiro estado do Fluxo Operacional: preencher completamente a Capacidade, sobretudo seus critérios de aceitação, transformando-a em contrato verificável.

**Estado** — Posição de um objeto em seu ciclo de vida. Trabalhos seguem os estados do Fluxo Operacional; os demais objetos seguem Rascunho → Ativo → Obsoleto.

**Executor** — Quem realiza trabalho dentro do SCOS: pessoa ou IA, sob as mesmas regras. Substituível por definição. *Ver também:* Sessão de Trabalho.

**Fluxo Operacional** — O caminho único de todo Trabalho: Ideia → Descoberta → Especificação → Desenvolvimento → Validação → Concluído (SCOS-DOC-04).

**Fonte Oficial da Verdade** — O repositório Git com arquivos Markdown onde vive todo o conhecimento oficial. O que não está nele não existe para o SCOS (Artigo 3º).

**Ideia** — Primeiro estado do Fluxo Operacional: o registro do que está sendo proposto e por quê.

**Modelo** — Esqueleto normativo de artefato, definido no SCOS-DOC-07 (M-01 a M-13). Todo artefato nasce de um Modelo.

**Módulo** — Objeto fundamental: grande área funcional dentro de um Projeto, que organiza Capacidades.

**Objeto Fundamental** — Um dos cinco tipos de coisas que existem no SCOS: Projeto, Módulo, Capacidade, Trabalho e Conhecimento. Nenhum outro tipo pode ser criado.

**Papel** — Responsabilidade oficial, não pessoa nem IA. São exatamente seis: CEO, Steward, Produto, Engenharia, Qualidade e Conhecimento.

**Portão** — Verificação formal que autoriza a transição entre dois estados: saída obrigatória registrada, declaração do responsável e confirmação do Steward.

**Portão de Nascimento** — Portão específico que torna um Projeto Ativo após a Entrevista de Projeto e a aprovação do CEO (SCOS-DOC-08, seção 4).

**Projeto** — Objeto fundamental: a maior unidade do SCOS; um produto ou iniciativa com objetivo próprio.

**Registro de Fluxo** — Tipo de item de Conhecimento que materializa as saídas obrigatórias dos estados do Fluxo Operacional.

**Sessão de Trabalho** — A unidade de atuação de um executor: abertura (orientação pela Fonte), execução (dentro do estado) e encerramento (inventário e registro). Definida no SCOS-DOC-09.

**Steward** — Papel que coordena: intermedia a comunicação operacional, opera todos os Portões e garante que o fluxo seja seguido. Não julga mérito.

**Termo** — Entrada deste Vocabulário; tipo de item de Conhecimento.

**Tipo de Registro** — Classificação de um item de Conhecimento: Decisão, Registro de Fluxo, Aprendizado, Defeito, Termo ou Documento Oficial.

**Trabalho** — Objeto fundamental: unidade de execução que percorre o Fluxo Operacional para servir a uma Capacidade ou à evolução do SCOS.

**Validação** — Quinto estado do Fluxo Operacional: verificação, pelo papel Qualidade, de que a entrega corresponde à especificação. Sua reprovação é a única transição para trás do fluxo.
