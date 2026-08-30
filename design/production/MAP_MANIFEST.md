# Map Manifest

## Regla de conteo

Un mapa jugable es una escena navegable cargada como una unidad, con layout, colisiones y eventos propios. El manifiesto tiene exactamente 55 cargas independientes: 6 pueblos, 9 rutas, 8 landmarks, 6 gimnasios, 1 Liga, 4 áreas postgame y 21 interiores. Faro y acuario son subzonas del único mapa LAND05; no se cuentan dos veces. Las subzonas internas de cualquier fila no agregan mapas.

| ID | Categoría | Nombre de trabajo | Zona | Fase | Carga independiente | Notas |
|---|---|---|---|---|---|---|
| TOWN01 | town | Pueblo Umbral | Litoral de Bruma | campaign | yes | Inicio; exterior del pueblo; no incluye interiores listados aparte. |
| TOWN02 | town | Villa Salitre | Litoral de Bruma | campaign | yes | Mercado y embarcadero exterior. |
| TOWN03 | town | Ciudad Vértice | Litoral de Bruma | campaign | yes | Nudo ferroviario y comercial. |
| TOWN04 | town | Poblado Lúmina | Litoral de Bruma | campaign | yes | Acceso al humedal y casa de pescador. |
| TOWN05 | town | Puerto Farallón | Litoral de Bruma | campaign | yes | Acantilados y acceso al complejo Faro-Acuario. |
| TOWN06 | town | Cuenca Ferrita | Litoral de Bruma | campaign | yes | Pueblo minero y taller. |
| ROUTE01 | route | Ruta del Canal | Umbral-Salitre | campaign | yes | Primer trayecto; conecta con Estación Vieja. |
| ROUTE02 | route | Sendero Nimbo | Salitre-Bosque | campaign | yes | Ruta corta con niebla. |
| ROUTE03 | route | Camino de Vértice | Bosque-Vértice | campaign | yes | Atajo y primer nodo de señales. |
| ROUTE04 | route | Pasarelas Lúmina | Vértice-Lúmina | campaign | yes | Ruta elevada sobre humedal. |
| ROUTE05 | route | Ruta del Puerto | Lúmina-Farallón | campaign | yes | Tramo costero; habilita Surf después. |
| ROUTE06 | route | Sendero Ferrita | Farallón-Ferrita | campaign | yes | Pendiente y entradas a la cantera. |
| ROUTE07 | route | Camino de Cénit | Ferrita-Observatorio | campaign | yes | Ascenso previo a la sexta medalla. |
| ROUTE08 | route | Ruta del Arco | Observatorio-Liga | campaign | yes | Tramo final y prueba de convergencia. |
| ROUTE09 | route | Camino de Regreso | Liga-Umbral | campaign | yes | Retorno de campaña; cambia de estado en postgame. |
| LAND01 | landmark | Estación Vieja | Ruta del Canal | campaign | yes | Una carga; andén y sala de baliza son subzonas del mismo mapa. |
| LAND02 | landmark | Bosque Nimbo | Sendero Nimbo | campaign | yes | Bosque principal; día/noche y follower. |
| LAND03 | landmark | Santuario de Mareas | Ruta del Canal | campaign | yes | Ruinas bajas; no incluye la Isla de Marea Baja. |
| LAND04 | landmark | Humedal Profundo | Poblado Lúmina | campaign | yes | Sector interior del humedal; pesca y pasarelas. |
| LAND05 | landmark | Complejo Faro-Acuario | Puerto Farallón | campaign | yes | Faro y acuario son subzonas de una única carga; no contar por separado. |
| LAND06 | landmark | Ruinas de Eco | Ciudad Vértice | campaign | yes | Landmark de memoria y registros. |
| LAND07 | landmark | Cantera Ferrita | Cuenca Ferrita | campaign | yes | Cantera y túnel de servicio en una única carga. |
| LAND08 | landmark | Observatorio Cénit | Camino de Cénit | campaign | yes | Observatorio principal; la Cumbre del Observatorio es postgame y separada. |
| GYM01 | gym | Gimnasio Sal | Villa Salitre | campaign | yes | Medalla 1; puzzle de corrientes. |
| GYM02 | gym | Gimnasio Niebla | Ciudad Vértice | campaign | yes | Medalla 2; lectura de señales. |
| GYM03 | gym | Gimnasio Marea | Poblado Lúmina | campaign | yes | Medalla 3; altura de agua. |
| GYM04 | gym | Gimnasio Faro | Puerto Farallón | campaign | yes | Medalla 4; luz y navegación. |
| GYM05 | gym | Gimnasio Ferrita | Cuenca Ferrita | campaign | yes | Medalla 5; presión y resistencia. |
| GYM06 | gym | Gimnasio Cénit | Observatorio Cénit | campaign | yes | Medalla 6; decisiones de ruta. |
| LEAGUE01 | league | Liga del Arco | Ruta del Arco | campaign | yes | Cuatro combates y sala final; no incluye la coda. |
| POST01 | postgame | Península del Velo | Litoral de Bruma | postgame | yes | Hub de postgame; hábitats Gen 4 y rutas de marea. |
| POST02 | postgame | Laboratorio de Meridiano | Península del Velo | postgame | yes | Reparación del sistema y cadenas de evolución. |
| POST03 | postgame | Isla de Marea Baja | Península del Velo | postgame | yes | Acceso por ventana de marea; no es una región separada. |
| POST04 | postgame | Cumbre del Observatorio | Península del Velo | postgame | yes | Superboss y señales residuales; separada de Observatorio Cénit. |
| INT01 | interior | Casa de Sofi | Pueblo Umbral | campaign | yes | Inicio y guardado narrativo. |
| INT02 | interior | Laboratorio Umbral | Pueblo Umbral | campaign | yes | Starter, Pokédex y Brújula. |
| INT03 | interior | Centro Pokémon Umbral | Pueblo Umbral | campaign | yes | Curación y PC. |
| INT04 | interior | Mercado Salitre | Villa Salitre | campaign | yes | Tienda y comerciante. |
| INT05 | interior | Centro Pokémon Salitre | Villa Salitre | campaign | yes | Curación y PC. |
| INT06 | interior | Casa de Crianza Salitre | Villa Salitre | campaign | yes | Huevos y cadena de crianza. |
| INT07 | interior | Estación Vértice | Ciudad Vértice | campaign | yes | Vestíbulo; Estación Vieja es otro landmark. |
| INT08 | interior | Centro Pokémon Vértice | Ciudad Vértice | campaign | yes | Curación y PC. |
| INT09 | interior | Radio Vértice | Ciudad Vértice | campaign | yes | Brújula, rumores y swarms. |
| INT10 | interior | Casa de Mapas Vértice | Ciudad Vértice | campaign | yes | Notas y cartografía. |
| INT11 | interior | Centro Pokémon Lúmina | Poblado Lúmina | campaign | yes | Curación y PC. |
| INT12 | interior | Casa del Pescador | Poblado Lúmina | campaign | yes | Pesca y rumores de marea. |
| INT13 | interior | Refugio del Humedal | Poblado Lúmina | campaign | yes | Sidequest ecológica. |
| INT14 | interior | Centro Pokémon Farallón | Puerto Farallón | campaign | yes | Curación y PC. |
| INT15 | interior | Casa de Mareas | Puerto Farallón | campaign | yes | Archivo marítimo; Faro-Acuario no se duplica. |
| INT16 | interior | Centro Pokémon Ferrita | Cuenca Ferrita | campaign | yes | Curación y PC. |
| INT17 | interior | Taller Ferrita | Cuenca Ferrita | campaign | yes | Objetos de campo y Núcleo de Meridiano. |
| INT18 | interior | Archivo de Nahue | Ciudad Vértice | campaign | yes | Registro de Gen 1-3; apéndice Gen 4 en postgame. |
| INT19 | interior | Sala de Registros Meridiano | Península del Velo | postgame | yes | Logs y requisitos de cadenas. |
| INT20 | interior | Refugio de la Liga | Liga del Arco | campaign | yes | Preparación y recuperación. |
| INT21 | interior | Cámara de Recuperación | Península del Velo | postgame | yes | Fallback de sidequests y especies perdibles. |

## Conteo auditado

- Pueblos: 6
- Rutas: 9
- Landmarks: 8
- Gimnasios: 6
- Liga: 1
- Postgame: 4
- Interiores: 21
- Total: **55**

Todas las filas son cargas independientes. El manifiesto no presupone que cada gimnasio tenga varias cargas; si el engine lo exige, debe fusionarse otro interior para conservar el máximo de 55.

