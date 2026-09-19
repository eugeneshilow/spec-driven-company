# AGENTS.md

Reglas para todo agente que trabaje en este repositorio. Lee este archivo primero: es el mapa.

Spec-Driven Company (SDC) en una línea: la verdad vive en especificaciones escritas, los agentes las ejecutan y el estado se ve sin preguntarle a nadie.

## Antes de nada: clasifica la tarea

Toda tarea es de uno de tres tipos. Decídelo antes de leer archivos o tocar git.

1. **Conversar.** Explicar, discutir, aconsejar. No tocar git.
2. **Leer.** Leer archivos, no cambiar nada. Actualizar `main` primero, luego leer.
3. **Escribir.** Cualquier cosa que pueda cambiar el repositorio, incluida una sola línea de docs. Preflight, worktree propio, nunca escribir en `main`.

## Dónde vive la verdad

- `docs/README.md` — una página: qué es este proyecto, qué decisiones se tomaron, dónde está cada cosa.
- `docs/journal.md` — decisiones y por qué: qué se decidió, qué se rechazó, con palabras de quién. Solo se añade, lo más nuevo arriba.
- `docs/<zona>.md` — el canon de una zona: cómo funciona ahora mismo. Una regla, escrita una vez, editada por reemplazo.

Los archivos de cada herramienta están junto a este y solo añaden, nunca debilitan: `CLAUDE.md` dirige a Claude Code hasta aquí; `CODEX.md` lleva lo que es específico de Codex. Donde discrepen con este archivo, gana este archivo.

El par en la raíz de `docs/` pertenece a todo el proyecto. Cada subcarpeta de `docs/` lleva su propio par: `README.md` (el resumen de la carpeta) y `journal.md` (el razonamiento detrás). Una carpeta nueva nace con los dos. Un archivo de zona nace con la primera regla de la zona; no crees archivos vacíos.

Si una regla no está escrita en una dirección, no existe. «Pregúntale a quien se acuerde» no es una dirección.

Tres clases de verdad, tres casas. Las decisiones de sentido (qué construimos, para quién, con qué voz) viven en `docs/`. Las convenciones de herramientas (linter, formateador, versiones) viven en sus archivos de configuración; no las copies a docs. Los datos vivos y los estados (usuarios, pedidos, estados de sensores) viven en la base de datos; docs describe cómo funciona, nunca qué dice ahora.

## Cómo trabajar

1. **Trabaja en un worktree.** Cada tarea tiene su propio worktree (una copia de trabajo separada del repositorio) en `_wt/`; `main/` nunca se edita a mano. Cómo, en la sección Git.
2. **Ninguna tarea sin criterio de terminado.** Si no hay forma de comprobar que la tarea está hecha, pregunta. No empieces.
3. **Especificación antes que código.** Requisitos, plan y diseño en un solo documento antes de la primera línea de código. Para cada forma que contenga, una página, un documento, una API, un nombre, busca quién resolvió mejor la misma tarea y toma su molde; inventa desde cero solo cuando puedas decir por qué ningún molde encaja. El plan son pasos ordenados, no fechas: un paso está hecho cuando están hechos los pasos de los que depende.
4. **Canon antes que código.** Una regla cambia primero en `docs/`, luego en el código y los tests, en el mismo cambio. Nunca «ahora el código, los docs después».
5. **Los tests sostienen las reglas.** Una regla que ya costó tiempo o dinero recibe un test. Si rompes un test, arréglalo antes de decir «hecho».
6. **En zonas de riesgo, prepara, no ejecutes.** Ver la tabla más abajo. El botón lo pulsa una persona.
7. **Informa del resultado, no del esfuerzo.** Di qué hiciste, qué no hiciste y qué no pudiste verificar.

## Respuestas que la persona puede usar

- Empieza por lo que salió y si se puede usar. Si el resultado es parcial, nombra el límite y qué significa en la práctica.
- Frases completas y llanas. Traduce un término, un error o un estado a su sentido práctico allí donde aparece; los comandos y los logs van después, como prueba.
- Di quién actúa a continuación. Si la persona tiene que hacer algo, dale una acción, el lugar y el resultado esperado.
- Distingue un fallo confirmado de algo que no pudiste comprobar. Lo no verificado no está hecho.
- Responde en el idioma en que escribe la persona; el código, los comandos y los nombres se quedan como están.

## Git

- **Disposición.** Un proyecto es una carpeta con dos cosas dentro: `main/`, el repositorio, un espejo limpio de la rama `main` en el remoto, y `_wt/`, un worktree por tarea, cada carpeta con el nombre de su rama. La rama por defecto es `main`; un repositorio que llegó con `master` se renombra una vez, antes que nada. Junto a ellas, en la carpeta del proyecto, hay dos archivos indicadores, `AGENTS.md` y `CLAUDE.md`, para que un agente abierto en la carpeta del proyecto encuentre las reglas en `main/`. Tras la primera instalación en `main/` no se edita nada a mano: solo se sincroniza y se limpia. Toda tarea de escritura, incluida una sola línea de docs, vive en su propio worktree bajo `_wt/`.
- A `main` solo se llega por merge. El código llega a `main` por un pull request que fusiona la persona; si la persona dijo «ship», el agente fusiona por sí mismo en cuanto la comprobación está en verde (o todavía no hay comprobación) y no se toca ninguna zona de riesgo. Un cambio que solo toca `docs/` y este archivo no necesita pull request: el agente lo fusiona en `main` por sí mismo. ¿Todavía no hay remoto? Las mismas reglas, fusionando en local; el remoto y los pull requests llegan con el primer código. La única excepción a «solo por merge» es la primera instalación, que ocurre en el propio `main/`: ¿todavía no hay repositorio? `git init -b main` en `main/`, construye la instalación allí, un commit en `main` y dilo en el informe.
- Preflight para toda tarea de escritura, en `main/`: `git status`, `git fetch --prune` (sáltalo si no hay remoto), fast-forward de `main`. Si `main` está sucio o va por delante del remoto, para y dilo. Luego limpia los worktrees que dejaron las tareas anteriores: `git worktree prune`, y toda carpeta bajo `_wt/` cuya rama ya está fusionada (desapareció del remoto, porque el repositorio borra la rama al fusionar; sin remoto, ya está contenida en `main`) y cuyo `git status` está limpio se elimina con `git worktree remove` y su rama se borra. Un worktree con archivos sin commit se queda y se nombra en el informe; si quedan más de siete worktrees tras la limpieza, enuméralos en el informe. La limpieza está aquí, al principio, porque la sesión que hizo una tarea normalmente ya se cerró cuando su pull request se fusiona; la siguiente tarea siempre llega, así que la limpieza siempre ocurre. Luego `git worktree add ../_wt/<rama> -b <rama> main`, y trabaja solo allí: ediciones, instalación, la comprobación, el servidor de desarrollo.
- Nombre de rama: `<agente>-<AAAA-MM-DD>-<tema>`, por ejemplo `codex-2026-09-02-signup-form` o `claude-2026-09-02-signup-form`. La carpeta del worktree lleva el mismo nombre.
- Haz commit en cada paso completo. Un commit es un punto al que puedes volver. Solo entran los cambios de esta tarea; nunca secretos, nunca el trabajo a medias de otra persona.
- Relee el diff como revisor, luego sube la rama y abre el pull request. Bloquean tres cosas: un bug en un camino por el que se mueven dinero, accesos o datos; un secreto en los archivos; un cambio que rompe algo que funcionaba. El estilo no es un hallazgo.
- Tras el merge, si la sesión sigue aquí: en `main/`, fast-forward de `main`; elimina el worktree y borra la rama. Si no, lo hace el preflight de la siguiente tarea. El ajuste del repositorio «Automatically delete head branches» está activado desde la primera instalación: por él una tarea posterior distingue un worktree fusionado de uno vivo.

## Stack

De qué está hecho este proyecto y los dos comandos que todo agente necesita. Se rellena en la instalación y se cambia por reemplazo cuando cambia el stack. ¿Todavía no hay código? Escribe «none yet» en las tres líneas; no inventes una comprobación para un proyecto que no tiene nada que comprobar.

- Hecho de: [lenguajes, frameworks, base de datos, hosting, en una línea]
- Comprobación: [un comando que ejecuta el formateador, el linter, los tipos y los tests, por ejemplo: pnpm check]
- Ejecución: [un comando y la dirección, por ejemplo: pnpm dev → http://localhost:3000]

## La comprobación

Ejecuta el comando de comprobación de la sección Stack antes de cada commit. Rojo significa no hecho, sea cual sea la razón. Un aviso que ya estaba antes no es motivo para llamar a una persona.

## Zonas de riesgo: prepara, no ejecutes

| Siempre | Pregunta primero | Nunca |
|---|---|---|
| trabajar en una rama, escribir la especificación, ejecutar la comprobación, informar | cualquier cosa que mueva dinero, toque claves o accesos, guarde o envíe datos personales, publique fuera del repositorio, cambie ajustes de producción | borrar datos, reescribir cambios de otra persona, hacer force-push a `main`, poner secretos en archivos o logs, pedir un secreto en el chat, imprimir un secreto de cualquier archivo o salida de comando, dejar archivos de trabajo (capturas, logs, volcados) dentro del repositorio |

«Pregunta primero» significa: haz todo hasta el botón, luego para y entrega una línea con la elección. No abras la discusión en mitad del trabajo.

Una parada para la persona tiene una sola forma. Primera línea: la única acción, empezando por un verbo; nada por encima. Luego dónde, como enlace clicable a la página exacta y los clics en orden (menú, pestaña, botón). Luego qué decir cuando esté hecho. Debajo, como mucho dos líneas sobre el estado. Sin historia, sin opciones, sin «estado hasta ahora». Si la persona responde con una captura, la primera línea dice si es la página correcta y la segunda da el siguiente clic.

Un secreto nunca pasa por el chat. La persona lo pone donde vive: la página de ajustes del hosting, o el archivo local de claves. El agente comprueba por el nombre de la variable y nunca pide ni imprime el valor. `--force` solo sobre un árbol sucio, y solo con permiso de la persona.

## Decisiones

Una decisión es una elección que mañana podría reabrirse. Se registra en `docs/journal.md` como una entrada con nombre estable:

```
## 2026-09-02 15:01 · <agente> · ⚖️ signup-without-password · Registro solo por enlace de correo

**Decidido.** ...
**Rechazado.** ... y por qué.
**Palabras del dueño.** «...»
```

«Palabras del dueño» es una cita de la persona. Si nadie habló y la tarea llegó como un prompt pegado, cita su primera frase.

Reglas alrededor de las decisiones:

- Una regla tiene una sola casa. Los demás documentos enlazan a ella; no la copian.
- El canon cambia por reemplazo. La regla vieja se borra en el mismo commit; la historia vive en el journal y en git.
- Antes de proponer un cambio de arquitectura, URLs, esquema de datos o proceso, lee el journal de esa zona. Las cuestiones decididas no se reabren sin que el dueño lo pida.
- Un «ahora no» se registra con el evento que lo reabre, no con una fecha.
- El razonamiento que ocurrió en el chat y no está en el journal es trabajo sin terminar, como código sin commit.

Cuando descubras que actuaste contra una regla escrita, arregla la causa antes que el síntoma, de arriba abajo: la regla no está escrita, escríbela; está escrita en el lugar equivocado, muévela; está escrita pero nadie la encontró, hazla encontrable desde el lugar donde empieza la tarea. «Tendré más cuidado» no es un arreglo.

## Estructura

Siete es un disparador, no una meta. Cuantas menos cosas, mejor; un nivel debe leerse de un vistazo. Cuando aparezca el octavo archivo, carpeta, tabla, variable o script en un nivel, plantea la pregunta de agrupar, y agrupa solo por sentido, nunca por el número. Dos archivos del mismo tipo en un nivel son un aviso temprano: pregunta si quieren una carpeta con un `README.md`.

`docs/README.md` se queda en una página. Si crece, algo debajo quiere su propia carpeta.

## Producción

Todo lo que vaya a funcionar sin una persona, un formulario, un webhook, una tarea programada, una integración, una nueva fuente de datos, nace con cuatro cosas en un solo cambio:

1. el elemento en sí;
2. su canon en `docs/`: de dónde viene la entrada, dónde escribe, bordes conocidos;
3. su cristal: un lugar donde se ve su estado, una página o una línea en una página existente;
4. su inmunidad: una comprobación externa que falla a gritos cuando el elemento está roto («el formulario se renderiza y el endpoint responde 200»), no una métrica de negocio.

El contenido y la maquetación sin un nuevo flujo de datos o dinero quedan fuera de esta regla.

## Informe

Toda tarea de escritura termina con el mismo bloque, para que la persona lo lea en diez segundos. Una línea que no tiene nada que decir se omite.

```
---
🧭 next · el paso que más mueve el proyecto, y por qué
📚 docs · los archivos de docs/ en los que se apoyó la tarea, uno por línea debajo
⚖️ cómputo · quién hizo el trabajo: <agente> 100 % solo, o el reparto entre agentes
✅ merged · <commit o pull request> · N files +X/-Y
   <ruta> +a/-b, una por línea; una entrada del journal lleva su título: docs/journal.md +12/-0 · «nombre de la entrada»
🌐 dónde mirar
   <dirección>, una por línea: local · preview · producción
🛂 pasaporte · elemento ✅ · canon ✅ · cristal ✅ · inmunidad ⬜ (solo cuando algo va a funcionar sin una persona)
⚠️ no verificado · qué no pudiste comprobar y por qué, o «nada»
```

La línea git es una de: `✅ merged · …` · `🔀 pull request #N · comprobación en verde, esperando a la persona` · `📝 commit hecho (solo primera instalación) · <commit>` · `⛔ bloqueado · por qué`. Los archivos debajo salen de `git diff --stat`, nunca de memoria.

## El ciclo

tarea en palabras → trabajo → aceptación por el criterio → entrega → observación → siguiente tarea

Cada unidad de trabajo es una vuelta completa de este ciclo. El mismo ciclo gira a toda escala: una funcionalidad, un producto, una zona del negocio, la empresa. La observación de la última vuelta es de donde sale la siguiente tarea.

---

Basado en [Spec-Driven Company](https://github.com/eugeneshilow/spec-driven-company) de Eugene Shilov, CC BY 4.0. Conserva esta línea cuando copies el archivo.
