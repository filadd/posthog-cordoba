---
date: 2026-04-26
presented: 2026-04-27
tags: [posthog, events, agentic-engineering, slides]
---

# Intro a la Ingeniería Agéntica — Slide Deck

Side event PostHog Córdoba. ~2h teoría + discusión. Narrativa alineada con el deck v2 (HTML armado en Claude Design).

## Estructura

- 32 slides · 5 bloques · ~2 horas
- Bloque 01 · Intro (~20 min)
- Bloque 02 · Vibe Coding (~30 min)
- Bloque 03 · Planificar y revisar (~25 min)
- Bloque 04 · Ingeniería Agéntica (~30 min)
- Cierre (~10 min)

---

## 01. Cover

> **Intro a la Ingeniería Agéntica.**
> *De "hacé lo que te pido" a trabajar con la IA como un equipo.*

PostHog Córdoba · Event 1 · 27 · 04 · 2026
Teoría + discusión · Bloques 01 — 04

---

## Bloque 01 — Intro (~20 min)

Recap del Event 0 · Debate en vivo · Agenda

### 02. Bloque 01 · Divider

`BLOQUE 01 — INTRO`

### 03. Lo que pasó en el Event 0

> *Diego presenta — ~5 min. Re-anclar al grupo en la experiencia compartida antes de pedirles que reflexionen sobre ella.*

- Qué construimos — juegos en una tarde con IA
- Quiénes participaron, qué herramientas
- Highlights y momentos memorables
- Mosaico de fotos del evento

Más info:
→ `posthog.com/events/180`
→ `github.com/PostHog/requests-for-comments-public/issues/508`

### 04. ¿Cómo fue vibe codear *para ustedes?*

> *Word cloud en vivo · Mentimeter (QR generado antes del evento).*

Abran el link y respondan con las primeras palabras que se les vengan a la cabeza.

**Disparadores**

1. ¿Cómo se sintieron trabajando con IA?
2. ¿Qué fue lo más frustrante?
3. ¿Alguien logró algo que no habría podido hacer solo?

### 05. Mentimeter en vivo

> *Slide full-bleed con el iframe de Mentimeter — para mostrar la nube de palabras mientras la gente responde.*

### 06. Algo que *quizás* les pasó

Le pedís algo → Sale bien → Otro cambio → Anduvo → Feature nuevo → **Algo raro** → Querés arreglarlo → **Se rompe**.

### 07. Hoy hablamos de eso

- ¿Qué pasa cuando vibe codeamos?
- ¿En qué momento se queda corto?
- ¿Cómo empezamos a entender y a hacer crecer los proyectos?
- ¿Cómo dejamos de usar IA para programar rápido y empezamos a usarla para trabajar mejor?

→ Bloque 02

---

## Bloque 02 — Vibe Coding (~30 min)

Definición · El problema del 80% · Modos de falla

### 08. Bloque 02 · Divider

`BLOQUE 02 — VIBE CODING`

### 09. ¿Qué es *vibe coding*?

> *El término lo acuñó Andrej Karpathy en un tweet del 2 de febrero de 2025. Se viralizó — pero la definición original es muy específica.*

**Definición** — Construir software con una IA **sin leer el código** que genera.

Le decís lo que querés, mirás si funciona, y si no — le pedís que arregle. El "vibe" es justamente que *no te metés en el cómo*.

> *Tweet de Karpathy:* "There's a new kind of coding I call **'vibe coding'**, where you fully give in to the vibes, embrace exponentials, and forget that the code even exists."
>
> `x.com/karpathy/status/1886192184808149383`

### 10. El loop de vibe coding

`Le pedís algo → Ves si funciona → SI SÍ: pedís algo más / SI NO: pedís que lo arregle → LOOP ↩`

En el medio, muchas veces no leemos lo que genera. Confiamos en que funciona y seguimos.

### 11. *El 80% funciona. El otro 20% es el que duele.*

Rápido al principio. Lento después. Cada cambio cuesta más.

```
        ¡FUNCIONA!
            ●
          /   \___
         /        \___
        /             \___ cada fix rompe otra cosa
       /                  \●
─────────────────────────────────→
     ↑ velocidad del progreso · tiempo →
```

**Por qué el último 20% cuesta tanto**

- **Juicio** — ¿está bien hecho, o apenas funciona?
- **Contexto** — ¿cómo afecta esto al resto del proyecto?
- **Edge cases** — ¿qué pasa si el usuario hace algo inesperado?
- **Acumulación** — un cambio rompe otra cosa; un fix parchea el síntoma; nadie sabe quién tiene la culpa de qué.

### 12. Tres deudas que se acumulan

| Deuda | Qué pasa | Por qué duele |
|---|---|---|
| **A — Deuda de comprensión** | No siempre entendés cómo funciona lo que se generó. | Con el tiempo se acumula. Cada vez entendés menos tu propio proyecto. |
| **B — Código frágil** | Anda para el caso feliz. Se rompe en cuanto cambiás algo. | Cada fix agrega complejidad en vez de reducirla. |
| **C — Falta de diseño y arquitectura** | Cada feature se agrega sin pensar cómo encaja con el resto. | Funciona pero no hay un plan. Cada cambio futuro se vuelve más difícil porque no hay estructura debajo. |

→ La **deuda de comprensión** es deuda cognitiva; el **código frágil + falta de estructura** es deuda técnica.

### 13. La IA falla convincentemente

> *A veces ni se nota que se equivocó — y eso es lo peligroso.*

| | |
|---|---|
| **01 — Falsa confianza** | "Parece que está bien, pero no lo está." `"Fixed the login issue"` — sigue fallando. Te dice que está listo, lo explica con confianza, y no lo está. |
| **02 — Siempre te da la razón** | Sycophancy: nunca te contradice. Le preguntás si está bien y te dice que sí. Le proponés una idea mala y te la celebra. **No es un revisor** — es un asistente entusiasta. |
| **03 — Errores en cadena** | Un problema se vuelve varios. Asume algo incorrecto → construye encima → parece funcionar → pedís un cambio → choca con la suposición → hay que deshacer varias capas. |
| **04 — Falta de juicio** | Hace de más, o hace de menos. *"Un botón para guardar"* → te lo entrega con validación, toast y logging que no pediste. O al revés: el botón está, pero adentro está vacío. **No mide qué corresponde.** |
| **05 — Pérdida de contexto** | Olvida lo que ya habías decidido. Empezaste con una landing, terminaste con un SaaS. **No fue un cambio grande, fueron muchos chicos** — cada uno parecía razonable. |
| **06 — Falta de estructura y buenas prácticas** | Funciona, pero es un quilombo. Un archivo de 2000 líneas, nombres que solo tienen sentido en el momento, copia-y-pega en vez de abstracciones. **Nadie** lo puede mantener — ni vos en dos semanas. |

→ Bloque 03

---

## Bloque 03 — Planificar y revisar (~25 min)

El pasante inteligente · Planificar antes de construir · Revisar antes de aceptar

### 14. Bloque 03 · Divider

`BLOQUE 03 — PLANIFICAR Y REVISAR`

### 15. Imaginate un pasante que…

- Programa muy rápido
- Sabe de todo — frontend, backend, bases de datos, diseño
- Trabaja 24/7 sin quejarse
- Pero **no sabe nada sobre tu proyecto ni de vos.** No conoce tus decisiones, tus prioridades, ni qué querés lograr.

¿Lo mandarías a "armá un proyecto" y volverías al día siguiente?
El problema no es la *capacidad* — es la **dirección.**

### 16. Planificar antes de construir

| | |
|---|---|
| **Qué es** | Iterar sobre la *idea* antes de iterar sobre el código. Decidís el qué y el cómo **antes** de que la IA escriba una línea. Conversás, ajustás, descartás — todo sin que se acumule deuda. |
| **Para qué sirve** | Cambiar de rumbo cuando todavía es *gratis*. Sin código, mover la idea no cuesta nada. Con código ya escrito, cada cambio se apila sobre lo anterior y el costo crece rápido. |

`FASE A · PLANIFICAR · Idea inicial → Conversás con la IA — sin código → Plan / spec corta` ↺ refinar · cambiar · descartar

→ `FASE B · IMPLEMENTAR · La IA construye con dirección clara`

### 17. Y revisar antes de aceptar

Planificar bien no te exime de revisar. La IA escribe rápido — vos sos el filtro. Si no mirás, no es tu trabajo: es el de la IA, con tu nombre arriba.

| | |
|---|---|
| **Revisar el código** | Leer el diff, no solo aceptarlo. ¿Cambió algo que no pediste? ¿Se agregaron dependencias raras? ¿La lógica se entiende? Si no podés explicar el cambio, todavía no es tuyo. **Aceptar sin leer es deuda futura.** |
| **Revisar el resultado** | Mirar la UI, correr el flujo. Abrir la pantalla, hacer click, probar el caso real. Los tests pasan y la UI puede estar rota igual: alineación, copy, estados vacíos, mobile. **Lo que el usuario ve es lo que importa.** |

### 18. Algunas formas de planificar mejor

| | |
|---|---|
| **01 — Que la IA te entreviste** | *Grill me* — que pregunte hasta entender. En vez de describirle la idea perfecta, pedile que **te entreviste a vos**. Dispara preguntas que no habías pensado: edge cases, supuestos, decisiones que evitabas. *"Hacéme preguntas hasta que tengas la spec clara."* |
| **02 — Explorar el código que ya existe** | Antes de agregar, entender qué hay. Pedile a la IA que **lea el repo** antes de proponer nada: convenciones, patrones, archivos relacionados. Así el plan encaja con lo que ya construiste — no choca. *"Mirá cómo manejamos auth hoy y proponé un plan consistente."* |
| **03 — Investigar / traer docs** | Que la IA lea la documentación real. Para librerías o APIs nuevas, conectarle **docs actualizadas** (Context7, MCPs de docs) evita que invente firmas o use APIs obsoletas. |
| **04 — Dar referencias** | "Como X, pero para Y." Mostrarle **ejemplos concretos** — un repo, un screenshot, un producto que te gusta — alinea el resultado más rápido que cualquier descripción larga. *"Quiero algo parecido a Linear, pero para gestionar X."* |

### 19. Plannotator

> *Una herramienta para revisar planes y diffs antes de aceptarlos.*

En vez de aceptar el plan o el diff a ciegas, lo abrís en una vista cómoda — anotás dudas, marcás cambios, y devolvés feedback estructurado a la IA.

- Visualiza el plan completo antes de ejecutarlo — y te deja anotar dudas ahí mismo.
- Anota líneas del diff con comentarios.

`github.com/backnotprop/plannotator`

### 20. Subagentes: un segundo par de ojos

`Agente A genera → Agente B revisa → Reporte → Vos decidís`

Otro modelo, otro prompt, instrucciones explícitas de buscar problemas. **No reemplaza tu juicio** — filtra el ruido. Vos te quedás con las decisiones de criterio.

Misma idea que un PR review: el autor está cerca, el revisor llega con ojos frescos.

→ Bloque 04

---

## Bloque 04 — Ingeniería Agéntica (~30 min)

Spec-driven development · Workflow · Skills · Validaciones

### 21. Bloque 04 · Divider

`BLOQUE 04 — INGENIERÍA AGÉNTICA`

### 22. Spec-driven: el plan, *escrito*

Consiste en bajar los aspectos definidos durante el planning en documentos que viven en el repo y describen distintos aspectos del proyecto — un feature, una decisión arquitectónica, un módulo, una integración.

| | |
|---|---|
| **Consistencia** | Sobreviven en el tiempo, describen el estado ideal del sistema. |
| **Iteración barata** | Cambiás un doc sin escribir código. Discutís, ajustás, recién entonces implementás. |
| **Menos suposiciones** | La IA no adivina las decisiones — las lee. |

> *Demo · Spec-driven en la práctica.*
>
> `github.com/asermax/munchkin-dungeon` — la spec del juego del Event 0, escrita antes del código
> `github.com/asermax/claude-plugins` — Katachi, skills que empaquetan el flujo spec-driven

### 23. Cómo se ve un flujo de spec-driven development

`SPEC (WHAT) → DESIGN (WHY / HOW) → PLAN (STEPS) → IMPLEMENT (ejecutar)`

Definís **qué** querés, después **por qué** y **cómo**, opcionalmente **los pasos** para la implementación. Recién ahí escribimos el código. Cada artefacto se revisa antes de pasar al siguiente.

### 24. Skills: conocimiento empaquetado

Son **prompts que encapsulan conocimiento, procesos y herramientas** — listos para que la IA los use cuando los necesite. Una vez los escribís, están disponibles siempre, en cada conversación, en cada proyecto.

**Ejemplos**

- **Standards de código** — convenciones, naming, patrones que usamos en este proyecto.
- **Pasos para debuggear** — cómo aislar un problema, qué logs mirar, cómo reproducir.
- **Cómo hacer queries a la base** — qué cliente usar, qué índices considerar, cómo paginar.

### 25. Por qué importan

- **Dejás de repetir instrucciones** — lo que aprendés una vez se aplica solo la próxima.
- **Conocimiento del equipo, no de una persona** — un skill es un proceso del equipo, no algo que sabe sólo el senior.
- **Componibles** — pequeñas unidades que se combinan. La IA elige cuáles aplican.
- **Crecen con el proyecto** — cada vez que descubrís cómo hacer algo bien, lo capturás como skill.
- **Capturalos donde tengan más sentido** — en el repo del proyecto, globalmente en tu config, o como plugins que instalás cuando los necesitás.

Simon Willison: *"hoard things you know how to do"* — acumular soluciones para combinar y reutilizar.

> *Demo · Skills empaquetados como plugins de Claude Code.*
>
> `github.com/filadd/cc-plugin-marketplace` — Filadd plugins y skills

### 26. Validaciones: dar feedback rápido para *mejorar el output*

Mecanismos automáticos que le dicen a la IA *"esto está bien"* o *"probá de nuevo"*. Con ese feedback puede iterar sola hasta acertar — sin que vos tengas que revisar cada cambio a mano.

`Escribir código → Validar → ¿Pasa? Sí → siguiente · No → leer error → ajustar`

**Mientras más temprano validás, más barato es arreglar.**

### 27. Los tests te dicen dos cosas

| | |
|---|---|
| **01 — Correctness** | Hace lo que tiene que hacer. No es garantía total — pero *mucho* mejor que "lo probé una vez y funcionó". |
| **02 — Safety net** | Cuando cambiás algo, te avisan si rompiste otra cosa. Sin tests, cada cambio es un salto al vacío. Modificás, esperás, rezás. |

### 28. Lo que *de verdad* cierra el loop

> *Más difíciles de configurar — pero la IA pasa de "creo que funciona" a "ví que funciona".*

| | |
|---|---|
| **Browser testing** | Que vea el resultado. La IA abre un navegador headless, navega tu app, toma screenshots, los lee. Detecta cosas que ningún unit test ve — un layout roto, un botón invisible, un overflow. |
| **Visual diffs** | ¿Cambió algo que no querías? Comparás el render contra una baseline. Cualquier diferencia visual aparece — la IA decide si es intencional o regresión. |
| **End-to-end** | El flujo completo. Recorridos reales del usuario — login, formularios, integraciones. Más caros de mantener, pero atrapan los bugs que más duelen. |

Configurar esto cuesta más que un linter. Pero le abrís a la IA un canal de feedback que cambia su forma de trabajar.

→ Cierre

---

## Cierre (~10 min)

La idea central · El toolkit

### 29. Cierre · Divider

`CIERRE`

### 30. *De aceptar lo que sale, a dirigir lo que se construye.*

> Pull quote · La idea central.
>
> *La IA sigue escribiendo el código. Vos decidís qué se escribe, cómo se organiza y cuándo está listo.*

### 31. El toolkit

> *Todo lo que pasamos hoy, en una sola página. No tenés que adoptar todo — empezá por el dolor que más te molesta.*

| Planificar & Revisar | Contexto | Ing. Agéntica | Validación |
|---|---|---|---|
| **Plan mode** — separar pensar de hacer | **Context7** — docs actualizadas | **Spec-driven** — spec → plan → código | **Tests + linters** — feedback rápido |
| **Grill me** — que la IA te entreviste | **MCPs de docs** — APIs, librerías | **Skills** — conocimiento empaquetado | **Browser testing** — que vea el resultado |
| **Plannotator** — anotar planes y diffs | **Web search** — antes de proponer | **Standards de código** — capturados, no repetidos | **Visual diffs** — detectar regresiones |
| **Subagentes** — segundo par de ojos | **Referencias** — repos, screenshots, "como X" | | **End-to-end** — el flujo completo |

### 32. Si querés meterte más a fondo

- **Simon Willison** · Agentic Engineering Patterns — patrones prácticos para coding agents
  `simonwillison.net/guides/agentic-engineering-patterns`
- **Peter Steinberger** · Just Talk To It — un enfoque pragmático sin specs formales
  `steipete.me/posts/just-talk-to-it`
- **Curso** · Vibe Coding to Agentic Engineering — versión completa de 4 semanas
  `próximamente`

*Gracias.*

Fin · 27 · 04 · 2026
