# Clase 2 (dom 18 oct) — Tarjeta de rescate: la descarga del INEI, verificada

**El riesgo de mañana:** la práctica del Bloque 4 pide que cada estudiante descargue en vivo la capa de límites distritales del INEI. Verificado hoy (sáb 17 oct, 12:36 p. m. PDT) contra el portal real:

## Lo que el portal realmente entrega (verificado)

- Portal: https://ide.inei.gob.pe/ → sección «Descarga de capas cartográficas» (ancla `#capas` en la misma página de inicio; no hay subpágina).
- Enlace directo, capa «Distrital (Actualizado al 2023)»: **https://ide.inei.gob.pe/files/Distrito.rar**
- El portal dice que las capas se descargan en formato GeoPackage, **pero el enlace real es un archivo .rar de 13,0 MB** (Content-Length 13 053 124 bytes; última modificación del servidor: 6 mar 2026).
- Contenido del .rar **(extraído y verificado)**: un solo archivo, `DISTRITO.gpkg` (29,1 MB descomprimido), capa DISTRITO con **1 890 distritos** de todo el Perú, campos ccdd/ccpp/ccdi/ubigeo/nombdist/nombprov/nombdep/fuente — y ojo: su CRS nativo es **EPSG:4326** (grados), no 32717. Al cargarla, QGIS la reproyecta al vuelo al CRS del proyecto; sirve para reforzar en vivo el punto del Bloque 3: **con la capa en grados no se mide** — el proyecto debe estar en EPSG:32717.

## Los 3 tropiezos previsibles (y su arreglo en 1 minuto)

1. **«No puedo abrir el .rar»** — Windows no abre .rar sin programa. Arreglo: 7-Zip (gratuito, 7-zip.org) o la herramienta «Extraer» de Windows 11 (versiones recientes sí soportan .rar). En la mesa de ayuda de los primeros 10 min, preguntar primero esto, no la instalación de QGIS.
2. **«¿Dónde está el .gpkg?»** — sí está, pero **dentro** del .rar: al extraer aparece `DISTRITO.gpkg`. En QGIS se carga igual: Capa → Añadir capa vectorial, o arrastrar el archivo al lienzo.
3. **Descarga lenta en vivo** — son 13 MB por estudiante, todos a la vez. Plan B **ya construido**: `clase-2-respaldo/distritos-chiclayo.gpkg` (esta misma carpeta del curso) — solo los **20 distritos de la provincia de Chiclayo**, ya en **EPSG:32717**, **256 KB**. Se comparte por el chat de la clase en segundos y la práctica sigue casi idéntica (cargar → simbología + etiquetas → comprobar medidas en metros); solo se salta el paso de filtrar/exportar, que se puede mostrar en pantalla con el archivo completo del docente.

## Guion de 20 segundos para abrir el Bloque 4

> «El enlace del INEI baja un archivo comprimido .rar de 13 MB — no se asusten. Lo extraen, cargan la capa en QGIS y seguimos. Si a alguien le demora la descarga, en el chat de la clase les dejo el respaldo con solo los distritos de Chiclayo: la práctica es la misma.»

---
_Nota de verificación (Astro, sáb 17 oct 2026, ~12:50 p. m. PDT): el .rar se descargó y extrajo de verdad desde este equipo; el .gpkg interno se leyó (1 890 distritos, EPSG:4326) y el respaldo se generó filtrando `nombprov = CHICLAYO` (20 distritos: Cayaltí, Chiclayo, Chongoyape, Eten, Eten Puerto, José Leonardo Ortiz, La Victoria, Lagunas, Monsefú, Nueva Arica, Oyotún, Pátapo, Picsi, Pimentel, Pomalca, Pucalá, Reque, Santa Rosa, Saña y Tumán) y reproyectando a EPSG:32717; el archivo resultante se releyó para confirmar capa, CRS y conteo._
