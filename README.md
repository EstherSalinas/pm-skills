# pm-skills

Skills de [Claude Code](https://claude.com/claude-code) para trabajo de product management —
metodologías reales empaquetadas para que Claude las siga de forma consistente, en vez de
depender de que se me ocurra pedir el rigor cada vez.

## Skills

- **[`north-star`](skills/north-star/)** — elige, define y pressure-testea el North Star
  Metric de un producto antes de construir nada encima. Basada en "The North Star Playbook"
  de Amplitude (John Cutler, Ted Clark, Abbie Kouzmanoff, Ibrahim Bashir). Validada con evals
  en [`skills/north-star/evals/`](skills/north-star/evals/evals.json) — 100% de aciertos en
  los 3 casos de prueba frente a un baseline sin la skill (77% de media, con mucha más
  varianza: se salta el vision statement, no define inputs, no fija disparador de revisión).

- **[`kpi-tree`](skills/kpi-tree/)** — construye un árbol de métricas (KPI tree) desde un
  North Star o goal hacia los inputs que lo mueven, con chequeo MECE en cada nivel. Basada en
  el método de Petra Wille & Shaun Russell.

Las dos están pensadas para usarse en cadena: `north-star` decide el top, `kpi-tree`
decompone lo que hay debajo.

## Instalación

Copia la carpeta de la skill que quieras a tu directorio de skills personales de Claude Code:

```bash
cp -r skills/north-star ~/.claude/skills/north-star
cp -r skills/kpi-tree ~/.claude/skills/kpi-tree
```

Se activan automáticamente cuando el contexto de la conversación encaja con su descripción, o
invocándolas explícitamente (`/north-star`, `/kpi-tree`).

## Por qué esto existe

Escribo sobre IA aplicada a product management. Estas skills nacieron de necesitarlas para mi
propio trabajo (definir KPIs de mi newsletter) y de encontrarme construyendo un árbol de KPIs
sin haber cuestionado antes el North Star — el fallo real que `north-star` existe para evitar.
