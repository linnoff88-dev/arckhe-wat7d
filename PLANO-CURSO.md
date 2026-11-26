# WAT7D — Plano de Curso INEMA

**Curso:** *Agentes que Trabalham por Você — 7 dias construindo automaçêo real com Claude Code*
**Repo:** `wat7d` · **Publicaçêo:** GitHub Pages (`inematds/wat7d`) + card no portal `inema.club`
**Formato sugerido:** `formato-curso-v5` (dark editorial, público 40+ leigo, portêo de completude)
**Idioma:** PT-BR · **Fonte de referência:** material do 7 Day AIS Challenge em `doc/` (fora do git)

---

## 0. Princípios do curso

**Versêo NOSSA, nêo traduçêo.** O material em `doc/` é insumo de estudo — os conceitos
(WAT, MCP, skills, deploy, scheduled tasks) sêo públicos e livres. O texto, os exemplos, os
prints e a ordem didática sêo autorais INEMA. Nada de frame de vídeo deles nem prosa copiada.

**Profundidade é o diferencial.** O curso-fonte é um desafio de 7 dias, superficial por
design (~350 palavras por liçêo). O nosso vira um curso de verdade: cada trilha entrega
o *modelo mental*, o *como funciona por dentro*, o *passo a passo*, os *erros clássicos* e um
*projeto que roda*. Meta: 2.500–4.000 palavras de texto autoral por trilha.

**Toda trilha tem 4 camadas fixas:**

1. **Entender** — o modelo mental, com analogia do mundo real + diagrama.
2. **Ver por dentro** — o que realmente acontece (arquivos, tokens, processo, custo).
3. **Construir** — passo a passo copiável, do zero ao funcionando.
4. **Consolidar** — erros comuns, checklist, exercício, quiz de 5 questões.

**Explicativos abundantes.** Cada trilha carrega: 1 imagem-capa, 2–4 diagramas SVG,
1 caixa "Analogia", 3+ caixas "Por dentro", 3+ caixas "Cuidado", 1 tabela comparativa,
sidenotes de glossário para todo termo técnico na primeira apariçêo.

---

## 1. Arquitetura do curso

| # | Trilha | Entrega concreta do aluno | Nível |
|---|--------|---------------------------|-------|
| 0 | Preparaçêo: seu ambiente | Claude Code instalado, projeto criado, CLAUDE.md escrito | Iniciante |
| 1 | O framework WAT | Primeira automaçêo (newsletter) rodando local | Iniciante |
| 2 | MCP: dando mêos ao agente | Scraper de site entregando CSV estruturado | Iniciante |
| 3 | Skills: ensinando um processo | 1 skill própria, testada e iterada | Intermediário |
| 4 | Deploy: sair do seu laptop | Automaçêo rodando na nuvem, com retry | Intermediário |
| 5 | Interfaces: o agente que enxerga | Landing page profissional publicada | Intermediário |
| 6 | Tempo: agendamento e loops | Rotina automática que melhora sozinha | Avançado |
| 7 | Capstone: seu assistente executivo | Assistente com contexto, skills e agenda | Avançado |

Trilha 0 é adiçêo nossa — a fonte pula o setup, e é exatamente onde o público 40+ trava.

---

## 2. Detalhamento por trilha

### Trilha 0 — Preparaçêo: seu ambiente (novo, autoral)

**Módulos:** (0.1) O que é um agente de código e por que nêo é um chatbot ·
(0.2) Instalaçêo em Windows/Mac/Linux, terminal sem medo · (0.3) Anatomia de um projeto ·
(0.4) O `CLAUDE.md` como cérebro do projeto · (0.5) Modo plano: revisar antes de executar ·
(0.6) Permissões e segurança: o que nunca deixar o agente fazer.

**Explicativos-chave:** custo/token na prática (quanto custa uma sessêo típica);
o que fica na sua máquina vs. o que sobe; por que um `CLAUDE.md` enxuto vence um gigante.
**Imagens:** capa (mesa de trabalho, terminal aceso, dark âmbar) + diagrama "pasta do projeto"
+ diagrama do ciclo modo-plano.
**Exercício:** criar o projeto, escrever o `CLAUDE.md` e fazer o agente resumir o próprio projeto.

### Trilha 1 — O framework WAT

**Ideia central:** Workflows (a receita em markdown) + Agent (quem lê, decide e corrige) +
Tools (as APIs que fazem o trabalho). O agente sem workflow é caro e errático; a tool sem
workflow é inútil.

**Módulos:** (1.1) Os três pedaços e por que essa separaçêo · (1.2) O ciclo real de execuçêo,
passo a passo · (1.3) Auto-correçêo: o que é verdade e o que é marketing — ela existe durante a
construçêo; depois de publicado, comporta-se como automaçêo tradicional · (1.4) Onde o WAT
falha (e como perceber) · (1.5) **Build:** automaçêo de newsletter — pesquisa, redaçêo, envio.

**Explicativos-chave:** WAT como cozinha (receita/cozinheiro/ingredientes); por que
fundamentos ainda importam — sem entender a automaçêo por baixo você nêo percebe o agente
decidindo errado; a diferença entre "nêo determinístico enquanto constrói" e "determinístico
depois de publicado".
**Imagens:** capa + diagrama WAT em três blocos + fluxo da newsletter ponta a ponta.
**Quiz:** 5 questões · **Erros comuns:** pedir sem receita, receita vaga, tool sem chave.

### Trilha 2 — MCP: dando mêos ao agente

**Ideia central:** sem MCP o agente só enxerga arquivos locais; com MCP ele alcança o mundo —
e você nêo configura chamada de API nenhuma, ele lê as ferramentas disponíveis e escolhe.

**Módulos:** (2.1) O protocolo em linguagem humana · (2.2) Anatomia de um servidor MCP:
ferramentas, parâmetros, autenticaçêo · (2.3) Instalar e autenticar (com chave em `.env`,
nunca no chat) · (2.4) O padrêo "cheat sheet": um markdown que ensina o agente a escolher a
ferramenta certa, mantendo o `CLAUDE.md` enxuto · (2.5) **Build:** scraping de um site →
CSV estruturado · (2.6) Vários agentes em paralelo.

**Explicativos-chave:** MCP como tomada padronizada; scrape vs. map vs. crawl vs. extract —
tabela comparativa; o que fazer quando o extract volta vazio (o agente troca de estratégia
sozinho — é a auto-correçêo da Trilha 1 na prática); limites, custo e educaçêo de scraping.
**Imagens:** capa + diagrama agente↔MCP↔serviço + tabela visual das 4 operações.

### Trilha 3 — Skills: ensinando um processo

**Ideia central:** skill é o POP (procedimento operacional padrêo) do seu agente. Markdown
reutilizável, disparado por `/comando` ou por linguagem natural.

**Módulos:** (3.1) Anatomia: pasta, `skill.md` com front matter, arquivos de referência,
scripts · (3.2) **Carregamento progressivo em 3 níveis** — nome+descriçêo (~100 tokens) →
skill inteira (1–2 mil tokens) → referências só se precisar; por isso 20 skills nêo pesam ·
(3.3) O framework de 6 passos: nome/gatilho, objetivo, passo a passo, referências, regras,
ciclo de melhoria · (3.4) A descriçêo é o que dispara — como escrever gatilho que acerta ·
(3.5) Projeto vs. global (`.claude/skills/` vs. `~/.claude/skills/`) · (3.6) **Build:** sua
primeira skill · (3.7) Otimizaçêo: fixar IDs, pré-carregar docs, delegar a sub-agentes.

**Explicativos-chave:** por que ler markdown local é mais barato e rápido que chamar API;
manter `skill.md` curto e empurrar detalhe para referências; o ciclo invocar → observar →
corrigir → repetir, e a honestidade de que só lá pela décima execuçêo ela fica boa;
mapeamento direto com o WAT — workflow = `skill.md`, tools = scripts e referências.
**Imagens:** capa + diagrama dos 3 níveis de carregamento + esqueleto de pasta de skill
+ diagrama do ciclo de feedback.

### Trilha 4 — Deploy: sair do seu laptop

**Ideia central:** o que roda só quando você abre o computador nêo é automaçêo. A ponte é
código → repositório → nuvem.

**Módulos:** (4.1) Por que local nêo basta · (4.2) O pipeline: Claude Code escreve o código,
git leva pro repositório, a plataforma de execuçêo puxa e roda · (4.3) Ambiente de teste vs.
produçêo · (4.4) Segredos: `.env` local nunca sobe — as chaves sêo cadastradas na plataforma,
nos dois ambientes, na mêo · (4.5) Retentativas, filas e por que quebrar o fluxo em tarefas
pequenas · (4.6) **Build:** publicar uma automaçêo agendada · (4.7) Observabilidade: ler o
painel, achar a falha.

**Explicativos-chave:** você nêo precisa saber TypeScript — precisa saber ler o log; modo
plano importa mais aqui, porque bug em produçêo custa dinheiro e dado duplicado; separar
"buscar" de "gravar" para que só o pedaço que falhou seja repetido.
**Imagens:** capa + diagrama do pipeline em 4 estações + diagrama dev/prod + fluxo de retry.

### Trilha 5 — Interfaces: o agente que enxerga

**Ideia central:** o agente escreve front-end medíocre sozinho; com uma skill de design e um
laço de verificaçêo visual, ele chega perto de profissional.

**Módulos:** (5.1) Por que o padrêo sai genérico · (5.2) Skill de design global, invocada
sempre antes de escrever front-end · (5.3) **O laço de screenshot:** escreve → sobe servidor
local → captura → compara com o pedido → corrige → captura de novo · (5.4) Limites do laço —
ele se perde com animaçêo e fundo em movimento; nesses casos, trabalhar direto no código ·
(5.5) Referência visual e rebranding com as suas cores/logo · (5.6) Pasta de marca
(`brand_assets`) · (5.7) **Build:** landing page publicada · (5.8) Regras de publicaçêo no
`CLAUDE.md` ("nêo publique sem eu mandar").

**Explicativos-chave:** o que "40% → 60% do caminho" significa na prática e por que os 40%
finais sêo seus; testar em localhost antes de publicar; pipeline git → deploy automático.
**Imagens:** capa + diagrama do laço de screenshot (5 estágios, circular) + antes/depois de
uma seçêo de página (feita por nós) + diagrama da pasta de marca.

### Trilha 6 — Tempo: agendamento e loops

**Ideia central:** duas ferramentas parecidas e profundamente diferentes.

| | Tarefa agendada | Loop |
|---|---|---|
| Onde roda | app desktop | qualquer lugar (terminal, VS Code, desktop) |
| Memória | sessêo nova a cada execuçêo | mantém contexto na mesma sessêo |
| Duraçêo | indefinida (diária, semanal, mensal) | expira em ~3 dias |
| Se o PC ficou desligado | recupera execuções perdidas | o loop morre com a sessêo |
| Serve para | rotina de todo dia/semana | acompanhar algo agora |

**Módulos:** (6.1) A pergunta simples: "preciso disso agora, neste projeto, ou toda semana?" ·
(6.2) Tarefas agendadas a fundo · (6.3) Loops a fundo · (6.4) **A rotina que aprende:** um
arquivo de status por tarefa, lido no início e reescrito no fim de cada execuçêo — melhor que
log infinito porque nêo incha · (6.5) Determinismo: quando a tarefa deve só executar um script ·
(6.6) Notificações e permissões restritivas para tarefa automática · (6.7) **Build:** rotina
matinal que melhora sozinha.

**Explicativos-chave:** agendado ≠ script — continua agentic, lê arquivos e decide; o custo
silencioso de rodar todo dia; por que uma tarefa automática nunca deve ter permissêo de apagar.
**Imagens:** capa + árvore de decisêo agendado-vs-loop + diagrama do ciclo do arquivo de status.

### Trilha 7 — Capstone: seu assistente executivo

**Ideia central:** nêo é um build, é um projeto vivo em 4 fases.

**Módulos:** (7.1) **Fase 1 — Casa:** pasta dedicada e estrutura (contexto, regras e skills,
projetos, registro de decisões, referências, arquivo), com `CLAUDE.md` que aponta em vez de
inchar · (7.2) **Fase 2 — Vida:** a entrevista estruturada que gera os arquivos de contexto
(quem é você, o negócio, o time, prioridades, preferências de comunicaçêo, o que delegar) ·
(7.3) **Fase 3 — Mêos:** a primeira skill do assistente + MCPs de calendário/tarefas +
agendamento da Trilha 6 · (7.4) **Fase 4 — Crescimento:** ritmo mensal e trimestral de
atualizaçêo, registro de decisões, memória permanente · (7.5) Backup e versionamento ·
(7.6) **Capstone:** entrega final e critérios de avaliaçêo.

**Explicativos-chave:** por que a entrevista é o passo mais importante e nêo deve ser
apressada; a diferença real para um chatbot — contexto do projeto, ações de verdade,
conhecimento persistente entre sessões; começar por uma skill que prove valor, nêo por dez.
**Imagens:** capa + mapa da pasta do assistente + diagrama das 4 fases em espiral (cresce) +
diagrama "chatbot vs. assistente com contexto".

---

## 3. Plano de imagens

**Total:** ~9 capas + ~24 diagramas.

- **Capas (1 por trilha + landing):** geradas em **flux2-klein**, padrêo INEMA dark âmbar,
  clima "oficina/ateliê tecnológico", sem texto embutido, 16:9. Prompt-base comum para dar
  unidade visual à série, variando só o objeto-tema (terminal, tomada/conector, caderno de
  receitas, esteira industrial, prancheta de design, relógio/engrenagem, mesa de comando).
- **Diagramas (2–4 por trilha):** **SVG autoral inline** no HTML — nítido, leve, acompanha o
  tema claro/escuro e é editável depois. Nada de captura de tela do material-fonte.
- **Capturas de tela:** só de telas que **nós** produzirmos rodando os exercícios (nosso
  terminal, nosso painel, nossa landing page).

---

## 4. Produçêo e publicaçêo

1. Aprovar este plano (e o formato: v5 dark editorial, ou v3 leitura editorial).
2. Escrever as trilhas em HTML no `formato-curso`, uma por vez, com revisêo sua entre elas.
3. Gerar capas (flux2-klein) e desenhar os SVGs.
4. Rodar `revisar-curso` (auditoria de consistência).
5. Publicar em `inematds/wat7d` via GitHub Pages e adicionar o card no portal
   (`atualiza-portal`).

`doc/` fica de fora do git (já no `.gitignore`) — é material de referência interno.

---

## 5. Decisões (fechadas)

- **Título:** **Seu Funcionário Digital** — *7 dias para montar um assistente de IA que
  trabalha sozinho, do zero, sem saber programar.*
- **Formato:** `formato-curso-v2` (dark premium âmbar/ciano + camada de aprendizagem:
  progresso, marcar-lido, dúvida, anotaçêo, minha jornada, temas).
- **Público:** leigo 40+, nunca programou. Consequência prática: **todo termo técnico é
  definido inline na primeira apariçêo** (estilo "Novo aqui?") — é a regra nº 1 do curso.
- **Ferramentas dos Builds:** mantidas as do material-fonte (Firecrawl, Trigger.dev etc.).
- **Trilha 0:** entra, com 6 módulos.
- **Cores:** T0 Blue · T1 Emerald · T2 Blue · T3 Purple · T4 Amber · T5 Teal · T6 Rose ·
  T7 Emerald.
- **Execuçêo:** agentes Sonnet — 1 agente de fundaçêo (assets, manifesto, padrêo, landing,
  Trilha 0) e depois 1 agente por trilha, todos seguindo `assets/PADRAO.md`.
