# SCOS — Documento 03 — Objetos Fundamentais

| Campo | Valor |
|---|---|
| Identificador | SCOS-DOC-03 |
| Nome | Objetos Fundamentais |
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

O SCOS possui exatamente **cinco objetos fundamentais**. Nenhum outro tipo de objeto pode ser criado; necessidades novas são atendidas por relacionamentos ou especializações internas, nunca por objetos novos.

Nenhum objeto é apagado. Objetos superados mudam de estado, mas permanecem na Fonte Oficial da Verdade (Constituição, Artigo 11).

## 2. Atributos comuns

Todo objeto, de qualquer tipo, possui:

| Atributo | Descrição |
|---|---|
| Identificador | Código único e imutável (ver seção 3) |
| Nome | Nome curto em português |
| Descrição | O que o objeto é e por que existe |
| Estado | Posição no ciclo de vida (ver seção 4) |
| Responsável | Papel responsável pelo objeto (Constituição, Artigo 7º) |
| Datas | Criado em, atualizado em e, quando aplicável, concluído em |
| Relacionamentos | Ligações com outros objetos (ver seção 6) |

## 3. Identificadores

O identificador segue o padrão `PREFIXO-NÚMERO`, com numeração sequencial por tipo:

| Objeto | Prefixo | Exemplo |
|---|---|---|
| Projeto | PRJ | PRJ-001 |
| Módulo | MOD | MOD-014 |
| Capacidade | CAP | CAP-032 |
| Trabalho | TRB | TRB-108 |
| Conhecimento | CON | CON-215 |

Identificadores nunca são reutilizados, nem mesmo de objetos obsoletos.

## 4. Estados

**4.1 — Trabalho** segue os estados do Fluxo Operacional (SCOS-DOC-04): Ideia, Descoberta, Especificação, Desenvolvimento, Validação, Concluído.

**4.2 — Todos os demais objetos** (Projeto, Módulo, Capacidade, Conhecimento) seguem um ciclo de vida único e simples:

`Rascunho → Ativo → Obsoleto`

- **Rascunho:** o objeto existe, mas ainda não foi aprovado pelo responsável adequado.
- **Ativo:** o objeto é oficial e vigente.
- **Obsoleto:** o objeto foi superado ou concluído; permanece pesquisável, nunca é apagado.

Transições só ocorrem para frente. Um objeto Obsoleto não volta a ser Ativo: cria-se um novo objeto (ou nova versão de Conhecimento) que o substitui, com relacionamento explícito entre ambos.

## 5. Os cinco objetos

### 5.1 Projeto
A maior unidade do SCOS. Um Projeto é um produto ou iniciativa com objetivo próprio (exemplo: MiPet). Responsável: CEO.

### 5.2 Módulo
Uma grande área funcional dentro de um Projeto (exemplos no MiPet: Assinaturas, Veterinários, Marketplace). Módulos organizam Capacidades; não contêm código nem requisitos diretamente. Responsável: Produto.

### 5.3 Capacidade
Algo que o software é capaz de fazer para alguém, descrito do ponto de vista de quem usa (exemplo: "cadastrar um pet"). A Capacidade é a unidade de requisito do SCOS: todo desenvolvimento é orientado por Capacidades, nunca por páginas ou telas. Responsável: Produto.

### 5.4 Trabalho
Uma unidade de execução: o esforço concreto de levar algo do estado Ideia ao estado Concluído através do Fluxo Operacional. Todo Trabalho serve a uma Capacidade (ou à evolução do próprio SCOS). Responsável: varia conforme o estado atual (mapeamento no SCOS-DOC-04).

### 5.5 Conhecimento
Qualquer informação registrada com valor duradouro: decisões, especificações, aprendizados, defeitos, vocabulário, documentos oficiais. É o único objeto versionado internamente (v1.0, v1.1...), conforme a Constituição, Artigos 9º a 13. Responsável: Conhecimento.

## 6. Relacionamentos oficiais

```
Projeto 1—N Módulo
Módulo 1—N Capacidade
Capacidade 1—N Trabalho
Conhecimento N—N qualquer objeto
```

- Um Projeto contém Módulos.
- Um Módulo agrupa Capacidades.
- Uma Capacidade é realizada por um ou mais Trabalhos.
- Conhecimento pode referenciar qualquer objeto, e todo objeto pode referenciar Conhecimento.
- Relacionamento adicional de substituição: qualquer objeto Obsoleto aponta para o objeto que o substituiu, quando existir.

---

## Decisões registradas (Constituição, Artigo 4º)

**D-03-01 — Ciclo de vida único (Rascunho → Ativo → Obsoleto) para objetos que não são Trabalho.** *Justificativa:* o resumo exigia que todo objeto tivesse Estado, mas só definia estados para o Trabalho; criar ciclos distintos por objeto violaria "simplicidade acima de complexidade". *Alternativa considerada:* estados específicos por tipo de objeto — rejeitada por complexidade sem benefício na Sprint 0.

**D-03-02 — Padrão de identificadores PREFIXO-NÚMERO com prefixos em três letras.** *Justificativa:* identificadores pesquisáveis e legíveis são exigência do Artigo 12; três letras evitam ambiguidade entre tipos. *Alternativa considerada:* UUIDs — rejeitados por não serem legíveis por humanos.

**D-03-03 — Trabalho pode servir à evolução do próprio SCOS**, não apenas a Capacidades de Projetos. *Justificativa:* a própria Sprint 0 é trabalho e deve ser rastreável pelas regras do sistema; um sistema que não consegue descrever a si mesmo teria uma exceção permanente.

**D-03-04 — Apenas Conhecimento possui versionamento interno** (v1.0, v1.1...); os demais objetos evoluem por substituição (novo objeto + relacionamento). *Justificativa:* versionar tudo duplicaria o mecanismo de histórico já garantido pelos Artigos 11 e 13; documentos oficiais são objetos de Conhecimento e herdam o versionamento naturalmente.
