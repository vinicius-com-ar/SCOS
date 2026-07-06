# SCOS — Documento 05 — Sistema de Conhecimento

| Campo | Valor |
|---|---|
| Identificador | SCOS-DOC-05 |
| Nome | Sistema de Conhecimento |
| Versão | 1.0 |
| Estado | Aprovado |
| Responsável | Conhecimento |
| Criado em | 2026-07-06 |
| Atualizado em | 2026-07-06 |

## Histórico de versões

| Versão | Data | Alteração | Justificativa |
|---|---|---|---|
| 1.0 | 2026-07-06 | Primeira versão oficial | Primeira etapa de detalhamento operacional da Sprint 0 |

---

## 1. A Fonte Oficial da Verdade

A Fonte Oficial da Verdade do SCOS é um **repositório Git contendo arquivos Markdown**.

Consequências diretas:

- O que não está no repositório **não existe** para o SCOS (Constituição, Artigos 3º e 9º).
- Conversas com IAs, memórias de executores, mensagens e anotações externas não têm valor normativo até serem registradas no repositório.
- O repositório é independente de ferramenta: qualquer executor capaz de ler texto consegue operá-lo.

Três artigos constitucionais são cumpridos pelo próprio mecanismo do Git:

| Artigo | Mecanismo |
|---|---|
| Art. 11 — nada é apagado | Histórico de commits |
| Art. 12 — pesquisável | Arquivos de texto + convenções de nome |
| Art. 13 — preserva histórico, data, autor e justificativa | O commit em si |

## 2. Estrutura oficial do repositório

```
SCOS/
├── 00-VISAO.md
├── 01-CONSTITUICAO.md
├── 02-ORGANIZACAO.md
├── 03-OBJETOS.md
├── 04-FLUXO.md
├── 05-CONHECIMENTO.md
├── 06-PADROES.md
├── 07-MODELOS.md
├── 08-INICIALIZACAO.md
├── 09-EXECUTOR.md
├── 10-CLAUDE.md
├── RESUMO.md
├── VOCABULARIO.md
├── registros/
│   └── CON-0001-exemplo-de-registro.md
└── projetos/
    └── PRJ-001-mipet/
        ├── PROJETO.md
        ├── modulos/
        ├── capacidades/
        ├── trabalhos/
        └── registros/
```

Regras da estrutura:

**2.1 —** A raiz contém exclusivamente os documentos oficiais do SCOS, o vocabulário e as duas pastas de nível superior. Nada mais entra na raiz.

**2.2 —** `registros/` guarda o Conhecimento do próprio SCOS (decisões sobre o sistema, aprendizados de processo).

**2.3 —** Cada Projeto vive em `projetos/PRJ-NNN-nome/` e reproduz internamente a mesma lógica: um arquivo de definição (`PROJETO.md`), pastas para Módulos, Capacidades e Trabalhos, e uma pasta `registros/` para o Conhecimento do projeto.

**2.4 —** Todo objeto fundamental é um arquivo Markdown com o cabeçalho padrão (seção 4).

## 3. Tipos de registro

Todo item de Conhecimento possui um **Tipo**, que é um atributo, não uma pasta. Os tipos oficiais são seis:

| Tipo | O que registra | Origem típica |
|---|---|---|
| Decisão | O que foi decidido, por quê, alternativas, quem decidiu | Constituição, Artigo 4º |
| Registro de Fluxo | As saídas obrigatórias dos estados (ideia, descoberta, especificação, relatório de validação, conclusão) | SCOS-DOC-04, seção 2 |
| Aprendizado | Algo que o SCOS ou o projeto aprendeu e não quer reaprender | Estado Concluído |
| Defeito | Um comportamento incorreto identificado, com contexto | Estado Validação |
| Termo | Uma entrada do vocabulário oficial | VOCABULARIO.md |
| Documento Oficial | Os documentos normativos do SCOS e dos projetos | Raiz e PROJETO.md |

Novos tipos só podem ser criados por nova versão deste documento.

## 4. Formato de um item de Conhecimento

Todo item usa o mesmo cabeçalho dos documentos oficiais, acrescido do Tipo:

```markdown
# CON-0042 — Título curto do item

| Campo | Valor |
|---|---|
| Identificador | CON-0042 |
| Tipo | Decisão |
| Versão | 1.0 |
| Estado | Ativo |
| Responsável | Engenharia |
| Criado em | AAAA-MM-DD |
| Atualizado em | AAAA-MM-DD |
| Relacionamentos | TRB-0108, CAP-0032 |

(corpo do item)
```

Nomes de arquivo seguem o padrão `CON-NNNN-titulo-em-minusculas.md`. O identificador no nome do arquivo garante unicidade; o título garante legibilidade humana.

## 5. Ciclo de vida e versionamento

**5.1 —** Itens de Conhecimento seguem o ciclo `Rascunho → Ativo → Obsoleto` (SCOS-DOC-03, seção 4.2).

**5.2 —** Conhecimento é o único objeto com versionamento interno (SCOS-DOC-03, D-03-04). Alterações de conteúdo em um item Ativo geram nova versão (v1.1, v2.0...) com linha no histórico do próprio arquivo. Correções triviais (ortografia, formatação) não geram versão.

**5.3 —** Ao obsoletar um item, registra-se no cabeçalho qual item o substituiu, quando existir.

**5.4 —** É proibido deletar arquivos do repositório e reescrever histórico (`force push`). Obsoletar é editar o Estado, nunca remover o arquivo.

## 6. Regras de registro (commits)

**6.1 —** Toda alteração no repositório é feita por commit com mensagem no padrão:

```
[Papel] ação: descrição curta (identificadores afetados)
```

Exemplos: `[Conhecimento] registro: decisão sobre banco de dados (CON-0042, TRB-0108)` · `[Engenharia] atualização: especificação técnica revisada (CON-0037)`.

**6.2 —** O Papel na mensagem indica **em qual papel** o executor agiu (SCOS-DOC-02, regra 1.2).

**6.3 —** Um commit trata de um assunto. Alterações não relacionadas entre si não compartilham commit.

**6.4 —** O papel Conhecimento é o guardião destas regras: audita periodicamente a conformidade dos registros e aponta desvios ao Steward.

## 7. Pesquisa

A pesquisa no repositório se apoia em três mecanismos, nesta ordem:

1. **Identificador:** todo objeto é encontrável pelo seu ID no nome do arquivo.
2. **Convenção de nomes:** títulos em minúsculas no nome do arquivo permitem localização por assunto.
3. **Busca textual:** qualquer ferramenta de busca em texto (grep, busca do GitHub, busca da IDE) cobre o restante.

Não existe índice manual. Índices mantidos à mão divergem do conteúdo real com o tempo e violariam o espírito do Artigo 3º (a fonte é o arquivo, não o índice).

## 8. O vocabulário oficial

`VOCABULARIO.md` é o dicionário do SCOS: cada termo próprio do sistema é uma entrada com definição curta. Terminologia própria é sempre em português (SCOS-DOC-00, seção 5). Termos novos só entram no vocabulário por registro do papel Conhecimento, e nenhum documento oficial pode usar termo próprio que não esteja no vocabulário.

---

## Decisões registradas (Constituição, Artigo 4º)

**D-05-01 — A Fonte Oficial da Verdade é um repositório Git com Markdown.** Decisão do CEO nesta sessão. *Justificativa:* os Artigos 11, 12 e 13 viram funcionalidade nativa do Git; Markdown é o formato mais neutro e independente de ferramenta. *Alternativas consideradas:* Notion/Obsidian e banco de dados — rejeitadas por criarem dependência de ferramenta específica (SCOS-DOC-00, seção 6).

**D-05-02 — Tipos de registro são atributos, não pastas.** *Justificativa:* estrutura por tipo obrigaria cada busca a saber o tipo de antemão; estrutura por contexto (SCOS vs. projeto) reflete quem é dono do conhecimento. *Alternativa considerada:* uma pasta por tipo — rejeitada por rigidez.

**D-05-03 — Seis tipos de registro oficiais.** *Justificativa:* cobrem todas as saídas obrigatórias do fluxo e as exigências constitucionais sem inventar categorias especulativas. Novos tipos exigem nova versão deste documento, protegendo contra a proliferação de categorias.

**D-05-04 — Sem índice manual.** *Justificativa:* índices manuais divergem do conteúdo com o tempo; a pesquisa se apoia em convenção de nomes e busca textual. *Alternativa considerada:* arquivo indice.md por pasta — rejeitada por custo de manutenção sem ganho real.

**D-05-05 — Padrão de mensagem de commit `[Papel] ação: descrição (IDs)`.** *Justificativa:* torna cada commit auditável quanto a responsável (Art. 7º), papel exercido (D-02-01) e objetos afetados, sem exigir tooling especial.

**D-05-06 — Proibição de deleção de arquivos e de reescrita de histórico.** *Justificativa:* aplicação direta do Artigo 11 ao mecanismo físico escolhido.
