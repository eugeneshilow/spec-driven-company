*[English](../../README.md) ∙ [Русский](../ru/README.md) ∙ Español*

# Spec-Driven Company

Una empresa donde la verdad vive en especificaciones escritas, los agentes las ejecutan y el estado se ve sin preguntarle a nadie.

Este repositorio no contiene código. Solo las especificaciones: las reglas que todo agente de programación con IA lee primero, y los documentos de los que crece un proyecto. Todo lo demás lo instala tu agente.

Esta es la versión en español. Los archivos en inglés en la raíz del repositorio son la fuente; esta carpeta es su espejo, palabra por palabra. Los prompts de abajo descargan los archivos en español, y el agente lleva docs, journal e informes en español.

## Instalación: pégalo en tu agente

Abre tu agente de programación (Codex, Claude Code, Cursor, Copilot, Gemini CLI, cualquier otro) y pega el prompt de tu situación. No en la terminal, en el agente. Cada prompt termina con un informe: léelo, abre los enlaces y da la siguiente tarea.

Todos los prompts construyen la misma disposición. Tú creas una carpeta y la abres en tu agente; el agente hace el resto:

```text
my-app/          la carpeta del proyecto: abre esta en tu agente
├─ AGENTS.md     indicador: las reglas están en main/
├─ CLAUDE.md     indicador para Claude Code
├─ main/         el repositorio, un espejo limpio de main; nunca se edita a mano
└─ _wt/          un worktree por tarea, con el nombre de su rama; se borra tras el merge
```

Si la carpeta vive en un disco en la nube (Dropbox, iCloud, OneDrive), excluye de la sincronización `_wt/` y todo `node_modules`, o mantén los proyectos fuera del disco.

**1. Carpeta vacía, tu propio stack.** No se instala nada. Qué construir se lo dices al agente en la siguiente tarea.

```text
Configura Spec-Driven Company en esta carpeta. Esta carpeta es la carpeta del proyecto: crea main/ y _wt/ dentro. Descarga AGENTS.md, CLAUDE.md, CODEX.md, docs/README.md y docs/journal.md desde https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/lang/es/ y guárdalos en main/ con las mismas rutas. En esta carpeta escribe dos archivos indicadores: AGENTS.md con el texto «Esta es la carpeta del proyecto. El repositorio es main/; los worktrees viven en _wt/, uno por tarea. Lee main/AGENTS.md primero y síguelo. En main/ no se edita nada a mano.» y CLAUDE.md con la única línea «@main/AGENTS.md». Lee main/AGENTS.md y síguelo desde ahora. Rellena main/docs/README.md y la primera entrada que ya está en main/docs/journal.md; en la sección Stack de main/AGENTS.md escribe «none yet». Luego haz git init -b main en main/ y un commit en main; AGENTS.md lo permite para la primera instalación. Es una instalación local: sin remoto, sin pull request, sin despliegue. Terminado cuando main/ contiene los cinco archivos sin marcadores entre corchetes (los enlaces no cuentan), _wt/ existe, los dos archivos indicadores están aquí y git log en main/ muestra un commit. Informa.
```

Luego di qué construir, por ejemplo: «Construye un bot de Telegram en Python con aiogram. Detente antes del token.» Las reglas se encargan del resto: especificación antes que código, la comprobación antes de cada commit, un alto ante las claves.

**2. Proyecto existente.** Tu código, tus reglas y tu stack se quedan. El método se pone encima.

```text
Configura Spec-Driven Company en este proyecto. Esta carpeta se convierte en la carpeta del proyecto: crea una subcarpeta main/ y mueve dentro todo lo demás que hay aquí, la carpeta .git incluida, para que el repositorio con su historia viva ahora en main/; crea _wt/ al lado. En esta carpeta escribe dos archivos indicadores: AGENTS.md con el texto «Esta es la carpeta del proyecto. El repositorio es main/; los worktrees viven en _wt/, uno por tarea. Lee main/AGENTS.md primero y síguelo. En main/ no se edita nada a mano.» y CLAUDE.md con la única línea «@main/AGENTS.md». Descarga AGENTS.md, CLAUDE.md, CODEX.md, docs/README.md y docs/journal.md desde https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/lang/es/. Guarda cada uno en main/ con la misma ruta si ese archivo no existe allí. Si existe, fusiona: usa la estructura del archivo descargado y coloca cada regla existente, palabra por palabra, en la sección que le corresponde; donde dos reglas choquen, conserva la existente, descarta la descargada y lista el conflicto en el informe. Si la rama por defecto es master, renómbrala a main primero. Rellena la sección Stack de main/AGENTS.md con lo que el proyecto ya usa: de qué está hecho, el comando de comprobación, el comando de ejecución; si no hay un único comando de comprobación, nombra los que existen. No instales nada, no crees scripts. Rellena main/docs/README.md y la primera entrada de main/docs/journal.md con lo que el proyecto ya tiene; donde no se sepa nada escribe «none yet», no inventes nada. Hazlo en un worktree bajo _wt/, como dice main/AGENTS.md; el cambio solo toca reglas y docs, así que fusiónalo tú mismo en main, elimina el worktree y, si hay remoto, sube main. Terminado cuando no quedan marcadores entre corchetes en main/AGENTS.md, main/docs/README.md ni main/docs/journal.md (los enlaces no cuentan), los dos archivos indicadores están aquí y el proyecto se ejecuta desde main/ como antes. Informa.
```

**3. Carpeta vacía, stack listo.** Una aplicación web con base de datos y una página de administración donde se ve el estado del proyecto, construida por tu agente a partir de la receta dentro del prompt. Es el stack sobre el que corre vibecoding.ru: Next.js, Tailwind, Convex. No se fijan versiones: el agente instala lo que esté vigente el día que lo ejecutes.

<details>
<summary>El prompt con la receta. Ábrelo, copia el bloque entero, pégalo.</summary>

```text
Configura Spec-Driven Company en esta carpeta con el stack Next.js y Convex. Esta carpeta es la carpeta del proyecto: crea main/ y _wt/ dentro. Descarga AGENTS.md, CLAUDE.md, CODEX.md, docs/README.md y docs/journal.md desde https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/lang/es/ y guárdalos en main/ con las mismas rutas. En esta carpeta escribe dos archivos indicadores: AGENTS.md con el texto «Esta es la carpeta del proyecto. El repositorio es main/; los worktrees viven en _wt/, uno por tarea. Lee main/AGENTS.md primero y síguelo. En main/ no se edita nada a mano.» y CLAUDE.md con la única línea «@main/AGENTS.md». Lee main/AGENTS.md y síguelo desde ahora. Luego construye la aplicación según la receta de abajo, dentro de main/. Es una instalación local: sin remoto, sin pull request, sin despliegue; haz git init -b main en main/ y termina con un commit en main (AGENTS.md lo permite para la primera instalación). Toda tarea posterior a esta instalación va a un worktree bajo _wt/, como dice main/AGENTS.md.

Qué contiene: Node.js LTS actual y pnpm; Next.js con App Router y TypeScript; Tailwind CSS; Convex para la base de datos y las funciones de servidor; Vitest para los tests, ESLint y Prettier para la comprobación. El destino de despliegue es Vercel, no forma parte de esta instalación. Usa el Node y el pnpm ya instalados si son compatibles; instala solo lo que falte, no actualices nada que funcione (una dependencia peer que exija un paquete nuevo no es una actualización).

Construye, en este orden:
0. Antes del primer comando, rellena main/docs/README.md a partir de esta receta: el nombre del proyecto es el nombre de la carpeta salvo que se diga otra cosa, de qué está hecho, qué está terminado y cuándo. No inventes requisitos de producto. AGENTS.md quiere la especificación antes que el código; esta receta es la especificación. Tras la construcción, corrígela según lo realmente construido.
1. Crea la aplicación Next.js en main/ con TypeScript, Tailwind, ESLint y App Router. El generador rechaza una carpeta no vacía y escribe su propio AGENTS.md, así que genera en una subcarpeta temporal main/scaffold-tmp con el archivo de agentes y git desactivados, sube los archivos a main/, borra la subcarpeta y descarta el arte de plantilla: el README.md generado (la página del proyecto es docs/README.md), los svg de public/ y el cableado de la fuente de Google. AGENTS.md, CLAUDE.md, CODEX.md y docs/ se quedan como se descargaron salvo las partes que se te pide rellenar: desactiva las dos cosas que escriben las reglas propias de Next en AGENTS.md, la opción del generador (--no-agents-md, o como la llame el --help actual) y la opción de configuración que deja que next dev lo regenere (agentRules: false), y añade AGENTS.md, CLAUDE.md y CODEX.md a .prettierignore.
2. Añade Prettier y Vitest. Añade un único script «check» que ejecute la comprobación del formateador, el linter, la comprobación de tipos y los tests, en ese orden, y escriba su resultado (verde o rojo, con la hora) en un pequeño archivo ignorado, para que la página de administración pueda mostrarlo. La comprobación de tipos necesita los tipos de rutas generados por Next, así que genéralos dentro del check antes del paso de tipos.
3. Página /: el nombre del proyecto de docs/README.md, una frase sobre qué es, y un enlace a /admin. Simple, legible, sin arte de plantilla.
4. Página /admin: el cristal. Renderiza docs/README.md y docs/journal.md desde los archivos como HTML (vale cualquier librería pequeña de markdown), lista cada decisión (los encabezados del journal que llevan ⚖️) con su fecha y nombre, y muestra el resultado de la última ejecución del check desde el archivo que el check escribe. Leer los archivos en cada petición basta; esta página no necesita base de datos.
5. Un test: /admin lista al menos la primera decisión del journal. Pon el check en verde.
6. Instala Convex. Añade el archivo de esquema todavía sin tablas, un proveedor de cliente que renderice la aplicación sin Convex mientras su variable de URL esté vacía, y un .env.local.example que nombre las variables que rellenará la CLI de Convex (CONVEX_DEPLOYMENT y NEXT_PUBLIC_CONVEX_URL); asegúrate de que .gitignore no oculte el archivo de ejemplo. No escribas funciones de servidor todavía: sus tipos generados aparecen solo cuando existe un despliegue. No ejecutes el login de Convex: crea un despliegue en la nube en la cuenta de la persona, y eso es una decisión de acceso. Prepara todo y detente con una línea: «Convex está conectado; ejecuta npx convex dev e inicia sesión cuando quieras la base de datos en vivo.»
7. Rellena la sección Stack de main/AGENTS.md: de qué está hecho, el comando de comprobación, el comando de ejecución con la dirección. Ajusta docs/README.md a lo construido. Rellena la primera entrada que ya está en docs/journal.md y añade una segunda encima, como decisión: Convex está conectado pero sin login; qué se instaló, qué se omitió, qué hace la persona a continuación.
8. Arranca el servidor de desarrollo desde main/, haz un commit en main e informa.

Detente antes de: el login de Convex (acceso), cualquier despliegue (publica fuera), cualquier clave en un archivo (claves; el archivo con las claves es .env.local, nunca se sube al repositorio).

Terminado cuando http://localhost:3000 (o el puerto que elegiste, si el 3000 está ocupado) responde con la página del proyecto, /admin responde y muestra el journal con la primera decisión, el check está en verde, no quedan marcadores entre corchetes en main/AGENTS.md, main/docs/README.md ni main/docs/journal.md (los enlaces no cuentan), _wt/ existe y los dos archivos indicadores están aquí. Informa las dos direcciones, el resultado del check, el commit y la línea sobre Convex.
```

</details>

## Qué obtienes

- `AGENTS.md` — las reglas: dónde vive la verdad, cómo trabajar, respuestas que la persona puede usar, git, el stack y la comprobación, zonas de riesgo, decisiones, estructura, producción, el informe, el ciclo. Su sección Stack es el único lugar que dice de qué está hecho tu proyecto y cómo comprobarlo y ejecutarlo.
- `CLAUDE.md` — una línea que dirige a Claude Code hacia `AGENTS.md`. Los demás agentes leen `AGENTS.md` directamente.
- `CODEX.md` — lo específico de Codex sobre `AGENTS.md`: enlaces y medios en Codex Desktop. Nunca debilita las reglas.
- `docs/README.md` — la única página de tu proyecto: qué es, decisiones, dónde está cada cosa.
- `docs/journal.md` — decisiones y por qué, solo se añade, lo más nuevo arriba. La primera entrada ya está: adoptaste el método.
- Dos archivos indicadores en la carpeta del proyecto, `AGENTS.md` y `CLAUDE.md`, los escribe el prompt, no se descargan: envían a cualquier agente abierto en la carpeta del proyecto hacia `main/`.

## Míralo funcionando

Abre [vibecoding.ru](https://vibecoding.ru) ahora mismo. Todo lo que hay allí, el código, las páginas, las noticias, las fichas, está escrito por agentes. Cien por cien, no noventa y nueve. El autor no escribió ni una línea. Escribió las reglas y aceptó el trabajo. El operador abre tres cosas y nada más: `docs/`, `AGENTS.md` con `CLAUDE.md` y `CODEX.md`, y el archivo con las claves. Cómo funciona, en vivo: [vibecoding.ru/open](https://vibecoding.ru/open).

## Por qué

Los agentes dan a una persona el poder de un equipo. Sin un sistema producen caos y necesitan una niñera permanente. Spec-Driven Company es el sistema: especificación, cadena de montaje, cristal. El concepto, en ruso, vive en [vibecoding.ru/sdc](https://vibecoding.ru/sdc). Este repositorio es la práctica.

Por qué no hay código aquí: el código tiene versiones, y las versiones necesitan mantenimiento. Una receta en palabras no caduca cuando caduca una librería. Tu agente la lee y usa lo que esté vigente el día que la ejecutes.

## Idiomas

Los archivos en inglés en la raíz son la fuente. Las traducciones viven en `lang/<código>/` y repiten las rutas de los archivos una a una; un cambio en un archivo en inglés y en sus traducciones va en un mismo pull request, y la traducción la hace el agente. Los commits, los issues y el README raíz están en inglés.

## Licencia

[CC BY 4.0](../../LICENSE). Úsalo, cópialo, cámbialo, vende lo que construyas con ello. Conserva la línea de atribución al final de `AGENTS.md`.

Autor: Eugene Shilov, [vibecoding.ru](https://vibecoding.ru).
