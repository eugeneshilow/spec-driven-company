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
Configura Spec-Driven Company en esta carpeta. Esta carpeta es la carpeta del proyecto: crea main/ y _wt/ dentro. Descarga AGENTS.md, CLAUDE.md, CODEX.md, docs/README.md y docs/journal.md desde https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/lang/es/ y guárdalos en main/ con las mismas rutas. En esta carpeta escribe dos archivos indicadores: AGENTS.md con el texto «Esta es la carpeta del proyecto. El repositorio es main/; los worktrees viven en _wt/, uno por tarea. Lee main/AGENTS.md primero y síguelo. En main/ no se edita nada a mano.» y CLAUDE.md con la única línea «@main/AGENTS.md». Lee main/AGENTS.md y síguelo desde ahora. Rellena main/docs/README.md y la primera entrada que ya está en main/docs/journal.md; en la sección Stack de main/AGENTS.md escribe «none yet» en las tres líneas. Luego haz git init -b main en main/ y un commit en main; AGENTS.md lo permite para la primera instalación. Es una instalación local: sin remoto, sin pull request, sin despliegue. Terminado cuando main/ contiene los cinco archivos sin marcadores entre corchetes (los enlaces no cuentan), _wt/ existe, los dos archivos indicadores están aquí y git log en main/ muestra un commit. Informa.
```

Luego di qué construir, por ejemplo: «Construye un bot de Telegram en Python con aiogram. Detente antes del token.» Las reglas se encargan del resto: especificación antes que código, la comprobación antes de cada commit, un alto ante las claves.

**2. Proyecto existente.** Tu código, tus reglas y tu stack se quedan. El método se pone encima.

```text
Configura Spec-Driven Company en este proyecto. Esta carpeta se convierte en la carpeta del proyecto: crea una subcarpeta main/ y mueve dentro todo lo demás que hay aquí, la carpeta .git incluida, para que el repositorio con su historia viva ahora en main/; crea _wt/ al lado. En esta carpeta escribe dos archivos indicadores: AGENTS.md con el texto «Esta es la carpeta del proyecto. El repositorio es main/; los worktrees viven en _wt/, uno por tarea. Lee main/AGENTS.md primero y síguelo. En main/ no se edita nada a mano.» y CLAUDE.md con la única línea «@main/AGENTS.md». Descarga AGENTS.md, CLAUDE.md, CODEX.md, docs/README.md y docs/journal.md desde https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/lang/es/. Guarda cada uno en main/ con la misma ruta si ese archivo no existe allí. Si existe, fusiona: usa la estructura del archivo descargado y coloca cada regla existente, palabra por palabra, en la sección que le corresponde; donde dos reglas choquen, conserva la existente, descarta la descargada y lista el conflicto en el informe. Si la rama por defecto es master, renómbrala a main primero. Rellena la sección Stack de main/AGENTS.md con lo que el proyecto ya usa: de qué está hecho, el comando de comprobación, el comando de ejecución; si no hay un único comando de comprobación, nombra los que existen. No instales nada, no crees scripts. Rellena main/docs/README.md y la primera entrada de main/docs/journal.md con lo que el proyecto ya tiene; donde no se sepa nada escribe «none yet», no inventes nada. Hazlo en un worktree bajo _wt/, como dice main/AGENTS.md; el cambio solo toca reglas y docs, así que fusiónalo tú mismo en main, elimina el worktree y, si hay remoto, sube main. Terminado cuando no quedan marcadores entre corchetes en main/AGENTS.md, main/docs/README.md ni main/docs/journal.md (los enlaces no cuentan), los dos archivos indicadores están aquí y el proyecto se ejecuta desde main/ como antes. Informa.
```

**3. Carpeta vacía, stack listo.** Elige una fila, abre su prompt debajo de la tabla, copia el bloque entero, pégalo. La receta vive dentro del prompt; no se fijan versiones: el agente instala lo que esté vigente el día que lo ejecutes.

| Stack | Qué obtienes | Dónde corre |
|---|---|---|
| Next.js · Tailwind · Convex | una aplicación web con base de datos y una página de administración donde se ve el estado del proyecto; el stack sobre el que corre vibecoding.ru | solo en tu máquina |
| Next.js · Tailwind · Convex · GitHub · Vercel | la misma aplicación, más un repositorio privado, una comprobación en cada pull request, una dirección de producción que se redespliega con cada merge, y la base de datos en la nube | en línea; tres inicios de sesión son tuyos: GitHub, Vercel, Convex |

<details>
<summary>Prompt local: Next.js · Tailwind · Convex. Ábrelo, copia el bloque entero, pégalo.</summary>

```text
Configura Spec-Driven Company en esta carpeta con el stack Next.js y Convex. Esta carpeta es la carpeta del proyecto: crea main/ y _wt/ dentro. Descarga AGENTS.md, CLAUDE.md, CODEX.md, docs/README.md y docs/journal.md desde https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/lang/es/ y guárdalos en main/ con las mismas rutas. En esta carpeta escribe dos archivos indicadores: AGENTS.md con el texto «Esta es la carpeta del proyecto. El repositorio es main/; los worktrees viven en _wt/, uno por tarea. Lee main/AGENTS.md primero y síguelo. En main/ no se edita nada a mano.» y CLAUDE.md con la única línea «@main/AGENTS.md». Lee main/AGENTS.md y síguelo desde ahora. Luego construye la aplicación según la receta de abajo, dentro de main/. Es una instalación local: sin remoto, sin pull request, sin despliegue; haz git init -b main en main/ y termina con un commit en main (AGENTS.md lo permite para la primera instalación). Toda tarea posterior a esta instalación va a un worktree bajo _wt/, como dice main/AGENTS.md.

Qué contiene: Node.js LTS actual y pnpm; Next.js con App Router y TypeScript; Tailwind CSS; Convex para la base de datos y las funciones de servidor; Vitest para los tests, ESLint y Prettier para la comprobación. El destino de despliegue es Vercel, no forma parte de esta instalación. Toma las versiones estables actuales, LTS donde la haya, nunca una prerelease. Usa el Node y el pnpm ya instalados si son compatibles; instala solo lo que falte, no actualices nada que funcione (una dependencia peer que exija un paquete nuevo no es una actualización).

Construye, en este orden:
0. Antes del primer comando, rellena main/docs/README.md a partir de esta receta: el nombre del proyecto es el nombre de la carpeta salvo que se diga otra cosa, de qué está hecho, qué está terminado y cuándo. No inventes requisitos de producto. AGENTS.md quiere la especificación antes que el código; esta receta es la especificación. Tras la construcción, corrígela según lo realmente construido.
1. Crea la aplicación Next.js en main/ con TypeScript, Tailwind, ESLint y App Router. El generador rechaza una carpeta no vacía y escribe su propio AGENTS.md, así que genera en una subcarpeta temporal main/scaffold-tmp con el archivo de agentes y git desactivados, sube los archivos a main/, borra la subcarpeta y descarta exactamente estas tres piezas de arte de plantilla, solo archivos, sin tocar carpetas: el README.md generado (la página del proyecto es docs/README.md), los svg dentro de public/ y el cableado de la fuente de Google. AGENTS.md, CLAUDE.md, CODEX.md y docs/ se quedan como se descargaron salvo las partes que se te pide rellenar: desactiva las dos cosas que escriben las reglas propias de Next en AGENTS.md, la opción del generador (--no-agents-md, o como la llame el --help actual) y la opción de configuración que deja que next dev lo regenere (agentRules: false), y añade AGENTS.md, CLAUDE.md y CODEX.md a .prettierignore.
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

<details>
<summary>Prompt en línea: Next.js · Tailwind · Convex · GitHub · Vercel. Ábrelo, copia el bloque entero, pégalo.</summary>

```text
Configura Spec-Driven Company en esta carpeta con el stack Next.js y Convex y ponlo en línea: un repositorio privado en GitHub, Vercel y Convex en la nube. Esta carpeta es la carpeta del proyecto: crea main/ y _wt/ dentro. Descarga AGENTS.md, CLAUDE.md, CODEX.md, docs/README.md y docs/journal.md desde https://raw.githubusercontent.com/eugeneshilow/spec-driven-company/main/lang/es/ y guárdalos en main/ con las mismas rutas. En esta carpeta escribe dos archivos indicadores: AGENTS.md con el texto «Esta es la carpeta del proyecto. El repositorio es main/; los worktrees viven en _wt/, uno por tarea. Lee main/AGENTS.md primero y síguelo. En main/ no se edita nada a mano.» y CLAUDE.md con la única línea «@main/AGENTS.md». Lee main/AGENTS.md y síguelo desde ahora. Luego construye la aplicación según la receta de abajo, dentro de main/. La parte local termina con git init -b main en main/ y un commit en main (AGENTS.md lo permite para la primera instalación); todo lo que viene después del push pasa por un worktree bajo _wt/ y un pull request, como dice main/AGENTS.md.

Al pegar este prompt autorizo: un repositorio privado en GitHub con el nombre de la carpeta del proyecto, un proyecto de Vercel conectado a él y despliegues de Convex en mi cuenta. Tres inicios de sesión son míos: antes del primer comando que necesite uno, comprueba gh auth status y vercel whoami; donde falte, ejecuta gh auth login o vercel login y espérame; el comando de Convex abre el navegador por sí mismo. ¿Todavía no tengo cuenta? La creo en la misma página que abre el inicio de sesión; es el mismo paso. Cada vez que pares por mí, escríbelo con una sola forma: primera línea la única acción; luego el enlace exacto y los clics en orden; luego qué decir de vuelta (nunca un secreto); para un inicio de sesión, el enlace y el código que imprimió el comando; nada más por encima.

Qué contiene: Node.js LTS actual y pnpm; Next.js con App Router y TypeScript; Tailwind CSS; Convex para la base de datos y las funciones de servidor; Vitest para los tests, ESLint y Prettier para la comprobación; GitHub para el repositorio y la comprobación en los pull requests; Vercel para el hosting. Toma las versiones estables actuales, LTS donde la haya, nunca una prerelease. Usa el Node y el pnpm ya instalados si son compatibles; instala solo lo que falte, no actualices nada que funcione (una dependencia peer que exija un paquete nuevo no es una actualización).

Construye, en este orden:
0. Antes del primer comando, rellena main/docs/README.md a partir de esta receta: el nombre del proyecto es el nombre de la carpeta salvo que se diga otra cosa, de qué está hecho, qué está terminado y cuándo. No inventes requisitos de producto. AGENTS.md quiere la especificación antes que el código; esta receta es la especificación. Tras la construcción, corrígela según lo realmente construido.
1. Crea la aplicación Next.js en main/ con TypeScript, Tailwind, ESLint y App Router. El generador rechaza una carpeta no vacía y escribe su propio AGENTS.md, así que genera en una subcarpeta temporal main/scaffold-tmp con el archivo de agentes y git desactivados, sube los archivos a main/, borra la subcarpeta y descarta exactamente estas tres piezas de arte de plantilla, solo archivos, sin tocar carpetas: el README.md generado (la página del proyecto es docs/README.md), los svg dentro de public/ y el cableado de la fuente de Google. AGENTS.md, CLAUDE.md, CODEX.md y docs/ se quedan como se descargaron salvo las partes que se te pide rellenar: desactiva las dos cosas que escriben las reglas propias de Next en AGENTS.md, la opción del generador (--no-agents-md, o como la llame el --help actual) y la opción de configuración que deja que next dev lo regenere (agentRules: false), y añade AGENTS.md, CLAUDE.md y CODEX.md a .prettierignore.
2. Añade Prettier y Vitest. Añade un único script «check» que ejecute la comprobación del formateador, el linter, la comprobación de tipos y los tests, en ese orden, y escriba su resultado (verde o rojo, con la hora) en un pequeño archivo ignorado, para que la página de administración pueda mostrarlo. La comprobación de tipos necesita los tipos de rutas generados por Next, así que genéralos dentro del check antes del paso de tipos.
3. Página /: el nombre del proyecto de docs/README.md, una frase sobre qué es, y un enlace a /admin. Simple, legible, sin arte de plantilla.
4. Página /admin: el cristal. Renderiza docs/README.md y docs/journal.md desde los archivos como HTML (vale cualquier librería pequeña de markdown), lista cada decisión (los encabezados del journal que llevan ⚖️) con su fecha y nombre, muestra el resultado de la última ejecución del check desde el archivo que el check escribe, y muestra el hash del commit y la dirección de producción cuando las variables de build de Vercel las proporcionan (VERCEL_GIT_COMMIT_SHA, VERCEL_PROJECT_PRODUCTION_URL), «local» en caso contrario. Leer los archivos en cada petición basta; esta página no necesita base de datos.
5. Un test: /admin lista al menos la primera decisión del journal. Pon el check en verde.
6. Instala Convex. Añade el archivo de esquema todavía sin tablas, un proveedor de cliente que renderice la aplicación sin Convex mientras su variable de URL esté vacía, y un .env.local.example que nombre las variables que rellenará la CLI de Convex (CONVEX_DEPLOYMENT y NEXT_PUBLIC_CONVEX_URL); asegúrate de que .gitignore no oculte el archivo de ejemplo. Luego ejecuta npx convex dev --once --configure new --dev-deployment cloud: me inicia sesión, crea el despliegue de desarrollo en la nube (no un backend local) y escribe .env.local, que nunca se sube al repositorio. No escribas funciones de servidor todavía.
7. Rellena la sección Stack de main/AGENTS.md: de qué está hecho, el comando de comprobación, el comando de ejecución con la dirección. Ajusta docs/README.md a lo construido. Rellena la primera entrada que ya está en docs/journal.md.
8. Arranca el servidor de desarrollo desde main/, comprueba que / y /admin responden, haz un commit en main.
9. GitHub: desde main/, crea un repositorio privado con el nombre de la carpeta del proyecto y sube main (gh repo create <nombre> --private --source=. --push).
10. A partir de aquí, trabaja en un solo worktree bajo _wt/ en una rama <agente>-<fecha>-go-online y termina con un solo pull request. En él: .github/workflows/check.yml que instala pnpm y ejecuta el comando de comprobación en cada pull request y en cada push a main; vercel.json con un comando de build que depende del entorno (la variable VERCEL_ENV): en producción "pnpm check && npx convex deploy --cmd 'pnpm build'", para que la comprobación escriba su resultado para /admin y Convex se despliegue a producción y fije la URL de la base de datos para el build; en preview simplemente "pnpm build", allí la aplicación funciona sin Convex; docs/deploy.md, el canon de la salida al exterior: repositorio, la comprobación, Vercel, Convex, dónde viven las claves, cómo volver atrás; .github/workflows/prod-alive.yml que pide cada hora la dirección guardada en la variable del repositorio PROD_URL y falla a gritos cuando no responde 200; una línea Deploy en la sección Stack («push a main → Vercel»); y una segunda entrada del journal encima de la primera, como decisión: el proyecto está en línea, qué se creó y dónde, qué hace la persona a continuación.
11. Vercel: desde main/, ejecuta vercel link --yes --project <nombre de la carpeta del proyecto> (no la carpeta main/); también conecta el repositorio, así que vercel git connect debería responder que ya está conectado; si alguno pide instalar la aplicación de Vercel en GitHub, dame el enlace que imprimió y espera. Luego crea tú mismo el despliegue de producción de Convex: npx convex deploy desde main/ con mi sesión lo crea en la primera ejecución. Los builds de producción en Vercel necesitan una clave de despliegue, y una clave nunca pasa por este chat: la pongo en Vercel yo mismo. Obtén primero las dos direcciones: el panel de producción con npx convex dashboard --prod --no-open, y la página de variables de entorno del proyecto en Vercel, https://vercel.com/<equipo>/<proyecto>/settings/environment-variables (vercel project ls muestra el equipo y el proyecto). Luego para exactamente con este texto, nada por encima: «Crea la production deploy key y ponla en Vercel; no la pegues aquí. 1. <enlace de Convex> → Settings → bloque Deploy Keys → botón Create Deploy Key → Name: vercel-production → Expiration: No expiration → marca exactamente tres permisos: deployment:deploy, deployment:env:view, deployment:env:write → Create → Copy (la clave se muestra una sola vez). 2. <enlace de Vercel> → botón Add Environment Variable → Type: Secret → Key: CONVEX_DEPLOY_KEY → Value: pegar → Environments: solo Production → Save → si Vercel ofrece Redeploy, pulsa Dismiss: el merge desplegará. Escribe «listo».» Tras mi «listo», comprueba con vercel env ls que CONVEX_DEPLOY_KEY existe en production; nunca pidas ni imprimas su valor.
12. Abre el pull request, espera a la comprobación, fusiónalo (lo autoricé al pegar este prompt), haz fast-forward de main en main/, elimina el worktree y la rama. El merge despliega. Espera al despliegue, toma la dirección de producción, guárdala como variable del repositorio PROD_URL (gh variable set PROD_URL) y pide la dirección una vez tú mismo. Lista los despliegues de producción con vercel ls --prod: cada uno en Error, incluido el primero antes de la clave, va al informe por su nombre.
13. Informa.

Detente antes de: hacer público el repositorio, borrar cualquier cosa, escribir cualquier clave en un archivo (el archivo con las claves locales es .env.local, nunca se sube al repositorio).

Terminado cuando http://localhost:3000 (o el puerto que elegiste, si el 3000 está ocupado) responde con la página del proyecto en local, el repositorio existe con main subido, la comprobación del pull request corrió en verde y el pull request está fusionado, la dirección de producción responde 200 con la página del proyecto y su /admin muestra el journal con dos decisiones, no quedan marcadores entre corchetes en main/AGENTS.md, main/docs/README.md ni main/docs/journal.md (los enlaces no cuentan), _wt/ vuelve a no tener carpetas de trabajo (los archivos de macOS como .DS_Store no cuentan) y los dos archivos indicadores están aquí. Informa la dirección del repositorio, la dirección de producción, la ejecución de la comprobación, el commit y lo que queda por mi parte.
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

**Por qué no hay código aquí.** El código tiene versiones, y las versiones necesitan mantenimiento. Una receta en palabras no caduca cuando caduca una librería. Tu agente la lee y usa lo que esté vigente el día que la ejecutes.

**Por qué el agente lo hace todo, incluso lo que un script haría en un segundo.** Porque lo escaso es tu tiempo y tu atención, no los tokens. Configurar un proyecto a mano son veinte decisiones pequeñas y una hora; pegar un prompt es una decisión y diez minutos del agente, a un coste en tokens que no deja de bajar. Dos cosas mantienen honesto este trato: cada prompt termina con un criterio de terminado que el agente debe cumplir, y los prompts se vuelven a ejecutar con agentes limpios tras cada cambio de la receta.

**Por qué este instalador no puede quedarse viejo.** No tiene nada que envejezca: ni versiones, ni opciones, ni lockfile. El agente toma las versiones estables de hoy (LTS donde la hay, nunca una prerelease) y lee el `--help` de hoy en vez de las opciones de ayer. Cuando una librería cambia de forma, la receta sigue diciendo adónde llegar, y el agente encuentra el nuevo camino.

## Idiomas

Los archivos en inglés en la raíz son la fuente. Las traducciones viven en `lang/<código>/` y repiten las rutas de los archivos una a una; un cambio en un archivo en inglés y en sus traducciones va en un mismo pull request, y la traducción la hace el agente. Los commits, los issues y el README raíz están en inglés.

## Licencia

[CC BY 4.0](../../LICENSE). Úsalo, cópialo, cámbialo, vende lo que construyas con ello. Conserva la línea de atribución al final de `AGENTS.md`.

Autor: Eugene Shilov, [vibecoding.ru](https://vibecoding.ru).
