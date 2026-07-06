# SCOS — Documento 06 — Padrões de Engenharia

| Campo | Valor |
|---|---|
| Identificador | SCOS-DOC-06 |
| Nome | Padrões de Engenharia |
| Versão | 1.0 |
| Estado | Aprovado |
| Responsável | Engenharia |
| Criado em | 2026-07-06 |
| Atualizado em | 2026-07-06 |

## Histórico de versões

| Versão | Data | Alteração | Justificativa |
|---|---|---|---|
| 1.0 | 2026-07-06 | Primeira versão oficial | Detalhamento operacional da Sprint 0 |

---

## 1. Princípio dos dois níveis

O SCOS é independente de linguagem, framework e ferramenta (SCOS-DOC-00, seção 6). Portanto, seus padrões de engenharia se dividem em dois níveis:

**Nível 1 — Padrões Universais.** Invariantes de comportamento que valem para qualquer tecnologia, definidos neste documento. Não mudam quando a tecnologia muda.

**Nível 2 — Padrões do Projeto.** Escolhas tecnológicas e convenções específicas (linguagem, framework, banco, estilo de código, estratégia de testes), definidas por cada Projeto como itens de Conhecimento do tipo Decisão.

Nenhum Trabalho pode entrar no estado Desenvolvimento antes que os Padrões do Projeto correspondente existam e estejam Ativos. Essa verificação integra o Portão da Especificação.

## 2. Padrões Universais

**P-01 — Rastreabilidade total.** Todo código nasce de um Trabalho. Nenhuma linha de código existe sem um TRB que a justifique, e toda entrega referencia seu TRB. Código sem origem rastreável não é aceito na Validação.

**P-02 — Todo código vive em Git.** O código-fonte de cada Projeto vive em repositório Git próprio, sob as mesmas regras de commit da Fonte Oficial da Verdade (SCOS-DOC-05, seção 6): mensagem `[Papel] ação: descrição (IDs)`, um assunto por commit, proibição de reescrita de histórico.

**P-03 — Decisões técnicas difíceis de reverter são registradas.** Escolha de arquitetura, de dependência estrutural, de modelo de dados ou qualquer decisão cujo desfazimento custaria mais de um Trabalho gera item de Conhecimento do tipo Decisão (Constituição, Artigo 4º). Decisões triviais e facilmente reversíveis não exigem registro.

**P-04 — A solução mais simples que atende à Especificação.** Entre duas soluções que cumprem os critérios de aceitação, vence a mais simples (SCOS-DOC-00, filosofia). Generalização especulativa — construir para necessidades que ninguém especificou — é considerada defeito de engenharia.

**P-05 — Evolução incremental.** Mudanças pequenas e frequentes têm precedência sobre mudanças grandes e raras. Reescritas totais exigem decisão registrada e aprovação do CEO.

**P-06 — Verificável por construção.** A Engenharia só inicia o que a Especificação definiu como verificável: se os critérios de aceitação não permitem julgar "pronto ou não pronto", o Trabalho volta ao Steward antes de qualquer código. Toda entrega inclui evidência de verificação (testes executados, demonstração registrada ou equivalente definido nos Padrões do Projeto).

**P-07 — Código escrito para ser lido.** A legibilidade prevalece sobre a esperteza. Comentários explicam *por que*, nunca *o que* — o "o que" deve estar legível no próprio código.

**P-08 — Idioma no código.** Termos de domínio (conceitos do produto e do SCOS) seguem o vocabulário oficial, em português. Termos técnicos seguem a convenção natural da tecnologia utilizada, normalmente em inglês. Exemplo: `buscarCapacidadePorModulo()` — domínio em português, sintaxe e verbos técnicos conforme a linguagem permitir.

**P-09 — Toda dependência externa é uma decisão.** Adicionar biblioteca, serviço ou API de terceiros gera registro de Decisão com a justificativa e a alternativa "fazer sem ela" considerada. Dependência é risco assumido, não conveniência silenciosa.

**P-10 — Nenhum segredo no repositório.** Senhas, chaves e tokens jamais entram em qualquer repositório do SCOS, nem na Fonte Oficial da Verdade nem nos repositórios de código. O mecanismo de gestão de segredos é definido nos Padrões do Projeto.

## 3. Definição de Pronto da Engenharia

Uma entrega do estado Desenvolvimento só se apresenta ao Portão quando, cumulativamente:

1. Implementa todos os critérios de aceitação da Especificação.
2. Respeita os dez Padrões Universais.
3. Respeita os Padrões do Projeto.
4. Tem suas decisões técnicas relevantes registradas (P-03).
5. Inclui evidência de verificação (P-06).

Essa lista é a "saída obrigatória" do estado Desenvolvimento (SCOS-DOC-04) em forma verificável.

## 4. Padrões do Projeto — conteúdo mínimo

Cada Projeto define, antes do primeiro Desenvolvimento, ao menos:

- Linguagens e frameworks adotados, com justificativa.
- Estrutura do repositório de código.
- Convenções de estilo e nomenclatura (respeitando P-08).
- Estratégia de verificação: o que conta como evidência (P-06).
- Mecanismo de gestão de segredos (P-10).
- Ambiente de execução e forma de implantação.

Os Padrões do Projeto são itens de Conhecimento e seguem o ciclo de vida normal: podem evoluir por versão, nunca por improviso.

---

## Decisões registradas (Constituição, Artigo 4º)

**D-06-01 — Dois níveis de padrões.** Universais no SCOS, tecnológicos no Projeto. *Justificativa:* é a única forma de ter padrões reais sem violar a independência tecnológica do SCOS-DOC-00. *Alternativa considerada:* definir uma stack padrão do SCOS — rejeitada por acoplar o sistema a tecnologias que envelhecem.

**D-06-02 — Termos de domínio em português no código (P-08).** *Justificativa:* mantém o código alinhado ao vocabulário oficial e elimina a tradução mental permanente entre documentação e implementação. *Alternativa considerada:* código integralmente em inglês — rejeitada por criar dois vocabulários para os mesmos conceitos, violando a identidade do SCOS-DOC-00.

**D-06-03 — Registro de decisão exigido apenas para o difícil de reverter (P-03).** *Justificativa:* exigir registro de toda microdecisão tornaria o Artigo 4º inobservável na prática; o critério "custaria mais de um Trabalho para desfazer" é objetivo o suficiente para ser auditável.

**D-06-04 — Padrões do Projeto são pré-requisito do Portão da Especificação.** *Justificativa:* descobrir a stack durante o Desenvolvimento é a receita clássica de improvisação; amarrar ao Portão dá ao Steward um ponto de verificação concreto.

**D-06-05 — Reescritas totais exigem aprovação do CEO (P-05).** *Justificativa:* reescrita é a decisão de engenharia com maior custo e maior apelo emocional; exigir a autoridade máxima cria o atrito saudável que a filosofia "evolução incremental acima de reescritas" pede.
