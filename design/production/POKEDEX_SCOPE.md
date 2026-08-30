# Pokédex Scope

## Estado

Alcance confirmado: especies 001-493. La tabla es un baseline de producción y cobertura prevista, no una verificación de gameplay. Todas las filas tienen status=planned hasta que exista una implementación y un test de recuperación. Los nombres se normalizaron a partir del endpoint de especies de [PokeAPI](https://pokeapi.co/api/v2/pokemon-species?limit=493&offset=0); la fuente de nombres no implica que los métodos estén implementados.

El conteo es disjunto: 458 especies ordinarias + 35 especies legendarias/míticas = 493. Gen 1-3 contiene 365 ordinarias + 21 legendarias/míticas = 386. Gen 4 contiene 93 ordinarias + 14 legendarias/míticas = 107. No hay species duplicadas por fase ni por método.

## Reglas de producción

- requires_trade=false, requires_version_exclusive=false y requires_external_game=false son objetivos contractuales de diseño; status=planned indica que todavía no están verificados en una build.
- Las evoluciones que normalmente requieren intercambio usarán Cable de Enlace u otro objeto interno equivalente.
- Los métodos primarios y alternativos son categorías de diseño. Deben reemplazarse por IDs de mapa, eventos, flags y tests concretos durante la implementación.
- Si una especie no puede recuperarse después de un fallo, una ventana horaria o una decisión de cadena, su método alternativo no está terminado.
- Gen 4 se concentra principalmente en postgame de Litoral de Bruma. No implica una región Sinnoh.

## Tabla completa

| ID | Especie | Generación | Clase | Fase prevista | Método primario | Método alternativo | requires_trade | requires_version_exclusive | requires_external_game | status |
|---|---|---:|---|---|---|---|---|---|---|---|
| 001 | Bulbasaur | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 002 | Ivysaur | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 003 | Venusaur | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 004 | Charmander | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 005 | Charmeleon | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 006 | Charizard | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 007 | Squirtle | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 008 | Wartortle | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 009 | Blastoise | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 010 | Caterpie | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 011 | Metapod | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 012 | Butterfree | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 013 | Weedle | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 014 | Kakuna | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 015 | Beedrill | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 016 | Pidgey | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 017 | Pidgeotto | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 018 | Pidgeot | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 019 | Rattata | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 020 | Raticate | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 021 | Spearow | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 022 | Fearow | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 023 | Ekans | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 024 | Arbok | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 025 | Pikachu | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 026 | Raichu | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 027 | Sandshrew | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 028 | Sandslash | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 029 | Nidoran-F | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 030 | Nidorina | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 031 | Nidoqueen | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 032 | Nidoran-M | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 033 | Nidorino | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 034 | Nidoking | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 035 | Clefairy | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 036 | Clefable | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 037 | Vulpix | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 038 | Ninetales | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 039 | Jigglypuff | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 040 | Wigglytuff | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 041 | Zubat | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 042 | Golbat | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 043 | Oddish | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 044 | Gloom | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 045 | Vileplume | 1 | ordinary | campaign_early | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 046 | Paras | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 047 | Parasect | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 048 | Venonat | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 049 | Venomoth | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 050 | Diglett | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 051 | Dugtrio | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 052 | Meowth | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 053 | Persian | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 054 | Psyduck | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 055 | Golduck | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 056 | Mankey | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 057 | Primeape | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 058 | Growlithe | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 059 | Arcanine | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 060 | Poliwag | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 061 | Poliwhirl | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 062 | Poliwrath | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 063 | Abra | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 064 | Kadabra | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 065 | Alakazam | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 066 | Machop | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 067 | Machoke | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 068 | Machamp | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 069 | Bellsprout | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 070 | Weepinbell | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 071 | Victreebel | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 072 | Tentacool | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 073 | Tentacruel | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 074 | Geodude | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 075 | Graveler | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 076 | Golem | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 077 | Ponyta | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 078 | Rapidash | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 079 | Slowpoke | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 080 | Slowbro | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 081 | Magnemite | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 082 | Magneton | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 083 | Farfetch'd | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 084 | Doduo | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 085 | Dodrio | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 086 | Seel | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 087 | Dewgong | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 088 | Grimer | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 089 | Muk | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 090 | Shellder | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 091 | Cloyster | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 092 | Gastly | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 093 | Haunter | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 094 | Gengar | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 095 | Onix | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 096 | Drowzee | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 097 | Hypno | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 098 | Krabby | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 099 | Kingler | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 100 | Voltorb | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 101 | Electrode | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 102 | Exeggcute | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 103 | Exeggutor | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 104 | Cubone | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 105 | Marowak | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 106 | Hitmonlee | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 107 | Hitmonchan | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 108 | Lickitung | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 109 | Koffing | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 110 | Weezing | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 111 | Rhyhorn | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 112 | Rhydon | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 113 | Chansey | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 114 | Tangela | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 115 | Kangaskhan | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 116 | Horsea | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 117 | Seadra | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 118 | Goldeen | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 119 | Seaking | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 120 | Staryu | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 121 | Starmie | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 122 | Mr. Mime | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 123 | Scyther | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 124 | Jynx | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 125 | Electabuzz | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 126 | Magmar | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 127 | Pinsir | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 128 | Tauros | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 129 | Magikarp | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 130 | Gyarados | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 131 | Lapras | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 132 | Ditto | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 133 | Eevee | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 134 | Vaporeon | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 135 | Jolteon | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 136 | Flareon | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 137 | Porygon | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 138 | Omanyte | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 139 | Omastar | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 140 | Kabuto | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 141 | Kabutops | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 142 | Aerodactyl | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 143 | Snorlax | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 144 | Articuno | 1 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 145 | Zapdos | 1 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 146 | Moltres | 1 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 147 | Dratini | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 148 | Dragonair | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 149 | Dragonite | 1 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 150 | Mewtwo | 1 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 151 | Mew | 1 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 152 | Chikorita | 2 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 153 | Bayleef | 2 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 154 | Meganium | 2 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 155 | Cyndaquil | 2 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 156 | Quilava | 2 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 157 | Typhlosion | 2 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 158 | Totodile | 2 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 159 | Croconaw | 2 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 160 | Feraligatr | 2 | ordinary | campaign_mid | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 161 | Sentret | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 162 | Furret | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 163 | Hoothoot | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 164 | Noctowl | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 165 | Ledyba | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 166 | Ledian | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 167 | Spinarak | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 168 | Ariados | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 169 | Crobat | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 170 | Chinchou | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 171 | Lanturn | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 172 | Pichu | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 173 | Cleffa | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 174 | Igglybuff | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 175 | Togepi | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 176 | Togetic | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 177 | Natu | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 178 | Xatu | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 179 | Mareep | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 180 | Flaaffy | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 181 | Ampharos | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 182 | Bellossom | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 183 | Marill | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 184 | Azumarill | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 185 | Sudowoodo | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 186 | Politoed | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 187 | Hoppip | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 188 | Skiploom | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 189 | Jumpluff | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 190 | Aipom | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 191 | Sunkern | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 192 | Sunflora | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 193 | Yanma | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 194 | Wooper | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 195 | Quagsire | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 196 | Espeon | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 197 | Umbreon | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 198 | Murkrow | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 199 | Slowking | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 200 | Misdreavus | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 201 | Unown | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 202 | Wobbuffet | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 203 | Girafarig | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 204 | Pineco | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 205 | Forretress | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 206 | Dunsparce | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 207 | Gligar | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 208 | Steelix | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 209 | Snubbull | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 210 | Granbull | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 211 | Qwilfish | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 212 | Scizor | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 213 | Shuckle | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 214 | Heracross | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 215 | Sneasel | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 216 | Teddiursa | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 217 | Ursaring | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 218 | Slugma | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 219 | Magcargo | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 220 | Swinub | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 221 | Piloswine | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 222 | Corsola | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 223 | Remoraid | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 224 | Octillery | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 225 | Delibird | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 226 | Mantine | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 227 | Skarmory | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 228 | Houndour | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 229 | Houndoom | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 230 | Kingdra | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 231 | Phanpy | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 232 | Donphan | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 233 | Porygon2 | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 234 | Stantler | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 235 | Smeargle | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 236 | Tyrogue | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 237 | Hitmontop | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 238 | Smoochum | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 239 | Elekid | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 240 | Magby | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 241 | Miltank | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 242 | Blissey | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 243 | Raikou | 2 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 244 | Entei | 2 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 245 | Suicune | 2 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 246 | Larvitar | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 247 | Pupitar | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 248 | Tyranitar | 2 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 249 | Lugia | 2 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 250 | Ho-Oh | 2 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 251 | Celebi | 2 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 252 | Treecko | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 253 | Grovyle | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 254 | Sceptile | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 255 | Torchic | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 256 | Combusken | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 257 | Blaziken | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 258 | Mudkip | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 259 | Marshtomp | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 260 | Swampert | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 261 | Poochyena | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 262 | Mightyena | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 263 | Zigzagoon | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 264 | Linoone | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 265 | Wurmple | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 266 | Silcoon | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 267 | Beautifly | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 268 | Cascoon | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 269 | Dustox | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 270 | Lotad | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 271 | Lombre | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 272 | Ludicolo | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 273 | Seedot | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 274 | Nuzleaf | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 275 | Shiftry | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 276 | Taillow | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 277 | Swellow | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 278 | Wingull | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 279 | Pelipper | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 280 | Ralts | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 281 | Kirlia | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 282 | Gardevoir | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 283 | Surskit | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 284 | Masquerain | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 285 | Shroomish | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 286 | Breloom | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 287 | Slakoth | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 288 | Vigoroth | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 289 | Slaking | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 290 | Nincada | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 291 | Ninjask | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 292 | Shedinja | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 293 | Whismur | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 294 | Loudred | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 295 | Exploud | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 296 | Makuhita | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 297 | Hariyama | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 298 | Azurill | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 299 | Nosepass | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 300 | Skitty | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 301 | Delcatty | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 302 | Sableye | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 303 | Mawile | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 304 | Aron | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 305 | Lairon | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 306 | Aggron | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 307 | Meditite | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 308 | Medicham | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 309 | Electrike | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 310 | Manectric | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 311 | Plusle | 3 | ordinary | campaign_late | wild encounter: campaign habitat assigned in encounter table | gift, egg or evolution path in campaign | false | false | false | planned |
| 312 | Minun | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 313 | Volbeat | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 314 | Illumise | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 315 | Roselia | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 316 | Gulpin | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 317 | Swalot | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 318 | Carvanha | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 319 | Sharpedo | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 320 | Wailmer | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 321 | Wailord | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 322 | Numel | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 323 | Camerupt | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 324 | Torkoal | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 325 | Spoink | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 326 | Grumpig | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 327 | Spinda | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 328 | Trapinch | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 329 | Vibrava | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 330 | Flygon | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 331 | Cacnea | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 332 | Cacturne | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 333 | Swablu | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 334 | Altaria | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 335 | Zangoose | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 336 | Seviper | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 337 | Lunatone | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 338 | Solrock | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 339 | Barboach | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 340 | Whiscash | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 341 | Corphish | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 342 | Crawdaunt | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 343 | Baltoy | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 344 | Claydol | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 345 | Lileep | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 346 | Cradily | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 347 | Anorith | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 348 | Armaldo | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 349 | Feebas | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 350 | Milotic | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 351 | Castform | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 352 | Kecleon | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 353 | Shuppet | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 354 | Banette | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 355 | Duskull | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 356 | Dusclops | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 357 | Tropius | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 358 | Chimecho | 3 | ordinary | postgame_habitat | wild encounter: postgame habitat assigned in encounter table | postgame sidequest reward or evolution path | false | false | false | planned |
| 359 | Absol | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 360 | Wynaut | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 361 | Snorunt | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 362 | Glalie | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 363 | Spheal | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 364 | Sealeo | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 365 | Walrein | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 366 | Clamperl | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 367 | Huntail | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 368 | Gorebyss | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 369 | Relicanth | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 370 | Luvdisc | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 371 | Bagon | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 372 | Shelgon | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 373 | Salamence | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 374 | Beldum | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 375 | Metang | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 376 | Metagross | 3 | ordinary | postgame_rare | swarm, rare fishing or exploration chain | recoverable gift or evolution path | false | false | false | planned |
| 377 | Regirock | 3 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 378 | Regice | 3 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 379 | Registeel | 3 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 380 | Latias | 3 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 381 | Latios | 3 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 382 | Kyogre | 3 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 383 | Groudon | 3 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 384 | Rayquaza | 3 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 385 | Jirachi | 3 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 386 | Deoxys | 3 | legendary-mythical | postgame_legendary_gen1_3 | legendary-chain: sanctuary, route or postgame landmark | none; recovery flag reopens the chain | false | false | false | planned |
| 387 | Turtwig | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 388 | Grotle | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 389 | Torterra | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 390 | Chimchar | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 391 | Monferno | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 392 | Infernape | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 393 | Piplup | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 394 | Prinplup | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 395 | Empoleon | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 396 | Starly | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 397 | Staravia | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 398 | Staraptor | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 399 | Bidoof | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 400 | Bibarel | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 401 | Kricketot | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 402 | Kricketune | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 403 | Shinx | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 404 | Luxio | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 405 | Luxray | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 406 | Budew | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 407 | Roserade | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 408 | Cranidos | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 409 | Rampardos | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 410 | Shieldon | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 411 | Bastiodon | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 412 | Burmy | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 413 | Wormadam | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 414 | Mothim | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 415 | Combee | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 416 | Vespiquen | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 417 | Pachirisu | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 418 | Buizel | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 419 | Floatzel | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 420 | Cherubi | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 421 | Cherrim | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 422 | Shellos | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 423 | Gastrodon | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 424 | Ambipom | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 425 | Drifloon | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 426 | Drifblim | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 427 | Buneary | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 428 | Lopunny | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 429 | Mismagius | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 430 | Honchkrow | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 431 | Glameow | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 432 | Purugly | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 433 | Chingling | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 434 | Stunky | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 435 | Skuntank | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 436 | Bronzor | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 437 | Bronzong | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 438 | Bonsly | 4 | ordinary | postgame_habitat | wild encounter: Península del Velo habitat | postgame sidequest or alternate habitat | false | false | false | planned |
| 439 | Mime Jr. | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 440 | Happiny | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 441 | Chatot | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 442 | Spiritomb | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 443 | Gible | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 444 | Gabite | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 445 | Garchomp | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 446 | Munchlax | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 447 | Riolu | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 448 | Lucario | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 449 | Hippopotas | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 450 | Hippowdon | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 451 | Skorupi | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 452 | Drapion | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 453 | Croagunk | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 454 | Toxicroak | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 455 | Carnivine | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 456 | Finneon | 4 | ordinary | postgame_gift | gift, egg or rescue chain | wild encounter in a later postgame habitat | false | false | false | planned |
| 457 | Lumineon | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 458 | Mantyke | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 459 | Snover | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 460 | Abomasnow | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 461 | Weavile | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 462 | Magnezone | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 463 | Lickilicky | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 464 | Rhyperior | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 465 | Tangrowth | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 466 | Electivire | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 467 | Magmortar | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 468 | Togekiss | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 469 | Yanmega | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 470 | Leafeon | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 471 | Glaceon | 4 | ordinary | postgame_evolution | evolution without trade: item, move, friendship, level or location | capture the pre-evolution and obtain the evolution requirement in-game | false | false | false | planned |
| 472 | Gliscor | 4 | ordinary | postgame_swarm_chain | swarm, rare fishing or exploration chain | recoverable gift or alternate postgame encounter | false | false | false | planned |
| 473 | Mamoswine | 4 | ordinary | postgame_swarm_chain | swarm, rare fishing or exploration chain | recoverable gift or alternate postgame encounter | false | false | false | planned |
| 474 | Porygon-Z | 4 | ordinary | postgame_swarm_chain | swarm, rare fishing or exploration chain | recoverable gift or alternate postgame encounter | false | false | false | planned |
| 475 | Gallade | 4 | ordinary | postgame_swarm_chain | swarm, rare fishing or exploration chain | recoverable gift or alternate postgame encounter | false | false | false | planned |
| 476 | Probopass | 4 | ordinary | postgame_swarm_chain | swarm, rare fishing or exploration chain | recoverable gift or alternate postgame encounter | false | false | false | planned |
| 477 | Dusknoir | 4 | ordinary | postgame_swarm_chain | swarm, rare fishing or exploration chain | recoverable gift or alternate postgame encounter | false | false | false | planned |
| 478 | Froslass | 4 | ordinary | postgame_swarm_chain | swarm, rare fishing or exploration chain | recoverable gift or alternate postgame encounter | false | false | false | planned |
| 479 | Rotom | 4 | ordinary | postgame_swarm_chain | swarm, rare fishing or exploration chain | recoverable gift or alternate postgame encounter | false | false | false | planned |
| 480 | Uxie | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |
| 481 | Mesprit | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |
| 482 | Azelf | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |
| 483 | Dialga | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |
| 484 | Palkia | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |
| 485 | Heatran | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |
| 486 | Regigigas | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |
| 487 | Giratina | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |
| 488 | Cresselia | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |
| 489 | Phione | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |
| 490 | Manaphy | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |
| 491 | Darkrai | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |
| 492 | Shaymin | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |
| 493 | Arceus | 4 | legendary-mythical | postgame_legendary_gen4 | legendary-chain: ruin, tide, meteorite or Meridiano archive | none; recovery flag reopens the chain | false | false | false | planned |

## Conteo de control

- IDs: 001-493, contiguos y únicos.
- Ordinarias: 458.
- Legendarias/míticas: 35.
- Gen 1-3: 386.
- Gen 4: 107.
- Total: **493**.
- Estado actual: **planned**, no coverage verified.

