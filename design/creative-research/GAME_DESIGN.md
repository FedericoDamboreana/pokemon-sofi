# Proyecto Sofi: Game Design Document

## Resumen ejecutivo

### Recomendación en una frase

Hacer una aventura Pokémon compacta de seis medallas en una región costera ficticia y densa, con estética y sistemas de la era Gen 4, donde un sistema creado para volver predecible la vida de la región empieza a borrar sus variaciones, y donde Fede es el arquitecto bienintencionado pero equivocado de ese sistema.

El conflicto no es "robar un legendario". Es una disputa sobre qué significa cuidar un mundo vivo: reducir toda incertidumbre a un modelo seguro o aceptar que los Pokémon, las personas y la protagonista tienen derecho a cambiar de rumbo.

### Producto objetivo

- Campaña principal: 5 a 8 horas para una primera partida normal.
- Postgame crítico: 6 a 10 horas de contenido intencional, no sólo rematches. La completitud de los 493 es una capa opcional separada.
- Alcance confirmado: las 493 especies de Generaciones 1 a 4 obtenibles en una única partida, sin exclusivos de versión, intercambios obligatorios ni contenido externo.
- Seis gimnasios, una Liga breve y una confrontación final narrativa.
- Pokémon siguiendo al jugador desde el primer tramo jugable.
- Ciclo día/noche, encuentros por horario, NPCs móviles y eventos diarios o semanales.
- Región original, compacta y costera. No se declara que sea Mar del Plata ni Argentina; cualquier inspiración geográfica real queda como decisión pendiente.
- Estética de pixel art inspirada en la era DS, sin copiar mapas, interfaz ni guion de HGSS.

### Tratamiento narrativo provisional recomendado

Fede aparece primero como un investigador de campo que ayuda a Sofi a leer la región. Proporciona el equivalente al PokéGear y parece una figura de apoyo. Más adelante se revela que dirige la infraestructura llamada **Meridiano**, una red de balizas que predice y redirige migraciones Pokémon. Su motivación es evitar accidentes y proteger hábitats, pero su solución transforma un mundo vivo en un sistema cerrado.

Fede no es inocente: oculta daños, manipula rutas y usa a la protagonista como prueba de que su modelo funciona. Tampoco es un sádico ni un conquistador. Su caída nace de una virtud llevada demasiado lejos: confunde comprender un sistema con tener derecho a fijarlo. Este tratamiento es una recomendación de trabajo, no una decisión canónica; la sección comparativa mantiene abiertas las alternativas hasta que Fede y Sofi lo aprueben.

### Evidencia nueva sobre Sofi y cómo interpretarla

La evidencia disponible indica que Sofi valoró especialmente:

- que los Pokémon la siguieran y dieran sensación de compañía;
- la nostalgia de Pokémon Oro y de la Generación 2;
- el diseño de la protagonista;
- la sensación de aventura y recorrido;
- la posibilidad de explorar una segunda gran zona equivalente a Kanto.

La evidencia inicialmente dejaba abierta si “cuarta generación” significaba estética o especies #387-493. La decisión posterior de Fede confirma que se refiere a las especies de Gen 4. Por lo tanto, 493 es un requisito de producto, mientras que la estética Gen 4 sigue siendo una referencia separada. No se presenta Litoral de Bruma como Sinnoh: las especies #387-493 llegan como migraciones, hábitats, regalos, evoluciones y cadenas de postgame dentro de una región original.

La resolución recomendada es una derrota con responsabilidad, no una absolución instantánea. Fede ayuda a desactivar el Meridiano después de perder, pero debe reparar sus consecuencias en el postgame. Allí puede convertirse en superboss opcional, no para volver a ser villano, sino para probar que por fin acepta la incertidumbre y entrena sin controlar cada variable.

## 1. Principios y alcance

### Pilares de diseño

#### 1. Viaje antes que exposición

Cada capítulo debe tener al menos un trayecto, una decisión de exploración y un momento de convivencia con el Pokémon seguidor. Si un bloque sólo transmite información, se recorta o se convierte en interacción espacial.

#### 2. Misterio legible, no críptico

El jugador debe poder formular una hipótesis antes de cada revelación. Las pistas aparecen en mapas, conversaciones, cambios de encuentros y reacciones del follower. No se reserva toda la explicación para una escena final.

#### 3. Referencias como descubrimiento

La referencia personal entra por capas: textura, nombre, frase, función y finalmente significado. Nunca debe ser necesaria para entender el conflicto.

#### 4. El mundo cambia sin castigar

El día, la noche y los eventos semanales ofrecen Pokémon, conversaciones y atajos. Ningún Pokémon único necesario para completar la Pokédex queda perdido permanentemente por no jugar en una franja concreta.

#### 5. Densidad sobre tamaño

Un mapa grande sólo entra si introduce una mecánica, un misterio, un ecosistema o una recompensa propia. Una ruta sin identidad se fusiona con otra.

#### 6. Pokémon primero

La historia nunca puede exigir que el jugador abandone la captura, el entrenamiento o el paseo con su equipo durante largos segmentos. La trama se expresa mediante decisiones de recorrido, combates y estados del mundo.

### Criterios de entrada y corte

Una idea entra en P0 si cumple dos de estas tres condiciones y no pone en riesgo las tres primeras:

1. Refuerza la relación Sofi-Pokémon.
2. Hace que la región parezca viva o memorable.
3. Produce una decisión o una recompensa jugable, no sólo diálogo.

Se corta si:

- requiere una segunda región completa;
- necesita una interfaz o sistema de red complejo para funcionar;
- agrega más de una familia de assets nuevos por minuto de experiencia;
- aparece una sola vez y no deja consecuencia;
- desplaza al follower, la campaña base, la Pokédex o el QA;
- depende de información personal que todavía no fue confirmada por Fede o Sofi.

### Prioridad del producto

| Prioridad | Contenido | Criterio de aceptación |
|---|---|---|
| P0 | Campaña de 5 a 8 horas | Se puede terminar sin bloqueos, con ritmo estable y dos picos narrativos claros |
| P0 | 493 especies obtenibles | Un archivo de datos y un test verifican cobertura en una partida |
| P0 | Follower base | Las 493 especies tienen comportamiento y representación válidos con cinco escalas y fallback específico; las reacciones especiales quedan fuera del mínimo |
| P0 | Día/noche | Cambian encuentros, arte ambiental y al menos un evento por zona |
| P0 | Región densa | Ninguna ruta principal supera 4 minutos sin una decisión o hallazgo |
| P0 | Fede-antagonista | La revelación se puede deducir y recontextualiza al menos tres escenas previas |
| P0 | Postgame crítico | 6-10 horas, Península del Velo, consecuencias del Meridiano y acceso funcional a las 493 especies |
| P1 | Eventos diarios/semanales | 8 eventos repetibles con estados persistentes |
| P1 | PokéGear equivalente | Mapa, llamadas o mensajes, horario y dos canales de información |
| P1/P2 | Reacciones especiales y rematches completas | 32 reacciones y equipos completos sólo después de validar el slice y la campaña |
| P1 | Actividad secundaria | Un minijuego o actividad profunda y tres cadenas de sidequests, con 10-12 sidequests totales |
| P1 | QA automatizado | Smoke tests de mapas, datos, flags y progresión |
| P2 | Pokéathlon completo | Sólo entra si el slice demuestra que el pipeline de minijuegos no amenaza el calendario |
| P2 | Crafting complejo | Fuera de la primera versión |
| P2 | Online, comercio o segunda región | Fuera de la primera versión |
| P1/P2 | Cadenas individuales de los 35 legendarios/míticos y completitud detallada | El roster y los caminos mínimos son P0; la autoría completa de cada cadena queda después del slice |
| P2 | Múltiples finales | Fuera salvo que aparezca una consecuencia simple y fuerte en playtest |

## 2. Alcance realista y presupuesto de contenido

### Geografía de la primera versión

- 6 ciudades o pueblos con identidad propia.
- 9 rutas cortas conectadas como red, no como pasillo único.
- 8 landmarks: faro, estación abandonada, bosque húmedo, ruinas, observatorio, acuario, cantera y santuario de mareas.
- 6 gimnasios.
- 1 sede de Liga compacta con cuatro combates y una sala final.
- 4 áreas de postgame: Península del Velo, laboratorio de Meridiano, isla de marea baja y cumbre del observatorio.
- 21 interiores con función. Las casas genéricas se agrupan visualmente y no se cuentan como contenido individual.

#### Regla única para contar mapas

Un mapa de producción es una escena navegable que se carga como una unidad y tiene layout, colisiones y eventos propios. Cada pueblo, ruta, landmark, gimnasio, área de Liga, área de postgame e interior funcional cuenta como un mapa. Una sala extra sólo cuenta si necesita una carga separada. Menús, batallas, transiciones, casas decorativas sin acceso y mapas de debug no cuentan en el manifiesto de contenido.

Con esa regla, el manifiesto fijo de la primera versión es de **55 mapas jugables**: 6 pueblos + 9 rutas + 8 landmarks + 6 gimnasios + 1 Liga + 4 áreas de postgame + 21 interiores. Si el engine obliga a separar un gimnasio en varias cargas, esas cargas deben salir de los 21 interiores o fusionarse en otra parte; no se aumenta el máximo sin una decisión de scope.

El listado auditable de IDs, fases y cargas está en [design/production/MAP_MANIFEST.md](../production/MAP_MANIFEST.md). Faro y acuario se cuentan como un único mapa `LAND05`; sus subzonas internas no se cuentan dos veces.

### Presupuesto de contenido

La siguiente cifra es un presupuesto de producción, no una estimación de dinero. Sirve para decidir qué se intenta hacer en una primera versión.

| Paquete | Volumen recomendado | Prioridad |
|---|---:|---|
| Mapas jugables según la regla única | 55 | P0 |
| NPCs nombrados | 24 a 30 | P0/P1 |
| NPCs de ambientación | 36 a 48 reutilizando arquetipos | P1 |
| Entrenadores con batalla | 70 a 86, contando Liga y postgame | P0 |
| Sidequests | 10 a 12, de las cuales 4 son cadenas | P1 |
| Escenas narrativas mayores | 14 a 18 | P0 |
| Especies en datos | 493 | P0 |
| Follower sprites o adaptaciones | 493, con 5 tamaños base y excepciones | P0 |
| Reacciones especiales de follower | 32, más interacciones genéricas | P1 |
| Tilesets principales | 5 familias | P0 |
| Música | 18 a 24 piezas o variaciones | P0/P1 |
| Retratos | 8 a 12 personajes | P1 |
| Herramientas de QA | 8 a 12 validadores y smoke tests | P1 |

La cifra de follower es alcanzable sólo si se utiliza un pipeline reproducible y se acepta que no todas las especies necesitan una animación única. El mínimo P0 es: silueta legible, colisión correcta, escala coherente, dirección de movimiento y fallback seguro. Las reacciones especiales son un multiplicador de calidad, no una condición para las 493.

### Qué no entra en la primera versión

- Kanto o una segunda región completa.
- Sistema online.
- Más de seis gimnasios si cada uno requiere puzzle nuevo.
- Fakemon o formas regionales.
- Un sistema de crafting con inventario propio.
- Una torre de batalla con varias reglas, salvo una versión simple de 10 combates.
- Más de dos legendarios integrados en la campaña principal.
- Voces completas o doblaje.
- Cinemáticas largas con assets exclusivos.

### Opciones consideradas y decisión confirmada

| Opción | Contenido | Efecto en encuentros | Efecto en historia y postgame | Duración y riesgo |
|---|---|---|---|---|
| A. Gen 1-3 | 386 especies | Menos presión sobre postgame, pero no satisface la decisión confirmada de incluir Gen 4 | 5-8 h + 4-8 h | Descartada |
| B. Gen 1-4 completa | 493 especies, incluyendo las 107 especies #387-493 | Requiere 107 especies adicionales, métodos de evolución, hábitats, regalos, sprites, encuentros, equipos y QA | 5-8 h + 6-10 h; completitud opcional 8-15 h adicionales | **Alcance confirmado** |
| C. Gen 1-3 + selección Gen 4 | 386 + 24 a 40 especies Gen 4 | Más controlable, pero contradice la decisión de obtener las 107 especies Gen 4 | 6-9 h + 5-9 h | Descartada |

#### Decisión explícita

El proyecto queda rebaselinado a **493 especies**. La campaña mantiene 5-8 horas porque las 107 especies Gen 4 se concentran principalmente en la Península del Velo, el laboratorio de Meridiano, regalos, evoluciones, cadenas y encuentros postgame. No se suma una región Sinnoh ni se agregan ocho gimnasios.

Para que B sea producible, se simplifican estas áreas:

- 6 gimnasios, no 8.
- 55 mapas jugables con una regla de conteo única, no una segunda región.
- 10-12 sidequests totales y 8 eventos semanales, no un calendario masivo.
- 32 reacciones especiales de follower, con comportamiento genérico para el resto.
- Una actividad secundaria profunda, no un Pokéathlon completo.
- Gen 4 sin formas regionales, Fakemon, gimnasios temáticos ni historia separada de Sinnoh.
- Rematches acotadas y una sola Liga.

La duración queda separada así:

- **Campaña obligatoria**: 5-8 horas, seis medallas, Liga y resolución del Meridiano.
- **Postgame narrativo y de exploración**: 6-10 horas, Península del Velo, consecuencias, rematches, cadenas legendarias y acceso a la mayoría de Gen 4.
- **Completitud opcional**: 8-15 horas adicionales para criar, evolucionar, buscar raros, resolver swarms y capturar los 35 legendarios/míticos. No se presenta como requisito para ver el final.

## 3. Visión del mundo y región

### Nombre de trabajo: Litoral de Bruma

Es una región ficticia construida alrededor de una costa semicerrada, una cadena de humedales y una elevación rocosa donde se levantan tres balizas antiguas. El nombre puede cambiar. La regla es que no se presenta como una versión encubierta de una ciudad real salvo que Sofi y Fede lo decidan.

La región tiene una forma de herradura. El jugador vuelve varias veces a los mismos puntos por caminos que se abren con Surf, Corte, Golpe Roca y una herramienta narrativa llamada **Sintonizador de Mareas**. La sensación buscada es de familiaridad creciente: un lugar que al principio parece pequeño y luego muestra capas.

### Lugares

| Lugar | Identidad | Función narrativa o jugable |
|---|---|---|
| Pueblo Umbral | Viviendas junto a un canal y un pequeño muelle | Inicio, laboratorio y primera aparición indirecta de Fede |
| Villa Salitre | Mercado, criadores y embarcadero | Primer gimnasio, economía y captura costera |
| Bosque Nimbo | Bosque bajo con niebla variable | Primer misterio del Meridiano; encuentros nocturnos |
| Ciudad Vértice | Nudo ferroviario y comercial | Segundo y tercer gimnasio, PokéGear y NPCs móviles |
| Humedal Lúmina | Lagos, pasarelas y juncos | Zona de seguimiento, pesca y cambios por horario |
| Puerto Farallón | Acantilados, acuario y faro | Cuarto gimnasio, mitología de navegación |
| Cuenca Ferrita | Cantera y túneles de servicio | Quinto gimnasio, consecuencias materiales del sistema |
| Observatorio Cénit | Altura rocosa y antenas antiguas | Sexto gimnasio, revelación y climax |
| Liga del Arco | Complejo al borde de la caldera | Liga y falsa sensación de cierre |
| Península del Velo | Zona postgame con mareas y ruinas | Consecuencias, legendarios y superboss |

### Gating

- Medalla 1: acceso al canal y a la red de atajos de Umbral.
- Medalla 2: Corte de campo y primera entrada opcional al Bosque Nimbo.
- Medalla 3: Sintonizador de Mareas, que permite leer cambios de agua y abrir rutas temporales.
- Medalla 4: Surf, acceso al Humedal Lúmina profundo y al faro.
- Medalla 5: Golpe Roca y acceso a la Cuenca Ferrita.
- Medalla 6: permiso de ascenso al Observatorio Cénit.
- Liga: se necesita haber investigado tres balizas, no sólo seis medallas. Esto evita que el final parezca una escalera de gimnasios sin relación.

El gating debe bloquear rutas, no curiosidad. Cada barrera tiene un borde visible, un objeto que la anticipa y una recompensa alternativa antes de desbloquearla.

### Día y noche

Se usan cuatro estados simples: mañana, día, tarde y noche. El cambio no debe alterar las escenas principales ni hacer perder especies únicas. En cada zona se modifican tres capas:

1. encuentros y porcentajes;
2. decoración, música o iluminación;
3. una interacción de NPC, follower u objeto.

Ejemplos:

- En el Bosque Nimbo, de noche aparecen luces de Paras, Shuppet o Chimecho y el follower puede señalar huellas.
- En el Humedal Lúmina, la marea baja abre una plataforma. La marea vuelve a bajar en la siguiente ventana si el jugador no llegó.
- En Ciudad Vértice, comerciantes y entrenadores se desplazan después de las 18:00, pero siempre dejan un cartel o una llamada que explica el cambio.

### NPCs móviles y eventos semanales

Los NPCs importantes tienen 3 estados: antes de su sidequest, durante la sidequest y resuelta. No se necesita un simulador complejo. Se recomienda una tabla de horarios por zona y un sistema de flags con fallback.

Eventos semanales P1:

- lunes: barco de pesca con una tabla de encuentros;
- miércoles: desafío de captura en Bosque Nimbo;
- viernes: rematch de un líder en un lugar variable;
- sábado: mercado de objetos raros;
- domingo: carrera de follower en el muelle.
- primer día de cada mes del juego: swarm anunciado por radio;
- después de cada rematch completa: una ruta de evolución alternativa;
- dos veces por semana: ventana de marea baja en la Península del Velo.

El día de la semana no debe ser la única manera de completar la Pokédex ni de obtener progreso narrativo. Son ocho eventos sistémicos, aunque algunos reutilizan una misma escena o mapa.

## 4. Estructura jugable por beats

Los tiempos suponen caminar, hablar, capturar algunos Pokémon y perder alguna batalla. Un jugador que ignore sidequests puede tardar menos.

| Tiempo | Beat | Objetivo del jugador | Mapas | Combates / capturas | Desbloqueo | Misterio / emoción |
|---:|---|---|---|---|---|---|
| 0:00-0:20 | Prólogo: el sonido de la baliza | Recibir starter y salir de Umbral | Casa, laboratorio, canal | Starter; tutorial opcional | Follower, Pokédex | Curiosidad, no exposición |
| 0:20-0:55 | Ruta del Canal | Llevar una muestra a un investigador | Ruta 1, estación vieja | 3 entrenadores, 3-5 especies | PokéGear simple | Una señal cambia encuentros |
| 0:55-1:25 | Villa Salitre | Conseguir la Medalla Sal | Villa, gimnasio, costa | 4 entrenadores, líder Lv 13-15 | Corte, mapa ampliado | Fede aparece como ayuda anónima en una nota |
| 1:25-2:00 | Bosque Nimbo | Investigar por qué emigran Pokémon | Bosque día/noche, santuario | 5 entrenadores, captura rara nocturna | Acceso a la baliza 1 | El follower reacciona a la niebla |
| 2:00-2:35 | Ciudad Vértice | Llegar al nudo de comunicaciones | Ruta 2, ciudad, estación | Rival amistoso, líder Lv 18-20 | PokéGear completo | Primer registro de Meridiano |
| 2:35-3:10 | Humedal Lúmina | Recuperar un objeto de investigación | Pasarelas, lago, casa de pescador | 4 entrenadores, pesca | Sintonizador de Mareas | Se descubre una ruta Pokémon alterada |
| 3:10-3:55 | Puerto Farallón | Seguir la señal hacia el faro | Puerto, acuario, faro | Líder Lv 24-26, evento doble | Surf | Fede aparece en persona, todavía aliado |
| 3:55-4:35 | Cuenca Ferrita | Cruzar una cantera dañada | Ruta 5, cantera, túnel | 6 entrenadores, líder Lv 29-31 | Golpe Roca | Consecuencia visible: hábitat desplazado |
| 4:35-5:15 | La tesis del Meridiano | Decidir si ayudar a reiniciar una baliza | Observatorio bajo, ciudad | Batalla contra administradores | Acceso a Cénit | Fede revela que conoce cada desvío de Sofi |
| 5:15-5:55 | Observatorio Cénit | Desactivar tres nodos | Ascenso, salas de antenas | 3 batallas, líder Lv 35-37 | Última medalla | El jugador entiende que Fede no quiere poder, quiere control |
| 5:55-6:35 | Liga del Arco | Completar la prueba de convergencia | Ruta final, Liga | 4 combates Lv 40-44 | Entrada al Hall of Fame | Victoria incompleta, señales aún activas |
| 6:35-7:10 | Falsa conclusión | Volver a Umbral y ver consecuencias | Pueblo, costa, laboratorio | Fede final campaña Lv 45-47 | Postgame, Pokédex ampliada | El mentor se vuelve antagonista |
| 7:10-8:00 | Coda: liberar el sistema | Elegir qué nodo apagar primero | Baliza central, costa | Batalla final narrativa y captura especial | Península del Velo | No se vence al mundo, se lo devuelve a su variación |

La tabla contiene margen. Si el playtest supera ocho horas sin hacer sidequests, hay que fusionar rutas o acortar puzzles, no aumentar la velocidad de texto.

## 5. Outline narrativo

### Premisa

En el Litoral de Bruma, los Pokémon migran siguiendo patrones conocidos: mareas, temperatura, sonidos y corrientes de energía. Desde hace meses, especies que nunca convivían aparecen juntas y otras desaparecen de sus hábitats. La explicación oficial es un cambio natural. Una red de balizas antiguas, reactivada por un grupo de investigadores, está alterando las rutas.

El sistema se llama Meridiano. Su propósito declarado es anticipar desastres, guiar a Pokémon perdidos y evitar que una población colapse. Su defecto es estructural: cuanto más intenta predecir el mundo, más lo modifica.

### Personajes

#### Sofi, protagonista

La evidencia disponible indica que le importan los followers, la compañía de los Pokémon, la nostalgia de Pokémon Oro y Gen 2, el diseño de la protagonista, la sensación de aventura y una segunda zona grande. Eso se traduce en una protagonista visualmente cuidada, con follower desde el comienzo, una región a la que se vuelve y una Península del Velo que se sienta como expansión real.

No se le asignan otros rasgos personales. Su identidad narrativa se construye por sus decisiones en juego: qué Pokémon captura, a quién ayuda, qué caminos explora y cómo responde a Fede. Su vínculo con el equipo es el centro emocional.

#### Fede, investigador y antagonista

Es observador, competente y capaz de explicar sistemas difíciles con claridad. Su defecto dramático es aceptar sólo las decisiones que puede medir. No busca destruir la región, pero sí volverla legible para él. Cuando Sofi contradice sus predicciones, lo vive como una anomalía que debe corregir.

#### Nahue, archivista de especies

El nombre entra como referencia a través de un personaje que mantiene una colección y un archivo de Pokémon de las tres primeras generaciones. La función se apoya en un dato confirmado del contexto: el interés de Nahue por esas generaciones. No se inventan otras preferencias ni anécdotas.

#### Curadora del observatorio

Figura institucional que ayudó a Fede a acceder a las balizas. No es una segunda villana. Su conflicto es haber aprobado el sistema porque funcionaba en simulación.

#### Rival de ruta

No es una copia de Silver o Blue. Su función es mostrar otra respuesta a la incertidumbre: improvisa, cambia de equipo y pierde con humor. Sirve de contrapunto mecánico a la obsesión de Fede.

### Acto I: aprender a mirar

1. Sofi recibe su starter y una Pokédex experimental.
2. El primer Pokémon puede seguirla inmediatamente. Al hablarle junto al canal, responde con una reacción sencilla.
3. Una baliza emite un tono que cambia los encuentros de la Ruta del Canal.
4. Fede no aparece aún como personaje. Una nota firmada sólo con "F." indica que alguien registró el cambio antes que la protagonista.
5. En Villa Salitre, un pescador dice que el mar "llegó a la hora equivocada". Es la primera pista diegética del reloj.

Diálogo representativo:

> Investigadora: "La señal no llamó a los Pokémon. Les dio una ruta que antes no existía."
>
> Sofi: "¿Y si la siguen porque quieren?"
>
> Investigadora: "Entonces el problema es que nadie sabe quién les está preguntando."

### Acto II: aprender a desconfiar

1. El Bosque Nimbo presenta reacciones de follower que no son decoración: el Pokémon señala un objeto, se niega a entrar en una zona o encuentra una huella.
2. En Ciudad Vértice, Fede aparece como investigador amable. Entrega el módulo de mensajes del PokéGear y ayuda a resolver una interrupción de encuentros.
3. Fede propone una hipótesis razonable: una baliza quedó desfasada y está creando ruido.
4. La jugadora recupera un nodo y descubre que el Meridiano está registrado como proyecto coordinado por Fede.
5. El tercer gimnasio no se desbloquea por una escena de villanos, sino al completar una ruta donde Sofi debe elegir entre el camino rápido y el camino que deja pasar a una migración.

Diálogo representativo:

> Fede: "No quiero decirle a cada Pokémon adónde ir. Quiero que deje de caminar hacia un incendio que todavía no podemos ver."
>
> Sofi: "¿Y quién decide cuál es el incendio?"
>
> Fede: "Por eso construimos el modelo. Para que no decida una sola persona."

La frase es parcialmente cierta y anticipa su autoengaño: delegar una decisión en un modelo no la vuelve neutral.

### Acto III: aprender el costo

1. En Puerto Farallón, la reactivación de una baliza produce un pico de encuentros. El área parece más viva al principio, pero un hábitat cercano queda vacío.
2. En la Cuenca Ferrita, el jugador encuentra Pokémon heridos o desplazados sólo mediante señales ambientales moderadas: nidos vacíos, objetos rotos, un NPC que busca a su compañero. No se usa sufrimiento gráfico.
3. Fede ya no sólo ayuda. Cierra un atajo, retira un nodo y altera deliberadamente los encuentros para forzar una prueba.
4. Sofi lo enfrenta por primera vez. Él reconoce que calculó sus decisiones con datos del PokéGear.
5. Se revela el vínculo con Sofi: Fede eligió a la protagonista como variable no entrenada. La relación no depende de un pasado personal inventado; depende de sus decisiones visibles durante la partida.

Diálogo representativo:

> Fede: "Tu equipo cambia cada vez que el camino te contradice. Eso era lo que necesitaba medir."
>
> Sofi: "No soy una medición."
>
> Fede: "Eso es exactamente lo que todavía no puedo demostrar."

### Acto IV: romper la predicción

1. En el Observatorio Cénit, Fede propone un reinicio total: si el Meridiano sincroniza las tres balizas, la región volverá a un patrón estable.
2. La Curadora revela que la simulación no modeló amistad, curiosidad ni decisiones humanas. Fede lo sabía, pero decidió que esas variables eran ruido.
3. Sofi debe apagar tres nodos en un orden elegido. Cada orden cambia una escena breve y un grupo de encuentros, pero no crea finales incompatibles.
4. Fede pelea con un equipo diseñado para cubrir respuestas previsibles. La batalla se vuelve más difícil cuando el jugador usa un equipo estable y más fácil si cambia de estrategia, una inversión temática del modelo.
5. El Meridiano se desactiva. Los legendarios no son botín. La distorsión de las balizas atrae a uno de ellos, que huye cuando el sistema cae.

### Coda y postgame

La Liga parece cerrar la historia. Al volver a Umbral, sin embargo, el mapa muestra nuevas rutas de encuentros y NPCs que ya no siguen sus horarios antiguos. Fede aparece en el laboratorio con un archivo incompleto. No pide perdón como atajo. Dice que quiere reparar el daño porque ahora sabe que no puede arreglarlo sólo con otro modelo.

El jugador desbloquea la Península del Velo, donde hay tres problemas derivados del Meridiano:

- Pokémon que quedaron habituados a una ruta artificial.
- Una baliza que sigue funcionando con energía residual.
- Un santuario que sólo puede leerse cuando la marea baja y el follower reacciona.

Al completar las tres cadenas, Fede desafía a Sofi en el **Combate sin Mapa**. Antes de la batalla entrega el módulo que permitía ver porcentajes de aparición y lo desactiva. La pelea no es una trampa. Es su forma de aceptar que no quiere conocer el resultado antes de jugarlo.

## 6. Fede como antagonista: comparación

| Tratamiento | Idea | Fortaleza | Debilidad | Uso del equipo | Veredicto |
|---|---|---|---|---|---|
| A. Arquitecto del Meridiano | Investigador que intenta estabilizar migraciones | Motivación concreta, conflicto jugable, recontextualiza el PokéGear y las rutas | Exige mostrar consecuencias sin convertirlo en monstruo | Pokémon de análisis, navegación y adaptación | Recomendado |
| B. Rival de optimización | Fede es un entrenador que cree que existe un equipo óptimo y quiere probarlo contra Sofi | Muy claro en batalla; relación directa con la protagonista | Puede sentirse pequeño para sostener toda la región | Equipo balanceado y calculador | Bueno como capa secundaria |
| C. Curador de un culto de la certeza | Dirige una organización que venera un patrón legendario | Gran iconografía y misterio | Se acerca demasiado al equipo malvado genérico | Pokémon con patrones, psíquicos y metálicos | No recomendado como núcleo |
| D. Falso villano | Parece responsable, pero otro actor usa su investigación | Permite un giro fuerte y un Fede más empático | Le quita agencia y puede diluir su aparición | Equipo incompleto, luego aliado | Sólo si Sofi quiere un tono más liviano |

### Por qué se recomienda A

Es la opción que convierte la personalidad de Fede en mecánica sin inventar biografía. Su antagonismo se puede ver en el mundo: encuentros alterados, atajos cerrados, horarios que fallan, registros del PokéGear y equipos que responden a patrones. También permite que el jugador lo admire antes de oponerse a él.

### Equipo tentativo de Fede

Los Pokémon son propuestas temáticas, no datos personales confirmados. Deben probarse contra el balance y contra lo que Fede realmente quiera representar.

| Etapa | Equipo tentativo | Función |
|---|---|---|
| Aparición aliada | Porygon, Magnemite | Investigación y señales; no debe ser una batalla difícil |
| Primer enfrentamiento | Porygon2, Magneton, Absol | Predicción, cálculo y advertencia |
| Antes del Observatorio | Metang, Manectric, Absol, Lanturn | Red eléctrica, navegación y cobertura |
| Final de campaña | Metagross, Manectric, Milotic, Absol, Flygon, Porygon2 | Equipo fuerte, flexible y todavía humano |
| Superboss | Metagross, Starmie, Milotic, Flygon, Absol, Deoxys forma base o Jirachi según la mitología elegida | No debe ser simplemente nivel alto; usa sets completos, objetos y cambios de ritmo |

La línea final no debe usar un legendario como trofeo de poder. Si Fede lleva uno en el superboss, debe ser porque el Pokémon eligió acompañarlo después de reparar el santuario, no porque lo capturó para activar el dispositivo.

### Diseño de la batalla final

La batalla de campaña tiene tres fases narrativas discretas:

1. **Patrón**: Fede abre con un Pokémon que castiga la estrategia más obvia.
2. **Ruido**: se activan campos o cambios de clima moderados que representan la inestabilidad de las balizas.
3. **Decisión**: al perder un Pokémon, Fede cambia de plan en lugar de seguir una secuencia fija.

El superboss usa equipos de nivel 58 a 62, IVs moderados, objetos y una IA que prioriza coherencia, no trampas. La dificultad debe provenir de sinergia y lectura, no de niveles absurdos.

## 7. Mitología y legendarios

### Mito central propuesto

El Litoral de Bruma conserva tres balizas construidas para **escuchar** el movimiento del mundo, no para controlarlo. Cada una está asociada a una función:

- **Marea**: movimiento y cambio.
- **Eco**: memoria y vínculo.
- **Cénit**: orientación y elección.

La mitología se apoya en Pokémon existentes, pero no necesita que uno sea el creador del universo. La mejor combinación inicial es:

- Latias y Latios como guardianes de rutas y señales, distribuidos como encuentros postgame.
- Jirachi como mito opcional del deseo formulado con honestidad, no como motor del villano.
- Celebi como encuentro de la Península del Velo, ligado a la reparación de una línea temporal local, no a un viaje temporal global.
- Deoxys como superboss o misterio de una señal externa en el observatorio, sólo si el arte y el presupuesto lo soportan.

Ho-Oh, Lugia, Rayquaza y el trío de Regis pueden aparecer como sidequests postgame independientes. No deben entrar todos en la campaña principal porque eso competiría por el mismo espacio mítico.

## 8. Distribución de los 493 Pokémon

### Regla de disponibilidad

Todos los Pokémon de Generaciones 1 a 4 son obtenibles en una partida. La mayoría aparece como captura, algunos como regalo, algunos por evolución y los legendarios mediante cadenas. No se requiere intercambio, otra versión, Mystery Gift, conexión online ni evento externo.

El objetivo es que el jugador descubra familias por ecosistema, no que vea 493 nombres en la primera hora. La Pokédex del juego debe informar "hábitat desconocido" y dar pistas por bioma, horario o sidequest.

### Presupuesto exacto por categoría

La división es disjunta y suma exactamente 493. “Ordinaria” significa cualquier especie que no sea legendaria ni mítica; una especie puede evolucionar después, pero se cuenta una sola vez en el método por el que se obtiene por primera vez.

| Categoría | Ordinarias | Legendarias/míticas | Total | Momento |
|---|---:|---:|---:|---|
| Prologue y primeras rutas | 45 | 0 | 45 | Antes de la Medalla 1 |
| Bosque, costa y Villa Salitre | 55 | 0 | 55 | Medallas 1-2 |
| Ciudad, humedal y cuevas iniciales | 65 | 0 | 65 | Medallas 2-3 |
| Puerto, faro y rutas de Surf | 75 | 0 | 75 | Medallas 3-4 |
| Cantera, observatorio bajo y rutas tardías | 35 | 0 | 35 | Medallas 4-6 |
| Liga y acceso inmediato al postgame | 25 | 0 | 25 | Final de campaña |
| Postgame de hábitats | 140 | 0 | 140 | Después de la Liga |
| Raros, regalos, swarms y cadenas | 18 | 0 | 18 | Variable, siempre recuperable |
| Legendarios y míticos Gen 1-3 | 0 | 21 | 21 | Principal y postgame |
| Legendarios y míticos Gen 4 | 0 | 14 | 14 | Postgame |
| **Total** | **458** | **35** | **493** | **Una única partida** |

Las seis primeras filas suman 300 especies ordinarias de Gen 1-3. El postgame añade 158 ordinarias: 47 especies Gen 1-3, 18 especies raras de Gen 1-3 y las 93 especies ordinarias de Gen 4. Las 35 legendarias/míticas completan el total: 21 de Gen 1-3 y 14 de Gen 4.

La campaña no introduce Gen 4 como una región separada. El jugador termina la Liga con 300 especies ordinarias posibles de Gen 1-3 y descubre después que la alteración del Meridiano abrió rutas ecológicas para las 107 especies #387-493.

### Distribución por familias

- No colocar una cadena evolutiva completa en la misma ruta si su evolución requiere un objeto o amistad. Eso reduce el sentido de criar y explorar.
- Cada starter y sus evoluciones deben poder obtenerse por una combinación de elección inicial, sidequest y huevo regalo.
- Cada especie de baja potencia debe tener un lugar temprano, un movimiento útil o una recompensa de amistad. No se reserva todo lo interesante para pseudo-legendarios.
- Las especies de Gen 1-3 deben mezclarse por bioma. La región no debe tener una zona de Gen 1, otra de Gen 2, otra de Gen 3 ni otra de Gen 4.
- Las 93 especies ordinarias de Gen 4 se reparten entre cuatro hábitats postgame y cadenas de obtención; no se apilan todas en una ruta final.
- Los encuentros raros no pueden depender de una sola hora. Si aparece de noche, también existe una ruta de recompensa alternativa en una sidequest.

### Legendarios y míticos: 35

El conjunto completo de especies legendarias y míticas de las cuatro generaciones debe estar disponible. Se agrupan así:

- Campaña: dos encuentros de navegación u observatorio que pueden ser vistos, pero cuya captura queda para después de la Liga.
- Postgame inmediato: tres aves, tres perros y el trío de Regis mediante cadenas de 20 a 30 minutos cada una.
- Postgame avanzado Gen 1-3: Ho-Oh, Lugia, Latias, Latios, Kyogre, Groudon, Rayquaza, Jirachi, Celebi, Mew, Mewtwo y Deoxys, con requisitos independientes.
- Postgame Gen 4: Uxie, Mesprit, Azelf, Dialga, Palkia, Heatran, Regigigas, Giratina, Cresselia, Manaphy, Phione, Darkrai, Shaymin y Arceus. Sus cadenas usan ruinas, mareas, meteoritos y registros del Meridiano, no localizaciones de Sinnoh.

La lista de especies está fija por el alcance confirmado; queda abierta sólo la asignación final de algunos santuarios y el tono de cada cadena. Ningún legendario es la llave única para terminar la campaña.

### Obtención de las 107 especies Gen 4

Las 107 especies #387-493 se obtienen sin intercambio, sin otra versión y sin conexión externa. Los 93 Pokémon ordinarios de Gen 4 se dividen en cuatro grupos disjuntos por su primer método de obtención:

| Método de primera obtención | Cantidad | Diseño de acceso |
|---|---:|---|
| Encuentro salvaje en hábitats postgame | 52 | Península del Velo, humedal profundo, cantera reabierta y costa de marea baja |
| Regalo, huevo o rescate | 18 | NPCs de cadenas de reparación, laboratorio y santuario; siempre recuperables |
| Evolución sin intercambio | 15 | Evoluciones por nivel, amistad, movimiento, piedra, zona o ciclo horario |
| Swarms, pesca rara y cadenas de exploración | 8 | Rumores de Brújula, eventos semanales y pistas del follower |
| **Total ordinario Gen 4** | **93** | **Postgame, sin contenido externo** |

Las 14 especies legendarias/míticas de Gen 4 se obtienen en cadenas independientes: el trío de los lagos, Dialga/Palkia/Giratina, Heatran, Regigigas, Cresselia, Manaphy/Phione, Darkrai, Shaymin y Arceus. Las cadenas se distribuyen entre ruinas, meteoritos, mareas y archivos del Meridiano para que no parezcan una visita tardía a Sinnoh.

Reglas para eliminar intercambios evolutivos:

- `Cable de Enlace` reemplaza las evoluciones que normalmente requieren intercambio.
- `Núcleo de Meridiano` reemplaza los objetos o condiciones de evolución que serían imposibles sin otra versión.
- Las evoluciones por amistad, horario, movimiento y ubicación siguen existiendo, pero la Pokédex da una pista recuperable.
- Porygon y sus evoluciones usan una cadena de laboratorio; Clamperl usa dos objetos obtenibles; Feebas usa una actividad de pesca; Tyrogue y las familias de amistad se resuelven mediante entrenamiento y tiempo.
- Las especies bebé que normalmente dependerían de crianza se entregan como huevos o se habilitan por una cadena de cuidado. No se exige encontrar un padre específico en otra partida.

El registro de cobertura debe listar, para cada especie, método primario, método alternativo, requisito, flag, zona y prueba de recuperación. Un Pokémon no cuenta como obtenible si puede aparecer en teoría pero su método depende de una fecha única, un intercambio o un evento de distribución.

### Cómo preservar el descubrimiento

- La Pokédex muestra silueta, bioma y una pista de horario, no un marcador GPS inmediato.
- Los NPCs usan lenguaje ecológico: "se oye un zumbido en los juncos" o "las huellas aparecen cuando baja la marea".
- El PokéGear registra rumores encontrados, no coordenadas exactas.
- Un mapa de hábitats se completa al hablar, capturar y observar al follower.
- Los swarms se anuncian por radio y por NPCs móviles.
- La completitud se verifica internamente con una tabla de cobertura, no con la obligación de que el jugador haga una lista externa.

## 9. Sistemas

### Follower Pokémon

P0 desde el inicio. El Pokémon líder sigue al jugador, sale del lado de la batalla y puede reaccionar en puntos predefinidos. Reglas:

- 493 especies válidas.
- Cinco escalas de colisión: diminuto, pequeño, humano, grande y enorme.
- Si una especie grande no cabe, se guarda en la Poké Ball durante bicicleta, interiores estrechos o escenas técnicas, con una línea explicativa.
- Interacción básica con estado de HP, amistad y horario.
- 20 puntos de reacción especiales en campaña y 12 en postgame, 32 en total.
- El follower nunca bloquea un warp, un puzzle o una captura.

#### Clases de representación

Las 493 especies deben tener una representación propia, pero no 493 pipelines artísticos distintos:

| Clase | Uso | Requisito |
|---|---|---|
| XS | bebés, insectos y criaturas muy pequeñas | desplazamiento corto, colisión de un tile y sprite legible |
| S | cuadrúpedos y aves pequeñas | seguimiento estándar y giro de cuatro direcciones |
| M | escala humana o similar | seguimiento estándar, interacción frontal y entrada a interiores |
| L | especies grandes | separación mínima del jugador y bloqueo sólo en puertas estrechas |
| XL | especies enormes o serpenteantes | sprite reducido o sombra de acompañamiento; fallback seguro en espacios estrechos |

Cada especie recibe una clave de escala y un asset específico. El tier de producción es de dos frames de movimiento y una sombra; sólo 32 reacciones usan animación o poses adicionales. Si falta el asset animado, el fallback es un sprite estático específico de esa especie con la misma colisión, nunca una especie genérica ni un crash. El validador debe comprobar que cada una de las 493 claves tiene escala, sprite, icono, sombra y fallback.

### PokéGear equivalente: Brújula

Nombre de trabajo: **Brújula**. Es una interfaz de cuatro módulos:

1. mapa y notas;
2. mensajes y llamadas;
3. radio de rumores;
4. registro de señales del Meridiano.

La cuarta pestaña se va corrompiendo de forma visible mientras avanza la historia. Es una pista narrativa que también sirve para orientar al jugador. En postgame registra las 107 especies Gen 4 como migraciones de hábitat, no como una Pokédex separada.

### Combate y dificultad

- Mecánicas base cercanas a Gen 4 o una generación posterior estable, decididas en la prueba técnica del engine.
- Sets de líderes con una idea clara, pero sin IA competitiva total en la campaña.
- El modo recomendado mantiene experiencia cómoda, objetos disponibles y guardado frecuente.
- Un modo difícil opcional añade mejores sets, menos regalos y escalado de rematches, pero no altera la historia.
- Curva de niveles propuesta: 13-15, 18-20, 24-26, 29-31, 35-37, 40-44, Fede 45-47, superboss 58-62.
- Los líderes no deben repetir siempre el tipo como único chiste. Cada gimnasio representa una relación con el mundo: conservación, adaptación, navegación, presión, resistencia y elección.

### Economía

- Dinero suficiente para curación y algunas Poké Balls sin grind obligatorio.
- Los objetos de captura y antídotos se desbloquean por disponibilidad, no por rareza artificial.
- Las recompensas de sidequest son objetos, movimientos, huevos y acceso, no sólo dinero.
- El mercado raro semanal vende dos objetos útiles y un objeto cosmético. No vende un legendario ni un requisito único.

### Rematches

Después de la Liga, cada líder recibe un segundo equipo de seis con niveles 52-55 y una regla temática. Las rematches se activan por Brújula y aparecen en horarios distintos. El jugador puede completar todas en una única partida.

### Actividades secundarias

P1, con una actividad profunda y tres cadenas:

- **Ruta de mareas**: carrera corta con follower, atajos dependientes de horario.
- **Archivo de Nahue**: registrar especies de las primeras tres generaciones mediante observación, captura o evolución; las especies Gen 4 se incorporan después como un apéndice de migraciones.
- **Faro sin luz**: reparar una cadena de lámparas, con encuentros nocturnos.
- **Caminantes de Vértice**: rematches y rumores según la ubicación de NPCs.

No se construye un Pokéathlon completo en la primera versión. Puede existir una prueba mínima de tres eventos sólo después de validar el slice.

## 10. Investigación comparativa y decisiones técnicas

### Qué se toma de HGSS

Hecho documentado: el manual oficial de HeartGold describe una región recorrida con la cooperación de los Pokémon, un PokéGear con teléfono, mapa y radio, programas de radio que cambian por horario y lugar, y eventos dependientes del reloj. También documenta Safari Zone, áreas con encuentros diferentes y un personalizador que altera las especies presentes. El diseño propuesto traduce esos principios a un alcance menor, sin copiar Johto ni sus personajes. Fuente: [manual oficial de Pokémon HeartGold](https://csassets.nintendo.com/noaext/image/private/t_KA_PDF/DS_Pokemon_HeartGold), especialmente las páginas 3, 5 y 8.

Hecho documentado por una referencia secundaria especializada: HGSS permite que el Pokémon líder camine con el jugador durante gran parte del juego y ofrece interacciones que pueden variar por especie, ubicación, clima, amistad, estado y hora. La propuesta usa esto como criterio para reacciones puntuales, no promete 493 líneas únicas. Fuente: [Walking Pokémon, Bulbapedia](https://bulbapedia.bulbagarden.net/wiki/Following_Pokemon).

Interpretación de diseño: lo que hace que HGSS se sienta especial no es sumar sistemas aislados, sino conectar viaje, reloj, follower, lugares con identidad y una segunda capa de exploración. Por eso Bruma prioriza esos cinco elementos y descarta una segunda región completa.

### Comparación de fangames

Hecho documentado: Pokémon Insurgence presenta una región propia, especies Delta, Secret Bases, personalización, dificultades y un endgame con quests y lugares. Pokémon Uranium presenta una región nueva, más de 150 Pokémon originales y un tipo Nuclear. Estos ejemplos muestran dos estrategias distintas: ampliar el lenguaje de Pokémon con nuevas especies y sistemas, o construir una aventura completa alrededor de una identidad propia. Fuentes: [sitio oficial de Pokémon Insurgence](https://p-insurgence.com/) y [sitio de Pokémon Uranium](https://pokemonuranium.co/).

Interpretación de diseño: Sofi ya tiene una restricción valiosa, los 493 Pokémon de Gen 1-4. Agregar Fakemon, tipos nuevos o variantes Delta competiría con esa promesa y con el presupuesto de follower. La identidad debe venir de región, ritmo, misterio y consecuencias, no de una tercera Pokédex.

### Engine recomendado

La recomendación provisional es **Pokémon Essentials v21.1 sobre RPG Maker XP**, sometido a una prueba técnica antes de comprometerse. Su repositorio oficial lo describe como un proyecto de RPG Maker XP muy modificado para funcionar como juego Pokémon, no como proyecto completo independiente, y mantiene scripts separados en archivos Ruby, lo que favorece versionado y automatización. Fuente: [repositorio oficial de Pokémon Essentials](https://github.com/Maruno17/pokemon-essentials).

Costos y riesgos documentados: el entorno depende de RPG Maker XP para editar mapas y eventos; la automatización de mapas no será tan limpia como editar datos de un engine propio. La documentación de un kit basado en Essentials señala esa dependencia del editor para mapas, eventos y tilesets. Fuente: [guía de Pokémon Essentials MMO Kit](https://github.com/SamDreamsMaker/pokemon-essentials-mmo-kit/blob/master/docs/GETTING-STARTED.md). Ese kit no es una recomendación de usar MMO; sólo aporta evidencia sobre el flujo de herramientas.

Alternativas:

- Godot propio: mejor control programático y packaging, pero hay que rehacer combate, evolución, datos, UI, guardado, follower y tooling.
- Pokémon Essentials: mayor cobertura base y mejor alineación con la experiencia objetivo, a cambio de editor y Ruby.
- Essentials en MV u otros forks: no se eligen sin una prueba porque la compatibilidad, documentación y madurez son menos seguras para este alcance.

Gate técnico de 2 a 4 días:

1. cargar 493 especies sin errores;
2. generar un mapa desde datos o al menos validar warps automáticamente;
3. hacer seguir al jugador a seis escalas distintas;
4. cambiar hora y encuentros;
5. ejecutar una batalla, captura y guardado;
6. correr un smoke test desde un checkpoint.

Si Essentials pasa cinco de seis sin workaround frágil, se adopta. Si falla follower o datos, se hace una spike de Godot de una semana antes de decidir. No se empieza por construir el juego completo en Godot por preferencia abstracta.

## 11. Vertical slice recomendado

### Slice de 12 a 15 minutos

El slice se llama **El sonido del canal**.

#### Mapa mínimo

- Casa de Sofi, 1 pantalla.
- Laboratorio de Umbral, 1 pantalla.
- Pueblo Umbral exterior, 2 pantallas.
- Ruta del Canal, 3 pantallas.
- Estación vieja, 1 interior.

#### Contenido

1. Elegir un starter entre tres opciones de Gen 1-3.
2. Caminar con el starter durante al menos dos minutos.
3. Hablar con el follower junto al agua y obtener una reacción contextual.
4. Recibir la Pokédex y la Brújula.
5. Capturar una especie salvaje en la Ruta del Canal.
6. Pelear contra dos entrenadores y una batalla tutorial corta.
7. Entrar a la estación vieja y encontrar una baliza apagada.
8. Cambiar manualmente de día a noche mediante un menú de debug, sin depender del reloj real.
9. Ver un cambio de encuentro y de iluminación.
10. Encontrar una nota firmada "F.". La referencia personal es sutil y no explica quién es.

El slice no fuerza la aparición de Gen 4 en los primeros quince minutos. La decisión es deliberada: la primera experiencia conserva la nostalgia de Oro/Gen 2 y el test de datos, ejecutado sobre la misma build, verifica que las 493 especies y sus métodos de obtención estén cargados antes de producir el postgame.

#### Assets mínimos

- 1 sprite de Sofi sujeto a aprobación.
- 3 starters con front, back e icono.
- 6 follower sprites representativos de escala.
- 1 tileset de pueblo, 1 de costa y 1 de estación.
- 6 NPCs, de los cuales 2 son nombrados.
- 3 retratos opcionales.
- 2 piezas de música, con variante nocturna.
- 1 animación o efecto de baliza.

#### Criterios de aceptación

- Un jugador nuevo llega al objetivo sin instrucciones externas.
- El follower nunca se separa, atraviesa paredes ni bloquea una puerta.
- Captura, experiencia, curación, guardado y carga funcionan.
- El cambio día/noche ocurre en menos de un segundo desde debug y conserva flags.
- La reacción del follower se entiende sin texto técnico.
- La nota "F." genera curiosidad pero no roba el foco.
- La base contiene las 493 especies; un test de cobertura falla si falta una especie, evolución, método primario o fallback.
- El slice se puede repetir tres veces sin crash.
- Un test automatizado confirma que todos los warps apuntan a mapas válidos.
- El playtest produce al menos una observación accionable de ritmo, legibilidad y afecto por el follower.

No se produce el Acto I completo hasta que el slice cumple estos criterios en una build limpia.

## 12. Roadmap de producción

### Fase 0: decisiones y control de scope

Entregables:

- este GDD revisado;
- matriz de decisiones pendientes;
- lista de datos personales confirmados, prohibidos y todavía vacíos;
- definición de engine provisional;
- tabla de cobertura de 493 especies, con método primario y alternativo por especie.

Dependencias: aprobación de Fede y Sofi sobre tono, nombres y límites de referencias.

### Fase 1: spike técnica

Entregables:

- proyecto base versionado;
- carga de especies;
- follower mínimo;
- día/noche;
- mapa y eventos;
- captura y guardado;
- primera batería de validadores.

Gate: el vertical slice debe ser realizable sin editar binarios manualmente.

### Fase 2: vertical slice

Entregables:

- 12 a 15 minutos jugables;
- arte temporal coherente;
- dos músicas;
- primera reacción contextual;
- reporte de playtest.

Gate: no expandir por entusiasmo si el slice no demuestra la relación entre caminar, follower, misterio y captura.

### Fase 3: campaña base

Entregables:

- Umbral a Ciudad Vértice;
- tres primeras medallas;
- 165 especies accesibles;
- Brújula completa;
- primera revelación de Meridiano;
- rematches simples opcionales.

### Fase 4: campaña final

Entregables:

- Humedal, Puerto, Cuenca y Observatorio;
- seis medallas;
- Liga;
- 300 especies ordinarias de Gen 1-3 cubiertas;
- Fede final de campaña;
- flags y consecuencias auditadas.

### Fase 5: postgame

Entregables:

- Península del Velo;
- 140 especies ordinarias de hábitat;
- 18 especies ordinarias raras, regalos, swarms y cadenas;
- 35 legendarios y míticos, con caminos mínimos P0 y cadenas completas P1/P2;
- 107 especies Gen 4 auditadas como obtenibles sin intercambio ni contenido externo;
- rematches completas;
- superboss de Fede;
- archivos de registro y final de reparación.

### Fase 6: polish y QA

Entregables:

- pruebas de cobertura de Pokédex;
- smoke tests de checkpoints;
- auditoría de flags y warps;
- revisión de dificultad;
- revisión narrativa independiente;
- revisión visual y de legibilidad;
- build limpia y changelog.

No se declara release-ready con screenshots o validaciones aisladas. Hace falta un playthrough completo a velocidad normal de la build candidata, con imagen, audio, checksum y registro de versión.

## 13. Riesgos

| Riesgo | Señal temprana | Mitigación |
|---|---|---|
| 493 followers consumen todo el tiempo | Cada especie requiere sprite manual único | Cinco escalas base, pipeline automático, fallback por tamaño y sólo 32 reacciones especiales |
| La trama de Fede se vuelve sermón | Escenas largas sin acción | Cada revelación debe cambiar un mapa, encuentro o combate |
| Referencias personales incómodas | Se escriben chistes antes de tener datos | Mantener un archivo LORE aprobado y placeholders explícitos |
| Scope de HGSS imposible | Se intenta replicar Kanto, Safari, Pokéathlon y Battle Frontier | Elegir principios, no inventario de features |
| Engine difícil de automatizar | Cambios sólo editables desde GUI | Datos declarativos, scripts separados y smoke tests desde temprano |
| Postgame vacío | Sólo hay rematches y capturas | Diseñar las consecuencias de Meridiano desde el Acto II |
| Dificultad inconsistente | El jugador sube niveles por encuentros abundantes | Curva de niveles, sets y pruebas de ruta documentados |
| Mundo demasiado lineal | Cada mapa sólo conecta el siguiente gimnasio | Volver a hubs, rutas de marea y sidequests con estados |

## 14. Decisiones pendientes para Fede y Sofi

Estas preguntas no se resuelven arbitrariamente:

1. ¿Sofi quiere que Fede sea reconocible desde temprano o que el nombre se revele tarde?
2. ¿El tono de Fede debe ser más inquietante, más divertido o equilibrado?
3. ¿La derrota de Fede debe permitir una redención parcial, una responsabilidad sin reconciliación o una ambigüedad abierta?
4. ¿Sofi tiene Pokémon favoritos que deban ocupar un lugar mítico, ser starter, follower especial o miembro del equipo de Fede?
5. ¿Qué referencias personales están autorizadas? Hace falta separar nombres, lugares, anécdotas, objetos, mascotas y chistes internos.
6. ¿Se quiere una región completamente ficticia, una región con clima costero genérico o una inspiración geográfica real? No se debe asumir Mar del Plata.
7. ¿El jugador protagonista debe tener apariencia, género y nombre definidos o personalizables?
8. ¿Se acepta un modo difícil opcional o se prioriza una experiencia única y controlada?
9. ¿Los legendarios deben ser capturables en la primera partida sin postgame, o se prefiere reservar la mayoría para después de la Liga?
10. ¿La primera build se mantendrá privada? Pokémon Essentials y los assets derivados de Nintendo requieren revisar las condiciones de uso antes de cualquier distribución pública.

## Cierre

La apuesta más fuerte es que el jugador recuerde tres cosas: un Pokémon que lo acompañó de verdad, un lugar al que quiso volver y el momento en que entendió que Fede no estaba intentando conquistar la región, sino impedir que cambiara.

El siguiente paso correcto no es dibujar toda la región ni escribir los 493 encuentros. Es aprobar el tratamiento de Fede, reunir el LORE personal autorizado y construir el slice de El sonido del canal con el baseline de datos completo. Si ese tramo se siente como una aventura Pokémon y no como una demo de sistemas, el resto del juego tiene una base defendible.
