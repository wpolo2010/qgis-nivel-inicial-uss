# Ejercicio de georreferenciación — Cartas Nacionales IGN 1:100 000
## Para la Clase 2 (dom 18 oct 2026, 18:00 PET) · estilo AsulGIS · QGIS 3.44 LTR

Dos ejercicios gemelos con hojas completas de la Carta Nacional del IGN (con márgenes: las coordenadas impresas en el marco SON los puntos de control):

- **Ejercicio A — Coordenadas geográficas → destino EPSG:4326.** Hoja de Chiclayo (Lambayeque).
- **Ejercicio B — Coordenadas UTM → destino EPSG:32717 (Zona 17 Sur).** Hoja de Piura.

> Estado de los PDF (actualizado 18 oct, 13:35 PDT): **LAS TRES HOJAS DESCARGADAS Y VERIFICADAS con márgenes completos** en `georreferenciacion/`:
> - `carta-nacional-chiclayo-14d-1-100000.pdf` — CHICLAYO, Serie J631 hoja 0957 (14-d), Ed. 2-IGN (GeoPDF que distribuye el IDEP; obtenido vía GEO GPS PERÚ → Google Drive, porque los portales oficiales no sirven la hoja escaneada: SIGMED caído, IDEP solo vector/índice, UT Austin sin esta hoja en su índice en vivo; GEOCATMIN recorta los márgenes y NO se usó). Marco confirmado por el índice oficial GEOCATMIN (14d.ecw: lon −80 a −79.5, lat −7 a −6.5).
> - `carta-nacional-piura-11b-1-100000.pdf` — PIURA, Serie J631 hoja 0760 (11-b), Ed. 2-IGN, misma procedencia. Marco: lon −80°30′ a −80°00′, lat −5°30′ a −5°00′.
> - `carta-nacional-cajamarca-1156-15f-1-100000.pdf` — respaldo de alta resolución (sección siguiente).
> Los marcos de Chiclayo y Piura coinciden con las tablas de los Ejercicios A y B de abajo. En clase, la primera lectura de esquinas se hace sobre el impreso: si un valor difiriera, manda el impreso.
> Ojo didáctico: estos dos PDF son **GeoPDF** (ya traen georreferenciación embebida) — el ejercicio consiste en georreferenciar a mano como si no la tuvieran; al final, el alumno puede contrastar su resultado contra la posición «real» de la hoja. No decirlo antes de tiempo: es el momento «ajá» del cierre.

---

## ✅ Hoja verificada en mano — CAJAMARCA (Serie J632, hoja 1156 / 15-f, Ed. 1-NIMA–IGN)

Archivo: `georreferenciacion/carta-nacional-cajamarca-1156-15f-1-100000.pdf` (13.7 MB, fuente: Perry-Castañeda Library, UT Austin). Hoja completa con márgenes, leyenda y notas. Marco LEÍDO del impreso: **longitud −79°00′ a −78°30′ · latitud −7°00′ a −7°30′** · cuadrícula UTM **Zona 17** (la hoja lo declara en su margen: «1,000 METROS UTM ZONA 17M», datum WGS 84, con tabla de conversión a PSAD56).

**Ejercicio A′ — Cajamarca con coordenadas geográficas (EPSG:4326)**

| GCP | Esquina | Longitud (X) | Latitud (Y) |
|---|---|---|---|
| 1 | Inferior izquierda (SO) | −79.0000 | −7.5000 |
| 2 | Inferior derecha (SE) | −78.5000 | −7.5000 |
| 3 | Superior izquierda (NO) | −79.0000 | −7.0000 |
| 4 | Superior derecha (NE) | −78.5000 | −7.0000 |
| 5 | Centro | −78.7500 | −7.2500 |

**Ejercicio B′ — Cajamarca con coordenadas UTM (EPSG:32717)**

Valores calculados desde el marco geográfico (WGS 84, proyección transversa de Mercator) y **cotejados con las etiquetas azules impresas** en la hoja (Este 721…776 km, Norte 9170…9226 km — calzan):

| GCP | Esquina | Este (X, m) | Norte (Y, m) |
|---|---|---|---|
| 1 | Inferior izquierda (SO) | 720 702 | 9 170 474 |
| 2 | Inferior derecha (SE) | 775 908 | 9 170 191 |
| 3 | Superior izquierda (NO) | 720 946 | 9 225 781 |
| 4 | Superior derecha (NE) | 776 213 | 9 225 516 |
| 5 | Centro | 748 442 | 9 197 998 |

Con estos dos ejercicios gemelos sobre la MISMA hoja, la clase ve el mismo territorio en los dos sistemas — y el contraste es la lección: mismos puntos, números distintos, CRS destino distinto.

---

## Ejercicio A — Chiclayo con coordenadas geográficas (EPSG:4326)

Marco de la hoja: **longitud −80°00′ a −79°30′ · latitud −7°00′ a −6°30′**

| GCP | Esquina / cruce | Longitud (X) | Latitud (Y) |
|---|---|---|---|
| 1 | Inferior izquierda | −80.0000 | −7.0000 |
| 2 | Inferior derecha | −79.5000 | −7.0000 |
| 3 | Superior izquierda | −80.0000 | −6.5000 |
| 4 | Superior derecha | −79.5000 | −6.5000 |
| 5 | Centro (cruce de retícula) | −79.7500 | −6.7500 |

- En el Georreferenciador: los GCP se ingresan como **X = longitud, Y = latitud** (en ese orden; invertirlos es el error clásico y la hoja «desaparece»).
- CRS de destino del ejercicio: **EPSG:4326**. Transformación: **Polinómica 1**, remuestreo Vecino más cercano, salida GeoTIFF.
- Cierre didáctico (el puente a la Clase 2): medir un distrito sobre la hoja ya georreferenciada en 4326 da valores en **grados** — inútiles. Se reproyecta la salida a EPSG:32717 y recién ahí se mide. Es el mismo tropiezo del archivo del INEI de hoy, ahora visto en papel.

## Ejercicio B — Piura con coordenadas UTM (EPSG:32717)

Marco de la hoja: **longitud −81°00′ a −80°30′ · latitud −5°30′ a −5°00′** (Zona 17 Sur; el borde oeste cae sobre el meridiano central −81°, por eso su Este es exactamente 500 000).

Valores UTM calculados desde la retícula geográfica (WGS84, fórmulas de proyección transversal de Mercator; redondeados al metro):

| GCP | Esquina / cruce | Este (X, m) | Norte (Y, m) |
|---|---|---|---|
| 1 | Inferior izquierda | 500 000 | 9 392 066 |
| 2 | Inferior derecha | 555 384 | 9 392 043 |
| 3 | Superior izquierda | 500 000 | 9 447 336 |
| 4 | Superior derecha | 555 428 | 9 447 315 |
| 5 | Centro | 527 703 | 9 419 695 |

- CRS de destino: **EPSG:32717**. Misma transformación y salida que el Ejercicio A.
- Detalle para explicar en vivo: los Nortes de las dos esquinas de un mismo borde **no son idénticos** (difieren ~20 m) porque el borde de la hoja es un paralelo, no una recta UTM. Por eso se marcan los 5 GCP y se deja que la transformación absorba la diferencia — y por eso un RMS de unos pocos metros en una hoja 1:100 000 es normal, no un error del alumno.

## Flujo en QGIS (ambos ejercicios, ~15 min c/u)

1. Capa → Georreferenciador → Abrir raster (el PDF de la hoja; si QGIS no lo abre directo, exportar la página a PNG a 300 dpi).
2. Configuración de transformación: Polinómica 1 · Vecino más cercano · CRS destino según el ejercicio · salida `*_georref.tif`.
3. Marcar los GCP **en las cruces de la retícula impresa**, en orden de esquina (no en fila), empezando por las 4 esquinas y cerrando con el centro.
4. Iniciar georreferenciación → cargar la salida al proyecto → bajar la opacidad al 60 % y contrastar contra la capa de distritos / base satelital: ríos, costa y vías principales deben calzar.
5. Leer el RMS por punto: si un punto se dispara, casi siempre es un dígito mal tecleado — se corrige el GCP, no se agrega otro encima.

**Criterio de logro (captura para el entregable):** hoja georreferenciada visible sobre la base, con la tabla de GCP abierta y RMS total visible. En 1:100 000, RMS de decenas de metros es esperable por la deformación del papel/escaneo; lo que no se acepta es un desplazamiento sistemático (toda la hoja corrida en una dirección = un GCP mal leído).

## Problemas típicos
- *La hoja cae en el océano / en otro continente* → X e Y invertidos, o signo de longitud sin el menos.
- *«No se puede» guardar el GCP* → falta fijar el CRS destino en la configuración de transformación antes de marcar puntos.
- *RMS enorme con GCP «bien» marcados* → se leyeron las coordenadas geográficas de la hoja UTM (o al revés): cada ejercicio usa SOLO su sistema.
- *El PDF abre recortado sin márgenes* → esa copia no sirve; avisar y usar la otra hoja mientras se consigue la completa.

## Puente a la Clase 4 (dom 25 oct)
Este ejercicio es la versión «en papel» de lo que la Clase 4 hará con un plano CAD/PDF de Chiclayo: mismos GCP, misma lectura del RMS, destino EPSG:32717. Quien domine hoy las dos tablas no necesita explicación nueva ese día.
