# Vertical Slice Spec: El sonido del canal

## Estado y propósito

Esta especificación convierte el slice narrativo del GDD en una unidad implementable de 12 a 15 minutos. No construye gameplay ni assets finales.

El slice debe demostrar:

- caminar y leer un mapa;
- elegir un starter;
- tener un Pokémon follower;
- capturar una especie;
- librar combates;
- entrar y salir de interiores;
- cambiar día/noche desde debug;
- encontrar la primera pista del Meridiano;
- guardar y cargar;
- usar la infraestructura de datos nacional 001-493 cuando el Gate 1 del spike esté aprobado.

La demo no debe mostrar Sinnoh, no debe producir 493 followers finales y no debe agregar mapas al manifiesto.

## Precondiciones

Antes de llamar al slice “jugable de producción”:

- el bug del evento de ribbons con party vacía debe estar corregido y repetido sin crash;
- Essentials v21.1 debe abrir y compilar en la copia local del spike;
- Gate 1 del spike debe confirmar la carga de 493 especies;
- los datos del slice deben provenir del snapshot versionado;
- los assets temporales deben tener provenance;
- ningún archivo propietario del ZIP de Essentials se copia al repo público.

Si el Gate 1 todavía está pendiente, se puede hacer una prueba de interacción con seis especies, pero el resultado debe etiquetarse `prototype_non_contractual`, no como evidencia de cobertura 493.

## Cargas usadas

El slice reutiliza exactamente cinco cargas del manifiesto existente.

| Orden | ID | Categoría | Función en el slice | Carga independiente |
|---:|---|---|---|---|
| 1 | INT01 | interior | Casa de Sofi; inicio, guardado y salida | yes |
| 2 | INT02 | interior | Laboratorio Umbral; starter, Pokédex y Brújula | yes |
| 3 | TOWN01 | town | Pueblo Umbral; tutorial espacial y conexión | yes |
| 4 | ROUTE01 | route | Ruta del Canal; captura, entrenadores y follower | yes |
| 5 | LAND01 | landmark | Estación Vieja; baliza apagada y nota firmada “F.” | yes |

No se crean variantes de estos mapas para noche. El estado temporal cambia iluminación, encuentros y eventos sobre las mismas cargas.

Referencia: [MAP_MANIFEST.md](MAP_MANIFEST.md).

## Estructura espacial mínima

### INT01: Casa de Sofi

- Sala de inicio.
- Punto de interacción para guardar.
- Salida única hacia TOWN01.
- No requiere NPCs familiares ni lore personal adicional.
- El follower todavía no está activo al entrar.

### INT02: Laboratorio Umbral

- Mesa de tres starters.
- Investigadora responsable de entregar la Pokédex.
- Terminal de Brújula.
- Salida hacia TOWN01.
- Una pared o ventana debe mostrar el canal para anticipar el motivo visual del slice.

### TOWN01: Pueblo Umbral

- Plaza central.
- Camino a INT01.
- Camino a INT02.
- Salida a ROUTE01.
- Un NPC de ambientación comenta que “el agua llegó antes”.
- Un punto de curación o recuperación rápido para evitar que el slice dependa de un recorrido innecesario.

### ROUTE01: Ruta del Canal

- Entrada desde TOWN01.
- Dos segmentos de hierba.
- Un tramo de agua bloqueado para Surf futuro.
- Dos entrenadores.
- Un objeto de campo.
- Un trigger de follower junto al canal.
- Entrada a LAND01.
- Retorno corto a TOWN01 para cerrar el objetivo.

### LAND01: Estación Vieja

- Andén o sala principal.
- Baliza apagada como objeto interactivo.
- Nota firmada “F.”.
- Salida a ROUTE01.
- No incluye acuario, faro ni una segunda sala cargada. Es una única escena navegable.

## Flags y variables

Prefijo obligatorio: `VS_`. Ninguna flag del slice debe reutilizar flags narrativas del juego terminado.

| ID | Tipo | Valor inicial | Se activa cuando | Uso |
|---|---|---:|---|---|
| VS_STARTED | switch | off | Se sale de INT01 por primera vez | Evita repetir el prólogo |
| VS_STARTER_SELECTED | switch | off | Se confirma un starter | Habilita follower y siguiente diálogo |
| VS_STARTER_ID | variable | 0 | Se confirma un starter | Guarda especie elegida |
| VS_POKEDEX_GIVEN | switch | off | Investigadora entrega Pokédex | Habilita registro |
| VS_COMPASS_GIVEN | switch | off | Se entrega Brújula | Habilita rumores y hora |
| VS_FOLLOWER_ENABLED | switch | off | Starter entra al equipo | Activa follower |
| VS_FOLLOWER_CANAL_REACTED | switch | off | Se interactúa junto al canal | Evita repetir reacción |
| VS_TRAINER_01_DEFEATED | switch | off | Se derrota al primer entrenador | Control de tutorial |
| VS_TRAINER_02_DEFEATED | switch | off | Se derrota al segundo entrenador | Control de tutorial |
| VS_WILD_CAPTURED | switch | off | Se captura cualquier especie del slice | Avanza objetivo |
| VS_BEACON_NOTE_FOUND | switch | off | Se inspecciona la baliza en LAND01 | Activa cierre |
| VS_RETURNED_TO_UMBRAL | switch | off | Se vuelve a TOWN01 con la nota | Marca fin jugable |
| VS_SLICE_COMPLETE | switch | off | Se muestra la última línea | Permite repetir/teletransportar |
| VS_DEBUG_TIME_MODE | variable | 0 | Debug cambia la hora | 0 día, 1 noche; no es requisito narrativo |
| VS_DEBUG_CHECKPOINT | variable | 0 | QA selecciona checkpoint | Sólo en build de prueba |

### Reglas de persistencia

- Guardar después de `VS_STARTER_SELECTED`.
- Guardar después de `VS_WILD_CAPTURED`.
- Guardar después de `VS_BEACON_NOTE_FOUND`.
- Cargar cada save en una ejecución separada.
- Si se carga un save anterior a una flag, el evento debe seguir siendo jugable.
- `VS_DEBUG_TIME_MODE` puede persistir sólo en build de prueba; la build de demo debe volver a día al iniciar una partida nueva.

## Eventos

| ID | Mapa | Evento | Condición | Resultado |
|---|---|---|---|---|
| E01 | INT01 | Inicio | !VS_STARTED | Muestra objetivo y habilita salida |
| E02 | INT01 | Guardado | Siempre | Ejecuta save normal |
| E03 | INT02 | Starter Bulbasaur | !VS_STARTER_SELECTED | Entrega Bulbasaur, activa flags |
| E04 | INT02 | Starter Cyndaquil | !VS_STARTER_SELECTED | Entrega Cyndaquil, activa flags |
| E05 | INT02 | Starter Mudkip | !VS_STARTER_SELECTED | Entrega Mudkip, activa flags |
| E06 | INT02 | Investigadora | !VS_POKEDEX_GIVEN | Entrega Pokédex y Brújula |
| E07 | INT02 | Activación follower | VS_STARTER_SELECTED | Enciende VS_FOLLOWER_ENABLED |
| E08 | TOWN01 | NPC del canal | !VS_BEACON_NOTE_FOUND | Explica la marea adelantada |
| E09 | ROUTE01 | Entrenador 1 | !VS_TRAINER_01_DEFEATED | Combate tutorial; activa flag al ganar |
| E10 | ROUTE01 | Entrenador 2 | !VS_TRAINER_02_DEFEATED | Combate breve; activa flag al ganar |
| E11 | ROUTE01 | Hierba salvaje | VS_FOLLOWER_ENABLED | Encuentro según tabla de hora |
| E12 | ROUTE01 | Reacción del follower | !VS_FOLLOWER_CANAL_REACTED | Texto y pose; activa flag |
| E13 | LAND01 | Baliza | !VS_BEACON_NOTE_FOUND | Sonido, animación, entrega nota |
| E14 | LAND01 | Nota firmada | VS_BEACON_NOTE_FOUND | Texto de “F.”; activa retorno |
| E15 | TOWN01 | Cierre | VS_BEACON_NOTE_FOUND && !VS_RETURNED_TO_UMBRAL | Diálogo final y VS_SLICE_COMPLETE |

No se implementan eventos de combate contra Fede en el slice. Su presencia es sólo la firma de la nota.

## Orden de escenas

### 0:00-1:00, salida de INT01

Diálogo mínimo:

> Investigadora: “Si vas a recorrer el canal, llevá a tu Pokémon con vos. Quiero saber qué nota.”

Objetivo mostrado:

> Llegá al Laboratorio Umbral.

Al salir, activar `VS_STARTED`.

### 1:00-3:00, starter en INT02

La investigadora presenta tres opciones sin explicar todavía la mitología.

> Investigadora: “No busco el Pokémon más fuerte. Busco ver qué pasa cuando alguien aprende un lugar junto a él.”

Al elegir:

> Investigadora: “Entonces van a aprender juntos.”

Entregar Pokédex, Brújula y 5 Poké Balls. Activar:

- `VS_STARTER_SELECTED`;
- `VS_STARTER_ID`;
- `VS_FOLLOWER_ENABLED`;
- `VS_POKEDEX_GIVEN`;
- `VS_COMPASS_GIVEN`.

Objetivo mostrado:

> Seguí el canal hasta la Estación Vieja.

### 3:00-4:00, TOWN01

El jugador puede recorrer la plaza. El NPC del canal dice:

> NPC: “El agua llegó antes de la marea. No sé cómo explicarlo sin sonar ridículo.”

No debe aparecer el nombre Meridiano todavía.

### 4:00-8:00, ROUTE01

El jugador atraviesa hierba, captura al menos una especie y derrota dos entrenadores.

Entrenador 1:

> “Si vas a cruzar, mirá primero dónde pisa tu Pokémon.”

Entrenador 2:

> “La ruta cambia cuando cae la tarde. O eso dicen.”

Después de entrar en la zona junto al canal, el follower reacciona:

> [Pokémon] mira el agua fijamente. Parece estar siguiendo un sonido que vos no escuchás.

Activar `VS_FOLLOWER_CANAL_REACTED` sólo una vez.

La captura no debe depender de una especie única. Cualquier captura válida activa `VS_WILD_CAPTURED`.

### 8:00-11:00, LAND01

Al inspeccionar la baliza:

> La baliza está apagada, pero todavía está tibia.

Reproducir un sonido breve y mostrar una animación simple. La nota dice:

> Registro 01. La señal no llamó a los Pokémon. Les ofreció una ruta.

Firma:

> F.

Activar `VS_BEACON_NOTE_FOUND`.

No explicar quién es Fede. La firma funciona como callback personal, no como revelación narrativa completa.

### 11:00-13:00, regreso

Al volver a TOWN01:

> NPC: “¿También escuchaste ese tono?”

Si `VS_WILD_CAPTURED` está off:

> Investigadora: “Podés volver después. Primero conocé a un Pokémon de la ruta.”

No bloquear el cierre por no capturar. Si se quiere medir captura, registrar la condición como métrica de playtest, no como requisito de historia.

Activar `VS_RETURNED_TO_UMBRAL` y `VS_SLICE_COMPLETE`.

## Día/noche en el slice

La transición se prueba con `VS_DEBUG_TIME_MODE`, no con el reloj del sistema.

### Día

- Encuentro común de ROUTE01.
- Paleta de agua clara.
- NPC del canal visible.

### Noche

- Encuentro alternativo de ROUTE01.
- Paleta de agua oscura y una luz en LAND01.
- El follower conserva colisión y seguimiento.
- La nota y los flags narrativos no cambian.

La noche no agrega una especie necesaria para completar el roster. Sólo demuestra el consumidor técnico del horario.

## Encuentros y combates

### Starter

- Bulbasaur, Cyndaquil o Mudkip.
- Nivel 5.
- Movimientos iniciales compatibles con el perfil de batalla elegido.

### ROUTE01

- Tabla de encuentros temporal con al menos dos especies de prueba.
- Una especie diurna y una nocturna deben ser distintas.
- La tabla debe poder reemplazarse por datos definitivos sin cambiar eventos.

### Entrenadores

- E09: un Pokémon, nivel 3-4, tutorial de ataque.
- E10: un Pokémon, nivel 4-5, usa al menos una acción distinta.
- No usar Fede ni un rival principal.
- La dificultad debe permitir terminar el slice sin grind.

El slice no intenta validar el balance completo de 493 especies. Valida que una tabla de encuentros, un trainer y una captura consuman el mismo registro canónico.

## Assets temporales y provenance

| Asset | Uso | Fuente temporal | Provenance | Estado |
|---|---|---|---|---|
| Sofi placeholder | Sprite de campo | Silueta original simple; sin likeness personal | original_work; creado para el slice; sin datos personales | temporary |
| Investigadora placeholder | NPC de INT02 | Arquetipo original simple | original_work; creado para el slice | temporary |
| Bulbasaur, Cyndaquil, Mudkip | Front, back, icon y follower | Assets locales del paquete privado o placeholders originales | existing o original_work; registrar hash y licencia antes de uso | temporary |
| Dos especies de ROUTE01 | Front, back, icon y follower | Assets locales del paquete privado o placeholders originales | existing o original_work; registrar hash y licencia | temporary |
| Seis representantes de escala | Test de follower | Placeholders originales por clase XS/S/M/L/XL; una clase puede repetirse | original_work; creado para el slice | temporary |
| Tileset de pueblo | TOWN01 e INT01 | Tileset local del spike o placeholder original | existing o original_work | temporary |
| Tileset de canal | ROUTE01 | Placeholder original de tres colores y transparencias | original_work | temporary |
| Tileset de estación | LAND01 | Placeholder original; no recrear una estación real | original_work | temporary |
| Nota y baliza | Evento de LAND01 | Tipografía/UI temporal propia | original_work | temporary |
| Música de día/noche | Ambiente | Dos loops temporales propios o silencio controlado | original_work; no usar música de Pokémon | temporary |

Reglas:

- No usar el slice como aprobación estética.
- No distribuir el paquete privado de Essentials.
- Cada asset no original debe tener `source_uri`, `source_revision`, `license`, `copyright_owner`, `sha256` y `transformation`.
- Un placeholder sirve para probar lógica, pero no cuenta como asset final.
- La ausencia de un asset final no debe impedir probar flags, captura o save/load.

## Criterios de aceptación

### Funcionales

- Una partida nueva permite elegir los tres starters en ejecuciones separadas.
- El starter sigue al jugador después de la elección.
- El follower no atraviesa paredes ni bloquea los cinco warps.
- Se puede capturar al menos una especie.
- Se pueden ganar ambos combates.
- Se puede entrar y salir de las cinco cargas.
- Guardar y cargar conserva starter, follower, captura y flags.
- El cambio debug día/noche modifica encuentros y presentación sin romper flags.
- LAND01 activa la nota una sola vez.
- El regreso a TOWN01 completa el slice.
- El evento de ribbons con party vacía ya no produce crash en la regresión del smoke test.

### Datos

- La build de slice usa el schema canónico y no una lista manual paralela.
- Si Gate 1 pasó, el manifest de datos contiene 493 especies.
- Las especies usadas en el slice tienen IDs, learnsets, assets y métodos trazables.
- El slice no declara coverage verified para especies cuyos métodos sigan planned.
- No hay requiere_trade, version exclusive ni external game en los datos usados.

### Narrativa

- El jugador entiende qué hacer sin instrucciones externas.
- La nota de F. produce curiosidad, no una explicación completa.
- No aparece Sinnoh ni una segunda región disfrazada.
- No se inventan referencias personales fuera de Sofi, Fede, Nahue y los datos ya aprobados.
- El follower tiene al menos una reacción contextual legible.

### Producción

- No se agregan IDs de mapa.
- No se crean 493 followers finales.
- Los assets temporales están marcados y tienen provenance.
- Tres ejecuciones desde save nuevo llegan al cierre sin crash.
- Un cuarto recorrido con save cargado conserva el estado.
- El slice se puede reconstruir desde el mismo commit e inputs.

## Checklist de playtest

### Preparación

- [ ] Copiar una build limpia de prueba.
- [ ] Confirmar commit, versión de Essentials y hash del snapshot.
- [ ] Crear tres saves nuevos con nombres de prueba.
- [ ] Activar logging de flags, mapas, encuentros y errores.
- [ ] Confirmar que no se está usando el ZIP propietario dentro del repo público.

### Recorrido base

- [ ] Iniciar partida nueva.
- [ ] Salir de INT01.
- [ ] Elegir Bulbasaur.
- [ ] Confirmar follower.
- [ ] Recibir Pokédex y Brújula.
- [ ] Recorrer TOWN01.
- [ ] Ver el comentario sobre la marea.
- [ ] Entrar a ROUTE01.
- [ ] Derrotar E09.
- [ ] Capturar una especie.
- [ ] Hablar con el follower junto al canal.
- [ ] Derrotar E10.
- [ ] Entrar a LAND01.
- [ ] Leer la nota de F.
- [ ] Volver a TOWN01.
- [ ] Confirmar `VS_SLICE_COMPLETE`.

### Variantes

- [ ] Repetir con Cyndaquil.
- [ ] Repetir con Mudkip.
- [ ] Activar noche desde debug antes de ROUTE01.
- [ ] Confirmar encuentro nocturno distinto.
- [ ] Confirmar luz/paleta nocturna en LAND01.
- [ ] Guardar antes de la captura y cargar.
- [ ] Guardar después de la captura y cargar.
- [ ] Guardar después de la nota y cargar.
- [ ] Intentar volver a leer la nota.
- [ ] Probar salida y entrada repetida por los cinco warps.
- [ ] Ejecutar el evento de ribbons con party vacía como regresión separada.

### Registro de observaciones

Para cada ejecución registrar:

- tiempo hasta starter;
- tiempo hasta follower;
- tiempo hasta primera captura;
- tiempo hasta primera pista;
- tiempo total;
- mapa donde el jugador dudó;
- diálogo que se salteó o no entendió;
- comportamiento del follower;
- errores de colisión;
- flags inesperadas;
- especie y hora del encuentro;
- crash, softlock o pérdida de save;
- una mejora prioritaria.

## Gate de salida del slice

El slice pasa a producción de Acto I sólo si:

1. las tres elecciones de starter funcionan;
2. los cinco mapas cargan y descargan correctamente;
3. no hay crash en tres recorridos nuevos;
4. save/load conserva estado;
5. follower y captura funcionan de día y noche;
6. la pista de F. se entiende sin explicar su identidad;
7. el smoke test de ribbons sigue pasando con party vacía;
8. el registro de provenance está completo;
9. el equipo confirma que el roster 493 sigue siendo una fuente única;
10. no se agregaron mapas, Sinnoh ni assets finales fuera de scope.

Si falla cualquiera de los puntos 2, 3, 4, 5, 7 u 8, no se expande el slice. Se corrige la infraestructura primero.
