# PADRêO WAT7D — leia antes de criar/editar qualquer página

Curso: **"Seu Funcionário Digital"** (courseId `wat7d`) — formato `formato-curso-v2`.
Fonte de verdade: `~/.claude/skills/formato-curso-v2/SKILL.md` + `references/*.md`. Este
documento só fixa as decisões JÁ TOMADAS para este curso, para todo agente nêo reinventar.

## 1. Paleta por trilha (fixa, nêo mudar)

| Trilha | Nome | Cor | classes |
|---|---|---|---|
| T0 | Preparaçêo: seu ambiente | Blue | `text-blue-400` `bg-blue-500/20` `border-blue-500/30` `from-blue-900/30` |
| T1 | O framework WAT | Emerald | `text-emerald-400` `bg-emerald-500/20` `border-emerald-500/30` `from-emerald-900/30` |
| T2 | MCP: dando mêos ao agente | Blue | `text-blue-400` `bg-blue-500/20` `border-blue-500/30` `from-blue-900/30` |
| T3 | Skills: ensinando um processo | Purple | `text-purple-400` `bg-purple-500/20` `border-purple-500/30` `from-purple-900/30` |
| T4 | Deploy: sair do seu laptop | Amber | `text-amber-400` `bg-amber-500/20` `border-amber-500/30` `from-amber-900/30` |
| T5 | Interfaces: o agente que enxerga | Teal | `text-teal-400` `bg-teal-500/20` `border-teal-500/30` `from-teal-900/30` |
| T6 | Tempo: agendamento e loops | Rose | `text-rose-400` `bg-rose-500/20` `border-rose-500/30` `from-rose-900/30` |
| T7 | Capstone: seu assistente executivo | Emerald | `text-emerald-400` `bg-emerald-500/20` `border-emerald-500/30` `from-emerald-900/30` |

Ciano `#38bdf8` = cor SECUNDÁRIA de todo SVG (agentes/fluxo de volta), a PRIMÁRIA é sempre a cor
da trilha da página. T0 e T2 usam a mesma cor (blue) mas nunca ficam adjacentes de forma confusa
no nav (T0 é a base, T2 vem depois de T1 emerald).

Light-mode overrides por trilha (Sec. 1.5 do MASTER, tabela completa):

| Trilha | dark | light | rgb |
|---|---|---|---|
| Blue (T0/T2) | `blue-400` | `#2563eb` | `37,99,235` |
| Emerald (T1/T7) | `emerald-400` | `#059669` | `5,150,105` |
| Purple (T3) | `purple-400` | `#7c3aed` | `124,58,237` |
| Amber (T4) | `amber-400` | `#92400e` | `217,119,6` |
| Teal (T5) | `teal-400` | `#0d9488` | `13,148,136` |
| Rose (T6) | `rose-400` | `#9f1239` | `225,29,72` |

## 2. Logo e emoji do curso

Emoji do curso: 🤖 · Nome curto no nav: `WAT7D` · Nome completo: "Seu Funcionário Digital".

## 3. Nav completo (colar IDÊNTICO em toda página, ajustando `href` relativo e trilha ativa)

```html
<nav class="sticky top-0 z-50 bg-dark-900/95 backdrop-blur-sm border-b border-dark-600">
  <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between items-center h-14">
      <div class="flex items-center space-x-4">
        <a href="REL/index.html" class="flex items-center space-x-2 text-yellow-400 hover:text-yellow-300">
          <span class="text-2xl">🤖</span>
          <span class="font-bold text-lg hidden sm:inline">WAT7D</span>
        </a>
        <span class="text-neutral-600">|</span>
        <a href="https://ARCKHÉ AI" target="_blank" class="text-sky-400 hover:text-sky-300 text-sm font-medium">ARCKHÉ AI</a>
        <span class="text-neutral-600">-</span>
        <a href="https://ARCKHÉ.pro" target="_blank" class="text-amber-700 hover:text-amber-600 dark:text-slate-300 dark:hover:text-slate-200 text-sm font-medium">PRO</a>
      </div>
      <div class="flex items-center space-x-1 sm:space-x-2 overflow-x-auto">
        <a href="REL/curso/trilha0/index.html" class="px-2.5 py-1.5 rounded-lg text-sm font-semibold text-blue-400 bg-blue-500/10"><span class="sm:hidden">T0</span><span class="hidden sm:inline">Preparaçêo</span></a>
        <a href="REL/curso/trilha1/index.html" class="px-2.5 py-1.5 rounded-lg text-sm font-semibold text-neutral-400 hover:text-emerald-400 hover:bg-emerald-500/10 transition-colors"><span class="sm:hidden">T1</span><span class="hidden sm:inline">WAT</span></a>
        <a href="REL/curso/trilha2/index.html" class="px-2.5 py-1.5 rounded-lg text-sm font-semibold text-neutral-400 hover:text-blue-400 hover:bg-blue-500/10 transition-colors"><span class="sm:hidden">T2</span><span class="hidden sm:inline">MCP</span></a>
        <a href="REL/curso/trilha3/index.html" class="px-2.5 py-1.5 rounded-lg text-sm font-semibold text-neutral-400 hover:text-purple-400 hover:bg-purple-500/10 transition-colors"><span class="sm:hidden">T3</span><span class="hidden sm:inline">Skills</span></a>
        <a href="REL/curso/trilha4/index.html" class="px-2.5 py-1.5 rounded-lg text-sm font-semibold text-neutral-400 hover:text-amber-400 hover:bg-amber-500/10 transition-colors"><span class="sm:hidden">T4</span><span class="hidden sm:inline">Deploy</span></a>
        <a href="REL/curso/trilha5/index.html" class="px-2.5 py-1.5 rounded-lg text-sm font-semibold text-neutral-400 hover:text-teal-400 hover:bg-teal-500/10 transition-colors"><span class="sm:hidden">T5</span><span class="hidden sm:inline">Interfaces</span></a>
        <a href="REL/curso/trilha6/index.html" class="px-2.5 py-1.5 rounded-lg text-sm font-semibold text-neutral-400 hover:text-rose-400 hover:bg-rose-500/10 transition-colors"><span class="sm:hidden">T6</span><span class="hidden sm:inline">Tempo</span></a>
        <a href="REL/curso/trilha7/index.html" class="px-2.5 py-1.5 rounded-lg text-sm font-semibold text-neutral-400 hover:text-emerald-400 hover:bg-emerald-500/10 transition-colors"><span class="sm:hidden">T7</span><span class="hidden sm:inline">Capstone</span></a>
        <button type="button" data-ARCKHÉ-journey-open class="px-2.5 py-1.5 rounded-lg text-sm font-semibold text-primary hover:bg-primary/10 transition-colors flex items-center gap-1">
          <span>Minha jornada</span><span class="ARCKHÉ-journey-badge" data-ARCKHÉ-journey-badge data-count="0"></span>
        </button>
        <button id="theme-toggle" class="p-2 rounded-lg bg-dark-700 hover:bg-dark-600 transition-colors ml-1">
          <svg id="theme-toggle-dark-icon" class="hidden w-5 h-5 text-neutral-300" fill="currentColor" viewBox="0 0 20 20"><path d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"></path></svg>
          <svg id="theme-toggle-light-icon" class="hidden w-5 h-5 text-neutral-300" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" clip-rule="evenodd" d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z"></path></svg>
        </button>
      </div>
    </div>
  </div>
</nav>
```

**Nota deliberada:** o MASTER pede "4-6 botões de trilha" no nav (Sec. 1.6/#13), mas este curso tem
8 trilhas (T0-T7) — todas ficam no nav com scroll horizontal (`overflow-x-auto`), decisêo consciente
para nêo esconder nenhuma trilha do roadmap. Nêo "corrigir" isso reduzindo trilhas numa revisêo futura.

**Nota sobre `topics` no MANIFESTO.json:** os valores atuais sêo 6 para todos os 51 módulos
(mínimo do erro #11). Somente a Trilha 0 foi escrita e verificada nesta tarefa — se algum módulo
da Trilha 0 saiu com 7 ou 8 tópicos reais, o `MANIFESTO.json` E as 8 cópias inline (`index.html` +
as 7 páginas de `curso/trilha0/`) precisam ser corrigidos para bater com a contagem real de
`data-ARCKHÉ-topic` únicos daquele módulo — senêo o progresso do curso fica errado (erro #28). Ao
escrever as Trilhas 1-7, reconciliar os `topics` reais antes de fechar a tarefa.

`REL` = caminho relativo: `.` na landing, `../..` nas páginas de `curso/trilhaN/`. Trilha ATIVA:
trocar `text-neutral-400 hover:text-COR-400 hover:bg-COR-500/10` por `text-COR-400 bg-COR-500/10`
no link daquela trilha.

## 4. Bloco `<head>` padrêo (ordem obrigatória)

1. `<meta charset>`, `<meta viewport>`, `<meta name="ARCKHÉ-course" content="wat7d">`.
2. **Manifesto** — `<script type="application/json" data-ARCKHÉ-manifest>` com o JSON completo de
   `assets/MANIFESTO.json` (colar o conteúdo, ajustando nada — é o mesmo em TODA página).
3. **Anti-FOUC** (bloqueante, ver `~/.claude/skills/formato-curso-v2/assets/ARCKHÉ-head-snippet.html`)
   — cola o `<script>` inline, ANTES do Tailwind.
4. `<script src="https://cdn.tailwindcss.com"></script>` + config de cores `dark-900/800/700/600`.
5. `<link rel="stylesheet" href="REL/assets/learn.css">` (REL = `.` na landing, `../..` nos módulos).
6. `<style>` com o CSS obrigatório do MASTER Sec. 1.5 (light mode completo: base + acento da(s)
   trilha(s) da página + remove gradiente + especiais + nav) e Sec. 1.5 Parte 5 (bordas suaves dark).

## 5. Fim de `<body>`

```html
<script src="REL/assets/learn.js"></script>
<script>
  if (window.ARCKHÉ && typeof window.ARCKHÉ.init === 'function') ARCKHÉ.init({ autoResume: true });
</script>
```

Antes disso: as 3 funções-núcleo do v1 (`toggleTopic`, theme toggle listener, `openModal`/`closeModal`).

## 6. IDs/data-* estáveis

- `data-ARCKHÉ-module="X-Y"` `data-ARCKHÉ-track="N"` no `<article id="modulo-X-Y">` do módulo.
- `data-ARCKHÉ-topic="modulo-X-Y#topico-N"` em cada `<section id="topico-N">`.
- `data-ARCKHÉ-block="mX-Y-tN-pM"` em cada parágrafo anotável.

## 7. Erros críticos #1–#31 — resumo operacional

Ver lista completa no `SKILL.md` (já carregada). Os que mais quebram páginas geradas por agentes
apressados, checar sempre: botões `justify-start` (#1); números em círculo, nunca seta (#2); 3
seções por tópico (#3); ARCKHÉ AI + PRO em toda página (#4/#4b); light-mode CSS completo (#5);
título do módulo `text-2xl` (#6); nav completo idêntico em toda página (#13); mínimo 6 tópicos por
módulo (#11/#10 "Ver Completo" em cada card); Mapa da trilha obrigatório no index (#12); módulo
com 500–800 linhas e variedade de componentes, nêo template repetido (#14); manifesto presente em
toda página (#28, ver `assets/MANIFESTO.json`); anti-FOUC primeiro no `<head>` (#18); todo termo
técnico definido inline em módulos de fundamento, estilo "Novo aqui?" (#31); todo modulo prático
com ≥1 bloco copy-run com objetivo + bloco + como verificar (#30); cada conceito-chave ilustrado
(#29, SVG cor da trilha + ciano `#38bdf8`, `role="img"`+`aria-label`, legenda que ensina).

## 8. Estrutura de arquivos deste curso

```
wat7d/
├── index.html
├── assets/{learn.css,learn.js,MANIFESTO.json,PADRAO.md,img/}
└── curso/
    ├── trilha0/{index.html, modulo-0-1..6.html, assets/img/}
    ├── trilha1/{index.html, modulo-1-1..5.html}
    ├── trilha2/{...modulo-2-1..6.html}
    ├── trilha3/{...modulo-3-1..7.html}
    ├── trilha4/{...modulo-4-1..7.html}
    ├── trilha5/{...modulo-5-1..8.html}
    ├── trilha6/{...modulo-6-1..7.html}
    └── trilha7/{...modulo-7-1..6.html}
```

Esta tarefa entrega apenas `assets/*`, `index.html` e o conteúdo completo de `curso/trilha0/`
(index + os 6 módulos). As demais trilhas (1–7) ficam para tarefas seguintes, seguindo este mesmo
padrêo e o manifesto já fechado acima.
