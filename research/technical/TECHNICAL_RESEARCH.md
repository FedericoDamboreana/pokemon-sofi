# Informe técnico: fangame Pokémon personalizado de Sofi

## Estado de las decisiones

- [Hecho confirmado] El roster objetivo es de 493 especies: Gen 1 a Gen 4 completas.
- [Hecho confirmado] Las 493 especies deben poder obtenerse en una única partida.
- [Hecho confirmado] No puede haber version exclusives ni intercambios obligatorios.
- [Decisión de diseño] No es necesario construir Sinnoh completo.
- [Recomendación] Incluir las 107 especies de Gen 4 dentro de la región existente, con una capa de postgame amplia pero compacta.
- [Pendiente] Definir la distribución exacta por zona, fase de campaña y método de obtención.
- [Pendiente] Decidir cuánto de las reglas de batalla históricas de Gen 4 se quiere conservar. Roster Gen 4, estética Gen 4 y reglas Gen 4 son decisiones separadas.

Las evaluaciones de esta investigación se distinguen así:

- [Hecho] Está respaldado por una fuente o por el comportamiento documentado de una herramienta.
- [Inferencia] Es una conclusión de diseño o ingeniería derivada del scope.
- [Pendiente] Requiere probarse en el spike o decidirse con el diseño narrativo.

## Resumen ejecutivo

Recomiendo Pokémon Essentials v21.1 sobre RPG Maker XP, acompañado por tooling externo en Python/Node para datos, mapas, assets, validación y QA.

La razón sigue siendo de scope, pero ahora con 493 especies confirmadas: Essentials ya resuelve combate, party, captura, evolución, movimientos, tipos, inventario, storage, encuentros, entrenadores, guardado, eventos, mapas y scripting. Godot 4.7.2 es más limpio, automatizable y testeable, pero obliga a construir ese núcleo desde cero y también a importar, validar y balancear 493 especies.

La recomendación queda condicionada a un spike de 1 a 3 días. El spike debe demostrar no sólo tres especies de prueba, sino también que un pipeline externo puede producir y validar el roster completo 001-493, con una muestra de seis especies de Gen 4 y varias evoluciones representativas.

La región no debe crecer hasta parecer Sinnoh. Las 107 especies nuevas pueden entrar mediante biomas ya existentes, evoluciones de especies previas, regalos, fósiles, encargos, encuentros raros, horarios y zonas pequeñas desbloqueadas en postgame. El postgame debe ser una progresión de obtención y dominio de la región, no una segunda aventura regional.

La decisión concreta es:

    Roster: 493 especies, cerrado y obtenible en una partida.
    Región: una región compacta propia, sin construir Sinnoh completo.
    Presentación: estética inspirada en HGSS/Gen 4, pero con UI y assets originales.
    Batalla: perfil Gen 4-lite recomendado, sin gimmicks posteriores y sin prometer paridad histórica completa.
    Engine candidato: Pokémon Essentials v21.1.
    Fallback: Godot 4.7.2 Standard si el spike no demuestra automatización, follower y QA suficientes.

## Interpretación del roster 493

### Qué cambia con la confirmación

[Hecho] Gen 4 agrega 107 especies, de la #387 Turtwig a la #493 Arceus.

[Inferencia] El aumento nominal es 27,7% sobre 386 especies, pero el trabajo no crece linealmente. Las 107 entradas arrastran:

- líneas evolutivas nuevas;
- evoluciones de especies de Gen 1-3;
- learnsets y movimientos;
- habilidades;
- formas;
- métodos de obtención;
- sprites de combate, iconos y followers;
- balance y cobertura de QA.

[Hecho] Pokémon Essentials separa especies, formas, movimientos, habilidades, evoluciones y Pokédex en datos PBS. Su código contempla Dex nacionales y regionales y el compilador valida referencias a especies y formas. [Pokémon Essentials: Pokédex y utilidades](https://github.com/Maruno17/pokemon-essentials/blob/master/Data/Scripts/019_Utilities/001_Utilities.rb), [compilador PBS](https://github.com/Maruno17/pokemon-essentials/blob/master/Data/Scripts/021_Compiler/002_Compiler_CompilePBS.rb), [pokemon_forms.txt](https://github.com/Maruno17/pokemon-essentials/blob/master/PBS/pokemon_forms.txt)

[Inferencia] 493 no es una modificación arquitectónica difícil en Essentials si el proyecto parte de una base con datos Gen 4 o posteriores. El riesgo está en la procedencia y coherencia de los datos, los assets faltantes y los métodos de adquisición, no en cambiar un contador de 386 a 493.

### Qué no significa 493

493 no implica:

- construir las rutas, ciudades y gimnasios de Sinnoh;
- agregar una segunda Pokédex regional completa;
- reproducir exactamente Pokémon Diamond/Pearl/Platinum;
- adoptar todas las reglas de batalla de Gen 4;
- crear 107 líneas narrativas nuevas;
- hacer que las 107 especies aparezcan durante la campaña principal.

### Distribución recomendada sin agrandar el mundo

[Inferencia] Un reparto inicial razonable es:

| Fase | Función | Rango orientativo |
|---|---|---:|
| Campaña temprana | Primeras especies de Gen 4, starters o encuentros accesibles | 12-20 |
| Campaña media | Biomas existentes y evoluciones de especies ya conocidas | 15-25 |
| Campaña tardía | Zonas de nivel alto, eventos y cadenas de misión | 15-25 |
| Postgame | Mayoría de raros, líneas completas, fósiles, formas y legendarios | 45-65 |

Los rangos no son un contrato de contenido. La restricción importante es que las 107 estén cubiertas en el ledger y que el postgame no dependa de una región nueva.

Métodos compatibles con una región compacta:

- encuentros en biomas existentes con rotación por horario, clima o progreso;
- evoluciones de especies Gen 1-3 que ya estén en la región;
- regalos de NPC y recompensas de cadenas de misiones;
- fósiles o restauración en un laboratorio existente;
- pesca, surf y cuevas ya presentes;
- encuentros raros desbloqueados en postgame;
- un santuario o área final pequeña para especies míticas/legendarias;
- objetos de evolución obtenidos por exploración, compras, encargos o logros;
- formas como contenido de laboratorio, clima, objetos o eventos, sin nuevas rutas.

[Inferencia] La región debería sumar como máximo dos o tres micro-áreas reutilizables para postgame, no una red de rutas equivalente a Sinnoh. El contenido puede cambiar por flags, encuentros y NPCs sin duplicar mapas.

### Métodos sin intercambio ni version exclusives

[Hecho confirmado por el producto] Un intercambio externo no puede ser requisito.

[Inferencia] Toda evolución originalmente dependiente de trade debe tener una sustitución explícita. Opciones preferidas:

- objeto de evolución comprable o entregado por una misión;
- uso del objeto sobre la especie;
- nivel + objeto;
- evento de NPC que simula el intercambio sin salir de la partida;
- amistad o condición contextual, si no destruye la identidad de la línea.

El ledger debe registrar el método canónico de diseño, no sólo el método de los juegos originales. Por ejemplo, Electabuzz -> Electivire puede usar Electrizer + nivel o un evento de laboratorio, con requires_trade=false.

No hay que borrar la relación histórica de la evolución. Hay que modelar un método de obtención jugable y cerrado.

## Separación de decisiones

| Capa | Decisión actual | Lo que no se debe inferir |
|---|---|---|
| Roster | 493 especies, Gen 1-4 completas | No obliga a construir Sinnoh |
| Estética | Inspiración HGSS/Gen 4 | No obliga a usar sprites oficiales |
| Batalla | Gen 4-lite recomendado | No obliga a reproducir cada edge case histórico |
| Región | Región propia compacta | No define todavía biomas ni ciudades |
| Historia | Sofi, Fede y Nahue como referencias progresivas | No define todavía al villano ni la trama completa |
| Postgame | Principal superficie para completar el roster | No obliga a una segunda campaña del tamaño de la principal |

La preferencia confirmada de Sofi por las especies de cuarta generación resuelve el roster. No resuelve por sí sola la región, la mecánica de combate ni la dirección artística.

## Matriz comparativa

Escala de 1 a 5. Son evaluaciones inferidas, no benchmarks formales. Los pesos se ajustan al contrato 493.

| Criterio | Peso | Essentials | Godot | pokeemerald | PokémonUnity | PokeWilds |
|---|---:|---:|---:|---:|---:|---:|
| Cobertura de sistemas y datos Pokémon | 30% | 5 | 1 | 4 | 2 | 2 |
| Encaje con follower y presentación HGSS | 15% | 5 | 5 | 2 | 3 | 2 |
| Extensibilidad a 493 y formas | 10% | 4 | 5 | 2 | 3 | 2 |
| Automatización por agentes | 15% | 3 | 5 | 4 | 3 | 3 |
| Mapas programáticos | 10% | 3 | 5 | 2 | 3 | 1 |
| QA headless y builds | 10% | 2 | 5 | 4 | 4 | 2 |
| Mantenimiento y documentación | 5% | 4 | 4 | 4 | 2 | 3 |
| Licencia y packaging | 5% | 2 | 5 | 1 | 2 | 2 |
| Total ponderado | 100% | 78 | 75 | 63 | 54 | 42 |

[Inferencia] 493 aumenta la ventaja práctica de Essentials porque el costo dominante de Godot sigue siendo construir y probar el motor Pokémon. La puntuación de Godot mejora en extensibilidad y QA, pero no compensa el núcleo que habría que implementar.

### Pokémon Essentials / RPG Maker XP

[Hecho] El repositorio público de Essentials es un proyecto de RPG Maker XP modificado para funcionar como juego Pokémon, con v21.1 como referencia. [Repositorio de Pokémon Essentials](https://github.com/Maruno17/pokemon-essentials)

Ventajas:

- reduce drásticamente el trabajo inicial;
- usa datos PBS relativamente legibles;
- permite modificar Ruby;
- tiene comunidad y plugins;
- encaja con combate, mapas y UX cercanos a HGSS;
- el modelo de datos ya contempla especies, formas, evoluciones, movimientos, habilidades y Dexes.

[Hecho] Following Pokémon EX para v21.1 contempla followers, animaciones, interacción contextual, surfing, combate, estados, movimiento, transferencias y diálogo específico. [Following Pokémon EX v21.1](https://eeveeexpo.com/resources/516/), [Following Pokémon EX v21.1 port](https://eeveeexpo.com/resources/1464/)

Impacto real de 493:

- compilar 493 especies es principalmente trabajo de datos y assets;
- las evoluciones Gen 4 que parten de especies antiguas reutilizan la entrada base y agregan una arista al grafo;
- pokemon_forms.txt permite separar formas del conteo de especies;
- regional_dexes.txt permite usar una Dex regional compacta y una Nacional de 493;
- se deben fijar versiones de los datos PBS y del plugin follower;
- la automatización del editor y del runtime sigue siendo el principal límite.

Problemas:

- los mapas de RPG Maker XP están en archivos binarios RXDATA;
- parte del workflow depende del editor visual;
- no existe un flujo headless tan limpio como en Godot;
- los plugins pueden tener compatibilidades frágiles;
- el follower debe probarse con las 107 especies nuevas y no sólo con una especie genérica;
- RPG Maker XP es una herramienta antigua y sus requisitos oficiales no soportan oficialmente sistemas operativos de 64 bits. [RPG Maker XP en Steam](https://store.steampowered.com/app/235900/RPGMakerXP/)

[Hecho] Essentials está bajo CC BY-NC-SA 4.0. No es una base adecuada para un producto comercial sin revisar permisos adicionales. RPG Maker XP también es propietario. [Licencia de Essentials](https://raw.githubusercontent.com/Maruno17/pokemon-essentials/master/LICENSE)

[Inferencia] Para un juego privado o no comercial, Essentials sigue siendo la opción de menor riesgo de ejecución. Para una distribución comercial, la licencia del engine y la IP de Pokémon son gates separados y pueden invalidar esta elección.

### Godot

[Hecho] Godot 4.7.2 es MIT y permite distribuir el juego bajo la licencia que corresponda. [Licencia de Godot](https://godotengine.org/license/), [archivo de versiones](https://godotengine.org/download/archive/)

Ventajas:

- escenas y recursos versionables;
- GDScript fácil de leer y generar;
- tipado gradual;
- TileMapLayer;
- exportación CLI;
- ejecución headless;
- logs configurables;
- integración con CI;
- mapas generables desde JSON;
- sin dependencia del editor para cada cambio de datos;
- buen encaje para una fuente de datos única que produzca runtime, Dex, encounters y QA.

Impacto real de 493:

- importar 493 registros no es el problema;
- el problema es implementar y probar todos los consumidores de esos registros;
- habrá que construir captura, party, moves, abilities, types, damage, status, evolution, storage, trainer AI, UI, save system y Pokédex;
- las formas y los métodos de evolución necesitan un sistema de condiciones, no simples campos;
- el pipeline de assets y el follower serían propios;
- el test suite tendría que cubrir el comportamiento de battle y data antes de producir la campaña.

[Hecho] La documentación oficial soporta scripts, validación, exportación, headless y logs desde línea de comandos. [Godot command line](https://docs.godotengine.org/en/latest/tutorials/editor/command_line_tutorial.html)

[Inferencia] Godot sólo pasa a ser la recomendación principal si el equipo decide que el valor del proyecto está en poseer un engine propio, controlar una distribución más amplia o hacer QA automatizado como prioridad superior a terminar rápido la experiencia Pokémon.

### Alternativas open source

[Hecho] pret/pokeemerald es una decompilación de Pokémon Emerald que compila una ROM de Game Boy Advance. Tiene battle engine y build reproducible, pero su target, resolución, memoria y workflow no encajan con una experiencia HGSS de 493 especies. [pokeemerald README](https://github.com/pret/pokeemerald) y [pokeemerald INSTALL](https://github.com/pret/pokeemerald/blob/master/INSTALL.md)

[Hecho] PokémonUnity tiene código C# MIT/BSD, pero está marcado como legacy y no ofrece un camino suficientemente claro frente a Godot. [PokémonUnity](https://github.com/PokemonUnity/PokemonUnity)

[Hecho] PokeWilds es un juego/engine Gen 2 basado en libGDX, con generación procedural y estado alpha. Sirve como referencia, no como base. [PokeWilds](https://github.com/SheerSt/pokewilds)

[Hecho] Existe un Pokémon Essentials separado para RPG Maker MV, TypeScript y Node.js, explícitamente WIP. No lo recomiendo frente a Essentials XP. [Pokémon Essentials MV](https://github.com/pokemon-essentials/pokemon-essentials)

## Datos Gen 4 que realmente hay que resolver

### Especies, líneas y evoluciones

[Hecho] La lista 387-493 no es una lista aislada. Varias entradas son preevoluciones o evoluciones conectadas con especies de Gen 1-3.

Ejemplos de líneas nuevas completas:

- Turtwig -> Grotle -> Torterra, evolución por nivel.
- Chimchar -> Monferno -> Infernape, evolución por nivel.
- Piplup -> Prinplup -> Empoleon, evolución por nivel.
- Starly -> Staravia -> Staraptor, evolución por nivel.
- Shinx -> Luxio -> Luxray, evolución por nivel.
- Budew -> Roselia -> Roserade, con condiciones de amistad/tiempo y piedra.
- Riolu -> Lucario, con amistad y condición temporal.
- Bidoof -> Bibarel, evolución por nivel.
- Cranidos -> Rampardos y Shieldon -> Bastiodon, con fósiles y nivel.
- Snover -> Abomasnow, evolución por nivel.
- Snorunt -> Froslass o Glalie, con género/objeto o nivel según el diseño elegido.

Ejemplos de evoluciones Gen 4 de especies previas:

- Aipom -> Ambipom;
- Lickitung -> Lickilicky;
- Tangela -> Tangrowth;
- Magneton -> Magnezone;
- Electabuzz -> Electivire;
- Magmar -> Magmortar;
- Eevee -> Leafeon o Glaceon;
- Rhydon -> Rhyperior;
- Piloswine -> Mamoswine;
- Dusclops -> Dusknoir;
- Togetic -> Togekiss;
- Sneasel -> Weavile;
- Gligar -> Gliscor;
- Porygon2 -> Porygon-Z;
- Nosepass -> Probopass.

[Hecho] Essentials documenta que las evoluciones se describen en archivos PBS como tripletas de método, parámetro y valor, y que soporta la mayoría de métodos existentes. [Evolución en Essentials](https://essentialsdocs.fandom.com/wiki/Evolution)

[Inferencia] El proyecto debe modelar las evoluciones como un grafo de condiciones y no como una lista plana de niveles. Eso permite sustituir trades o ubicaciones de Sinnoh sin romper la línea.

### Movimientos y learnsets

[Hecho] El compilador de Essentials valida referencias a especies y formas y el proyecto mantiene datos PBS para especies y formas. La existencia de una entrada no garantiza que el learnset elegido sea coherente con la época de batalla deseada. [Compilador PBS](https://github.com/Maruno17/pokemon-essentials/blob/master/Data/Scripts/021_Compiler/002_Compiler_CompilePBS.rb), [pokemon_forms.txt](https://github.com/Maruno17/pokemon-essentials/blob/master/PBS/pokemon_forms.txt)

Hay que decidir por separado:

- learnsets por nivel;
- movimientos por tutor;
- TMs/HMs o equivalentes;
- movimientos de huevo;
- movimientos de evento;
- disponibilidad de movimientos introducidos después de Gen 4;
- compatibilidad con el perfil de batalla elegido.

[Inferencia] Para proteger QA, el roster puede ser 493 sin incluir todos los movimientos de todas las generaciones. Recomiendo un catálogo de movimientos cerrado para el juego, con learnsets completos sólo para las especies jugables y movimientos fuera del catálogo bloqueados por el validador.

[Pendiente] Decidir si las especies de Gen 1-4 usan learnsets históricos de Gen 4 o learnsets propios balanceados. No conviene mezclar silenciosamente ambos.

### Habilidades

[Hecho] Las habilidades forman parte del modelo de datos de Essentials y se definen por especie o forma. [pokemon_forms.txt](https://github.com/Maruno17/pokemon-essentials/blob/master/PBS/pokemon_forms.txt)

[Inferencia] Si se adopta un perfil Gen 4-lite, cada especie debe tener:

- habilidades disponibles en el juego;
- slots normales;
- habilidad oculta deshabilitada salvo que el diseño la necesite;
- efecto soportado por el engine;
- tests para habilidades que afectan encuentros, clima, prioridad, inmunidades o evolución.

No hay que importar habilidades modernas por defecto sólo porque el dataset externo las incluya.

### Formas

Las 107 especies no se reducen a 107 sprites únicos. Hay que registrar formas que afectan datos, visuales o adquisición.

Casos relevantes a auditar:

- Burmy, Wormadam y Mothim;
- Shellos y Gastrodon;
- Cherrim;
- Rotom;
- Giratina;
- Shaymin;
- Arceus;
- cualquier forma adicional que el proyecto decida excluir explícitamente.

[Inferencia] El conteo contractual debe ser:

    493 especies nacionales obligatorias.
    N formas obligatorias o permitidas, registradas aparte.
    493 filas de cobertura como mínimo.
    Una fila adicional por forma si la forma tiene método de obtención o asset propio.

[Pendiente] Decidir si las formas de combate/cosméticas cuentan para completar la Pokédex. Recomendación: la especie cuenta con una forma base; las formas relevantes deben ser obtenibles o demostrables, pero no convertir cada variante cosmética en una cadena de contenido obligatoria.

## ¿Conviene usar reglas de batalla de Gen 4?

### Recomendación: perfil Gen 4-lite

[Inferencia] No recomiendo prometer una reproducción exacta de todas las reglas de Diamond/Pearl/Platinum. Recomiendo un perfil explícito con:

- separación física/especial por movimiento;
- habilidades y tipos disponibles hasta Gen 4;
- ítems y efectos necesarios para las 493 especies;
- ausencia de Mega Evolution, Z-Moves, Dynamax, Teracristalización y otras gimmicks posteriores;
- velocidad y prioridades estables;
- breeding opcional, no necesario para completar el roster;
- encuentros y trainers balanceados para la región propia;
- excepciones documentadas cuando la implementación histórica no compense el costo de QA.

Este perfil captura la identidad mecánica importante de la era Gen 4 sin obligar a replicar cada bug, fórmula, edge case o contenido externo.

### Por qué no usar reglas modernas sin más

[Inferencia] Un sistema moderno puede hacer que la estética diga HGSS mientras la batalla se sienta de otra época. También introduce movimientos, habilidades, formas o interacciones que no tienen espacio en el diseño.

### Por qué no hacer una emulación completa

[Inferencia] La paridad exacta multiplica la superficie de pruebas. Habría que congelar fórmulas, orden de resolución, efectos de movimientos, interacción de habilidades, clima, estados, críticos, precisión, prioridad, breeding y comportamiento de IA.

[Pendiente] El spike debe probar primero el perfil Gen 4-lite. Si la diferencia con una configuración estándar de Essentials es pequeña y los smoke tests pasan, se mantiene. Si exige parches invasivos, se documentan las excepciones y se protege el calendario.

## Stack y toolchain

### Obligatorio para Essentials

- RPG Maker XP comprado desde Steam.
- Pokémon Essentials v21.1.
- Ruby fijado después del spike.
- Python 3.13, ya instalado localmente.
- Git y Git LFS, ya instalados localmente.
- Proyecto versionado desde el primer día.
- Una fuente de datos propia para 001-493.
- Compilador determinista hacia PBS y manifests de QA.

RubyInstaller ofrece actualmente Ruby 4.0.6 y Ruby 3.4.10. Essentials incluye un runtime ruby310, por lo que la versión exacta debe validarse en el spike. [RubyInstaller](https://rubyinstaller.org/downloads/)

Comandos Python previstos para el entorno de tooling:

    py -3.13 -m venv .venv
    .\\.venv\\Scripts\\python.exe -m pip install --upgrade pip
    .\\.venv\\Scripts\\python.exe -m pip install pillow jsonschema pytest pytest-cov pyyaml

### Recomendado

- Tiled 1.12.2 para layouts y mapas auxiliares. [Tiled](https://github.com/mapeditor/tiled)
- Grasswhistle V2 para layouts compatibles con RPG Maker XP. [Grasswhistle](https://github.com/LancelotXIII/Grass-Whistle)
- Essentials Unpack’d 3.0.0 para extraer RXDATA a YAML/Ruby. [Essentials Unpack’d](https://github.com/ra101/Essentials-Unpackd)
- VS Code.
- LibreSprite o Aseprite.
- ImageMagick.
- Krita.
- GitHub Actions con Windows runner cuando exista repositorio.

WinGet detecta Tiled 1.12.2:

    winget install --id Tiled.Tiled -e

No se instaló ninguna herramienta durante esta investigación.

### Fuente de datos y lockfile

[Inferencia] El proyecto debe tener una fuente de datos canónica externa al editor:

    data/
      species_001_493.yaml
      moves_gen1_gen4.yaml
      abilities_gen3_gen4.yaml
      evolution_methods.yaml
      forms_001_493.yaml
      acquisition_ledger.csv
      battle_profile_gen4_lite.yaml
      provenance.yml
    generated/
      essentials/
      manifests/
      reports/

La fuente puede importar datos estructurados de PokeAPI o de PBS, pero el resultado debe quedar congelado con versión, fecha, commit/hash y transformaciones documentadas.

[Hecho] PokeAPI ofrece datos estructurados bajo BSD, pero eso no convierte sus sprites en assets redistribuibles libres. El repositorio de sprites aclara que las imágenes son copyright de The Pokémon Company aunque el repositorio use CC0. [PokeAPI](https://github.com/PokeAPI/pokeapi), [licencia de sprites](https://github.com/PokeAPI/sprites/blob/master/LICENCE.txt)

[Inferencia] PokeAPI debe usarse como fuente de verificación de datos, no como justificación para redistribuir sprites oficiales. El pipeline debe separar data provenance de asset provenance.

### Alternativa Godot

    winget install --id GodotEngine.GodotEngine -e

Elegir Godot Standard, no Mono, salvo razón concreta para C#. Fijar Godot 4.7.2 desde el archivo oficial para evitar drift de versiones. [Godot archive](https://godotengine.org/download/archive/)

Comandos básicos:

    godot --version
    godot --headless --path . --editor --quit
    godot --headless --path . --check-only
    godot --headless --path . --export-release "Windows Desktop" "builds\\sofi.exe"

En Godot el mismo schema podría alimentar runtime, Dex, encounters, battle tests y UI. Esa ventaja no elimina el costo de implementar todos los sistemas.

## Pipeline reproducible de assets

### Taxonomía de procedencia

Cada asset debe declarar una de estas categorías:

| Categoría | Definición | ¿Cuenta como trabajo original? |
|---|---|---|
| Existente del engine o pack | Asset incluido por Essentials, RPG Maker o un pack externo | No |
| Adaptado | Redimensionado, recoloreado, limpiado o reencuadrado desde una fuente existente | No; es derivado |
| Referencia | Imagen usada para estudiar proporciones, pose o paleta | No |
| Original | Dibujado o pixelado para este proyecto sin reutilizar un sprite oficial | Sí |
| IA exploratoria | Concept art o variantes que todavía no pasan producción | No, hasta ser redibujadas y documentadas |

[Inferencia] La entrega no debe contar 107 Pokémon “hechos” si sólo se copió o adaptó un pack. El manifest debe guardar fuente, licencia, hash, autor, transformación y estado de aprobación.

### Carga de las 107 especies

Para cada especie Gen 4 se deben auditar, como mínimo:

- sprite frontal de combate;
- sprite trasero de combate;
- icono de party/Dex;
- sprite o pose de menú si aplica;
- follower overworld;
- animaciones mínimas de follower;
- escala y clase de colisión;
- portrait o ilustración sólo si la UI lo requiere;
- formas separadas cuando cambien la apariencia.

[Inferencia] Para proteger el scope, la producción puede dividirse así:

1. reutilizar assets existentes sólo cuando la licencia y la procedencia estén documentadas;
2. adaptar sólo assets que tengan una justificación técnica clara;
3. producir followers originales por lotes y por clases de tamaño/movimiento;
4. completar primero las seis especies del spike;
5. no producir los 107 followers finales antes de validar el contrato visual y la colisión.

[Pendiente] Definir si el follower debe tener animación única por especie o un set común de animaciones con poses específicas. Recomendación: pose y silueta propias por especie, pero animación de locomoción normalizada por clase.

### Pipeline de personajes

1. Definir plantilla, canvas, grilla, paleta y proporciones.
2. Generar concept art sólo como referencia.
3. Redibujar o pixelar sobre la plantilla.
4. Exportar caminar, correr, bicicleta y poses sólo donde aplique.
5. Validar dimensiones y transparencia.
6. Generar spritesheet final.
7. Registrar provenance y hash.

Estructura propuesta:

    assets/
      source/characters/
      source/pokemon/
      source/tilesets/
      source/ui/
      source/portraits/
      processed/
      manifests/assets.json
      palettes/hgss-inspired.json
    tools/assets/
      build_character.py
      build_spritesheet.py
      validate_assets.py
      validate_follower_classes.py
      recolor.py

Interfaces:

    import_reference_asset
    generate_character_sprite
    generate_follower_variant
    compose_sprite_sheet
    validate_asset
    validate_follower_manifest
    validate_asset_manifest

No conviene pedirle a una IA un tileset completo. Es mejor definir una gramática visual, bloques base, paleta limitada, autotiles, patrones reutilizables, reglas seamless, colisiones y terrain tags.

La UI debe ser original e inspirada en HGSS, no una copia literal: paneles modulares, iconos normalizados, tipografía consistente, portraits en varios tamaños, contraste validado y textos separados de imágenes.

[Hecho] Aseprite tiene CLI para spritesheets y permite usar los assets creados en juegos comerciales, aunque su aplicación es propietaria. [Aseprite FAQ](https://www.aseprite.org/faq)

[Hecho] LibreSprite es GPLv2. Krita es GPLv3 y permite uso comercial de las obras creadas. ImageMagick sirve para validación y conversión batch. [LibreSprite](https://github.com/LibreSprite/LibreSprite), [Licencia de Krita](https://krita.org/en/about/license/), [Licencia de ImageMagick](https://imagemagick.org/license/)

### Followers y las 107 especies

[Inferencia] Following Pokémon EX resuelve lógica de seguimiento, no la garantía de que existan assets coherentes para las 107 especies. El spike debe demostrar:

- resolución de sprite por especie y forma;
- fallback explícito si falta un asset;
- clases de escala;
- colisión;
- interacción;
- entrada y salida de combate;
- transferencia de mapa;
- agua, escaleras, puentes y puertas;
- día/noche si el follower cambia de pose o visibilidad.

Un fallback visual genérico puede servir para probar lógica, pero no puede declararse asset final. Las 107 especies necesitan una fila de asset y una fila de QA aunque su arte final se produzca después.

## MCP, CLI e integraciones

### Disponibles ahora

[Hecho, verificado localmente]

- exec_command para scripts y builds;
- apply_patch para editar archivos;
- view_image para inspección visual;
- navegación web;
- ImageGen para concept art;
- coordinación de tareas de Codex.

No hay un MCP específico para RPG Maker XP, Pokémon Essentials, Godot, Tiled, screenshots del juego o lectura estructurada de logs. Los plugins de GitHub y Google Drive aparecen como recomendados, pero no están instalados y no hacen falta para el spike.

[Inferencia] Conviene construir primero un CLI local reproducible. Un MCP propio debería envolverlo, no reemplazarlo.

Superficie propuesta:

    project_validate
    data_import_snapshot
    data_validate
    species_validate
    move_validate
    ability_validate
    evolution_validate
    form_validate
    coverage_ledger_validate
    map_list
    map_read
    map_generate
    map_export
    asset_validate
    follower_validate
    asset_build
    game_compile
    game_run_scenario
    game_capture_screenshot
    game_read_logs
    qa_smoke_test
    artifact_hash

Cada herramienta debe:

- aceptar rutas explícitas;
- devolver JSON;
- usar seeds deterministas;
- no ejecutar comandos arbitrarios;
- separar operaciones destructivas;
- fallar con códigos claros;
- guardar versión de schema y fuente de datos;
- producir artefactos reproducibles.

MCP no debe ser el lugar donde se decide qué especies existen. Esa decisión debe vivir en el schema, el ledger y el commit versionado.

## Schema, ledger y validadores

### Schema mínimo por especie

Cada especie 001-493 necesita al menos:

    national_id
    species
    generation
    base_species
    types
    abilities
    hidden_ability
    base_stats
    height
    weight
    gender_ratio
    hatch_steps
    egg_groups
    levelup_learnset
    tm_tutor_learnset
    egg_moves
    evolutions
    forms
    availability_phase
    acquisition_methods
    asset_refs
    provenance

El campo generation no debe controlar por sí solo la disponibilidad. Una especie Gen 4 puede estar en postgame y una especie Gen 1 puede ser exclusiva de una misión.

### Schema de evolución

Cada arista del grafo debería poder expresar:

    from_species
    to_species
    method
    level
    item
    move
    friendship
    time_window
    gender
    location_tag
    weather
    form_condition
    requires_trade
    requires_external_game
    one_playthrough_method
    fallback_method
    notes

[Inferencia] requires_trade y requires_external_game deben ser booleanos validables y estar prohibidos para el roster final. one_playthrough_method debe apuntar a una condición que el ledger pueda demostrar.

### Ledger de cobertura 001-493

Una fila por especie, con filas adicionales para formas relevantes:

    national_id
    species
    generation
    availability_phase
    location_id
    method
    prerequisite_flags
    evolution_source
    form_id
    single_playthrough
    requires_trade
    requires_version_exclusive
    requires_external_game
    proof_scenario
    asset_status
    data_status
    qa_status

Reglas bloqueantes:

- exactamente 493 especies nacionales;
- IDs únicos y contiguos 001-493;
- toda especie tiene al menos un método de obtención;
- toda especie tiene un proof_scenario;
- single_playthrough=true;
- requires_trade=false;
- requires_version_exclusive=false;
- requires_external_game=false;
- todo objeto, NPC, flag, mapa y evento previo existe;
- toda evolución tiene un método alcanzable;
- no hay ciclos ilegales;
- las formas con impacto jugable tienen método y asset;
- ningún movimiento o habilidad referenciado está fuera del catálogo congelado;
- no hay assets finales sin provenance;
- no hay especies “cubiertas” sólo porque aparecen en el schema.

### Validadores y reportes

El tooling debería incluir:

    validate_species_001_493.py
    validate_moves_and_abilities.py
    validate_evolution_graph.py
    validate_forms.py
    validate_acquisition_ledger.py
    validate_no_trade_or_version_exclusive.py
    validate_assets.py
    validate_followers.py
    build_essentials_pbs.py
    run_smoke_scenarios.py
    make_coverage_report.py

Reportes mínimos:

    reports/species_coverage.html
    reports/gen4_gap_report.html
    reports/evolution_graph.json
    reports/asset_gap_report.json
    reports/battle_profile_report.json
    reports/qa-report.json

## QA y validación

### Validación estática

- especies 001-493;
- movimientos y tipos;
- habilidades;
- evoluciones;
- formas;
- learnsets;
- encounters alcanzables;
- warps con destino existente;
- mapas conectados;
- flags y variables documentadas;
- assets con dimensiones, alpha y nombres correctos;
- ausencia de referencias rotas;
- Pokédex completa;
- prohibición de trade y version exclusives;
- procedencia de datos y assets.

### Escenarios dinámicos de roster

Cada especie debe tener como mínimo una de estas pruebas:

- captura directa;
- regalo;
- recompensa;
- fósil restaurado;
- evolución desde especie obtenible;
- cambio de forma;
- encuentro condicionado por horario, clima o postgame.

[Inferencia] No hace falta jugar 493 capturas a mano en cada commit. Hace falta que cada fila tenga una ruta demostrable y que el runner ejecute una muestra por método, por fase y por familia de errores.

### Seis especies de Gen 4 para el spike

El spike debe incluir al menos estas seis:

| Especie o línea | Qué prueba |
|---|---|
| Turtwig -> Grotle -> Torterra | línea de tres etapas y evolución por nivel |
| Budew -> Roselia -> Roserade | especie bebé, amistad/tiempo y piedra de evolución |
| Riolu -> Lucario | amistad, hora del día y evolución de una etapa |
| Magneton -> Magnezone | evolución Gen 4 de especie previa con sustitución de ubicación |
| Electabuzz -> Electivire | evolución histórica por trade/objeto convertida en método interno |
| Rotom | especie Gen 4 con formas y cambio de estado/asset |

La sexta prueba no debe tratar Rotom como una simple especie. Debe verificar forma base, transformación, persistencia en save, asset del follower y reversión si corresponde.

Casos adicionales recomendados para la segunda iteración:

- Eevee -> Leafeon y Glaceon;
- Gligar -> Gliscor;
- Piloswine -> Mamoswine;
- Burmy/Wormadam/Mothim;
- Shellos/Gastrodon;
- Snorunt -> Froslass;
- Porygon2 -> Porygon-Z.

### Smoke tests del engine

Cada run debe demostrar:

- arranque desde carpeta limpia;
- compilación de datos;
- creación de save;
- obtención de una especie por captura;
- obtención por regalo;
- evolución por nivel;
- evolución por amistad/tiempo;
- evolución por piedra;
- evolución sin trade;
- cambio de forma;
- follower en exterior/interior;
- follower en escalera, puerta, puente y agua;
- follower al entrar y salir de combate;
- warp entre tres mapas;
- día/noche;
- encuentro de postgame;
- Pokédex que cuenta especie y forma según la política elegida;
- guardado/carga con los nuevos datos;
- build y hash reproducibles.

En Essentials son viables compilación automática, Debug Mode, escenarios mediante eventos, screenshots externos, lectura de logs, validación PBS/mapas fuera del engine y smoke tests con saves preparados. Es más difícil el headless puro, el control fiable de inputs y las capturas deterministas.

En Godot son viables headless, scripts de validación, exportación CLI, logs, escenarios con argumentos, CI, tests puros de battle/data, screenshots desde viewport y builds con hash. Eso reduce el riesgo operativo, pero no el costo de construir el battle engine.

Cada build debería producir:

    build/
      sofi-windows.zip
      SHA256SUMS.txt
      build-manifest.json
      qa-report.json
      logs/
      screenshots/

El manifest debe contener engine version, commit, data version, schema version, asset manifest hash, seed, fecha, tests y output hash.

## Spike técnico de 1 a 3 días

No instalar herramientas ni producir contenido grande antes de este spike. El objetivo es validar el contrato técnico 493 con una región mínima.

### Día 1: base de datos y Essentials

- crear proyecto limpio;
- obtener Essentials v21.1;
- definir schema 001-493;
- importar o cargar seis especies Gen 4;
- compilar PBS;
- configurar una Dex Nacional de 493;
- crear mapa exterior e interior;
- agregar NPC, diálogo y starter;
- capturar Turtwig o una especie equivalente;
- hacer combate, save y load.

Gate:

- 493 IDs pueden pasar por el schema sin hardcodes de 386;
- las seis especies se compilan;
- los learnsets, habilidades y referencias se validan;
- no hay error por formas o evoluciones;
- los cambios se reproducen desde archivos fuente.

### Día 2: follower, evoluciones y battle profile

- instalar Following Pokémon EX;
- probar follower de una especie pequeña, una grande y Rotom;
- probar las seis especies del spike;
- ejecutar Turtwig, Budew, Riolu, Magnezone y Electivire por sus métodos;
- probar Rotom con cambio de forma;
- probar exterior/interior, agua, escaleras, puente, combate, día/noche;
- configurar el perfil Gen 4-lite;
- comparar una batalla con el perfil estándar de Essentials;
- registrar cualquier parche o excepción.

Gate crítico:

- el follower no se duplica;
- no queda bloqueado;
- no rompe transferencias;
- no aparece mal posicionado;
- entra y sale correctamente de combate;
- las evoluciones no requieren trade ni una región externa;
- formas y save/load son estables;
- el perfil de batalla elegido no exige parches invasivos.

### Día 3: región compacta, ledger y build

- definir una región mínima con los biomas existentes;
- asignar las seis líneas del spike al ledger;
- crear al menos un método de campaña y uno de postgame;
- representar dos o tres micro-áreas de postgame reutilizables;
- generar mapas o layouts con Grasswhistle o conversor propio;
- exportar mapas y conexiones;
- ejecutar Essentials Unpack’d;
- validar el ledger completo 001-493 con placeholders;
- correr escenarios automáticos;
- capturar screenshots y logs;
- producir build y SHA-256;
- abrirla en una carpeta limpia.

Gate de decisión:

Essentials continúa si cumple:

- schema y ledger 493 sin excepciones ocultas;
- mapa reproducible;
- follower estable con la muestra;
- evoluciones internas sin trade;
- formas persistentes;
- perfil de batalla explícito;
- compilación automatizable;
- smoke test repetible;
- build ejecutable fuera del entorno de desarrollo.

Si falla cualquiera de los tres primeros gates, especialmente follower, datos reproducibles o cobertura de evolución, conviene pasar a Godot antes de producir contenido grande.

## Qué simplificar para proteger campaña, postgame y QA

[Inferencia] El alcance confirmado no debe resolverse agregando más mundo. Hay que reducir la cantidad de sistemas que interactúan.

Simplificaciones recomendadas:

- una sola región compacta;
- máximo dos o tres micro-áreas nuevas en postgame;
- una Dex Nacional de 493 y pocas Dexes regionales;
- no crear Sinnoh completo;
- no implementar múltiples regiones;
- no hacer breeding necesario para completar;
- no exigir habilidades ocultas;
- no exigir movimientos de huevo;
- no exigir intercambios;
- no exigir versión exclusiva;
- reemplazar evoluciones por trade con métodos internos;
- limitar formas obligatorias a formas con valor jugable;
- no hacer Pokéathlon ni crafting complejo en la primera versión;
- no agregar gimmicks posteriores;
- limitar la IA de entrenadores a perfiles simples y testeables;
- diseñar 493 obtenciones, pero producir contenido narrativo nuevo sólo para una fracción de ellas;
- priorizar el postgame como sistema de flags, encuentros y recompensas, no como mapa nuevo.

La campaña principal puede terminar con un roster parcial disponible. La promesa es que el jugador pueda completar las 493 durante la partida completa, incluyendo postgame.

## Riesgos y mitigaciones

### Scope

Riesgo alto. 493 especies, follower, sidequests, sistemas diarios y postgame pueden multiplicar el contenido.

Mitigación: vertical slice obligatorio, región compacta, 5 a 8 horas como objetivo, postgame diseñado temprano pero implementado después, y límites explícitos a breeding, minijuegos, gimmicks y regiones adicionales.

### Datos inconsistentes

Riesgo alto. Importar datos externos puede traer movimientos, habilidades, formas o evoluciones que contradigan el perfil Gen 4-lite.

Mitigación: snapshot congelado, schema canónico, provenance, catálogo de movimientos cerrado y validadores bloqueantes.

### Métodos de obtención imposibles

Riesgo alto. Un juego con 493 entradas puede declarar cobertura sin que el jugador pueda completar una línea.

Mitigación: ledger por especie, proof_scenario, tests por método, no trade, no version exclusives, no external game y revisión del grafo de evoluciones.

### Assets y followers

Riesgo alto. Los sprites de batalla y followers son trabajo separado; adaptar un pack no equivale a crear assets originales.

Mitigación: manifest de procedencia, placeholders explícitos, producción por lotes, seis especies primero, clases de follower y QA visual/colisión.

### Plugins

Following Pokémon EX es una dependencia comunitaria, no una feature central garantizada por el engine. Su página anuncia compatibilidad con v21.1, pero eso no sustituye una auditoría ni garantiza compatibilidad futura. [Following Pokémon EX](https://eeveeexpo.com/resources/516/)

Mitigación: fijar versión, guardar copia y hash, encapsular integraciones, limitar plugins y crear un fallback de follower mínimo propio si falla.

### Licencias e IP

El engine no elimina el riesgo legal. Pokémon, nombres, diseños, música y sprites pertenecen a sus titulares. Pokémon.com indica que su contenido debe considerarse protegido salvo autorización o excepción legal. [Copyright de Pokémon](https://www.pokemon.com/us/legal/copyright)

Mitigación: mantenerlo no comercial, no usar logos ni música oficial, crear assets originales, documentar provenance, revisar licencias de terceros y consultar asesoría legal si se pretende publicar ampliamente.

### Expansión silenciosa a Sinnoh

Riesgo medio-alto. Agregar 107 especies puede activar la expectativa de rutas, ciudades y lore de Sinnoh.

Mitigación: mantener un documento de separación de decisiones, diseñar las especies como roster y el mundo como región propia, y usar postgame compacto con flags y encuentros.

## Decisiones para tomar ahora

1. Usar Essentials v21.1 como candidato principal.
2. Fijar 493 especies como contrato de roster.
3. Definir schema y ledger antes de crear los 107 assets finales.
4. Mantener una región compacta propia, sin Sinnoh completo.
5. Adoptar estética HGSS/Gen 4 sin copiar assets oficiales.
6. Probar el perfil de batalla Gen 4-lite.
7. Hacer el spike con seis especies de Gen 4 y varias evoluciones.
8. Definir sustituciones de trade y métodos de obtención cerrados.
9. Adoptar un pipeline CLI antes de producir muchos mapas o sprites.
10. Documentar provenance de datos y assets desde el primer commit.

## Decisiones para postergar

- distribución exacta de las 107 especies por zona;
- método final de cada legendario o mítico;
- formas obligatorias de Rotom, Giratina, Shaymin y Arceus;
- learnsets históricos versus learnsets balanceados;
- exactitud de cada edge case de batalla Gen 4;
- tipo exacto del villano de Fede;
- región inspirada en Mar del Plata o totalmente ficticia;
- selección final de legendarios;
- PokéGear o sistema equivalente;
- minijuegos;
- música;
- publicación pública;
- distribución comercial.

## Recomendación final

Stack principal:

    Pokémon Essentials v21.1
    RPG Maker XP
    Following Pokémon EX
    Python 3.13 para schema, importación, tooling y QA
    Ruby fijado después del spike
    Tiled 1.12.2
    Grasswhistle V2 como apoyo opcional
    Essentials Unpack’d
    Git + Git LFS
    LibreSprite o Aseprite
    ImageMagick

Stack alternativo:

    Godot 4.7.2 Standard
    GDScript tipado
    schema único para 493
    Tiled 1.12.2
    Python 3.13
    Pillow
    pytest
    Git + Git LFS

Decisión: empezar validando Essentials con el contrato completo de 493, pero sólo con seis especies representativas y placeholders controlados. No construir Sinnoh. No producir los 107 followers finales antes de validar el pipeline. No adoptar reglas Gen 4 completas antes de medir el costo de QA. El objetivo es que el roster confirmado se sienta amplio en la partida, mientras la campaña, el postgame y la región siguen siendo pequeños y terminables.

## Entregables auditables antes del spike

El contrato 493 queda separado en tres artefactos:

- [ROSTER_SCHEMA.md](ROSTER_SCHEMA.md) define especies, formas, movimientos, habilidades, evoluciones, adquisiciones, assets, provenance y reglas bloqueantes.
- [ROSTER_LEDGER.csv](ROSTER_LEDGER.csv) contiene exactamente una fila por especie nacional 001-493. Sus decisiones de fase, método, escenario y estado están en pending y no se presentan como cobertura verificada.
- [SPIKE_PLAN.md](SPIKE_PLAN.md) define gates pass/fail para compilación, seis líneas Gen 4, follower, forms, evolución interna sin trade, día/noche, save/load, build limpia y hash.

La validación local del ledger, cuando exista el tooling, debe comprobar:

    $rows = Import-Csv research/technical/ROSTER_LEDGER.csv
    $rows.Count -eq 493
    (($rows.national_id | Sort-Object) -join ',') -eq ((1..493 | ForEach-Object { $_.ToString('000') }) -join ',')
    ($rows.national_id | Sort-Object | Get-Unique).Count -eq 493
    ($rows.status | Where-Object { $_ -notin @('planned','pending','verified','blocked') }).Count -eq 0

En el spike real, estas comprobaciones deben convertirse en un validador versionado y ejecutarse junto al compilador. No se instalaron herramientas ni se ejecutó el juego para crear estos documentos.

