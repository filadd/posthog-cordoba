# PostHog Side Event: Intro to Agentic Engineering

Side event in the PostHog Córdoba series. A ~2 hour afternoon theory + discussion session for people who vibe-coded during Event 0 — bridging from "just tell it what to build" to structured agentic engineering.

## Context

Most attendees at Event 0 used AI to help build games, but experienced it purely as vibe coding (prompt → accept → iterate when broken). They're not working professionals so they lack exposure to structured workflows. This session introduces the concepts behind structured agentic engineering, starting from their own experience.

## Format

- **Duration**: ~2 hours, weekday afternoon
- **Size**: smaller group than main events
- **Vibe**: PostHog buys merienda, theory + discussion, casual
- **Venue**: Filadd, Independencia 1487 (same as always)
- **No laptops required** — this is a talk/discussion session, not a workshop

## Session Outline

5 blocks · ~2 horas · teoría + discusión. Slide-level detail lives in [[slides|slides.md]]; the visual deck was built in Claude Design.

### Bloque 01 — Intro (~20 min)

Recap del Event 0 (Diego), word cloud en vivo + Mentimeter full-bleed, prompts de discusión para que el grupo cuente su experiencia con vibe coding. Validar lo que probablemente les pasó y abrir agenda.

### Bloque 02 — Vibe Coding (~30 min)

Definición original de Karpathy (construir software sin leer el código), el loop de vibe coding, el problema del 80%, las tres deudas que se acumulan (comprensión, código frágil, falta de diseño/arquitectura) y los seis modos de falla (falsa confianza, sycophancy, errores en cadena, falta de juicio, pérdida de contexto, falta de estructura).

### Bloque 03 — Planificar y revisar (~25 min)

"Manejar a un pasante inteligente" como eje. Planificar antes de construir — iterar sobre la idea, dejar que la IA te entreviste (grill me), explorar el código existente, traer docs (Context7, MCPs) y dar referencias. Revisar antes de aceptar — código y resultado. Plannotator para anotar planes y diffs. Subagentes como segundo par de ojos.

### Bloque 04 — Ingeniería Agéntica (~30 min)

Spec-driven development como evolución del planning (specs viviendo en el repo), workflow `SPEC → DESIGN → PLAN → IMPLEMENT`, skills como conocimiento empaquetado y reutilizable, validaciones rápidas (tests + linters) y validaciones que cierran el loop (browser testing, visual diffs, end-to-end).

### Cierre (~10 min)

De aceptar lo que sale, a dirigir lo que se construye. El toolkit consolidado en una página (planificar & revisar, contexto, ing. agéntica, validación). Recursos para profundizar.
