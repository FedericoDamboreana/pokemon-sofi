# Proyecto: juego Pokémon personalizado para Sofi

## 1. Objetivo general

Crear un fangame personalizado de Pokémon para Sofi, desarrollado con fuerte asistencia de Codex y subagentes especializados.

La intención no es hacer simplemente un "Pokémon retro", sino un juego original que capture especialmente la sensación de **Pokémon HeartGold / SoulSilver**, ya que **Pokémon HeartGold es el juego favorito de Sofi**.

El juego debe sentirse como una aventura Pokémon real, no como una demo técnica o una sucesión de referencias personales.

Las referencias a Sofi, Fede, Nahue y otras personas/lugares reales deberían integrarse de forma progresiva, natural y, cuando corresponda, sorpresiva.

---

## 2. Contexto personal relevante

### Sofi

- Su juego favorito de Pokémon es **Pokémon HeartGold**.
- Por lo tanto, HeartGold debe ser la referencia principal para:
  - sensación de aventura;
  - estructura del mundo;
  - exploración;
  - estética;
  - relación con los Pokémon;
  - contenido secundario;
  - postgame;
  - ritmo general.

### Nahue

- Le encantan especialmente las **primeras tres generaciones de Pokémon**.
- Esto llevó a definir que el juego debería incluir **todos los Pokémon de Generación 1, 2 y 3**.

### Fede

- Fede quiere aparecer dentro del juego.
- Surgió la idea de que **Fede sea un villano o antagonista**.
- Esta idea gusta y debería ser explorada seriamente en la trama.
- No está definido todavía:
  - si será el villano principal;
  - un antagonista recurrente;
  - un falso villano;
  - un rival;
  - un líder de una organización;
  - un personaje con motivaciones ambiguas;
  - o una combinación de varias de estas ideas.
- Es importante que los subagentes de narrativa investiguen y propongan alternativas antes de cerrar esta decisión.

---

## 3. Pokédex

### Alcance

El juego debería contener los **386 Pokémon de las primeras tres generaciones**, es decir:

- Generación 1: #001 Bulbasaur a #151 Mew
- Generación 2: #152 Chikorita a #251 Celebi
- Generación 3: #252 Treecko a #386 Deoxys

### Filosofía

Los 386 Pokémon deberían poder obtenerse en una única partida.

Evitar, salvo que exista una excelente razón narrativa:

- version exclusives;
- necesidad de intercambios externos;
- contenido inaccesible sin otro juego;
- mecánicas que hagan imposible completar la Pokédex jugando normalmente.

### Distribución sugerida

No mostrar los 386 desde el comienzo.

Una posible estructura:

- ~180 Pokémon disponibles durante la aventura principal;
- ~100 adicionales desbloqueados en el postgame;
- ~60 mediante zonas especiales, swarms, eventos o sidequests;
- legendarios, míticos y encuentros especiales distribuidos cuidadosamente.

La intención es preservar el descubrimiento durante toda la partida.

---

## 4. Referencia principal: Pokémon HeartGold

El juego debe tomar como inspiración a HeartGold / SoulSilver más por sus **principios de diseño** que por copiar contenido directamente.

### 4.1. Pokémon siguiendo al jugador

Feature de prioridad máxima.

El primer Pokémon del equipo debería poder seguir al jugador por el mapa.

Idealmente:

- cualquier Pokémon de los 386 puede seguir al jugador;
- diferentes sprites según especie;
- interacción contextual;
- pequeñas reacciones dependiendo de:
  - ubicación;
  - clima;
  - hora;
  - amistad;
  - estado de la historia;
  - especie.

Ejemplo:

> Mudkip está mirando fijamente el mar.  
> Parece querer meterse al agua.

Se pueden agregar eventos especiales para que determinados Pokémon tengan reacciones únicas en momentos importantes de la historia.

---

## 5. Sensación de mundo vivo

HeartGold transmite que el mundo existe independientemente del jugador.

El fangame debería buscar esa misma sensación mediante:

- ciclo día/noche;
- encuentros Pokémon diferentes por horario;
- NPCs que cambian de ubicación;
- eventos en determinados días;
- eventos semanales;
- tiendas o comerciantes especiales;
- llamadas, mensajes o sistema equivalente al PokéGear;
- rematches;
- secretos nocturnos;
- eventos que sólo suceden bajo determinadas condiciones.

No es necesario replicar los horarios exactos de HeartGold.

La prioridad es replicar la sensación de que el mundo cambia.

---

## 6. Exploración

La región debe ser relativamente compacta pero densa.

Preferimos:

> 8 horas excelentes con lugares memorables

antes que:

> 25 horas con rutas genéricas y contenido de relleno.

### Objetivo tentativo de duración

- Historia principal: aproximadamente 5 a 8 horas.
- Postgame: significativo.
- Sidequests y secretos: suficientes para extender considerablemente la experiencia.

Esto es un objetivo inicial, no una restricción rígida.

### Filosofía de mapas

Evitar una estructura excesivamente lineal de:

> pueblo → ruta → gimnasio → ruta → gimnasio.

Crear lugares memorables con identidad propia.

Inspiración conceptual de HeartGold:

- Ecruteak City;
- Goldenrod City;
- Ruins of Alph;
- Lake of Rage;
- Burned Tower;
- National Park;
- Mt. Silver.

La nueva región debería tener equivalentes en términos de impacto y personalidad, no copias directas.

---

## 7. Estructura de aventura y postgame

HeartGold tiene una de sus características más memorables en la enorme expansión posterior a la Liga.

No es necesario construir literalmente dos regiones completas, pero sí debería existir un momento donde el jugador crea que la aventura está terminando y descubra una cantidad considerable de contenido adicional.

### Posible estructura

#### Acto 1

- región principal;
- gimnasios;
- trama central;
- Liga Pokémon;
- aparente conclusión.

#### Acto 2 / postgame

- nueva zona o subregión;
- nuevos Pokémon disponibles;
- nuevos desafíos;
- rematches;
- sidequests;
- misterios;
- legendarios;
- enfrentamientos especiales.

### Superboss

HeartGold culmina memorablemente con Red en Mt. Silver.

El fangame debería tener un equivalente.

Existe una posibilidad especialmente atractiva:

- Fede como antagonista durante la historia;
- o Fede como personaje ambiguo;
- y eventualmente un enfrentamiento final o secreto extremadamente difícil contra él.

No cerrar esto todavía. Investigar alternativas narrativas.

---

## 8. Historia y tono

La historia no debería depender constantemente de una amenaza de destrucción mundial.

El tono buscado se parece más a:

- aventura;
- misterio;
- humor;
- descubrimiento;
- personajes;
- pequeños momentos emotivos;
- mitología Pokémon;
- sensación de viaje.

Puede existir una organización antagonista o conflicto serio, pero el jugador también debería tener tiempo para simplemente recorrer el mundo junto a sus Pokémon.

---

## 9. Fede como villano / antagonista

Esta dirección creativa debe investigarse en profundidad.

La gracia está en que Sofi eventualmente descubra que Fede forma parte importante del juego.

### Posibilidades a explorar

- Fede es el líder secreto de una organización antagonista.
- Fede aparece inicialmente como aliado.
- Fede es un rival recurrente.
- Fede parece villano, pero tiene una motivación legítima.
- Fede es manipulador pero no completamente malvado.
- Fede tiene una obsesión relacionada con un Pokémon legendario.
- Fede busca alterar algún aspecto del mundo Pokémon por una razón aparentemente razonable.
- Fede es un falso villano y existe otro antagonista.
- Fede es el villano principal durante la campaña y luego un superboss opcional.
- Fede desaparece tras el final y reaparece en el postgame como el entrenador más fuerte.

### Requisito narrativo

Evitar una interpretación demasiado obvia o caricaturesca.

Queremos un personaje divertido y memorable, pero con suficiente profundidad para que funcione incluso más allá del chiste personal.

---

## 10. Referencias personales

Las referencias personales deben aparecer progresivamente.

No comenzar el juego saturándolo de nombres y chistes internos.

### Posible progresión

#### Etapa 1

Parece un fangame Pokémon normal.

#### Etapa 2

Aparecen pequeñas coincidencias:

- nombres conocidos;
- lugares familiares;
- objetos;
- frases;
- NPCs secundarios.

#### Etapa 3

Las referencias se vuelven inequívocas.

#### Etapa 4

La relación entre el mundo del juego y Sofi/Fede/Nahue pasa a formar parte importante de la experiencia.

### Archivo futuro recomendado

Crear:

`design/LORE.md`

Con información estructurada sobre:

- Sofi;
- Fede;
- Nahue;
- amigos;
- mascotas;
- lugares;
- anécdotas;
- chistes internos;
- gustos;
- momentos importantes;
- referencias que sí deben aparecer;
- referencias que deben evitarse.

No inventar contenido personal que no exista en este archivo.

---

## 11. Legendarios y mitología

La región debe tener mitología propia.

HeartGold integra Ho-Oh, Lugia, las torres, las Kimono Girls y la historia de Johto dentro del mundo.

El nuevo juego debería hacer algo similar utilizando Pokémon existentes de Generaciones 1-3.

No es necesario crear Fakemon.

### Posibilidades

Elegir uno o varios Pokémon como ejes de la mitología:

- Celebi;
- Jirachi;
- Latias / Latios;
- Rayquaza;
- Suicune;
- Ho-Oh;
- Lugia;
- Mew;
- Deoxys;
- otros.

La elección debería estar motivada por la trama y, si es posible, por preferencias reales de Sofi.

---

## 12. Contenido secundario

HeartGold tiene muchísimo contenido que no está directamente relacionado con avanzar al siguiente gimnasio.

El fangame debería incluir varias actividades opcionales.

No es obligatorio replicar el Pokéathlon.

### Ideas

- concurso de pesca;
- Bug-Catching Contest o equivalente;
- carreras de Pokémon;
- Safari Zone o área especial;
- búsqueda de objetos;
- torneos;
- minijuegos;
- arcade;
- cocina;
- crafting sencillo;
- NPCs con cadenas de sidequests;
- swarms;
- eventos semanales;
- secretos;
- Pokémon regalo;
- encuentros raros;
- rematches.

La prioridad es diversidad y sorpresa, no cantidad.

---

## 13. Estética

### Dirección visual

No apuntar a Game Boy Color.

La referencia visual debería ser:

> Pokémon HeartGold / SoulSilver, era Nintendo DS / Generación 4.

Aunque el Pokédex termine en Generación 3.

### Elementos

- pixel art estilo DS;
- sprites de batalla acordes;
- overworld detallado;
- interiores ricos en detalles;
- follower sprites;
- UI inspirada en HGSS;
- animaciones simples;
- música con una identidad compatible con la era DS.

No copiar necesariamente la interfaz píxel por píxel.

El objetivo es generar familiaridad.

---

## 14. Assets

Se propone una estrategia híbrida.

### Pokémon existentes

Utilizar sprites existentes cuando sea razonable:

- front sprites;
- back sprites;
- iconos;
- follower sprites;
- cries.

### Assets personalizados

Generar específicamente:

- Sofi como entrenadora;
- Fede;
- Nahue;
- otros personajes;
- NPCs;
- edificios;
- lugares;
- objetos;
- carteles;
- portraits;
- elementos ambientales.

### Pipeline sugerido

En lugar de depender exclusivamente de una herramienta visual manual, Codex debería poder usar scripts especializados.

Ejemplo:

```text
/tools
  create_sprite.py
  recolor_sprite.py
  compose_sprite_sheet.py
  validate_assets.py
  generate_tileset_element.py
```

Posibles interfaces:

```text
generate_character_sprite
generate_pokemon_sprite
generate_portrait
generate_tileset_element
generate_item_icon
compose_sprite_sheet
```

Los scripts deberían validar automáticamente:

- dimensiones;
- paleta;
- transparencia;
- formato;
- sprite sheets;
- compatibilidad con el engine.

---

## 15. Engine

La opción inicialmente considerada es **Pokémon Essentials**, por proveer gran parte del comportamiento base de un juego Pokémon:

- combate;
- party;
- tipos;
- movimientos;
- evoluciones;
- inventario;
- NPCs;
- encuentros salvajes;
- entrenadores;
- mapas;
- eventos;
- estados;
- experiencia;
- PC;
- etc.

Sin embargo, Codex y sus subagentes deberían **evaluar la opción técnica antes de comprometerse**.

Comparar al menos:

- Pokémon Essentials;
- motores open source orientados a Pokémon;
- implementación propia en Godot;
- implementación propia en otro engine si existe una ventaja clara.

### Criterios de evaluación

- capacidad de automatización por agentes;
- facilidad para modificar mapas programáticamente;
- soporte para follower Pokémon;
- compatibilidad con 386 especies;
- battle engine;
- scripting;
- packaging;
- testing automatizado;
- documentación;
- mantenimiento;
- integración con generación automática de assets.

La prioridad no es usar una tecnología específica. Es maximizar la capacidad de Codex de construir y mantener el juego autónomamente.

---

## 16. Arquitectura de trabajo con Codex

Codex debería comportarse como un pequeño estudio de videojuegos.

No intentar generar el juego completo en un único paso.

### Subagentes sugeridos

#### Game director

Responsable de mantener coherencia global.

#### Narrative designer

Investiga y desarrolla:

- trama;
- Fede como antagonista;
- personajes;
- tono;
- misterios;
- estructura narrativa.

#### Pokémon / systems designer

Responsable de:

- progresión;
- niveles;
- encounters;
- balance;
- gimnasios;
- Pokédex;
- movesets;
- economía.

#### World designer

Responsable de:

- región;
- ciudades;
- rutas;
- landmarks;
- exploración;
- gating;
- postgame.

#### HeartGold researcher

Analiza específicamente:

- estructura de HGSS;
- features;
- pacing;
- mapa;
- eventos;
- postgame;
- sistemas secundarios;
- UX;
- qué hace que se sienta distinto a otros Pokémon.

Debe separar:

- features esenciales;
- features valiosas;
- features prescindibles;
- cosas que envejecieron mal.

#### Technical lead

Evalúa engine y arquitectura.

#### Asset pipeline engineer

Diseña tooling para sprites, tilesets y assets.

#### QA agent

Automatiza validaciones y playthroughs.

---

## 17. Metodología recomendada

### Fase 1: investigación

Antes de programar:

1. estudiar HeartGold / SoulSilver;
2. estudiar fangames similares;
3. evaluar engines;
4. estudiar toolchains para mapas y sprites;
5. investigar automatización del engine elegido.

### Fase 2: Game Design Document

Crear:

- `GAME_DESIGN.md`
- `STORY.md`
- `WORLD.md`
- `CHARACTERS.md`
- `POKEDEX.md`
- `SYSTEMS.md`
- `TECHNICAL_DESIGN.md`

### Fase 3: vertical slice

Crear aproximadamente 10-20 minutos de juego.

Debe incluir:

- caminar;
- diálogo;
- combate;
- captura;
- follower;
- interiores;
- transición día/noche;
- un evento narrativo;
- al menos una referencia personal sutil.

No expandir el juego hasta que este slice funcione correctamente.

### Fase 4

Construir Acto 1.

### Fase 5

Liga y climax.

### Fase 6

Postgame.

### Fase 7

Polish y QA.

---

## 18. Testing

Automatizar todo lo posible.

### Validaciones estáticas

- mapas conectados;
- warp destinations válidos;
- encuentros posibles;
- especies existentes;
- trainers válidos;
- movimientos válidos;
- evoluciones válidas;
- items válidos;
- assets con dimensiones correctas;
- referencias de scripts válidas.

### QA dinámico

Idealmente desarrollar tooling que permita:

- mover al jugador automáticamente;
- iniciar combates;
- completar diálogos;
- teletransportarse entre checkpoints;
- validar flags;
- capturar screenshots;
- leer logs;
- detectar crashes;
- ejecutar smoke tests.

---

## 19. Principios de diseño

1. Primero debe ser un buen juego Pokémon.
2. Después debe ser un juego personalizado.
3. Las referencias personales deben recompensar al jugador, no reemplazar al contenido.
4. HeartGold es la referencia principal de feeling.
5. Todos los Pokémon de Gen 1-3 deben ser obtenibles.
6. El mundo debe sentirse vivo.
7. La exploración debe recompensar curiosidad.
8. El postgame debe importar.
9. La región debe ser compacta y memorable.
10. Priorizar calidad sobre duración.
11. Automatizar la producción siempre que sea razonable.
12. No asumir que una idea inicial es definitiva. Los subagentes deben investigar y cuestionar decisiones cuando tengan argumentos sólidos.

---

## 20. Prioridades actuales

### P0

- juego divertido incluso sin referencias personales;
- inspiración fuerte en HeartGold;
- 386 Pokémon;
- Pokémon siguiendo al jugador;
- mundo explorable;
- día/noche;
- buena trama;
- Fede como antagonista a investigar;
- región original;
- postgame significativo;
- estética HGSS;
- pipeline reproducible para Codex.

### P1

- eventos diarios/semanales;
- rematches;
- sistema estilo PokéGear;
- actividades secundarias;
- legendarios con mitología integrada;
- secretos;
- callbacks personales;
- herramientas automáticas de QA.

### P2

- sistemas grandes como Pokéathlon completo;
- crafting complejo;
- múltiples regiones completas;
- sistemas que aumenten scope sin mejorar sustancialmente la experiencia.

---

## 21. Preguntas abiertas para los subagentes

Estas preguntas NO deben responderse arbitrariamente. Deben investigarse y discutirse.

### Narrativa

- ¿Qué clase de villano debería ser Fede?
- ¿Cuándo debería descubrir Sofi que Fede está involucrado?
- ¿Cuál es la motivación de Fede?
- ¿Debe ser genuinamente malvado, ambiguo o un falso antagonista?
- ¿Qué Pokémon debería estar vinculado a él?
- ¿Cuál debería ser el conflicto central?
- ¿Cómo evitar una trama genérica de "equipo malvado roba legendario"?

### Mundo

- ¿La región debería estar inspirada en Mar del Plata / Argentina?
- ¿Debería ser totalmente ficticia?
- ¿Una mezcla?
- ¿Qué landmarks reales podrían transformarse en lugares Pokémon sin resultar demasiado obvios?
- ¿Cuántas ciudades y gimnasios maximizan densidad sin hacer el proyecto interminable?

### Sistemas

- ¿8 gimnasios clásicos?
- ¿6 gimnasios + desafíos alternativos?
- ¿Qué mecanismos de progresión podrían conservar la esencia de Pokémon y sorprender a Sofi?
- ¿Cómo distribuir 386 Pokémon sin saturar las primeras rutas?

### Tecnología

- ¿Pokémon Essentials es realmente la mejor opción para desarrollo agentic?
- ¿Qué componentes de RPG Maker presentan problemas para automatización?
- ¿Puede crearse tooling para generar mapas directamente?
- ¿Existen alternativas modernas más adecuadas?
- ¿Qué parte del juego puede testearse headlessly?

### Arte

- ¿Qué resolución y reglas visuales reproducen mejor el feeling de HGSS?
- ¿Usar sprites originales como base o recrear un estilo compatible?
- ¿Cómo generar personajes personalizados consistentes automáticamente?

---

## 22. Definición provisional del producto

> Un fangame original de Pokémon inspirado principalmente en HeartGold / SoulSilver, protagonizado por Sofi, con los 386 Pokémon de Generaciones 1-3 disponibles en una única partida, una región nueva y compacta, Pokémon followers, ciclo día/noche, exploración, secretos, contenido secundario, una historia de aventura y misterio, un postgame significativo y Fede como posible antagonista central.

La duración objetivo inicial de la campaña principal es aproximadamente **5 a 8 horas**, priorizando densidad y calidad sobre tamaño.

Este documento describe el contexto y las decisiones tomadas hasta ahora.

**No es una especificación final.**

La primera responsabilidad del equipo de subagentes de Codex debería ser investigar, cuestionar, expandir y convertir este contexto en un Game Design Document coherente antes de comenzar la implementación a gran escala.
