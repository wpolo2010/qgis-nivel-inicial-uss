# USS · SAF QGIS – Nivel Inicial — Guía del tercer fin de semana (Semana 3)
**Docente:** Arq. William Polo · Resolución Rectoral N.° 241-2026/USS
**Tema oficial de la semana:** Geoprocesamiento y análisis espacial aplicado a proyectos urbanos

| Sesión | Fecha | Hora Perú (PET) | Tu hora en California | Contenidos oficiales |
|---|---|---|---|---|
| Clase 5 | Sáb 31 oct 2026 | 18:00–21:20 | **16:00–19:20 PDT** | Consultas espaciales y selección por ubicación · Buffers y áreas de influencia · Análisis de proximidad y localización de equipamientos |
| Clase 6 | Dom 1 nov 2026 | 18:00–21:20 | **15:00–18:20 PST** ⚠️ | Herramientas Clip e Intersect · Union y Difference · Análisis de accesibilidad y diagnóstico urbano integrado |

Guiones listos: `clase-5-guion-y-practica.md` y `clase-6-guion-y-practica.md` (mismo formato de las Clases 1–4: 4 bloques de 50 min, práctica con entregable verificable).

## ⚠️ Lo único verdaderamente nuevo de este fin de semana: el reloj cambia ENTRE las dos clases

- La Clase 5 (sáb 31 oct) es todavía con desfase de 2 h: **16:00 PDT** en California.
- En la madrugada del **dom 1 nov** EE. UU. sale del horario de verano: la Clase 6, a la misma hora de Perú (18:00 PET), empieza en California a las **15:00 PST**.
- Es el único fin de semana del curso cuyas dos sesiones empiezan a **horas distintas** para William. De la Clase 6 en adelante todo queda fijo en 15:00–18:20 PST.
- Los recordatorios por clase ya existen (`uss-qgis-rec-clase05` el 31 oct y `uss-qgis-rec-clase06` el 1 nov, ambos 17:00 PET = 1 h antes); el de la Clase 6 cae a las **14:00 PST**, coherente con el nuevo horario.
- El aviso a los alumnos se da dos veces antes: al cierre de la Clase 4 (dom 25 oct, ya está en su guion) y al cierre de la Clase 5. Para los alumnos en Perú no cambia nada.

## Lo que hace que este fin de semana funcione (preparado el sáb 17 oct, antes incluso de la Clase 1)

1. **Continuidad real:** la Semana 3 no introduce datos nuevos — opera sobre el proyecto integrador de la Semana 2 (`equipamientos_pt`, `vias_ln`, `area_estudio_pg` con áreas y longitudes ya calculadas). La Clase 5 pregunta (selección por ubicación, buffers, cercanía) y la Clase 6 combina (clip/intersect/union/difference) hasta el diagnóstico de cobertura con % calculado.
2. **El entregable de la Clase 6 es el primer diagnóstico completo del curso:** cobertura total vs. territorio sin cobertura de cada sector, con la frase de diagnóstico de cada alumno. Es el insumo que la Semana 5 (análisis multicriterio, Clases 9–10) va a reutilizar — por eso ambos guiones insisten en guardar cada resultado al GeoPackage con nombre propio.
3. **Honestidad metodológica enseñada en voz alta:** los radios de buffer (educación 500 m, salud 800 m, comercio 500 m, culto/gestión 300 m) están marcados en el guion de la Clase 5 como **criterios didácticos de clase, no valores normativos**, y las distancias como **euclidianas, no por red vial**. Que los alumnos lo declaren en su entregable.
4. **Cruce del sábado — ya resuelto, no se reabre:** igual que los sábados anteriores, los alumnos USAT quedan en práctica 17:00–19:00 PET y William abre la USS en vivo a las 18:00 PET (decisión de William del 17 oct). El sáb 31 oct no mueve nada de ese esquema.

## Checklist de la víspera (vie 30 oct)
- [ ] Confirmar que los entregables de la Semana 2 llegaron (proyecto integrador con `area_ha`/`long_m`); a quien falte, enviarle el respaldo de Chiclayo + la versión mínima de capas de la Clase 5 antes del sábado.
- [ ] Abrir el proyecto propio en EPSG:32717 y probar una vez el flujo completo buffer → unión → diferencia, para dictarlo sin tropiezos.
- [ ] Guiones de Clases 5 y 6 a la mano; recordar que el domingo la clase empieza **una hora antes en California (15:00 PST)**.
