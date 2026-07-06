# SCOS — Documento 08 — Inicialização

| Campo | Valor |
|---|---|
| Identificador | SCOS-DOC-08 |
| Nome | Inicialização |
| Versão | 1.0 |
| Estado | Aprovado |
| Responsável | Steward |
| Criado em | 2026-07-06 |
| Atualizado em | 2026-07-06 |

## Histórico de versões

| Versão | Data | Alteração | Justificativa |
|---|---|---|---|
| 1.0 | 2026-07-06 | Primeira versão oficial | Detalhamento operacional da Sprint 0; inclui o Protocolo de Profundidade por determinação do CEO |

---

## 1. As duas inicializações

O SCOS possui dois procedimentos de nascimento:

1. **Inicialização do SCOS** — feita uma única vez: criação da Fonte Oficial da Verdade e aprovação dos documentos oficiais. Concluída na Sprint 0.
2. **Inicialização de Projeto** — feita a cada novo projeto, por meio da **Entrevista de Projeto**. É o único caminho para um Projeto passar a existir.

**Regra absoluta:** nenhum Projeto entra em operação — e nenhuma linha de código é escrita — sem ter passado pela Entrevista de Projeto e pelo Portão de Nascimento. Esta regra é a aplicação direta do Artigo 2º da Constituição: o SCOS nunca assume informações, e um projeto não entrevistado é uma pilha de suposições.

## 2. A Entrevista de Projeto

A Entrevista é conduzida pelo executor no papel **Produto**, com o CEO (e demais interessados) como entrevistados. Ela transforma a visão que existe na cabeça das pessoas em artefatos registrados.

Regras de condução:

- **Nenhuma resposta é assumida.** Pergunta sem resposta fica registrada como pendência, nunca preenchida por dedução.
- **Poucas perguntas por vez.** O entrevistador conduz em blocos, aprofundando onde as respostas pedirem, em vez de despejar o questionário inteiro.
- **Nenhuma resposta genérica é aceita.** Toda resposta é testada contra o Critério de Suficiência (seção 3) antes de o entrevistador seguir adiante.
- **O entrevistador auxilia ativamente.** Cada pergunta vem acompanhada do nível de detalhe esperado e de exemplos calibradores (seção 3.3).
- **Síntese confirmada.** Ao final de cada bloco, o entrevistador apresenta sua síntese e o entrevistado confirma ou corrige antes de virar artefato.
- **Respostas viram artefatos imediatamente**, usando os Modelos do SCOS-DOC-07.

## 3. Protocolo de Profundidade

### 3.1 Critério de Suficiência

Uma resposta é **suficiente** quando permite preencher a seção correspondente do Modelo **sem inventar, deduzir ou generalizar nada**. Se ao redigir o artefato o entrevistador precisaria completar qualquer lacuna com suposição própria, a resposta é insuficiente — e a entrevista **não avança** naquele ponto.

Este critério é objetivo e auditável: qualquer pessoa pode pegar a resposta registrada, tentar preencher o Modelo, e verificar se sobrou lacuna.

### 3.2 Ciclo de Aprofundamento

Diante de resposta insuficiente, o entrevistador executa, nesta ordem:

1. **Nomeia a insuficiência**, com respeito e sem burocratês: diz exatamente o que ainda falta para a resposta virar artefato.
2. **Reformula em perguntas menores e mais concretas**: quem exatamente, quantos, com que frequência, como isso é feito hoje, me dê um exemplo real, o que acontece se der errado.
3. **Pede detalhe técnico quando a natureza da pergunta exigir** (sobretudo no Bloco C): versões, volumes, integrações existentes, restrições de infraestrutura. "Vai ser na nuvem" não atravessa o Critério de Suficiência.
4. **Oferece exemplos calibradores** (seção 3.3) se o entrevistado demonstrar não saber *como* responder.
5. **Registra pendência** se, mesmo após os passos anteriores, o entrevistado genuinamente não souber (seção 3.4).

**Exemplo do ciclo em funcionamento:**

> **Pergunta:** Que problema este projeto resolve?
> **Resposta recebida:** "Quero um app para donos de pets."
> **Entrevistador:** Isso me diz o público, mas ainda não o problema — com essa resposta eu teria que inventar o motivo do projeto, e o SCOS me proíbe de inventar. Vamos por partes: o que um dono de pet tenta fazer hoje e não consegue, ou consegue mal? Me conte uma situação real que você presenciou. Para calibrar o nível de detalhe, uma resposta suficiente se parece com: "Donos de pets em cidades médias não têm como encontrar veterinários disponíveis de madrugada; hoje recorrem a grupos de WhatsApp e muitas vezes não obtêm resposta a tempo."

### 3.3 Exemplos calibradores

Exemplos calibradores mostram **o formato e a profundidade** de uma resposta suficiente — nunca sugerem o conteúdo da resposta certa. O entrevistador deve deixar isso explícito ("isto é um exemplo do nível de detalhe, não uma sugestão do que responder") e, sempre que possível, oferecer **dois ou três exemplos em direções diferentes**, para que o entrevistado não seja puxado para uma única resposta.

Induzir a resposta do entrevistado é violação do Artigo 2º tanto quanto assumi-la: nas duas situações, o conteúdo registrado deixou de vir de quem sabe.

### 3.4 O limite honesto: pendência

Se após o Ciclo de Aprofundamento o entrevistado genuinamente não souber responder, a resposta **não é preenchida com o melhor palpite**. Registra-se uma pendência: o que falta saber, quem pode saber, e como se pretende descobrir. Pendências em perguntas essenciais impedem o Portão de Nascimento; pendências em perguntas acessórias são levadas para a Descoberta dos primeiros Trabalhos.

Perguntas essenciais (bloqueiam o Portão): 1, 2, 4, 6, 7, 8, 14.
As demais são acessórias e podem virar pendência sem bloquear o nascimento.

## 4. As perguntas oficiais

### 4.1 Bloco A — Propósito (alimenta o PROJETO.md, M-02)

1. Que problema este projeto resolve?
2. Para quem? Quem sofre o problema hoje e como resolve sem o projeto?
3. Por que agora?
4. Como saberemos que o projeto está dando certo? (resultado esperado, observável)
5. O que este projeto explicitamente **não** é? (fronteiras)

### 4.2 Bloco B — Estrutura (alimenta Módulos M-03 e Capacidades M-04)

6. Quais são as grandes áreas funcionais do produto? (candidatas a Módulo)
7. Para cada área: o que as pessoas serão **capazes de fazer**? (candidatas a Capacidade — sempre na forma "quem é capaz de quê para quê", nunca em termos de telas)
8. Se só uma fração disso existir na primeira entrega, o que é indispensável? (prioridade inicial)

### 4.3 Bloco C — Técnica (alimenta os Padrões do Projeto, SCOS-DOC-06 seção 4)

9. Existem restrições tecnológicas dadas? (sistemas legados, contratos, plataformas obrigatórias)
10. Há preferências de linguagem, framework ou banco? Por quê?
11. Onde o software vai rodar e como será implantado?
12. O que contará como evidência de verificação? (P-06)
13. Como serão geridos os segredos? (P-10)

Neste bloco, o Ciclo de Aprofundamento exige respostas em nível técnico verificável. Quando o entrevistado não tiver formação técnica, o entrevistador traduz cada pergunta para consequências práticas ("quantas pessoas usarão ao mesmo tempo?", "pode ficar fora do ar de madrugada?", "quanto pode custar por mês?") e registra tanto a resposta leiga quanto a tradução técnica proposta — que o entrevistado confirma.

### 4.4 Bloco D — Operação

14. Quem ocupa cada um dos seis papéis neste projeto? (SCOS-DOC-02, regra 1.4)
15. Qual a cadência de trabalho esperada?
16. Quais riscos já são conhecidos?

## 5. Saídas obrigatórias da Entrevista

A Entrevista só termina quando existem, em estado Rascunho:

| Artefato | Modelo | Origem |
|---|---|---|
| PROJETO.md | M-02 | Bloco A |
| Módulos iniciais | M-03 | Bloco B |
| Capacidades iniciais (ao menos as indispensáveis) | M-04 | Bloco B |
| Padrões do Projeto | M-10 (Decisão) | Bloco C |
| Designação de papéis e riscos | M-10 (Decisão) | Bloco D |
| Transcrição sintetizada da entrevista, incluindo pendências | M-01, Tipo Registro de Fluxo | Todos |

## 6. O Portão de Nascimento

O Projeto transita de Rascunho para **Ativo** quando:

1. Todos os artefatos da seção 5 existem e estão registrados na Fonte Oficial da Verdade.
2. Nenhuma pendência de pergunta essencial (seção 3.4) permanece aberta.
3. O CEO aprova formalmente o PROJETO.md.
4. O Steward confirma e registra a transição.

Somente após o Portão de Nascimento as Capacidades podem gerar Trabalhos, e os Trabalhos entrarem no Fluxo Operacional (SCOS-DOC-04).

## 7. Projetos incompletos

Uma Entrevista pode revelar que o projeto não está maduro. Nesse caso o Projeto permanece em Rascunho, com as pendências registradas, sem prazo de expiração. Rascunho não é fracasso: é a Constituição impedindo que suposições virem código.

---

## Decisões registradas (Constituição, Artigo 4º)

**D-08-01 — A Entrevista de Projeto é o único caminho de nascimento de um Projeto.** *Justificativa:* aplicação estrutural do Artigo 2º; sem esse monopólio, projetos nasceriam por atalho justamente sob pressão, quando as suposições são mais perigosas.

**D-08-02 — A Entrevista é conduzida em blocos com síntese confirmada, não como questionário.** *Justificativa:* despejar dezesseis perguntas de uma vez produz respostas rasas; a confirmação da síntese impede que a interpretação do entrevistador substitua a intenção do entrevistado (Artigo 2º).

**D-08-03 — Projeto imaturo permanece em Rascunho sem expiração.** *Justificativa:* criar prazo forçaria aprovação ou descarte artificial; o estado Rascunho já comunica exatamente a situação real.

**D-08-04 — A designação de papéis é saída obrigatória da Entrevista.** *Justificativa:* a regra 1.4 do SCOS-DOC-02 exige titular para todo papel em projeto ativo; verificar isso no nascimento evita descobrir a ausência no meio do fluxo.

**D-08-05 — Respostas genéricas são formalmente recusadas via Critério de Suficiência.** Determinação do CEO nesta sessão. *Justificativa:* aceitar resposta vaga é a forma mais educada de assumir informação (Artigo 2º); o critério "preencher o Modelo sem inventar nada" é objetivo e auditável por qualquer pessoa. *Alternativa considerada:* deixar a profundidade ao julgamento de cada entrevistador — rejeitada por reintroduzir a variabilidade que o SCOS existe para eliminar.

**D-08-06 — Exemplos calibradores mostram profundidade, nunca conteúdo, e vêm em direções variadas.** *Justificativa:* auxiliar quem não sabe *como* responder é dever do entrevistador, mas induzir *o que* responder corrompe o registro na origem — a resposta passaria a vir do entrevistador, não de quem sabe.

**D-08-07 — "Não sei" vira pendência registrada, e pendência essencial bloqueia o Portão de Nascimento.** *Justificativa:* forçar resposta produz ficção com aparência de dado; a lista fechada de perguntas essenciais (1, 2, 4, 6, 7, 8, 14) define objetivamente o mínimo sem o qual um projeto seria apenas aposta.

**D-08-08 — No Bloco C, entrevistados leigos respondem por consequências práticas, com tradução técnica proposta e confirmada.** *Justificativa:* exigir jargão de quem não o domina produziria respostas inventadas para agradar; a dupla (resposta leiga + tradução confirmada) preserva a origem da informação e a precisão técnica ao mesmo tempo.
