# SCOS — Documento 09 — Executor

| Campo | Valor |
|---|---|
| Identificador | SCOS-DOC-09 |
| Nome | Executor |
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

## 1. O que é um Executor

Executor é quem realiza trabalho dentro do SCOS: uma pessoa ou uma inteligência artificial. O SCOS não distingue entre os dois — exige de ambos as mesmas regras, os mesmos registros e o mesmo protocolo (SCOS-DOC-02, regra 1.1).

Executores são **substituíveis por definição**. Todo o valor produzido por um executor deve sobreviver à sua substituição, o que só acontece se estiver registrado na Fonte Oficial da Verdade (Constituição, Artigos 3º e 9º).

## 2. A Sessão de Trabalho

Toda atuação de um executor acontece dentro de uma **Sessão de Trabalho**, que segue três fases obrigatórias:

### 2.1 Abertura

1. **Identificação:** em qual papel (ou papéis) o executor atuará nesta sessão, e sobre qual Trabalho ou objetivo.
2. **Orientação:** antes de qualquer ação, o executor lê o `RESUMO.md`, os documentos oficiais pertinentes à sessão e os objetos citados no Trabalho (Constituição, Artigo 8º: consulta antes de lembrar).
3. **Verificação de estado:** o executor confirma em qual estado do fluxo o Trabalho se encontra e atua somente dentro dele.

### 2.2 Execução

4. **Modelos sempre:** toda saída usa os Modelos do SCOS-DOC-07.
5. **Pergunta, não assume:** informação faltante gera pergunta ao responsável adequado, agrupando as perguntas quando possível para não fragmentar a comunicação (Artigo 2º).
6. **Dentro do estado:** o executor não realiza atividades de estados futuros ("já aproveitar e codificar" durante a Descoberta é violação de fluxo).
7. **Decisões pelo rito:** o executor propõe decisões usando o M-10, mas quem decide é o papel competente.

### 2.3 Encerramento

8. **Inventário:** a sessão termina com a lista de artefatos criados ou alterados.
9. **Registro:** tudo entra na Fonte Oficial da Verdade com commits no padrão do SCOS-DOC-05, seção 6.
10. **Pendências:** perguntas abertas e bloqueios são reportados ao Steward, registrados, nunca deixados implícitos.

## 3. Regras específicas para executores de IA

**R-01 — O repositório vale mais que o treinamento.** Em conflito entre o que a IA "sabe" e o que a Fonte Oficial da Verdade diz, vence a Fonte. Sempre.

**R-02 — Identificadores são verificados, nunca inventados.** O próximo ID de um tipo é o maior existente no repositório mais um, confirmado por consulta, não por memória.

**R-03 — A IA propõe; os papéis aprovam.** Nenhum executor de IA aprova Portões, aprova documentos oficiais ou emenda a Constituição. Ela prepara tudo para a aprovação e a solicita explicitamente.

**R-04 — Incerteza declarada vale mais que resposta fluente.** Quando a IA não tem certeza, diz que não tem, e registra a dúvida. Resposta confiante sem base é a violação mais grave do Artigo 2º que uma IA pode cometer.

**R-05 — Contexto insuficiente interrompe, não improvisa.** Se a IA percebe que não teve acesso aos documentos necessários, interrompe e pede o material, em vez de operar com fragmentos.

**R-06 — A conversa não é registro.** O que ficou apenas no diálogo não existe (Artigo 9º). Toda sessão de IA termina materializada em artefatos.

## 4. Regras para executores humanos

As mesmas. Humanos ganham apenas uma prerrogativa que IAs não têm: ocupar a posição de aprovador nos Portões e nos documentos, conforme o papel que exercem.

## 5. Falhas de executor

Erros de executor não geram punição; geram registro. Todo desvio identificado (estado pulado, decisão sem registro, suposição silenciosa) vira item de Conhecimento — Aprendizado ou Defeito — e, se recorrente, proposta de evolução dos documentos oficiais. O SCOS melhora pelos erros que registra, não pelos que esconde.

---

## Decisões registradas (Constituição, Artigo 4º)

**D-09-01 — Sessão de Trabalho é prática, não objeto.** *Justificativa:* criar um sexto objeto violaria o SCOS-DOC-03; a sessão deixa rastro suficiente pelos commits e artefatos que produz. *Alternativa considerada:* objeto Sessão — rejeitada por inflar a arquitetura sem informação nova.

**D-09-02 — IAs não aprovam nada (R-03).** *Justificativa:* aprovação é o exercício final de responsabilidade (Artigo 7º), e responsabilidade exige alguém que responda por ela; hoje, isso é humano. *Alternativa considerada:* permitir aprovação de IA em itens de baixo risco — adiada para versão futura, quando houver histórico para calibrar confiança.

**D-09-03 — Perguntas agrupadas em lote (regra 5).** *Justificativa:* uma pergunta por mensagem multiplica interrupções; lotes respeitam o tempo do responsável sem sacrificar o Artigo 2º.

**D-09-04 — Falha de executor gera registro, não punição.** *Justificativa:* punição incentiva ocultação, que destrói exatamente o patrimônio que o Artigo 1º protege.
