# Plan del spike técnico 493

## Objetivo

Demostrar que Pokémon Essentials v21.1 puede sostener el contrato real del proyecto antes de producir campaña, mapas grandes o los 107 followers finales.

El spike no busca hacer un vertical slice bonito. Busca producir evidencia reproducible sobre datos, compilación, evolución, forms, follower, día/noche, save/load, QA y packaging.

No se instalarán herramientas durante esta fase documental.

## Criterio general

Un gate es hard pass/fail:

- Pass: existe evidencia guardable, repetible y revisable por otra persona.
- Fail: hay error, comportamiento no determinista, dependencia manual no documentada o cobertura simulada.
- Pending: no se probó todavía. Pending no habilita producción grande.
- Blocked: la herramienta o plugin impide obtener evidencia confiable.

Un workaround es inaceptable cuando oculta el incumplimiento del contrato, depende de un juego externo o convierte una prueba automatizable en una inspección manual única.

## Gate 0: preparación auditable

Pass si:

- el commit del spike y las versiones de engine/plugin están fijados;
- existe schema canónico y snapshot de datos;
- existe ROSTER_LEDGER.csv con IDs 001-493;
- el ledger tiene columnas de estado y proof_scenario;
- los datos y assets tienen provenance separada;
- se puede reconstruir el mismo input desde una carpeta limpia.

Fail si:

- se edita sólo dentro del editor sin fuente regenerable;
- se usa una lista de 493 sin vínculo con datos compilables;
- se confunden placeholders con cobertura;
- no se puede identificar qué versión de datos o plugin produjo la build.

## Gate 1: carga y compilación de 493

Pass si:

- el schema carga exactamente 493 especies;
- los IDs son contiguos 001-493 y no duplicados;
- Essentials compila los datos sin errores;
- la Dex Nacional se configura con 493 especies;
- tipos, habilidades, movimientos, formas y evoluciones referenciados existen;
- una segunda compilación con los mismos inputs produce el mismo manifest;
- la compilación se puede repetir sin editar manualmente 493 entradas.

Fail si:

- hay que truncar el roster a 386;
- alguna especie Gen 4 sólo aparece como comentario, placeholder no compilable o fila ignorada;
- el editor acepta datos que el compilador externo no puede validar;
- hay que corregir a mano archivos generados después de cada compilación.

Workaround inaceptable:

- declarar “493 soportadas” mientras sólo se compilan seis;
- mantener 107 filas deshabilitadas sin una razón de schema documentada;
- usar una Dex visual de 493 sin rutas de adquisición.

## Gate 2: seis líneas de Gen 4

Las pruebas mínimas son:

1. Turtwig -> Grotle -> Torterra, línea de tres etapas por nivel.
2. Budew -> Roselia -> Roserade, bebé, amistad/tiempo y piedra.
3. Riolu -> Lucario, amistad y hora del día.
4. Magneton -> Magnezone, evolución Gen 4 de especie previa y condición interna equivalente.
5. Electabuzz -> Electivire, sustitución explícita del trade por un método interno.
6. Rotom, cambio de forma y persistencia del estado.

Pass si cada línea:

- parte de una obtención reproducible;
- ejecuta su condición de evolución;
- muestra la evolución en runtime;
- se guarda y carga sin perder el estado;
- actualiza la Dex;
- mantiene el asset correcto;
- no requiere trade, version exclusive ni juego externo;
- tiene un proof_scenario que otro runner puede repetir.

Fail si una evolución sólo funciona editando directamente el save, usando un evento de debug no disponible en una partida o saltando la condición real.

Workarounds inaceptables:

- evolucionar cualquier especie mediante un botón universal de debug;
- reemplazar Electivire por una especie distinta;
- marcar Magnezone como obtenido aunque no exista una condición jugable;
- probar Rotom sólo en la Dex sin cambiar su forma en una partida.

## Gate 3: formas y follower

Pass si:

- Rotom puede cambiar de forma y volver a cargar correctamente;
- el sistema resuelve follower por especie y forma;
- se prueban una especie pequeña, una grande y una forma especial;
- el follower no se duplica;
- no queda bloqueado en puertas, escaleras, puentes o agua;
- no rompe warps ni entrada/salida de combate;
- tiene fallback explícito para assets faltantes;
- la clase de escala, colisión y animación queda registrada.

Fail si:

- el follower sólo funciona con un sprite genérico sin demostrar resolución por especie;
- una forma carga el follower de otra forma sin una decisión explícita;
- el plugin rompe la transferencia, el save/load o la batalla;
- la colisión exige mapas diseñados alrededor de bugs desconocidos.

Workarounds inaceptables:

- desactivar follower en postgame;
- ocultar el follower de las seis pruebas;
- usar un sprite placeholder como evidencia de asset final;
- corregir cada mapa manualmente sin registrar una regla general.

## Gate 4: batalla Gen 4-lite

Pass si:

- la separación física/especial por movimiento se comporta como está especificada;
- sólo se habilitan movimientos, habilidades, tipos e ítems aprobados por el perfil;
- no aparecen gimmicks posteriores no decididas;
- los seis casos del spike pueden combatir;
- los learnsets compilados coinciden con el catálogo congelado;
- cualquier excepción histórica queda documentada;
- el perfil no requiere parches invasivos que bloqueen el resto del engine.

Fail si:

- no se puede saber qué reglas están activas;
- las especies usan movimientos o habilidades fuera del perfil;
- la configuración rompe captura, evolución, save/load o follower;
- se promete paridad completa sin pruebas de fórmulas y orden de resolución.

Workaround inaceptable:

- llamar “Gen 4” a una configuración moderna sin documentar diferencias;
- copiar una tabla de movimientos sin probar sus efectos;
- excluir una especie porque su habilidad o forma no entra en el perfil sin registrarlo como decisión.

## Gate 5: día/noche y obtención

Pass si:

- una especie de campaña y una de postgame tienen rutas separadas;
- se prueba al menos una condición de horario;
- se prueba al menos una evolución dependiente de horario;
- se demuestra que la ruta funciona en una única partida;
- el ledger no contiene trade, version exclusive ni external game;
- la Pokédex muestra estado coherente después de captura, regalo, evolución y forma.

Fail si:

- postgame sólo existe como texto sin encuentro o recompensa jugable;
- las condiciones dependen de cambiar el reloj del sistema manualmente;
- la cobertura sólo se consigue con otro save, versión o jugador;
- el ledger dice planned/pending pero el reporte lo cuenta como verified.

Workarounds inaceptables:

- entregar especies mediante un save externo;
- usar intercambio local obligatorio;
- cambiar flags internos sin ejecutar el método que verá el jugador;
- contar una línea como completa aunque falte su forma o evolución requerida.

## Gate 6: save/load y regresión

Pass si:

- se guarda y carga una partida con una especie Gen 4;
- se guarda y carga después de evolucionar;
- se guarda y carga con Rotom en una forma alternativa;
- el follower reaparece correctamente;
- la Dex conserva especie y forma según la política elegida;
- los datos no cambian entre dos builds con el mismo manifest;
- un smoke test desde save preparado produce el mismo resultado.

Fail si:

- la forma se pierde;
- la evolución retrocede;
- el follower queda en un estado inválido;
- una compilación borra datos anteriores sin migración documentada;
- el resultado depende del orden en que se abrieron los mapas.

Workaround inaceptable:

- no probar save/load;
- borrar los saves antes de declarar el test;
- usar sólo partidas nuevas cuando el cambio afecta datos persistidos.

## Gate 7: build limpia y hash

Pass si:

- la build arranca en una carpeta limpia;
- no necesita el editor, Ruby externo ni archivos locales no declarados;
- contiene el manifest de engine, datos, schema, assets, commit y seed;
- produce SHA256SUMS.txt;
- una segunda build reproducible identifica las mismas entradas;
- los logs y el qa-report quedan junto al artefacto.

Fail si:

- sólo funciona en el equipo de desarrollo;
- faltan DLLs, assets o datos no versionados;
- el hash cambia sin una explicación en el manifest;
- el build depende de archivos temporales o rutas absolutas.

Workaround inaceptable:

- copiar manualmente archivos hasta que arranque;
- ignorar el hash porque “el juego se ve igual”;
- declarar build limpia usando la misma carpeta de desarrollo.

## Evidencia mínima a guardar

    spike/
      input-manifest.json
      data-manifest.json
      compile-log.txt
      evolution-scenarios.json
      follower-scenarios.json
      battle-profile-report.json
      save-load-report.json
      coverage-report.json
      qa-report.json
      build-manifest.json
      SHA256SUMS.txt
      screenshots/
      logs/

La evidencia visual ayuda, pero no reemplaza logs, manifests ni escenarios reproducibles.

## Qué queda fuera del spike

No se va a probar todavía:

- Sinnoh completo;
- 493 followers finales;
- 35 cadenas legendarias completas;
- publicación pública;
- distribución comercial;
- campaña completa de 5 a 8 horas;
- postgame completo;
- todos los mapas finales;
- todos los trainers finales;
- todos los learnsets balanceados;
- parity exacta con Diamond/Pearl/Platinum;
- breeding como requisito de completitud;
- Pokéathlon, crafting o gimmicks posteriores.

La exclusión de estos puntos no reduce el contrato del roster. Significa que el spike prueba la arquitectura y las clases de riesgo, no que el juego terminado ya tenga 493 assets ni contenido final.

## Decisión después del spike

Continuar con Essentials si todos los gates 0-7 pasan y no hay workaround inaceptable.

Pasar a Godot si:

- Essentials no puede compilar o validar 493 de forma repetible;
- Following Pokémon EX no puede sostener la muestra;
- las evoluciones internas requieren parches frágiles;
- save/load o forms son inestables;
- la build limpia no es reproducible.

No pasar a producción grande con gates pending en compilación, follower, evolución, save/load o build.

