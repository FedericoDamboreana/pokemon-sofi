# Roster schema canónico 001-493

## Propósito

Este documento define la fuente de datos auditable para las 493 especies nacionales del juego. El schema es independiente del engine y debe poder compilarse hacia Pokémon Essentials PBS o consumirse desde Godot si se activa el fallback.

El roster contractual es:

    national_id 001-493
    generation 1-4
    single_playthrough true
    requires_trade false
    requires_version_exclusive false
    requires_external_game false

El ledger puede tener decisiones pendientes. Que una especie exista en el schema no significa que esté cubierta por el juego.

## Convenciones

- [Hecho] Los datos de Essentials separan especies, formas, evoluciones, movimientos, habilidades y Dexes en PBS.
- [Inferencia] El schema canónico debe vivir fuera del editor y generar los archivos compilados.
- [Pendiente] La fuente primaria concreta y su snapshot todavía deben fijarse en el spike.
- Los identificadores internos deben ser estables y no depender del orden de una lista regional.
- Los nombres de especies, movimientos, habilidades, formas y métodos deben normalizarse antes de compilar.
- Las formas no incrementan el conteo contractual de 493 especies.
- Una fila de especie no equivale a una obtención verificada.

Fuentes conservadas en el informe técnico:

- [Pokémon Essentials](https://github.com/Maruno17/pokemon-essentials)
- [Compilador PBS](https://github.com/Maruno17/pokemon-essentials/blob/master/Data/Scripts/021_Compiler/002_Compiler_CompilePBS.rb)
- [pokemon_forms.txt](https://github.com/Maruno17/pokemon-essentials/blob/master/PBS/pokemon_forms.txt)
- [regional_dexes.txt](https://github.com/Maruno17/pokemon-essentials/blob/master/PBS/regional_dexes.txt)
- [PokeAPI](https://github.com/PokeAPI/pokeapi)
- [PokeAPI sprites license](https://github.com/PokeAPI/sprites/blob/master/LICENCE.txt)

## Entidades canónicas

### Species

Una entrada por cada ID nacional 001-493.

    national_id: integer
    species: string
    generation: integer
    category: enum
    base_species: string | null
    types: array[1..2] of type_id
    abilities: array[1..3] of ability_id
    hidden_ability: ability_id | null
    base_stats:
      hp: integer
      attack: integer
      defense: integer
      special_attack: integer
      special_defense: integer
      speed: integer
    height: number
    weight: number
    gender_ratio: enum | numeric
    hatch_steps: integer
    egg_groups: array of egg_group_id
    levelup_learnset: array of learnset_entry
    tm_tutor_learnset: array of move_id
    egg_moves: array of move_id
    evolutions: array of evolution_id
    forms: array of form_id
    availability_phase: enum
    acquisition_methods: array of acquisition_id
    asset_refs: array of asset_id
    provenance: provenance_id

Allowed category values:

    species
    starter
    baby
    legendary
    mythical

The category is metadata. It must not decide whether an entry is available during campaign or postgame.

### Form

A form is a state or visual/data variant of a species.

    form_id: string
    national_id: integer
    form_name: string
    form_kind: enum
    types_override: array of type_id | null
    abilities_override: array of ability_id | null
    stats_override: object | null
    learnset_override: object | null
    battle_change: boolean
    visual_change: boolean
    acquisition_id: acquisition_id | null
    asset_refs: array of asset_id
    counts_for_completion: boolean
    provenance: provenance_id

Initial form audit:

    BURMY
    WORMADAM
    MOTHIM
    SHELLOS
    GASTRODON
    CHERRIM
    ROTOM
    GIRATINA
    SHAYMIN
    ARCEUS

[Pendiente] Confirmar cuáles de estas forms son required, optional o excluded. A form excluded from completion must still be represented in the decision log.

### Move

    move_id: string
    name: string
    introduced_generation: integer
    type_id: string
    category: physical | special | status
    power: integer | null
    accuracy: integer | null
    pp: integer
    priority: integer
    flags: array of string
    effect_id: string
    battle_profile: gen4_lite | custom
    provenance: provenance_id

[Inferencia] El catálogo del juego debe congelarse. No se deben importar silenciosamente movimientos posteriores sólo porque una fuente externa los contenga.

### Ability

    ability_id: string
    name: string
    introduced_generation: integer
    effect_id: string
    battle_profile: gen4_lite | custom
    enabled: boolean
    provenance: provenance_id

Una habilidad deshabilitada no debe aparecer en encounters, especies, trainers o tests como si fuera usable.

### Evolution

Cada arista del grafo representa una transición jugable.

    evolution_id: string
    from_species: integer
    to_species: integer
    from_form: form_id | null
    to_form: form_id | null
    method: enum
    level: integer | null
    item: string | null
    move: move_id | null
    friendship: integer | null
    time_window: day | night | any | null
    gender: male | female | any | null
    location_tag: string | null
    weather: string | null
    form_condition: string | null
    requires_trade: boolean
    requires_external_game: boolean
    one_playthrough_method: string
    fallback_method: string | null
    notes: string

Allowed method values should cover at least:

    level
    friendship
    friendship_time
    item
    item_level
    move_known
    gender_item
    time_item
    location
    form_change
    event
    custom

[Inferencia] Trade puede permanecer en provenance o notes como método histórico, pero debe ser false en la transición diseñada para este juego. No se acepta un NPC que sólo diga “intercambia con otro jugador” como workaround.

### Acquisition

Cada especie o forma necesita una ruta que el jugador pueda completar dentro de la partida.

    acquisition_id: string
    national_id: integer
    form_id: form_id | null
    phase: campaign | postgame
    method: wild | gift | quest_reward | fossil | evolution | form_change | event | shop | other
    location_id: string
    encounter_condition: string | null
    prerequisite_flags: array of string
    source_species: integer | null
    source_item: string | null
    single_playthrough: boolean
    requires_trade: boolean
    requires_version_exclusive: boolean
    requires_external_game: boolean
    proof_scenario: string
    status: planned | pending | verified | blocked
    notes: string

[Inferencia] La misma especie puede tener varios acquisition records. Debe existir uno primario y puede haber alternativos, pero todos deben respetar las restricciones del producto.

### Asset

    asset_id: string
    national_id: integer
    form_id: form_id | null
    asset_kind: battle_front | battle_back | party_icon | dex_icon | follower | portrait | menu | other
    variant: string
    path: string
    width: integer
    height: integer
    frame_count: integer
    alpha: boolean
    follower_class: string | null
    source_kind: existing | adapted | reference | original | ai_exploratory
    source_uri: string | null
    license: string
    author: string
    transformation: string | null
    sha256: string
    status: missing | placeholder | review | approved
    provenance: provenance_id

Un asset placeholder puede pasar el smoke test de lógica, pero no se puede contar como asset final.

### Provenance

    provenance_id: string
    source_kind: data_source | engine | pack | original_work | ai_reference
    source_uri: string
    source_revision: string
    retrieved_at: date
    license: string
    copyright_owner: string | null
    transformation: string | null
    notes: string

Data provenance y asset provenance deben ser registros separados. PokeAPI puede ayudar a verificar datos estructurados, pero su existencia no libera sprites de copyright.

## Reglas bloqueantes

El validador debe fallar el build si:

1. faltan filas o sobran filas para IDs 001-493;
2. hay IDs duplicados, no numéricos o fuera del rango;
3. una especie usa un nombre no normalizado;
4. la generación no coincide con el rango nacional;
5. una referencia de tipo, movimiento, habilidad, forma, evolución o asset no existe;
6. una especie tiene learnset con movimiento fuera del catálogo congelado;
7. una habilidad marcada enabled=false se referencia como activa;
8. una evolución apunta a una especie inexistente o genera un ciclo ilegal;
9. una evolución final tiene requires_trade=true;
10. una adquisición tiene requires_trade=true;
11. una adquisición tiene requires_version_exclusive=true;
12. una adquisición tiene requires_external_game=true;
13. una especie no tiene primary_method o proof_scenario;
14. una especie no tiene ruta alcanzable desde un save nuevo o desde una especie obtenible;
15. una forma jugable no tiene acquisition o asset cuando corresponde;
16. un asset approved no tiene hash, licencia o provenance;
17. un follower no tiene clase de escala y colisión;
18. una ubicación, flag, NPC, objeto o evento requerido no existe;
19. una región o fase se declara verified sin evidencia de smoke test;
20. el archivo compilado no es reproducible desde el mismo snapshot y commit.

## Reglas de completabilidad

El reporte de cobertura debe demostrar:

- 493 especies nacionales;
- 493 rutas de obtención dentro de una única partida;
- cero trades obligatorios;
- cero version exclusives;
- cero dependencias de otro juego;
- cada línea evolutiva cerrada;
- cada método especial probado por al menos un escenario;
- cada forma requerida con ruta y asset;
- cada especie con estado separado para data, acquisition, asset y QA.

Completar la Pokédex puede requerir postgame. Eso no es un fallo siempre que el ledger indique la fase y el escenario de prueba.

## Compilación y salidas

La fuente canónica debe producir:

    generated/essentials/pokemon.txt
    generated/essentials/pokemon_forms.txt
    generated/essentials/moves.txt
    generated/essentials/abilities.txt
    generated/essentials/regional_dexes.txt
    generated/manifests/data-manifest.json
    generated/reports/species_coverage.html
    generated/reports/gen4_gap_report.html
    generated/reports/evolution_graph.json

El engine no debe ser la fuente de verdad. Los PBS compilados son artefactos regenerables.

## Validación ejecutable futura

Cuando exista el tooling, el orden recomendado será:

    py -3.13 tools/validate_species_001_493.py
    py -3.13 tools/validate_moves_and_abilities.py
    py -3.13 tools/validate_evolution_graph.py
    py -3.13 tools/validate_forms.py
    py -3.13 tools/validate_acquisition_ledger.py
    py -3.13 tools/validate_no_trade_or_version_exclusive.py
    py -3.13 tools/validate_assets.py
    py -3.13 tools/make_coverage_report.py

En esta etapa son comandos previstos, no ejecutados: todavía no se creó el proyecto del engine ni el tooling.

