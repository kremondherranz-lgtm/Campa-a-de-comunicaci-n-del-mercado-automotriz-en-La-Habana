# Datos

Datos del estudio del mercado automotriz en La Habana, separados por etapa del flujo.

```
data/raw/*        →  fuentes sin procesar
data/processed/*  →  resultados listos para análisis
data/journals/*   →  trazabilidad de fuentes y procesamiento
```

Los scripts que generan los resultados (`src/transform.py` y `src/clean_survey.py`) no forman parte de este paquete: están en el repositorio del proyecto.

## raw/

Un archivo por fuente, sin procesar.

**Oferta formal (concesionarios y comercializadoras):**

- `dongfeng_nwi_commercial.csv` — catálogo de Dongfeng Cuba (22 filas).
- `mcv_commercial_2026-03-03.csv` — catálogo de MCV Comercial, marzo 2026 (43 filas).
- `womy_catalog_july_2026.csv` — catálogo de Womy, julio 2026 (17 filas).
- `bdcone_commercial.csv` — catálogo de BDC One (13 filas).
- `bdcone_commercial_tipo_de_propulsion.csv` — variante de BDC One con tipo de propulsión (13 filas).
- `oferta_4_concecionarias.xlsx` — oferta consolidada de las cuatro concesionarias.

**Oferta informal:**

- `revolico_cars.csv` — 100 anuncios de Revolico, con columna `marca` añadida manualmente.
- `oferta_de_revolico.csv` — copia idéntica de la misma muestra de Revolico.

**Demanda (encuesta):**

- `ESTUDIO DEL MERCADO AUTOMOTRIZ EN LA HABANA (respuestas) - Respuestas de formulario 1 (*).csv` — siete exportaciones sucesivas del formulario de Google: `(1)`, `(2)`, `(3)`, `(4)`, `(6)`, `(7)` y `(9)`, con 11 a 33 respuestas. La más reciente es la `(9)`, con 33 respuestas y 46 columnas; las anteriores tienen 47 columnas porque incluyen el bloque de puertas.
- `prefrencias_propulsión_encuesta.xlsx` — preferencias de propulsión de los encuestados.

**Fuentes complementarias:**

- `arrendadores_vivienda_plaza.xlsx` — arrendadores de vivienda en La Habana.
- `Registro de vehículos_eléctricos.xlsx` — registro de vehículos eléctricos.
- `Registro de autos_eléctricos_adquiridos por particulares.xlsx` — adquisiciones de eléctricos por particulares.
- `Registro de autos_eléctricos_adquiridos por entidades estatales.xlsx` — adquisiciones de eléctricos por entidades estatales.
- `embudos_vehiculos.xlsx` — datos de embudos (funnels) de vehículos.
- `Mcv_tipo de carros.xlsx`, `Gongfeng_tipo de carros.xlsx`, `womy_tipo de carros.xlsx`, `BDCone_tipo de carros.xlsx` — desglose por tipo de vehículo de cada comercializadora.

## processed/

Resultados listos para análisis.

- `survey.csv` — encuesta con columnas renombradas a inglés: 11 filas y 47 columnas. Corresponde a la exportación `(1)`; está pendiente regenerarla desde la `(9)`.
- `INFORME_4_11_2026_con_interpretaciones.docx` — informe con interpretaciones de los resultados.
- `tablas_gráficas/` — tablas y gráficas del análisis exploratorio de la encuesta (`graficas_preliminares.xlsx`, `graficas_analisis_combinando varias preguntas.xlsx` y `graficas_analisis_inicial_caracterizacion_encuestados.xlsx`).

`unified_cars.csv` no está incluido en este paquete; se regenera ejecutando `src/transform.py` en el repositorio del proyecto.

## journals/

Notas de trabajo sobre las fuentes y el procesamiento:

- `2026-11-05.md` — inventario de fuentes, duplicados detectados y estado de los resultados procesados.
- `2026-11-08.md` — revisión del paquete de campaña, nueva infografía, artículo actualizado y conciliación del inventario.
- `2026-11-09.md` — revisión de la infografía: nueva versión exportada de Canva y decisión de conservar ambas.

## Reglas

- No editar manualmente los archivos de `raw/` salvo la columna `marca` de `revolico_cars.csv`, que se completa a mano.
- Los precios se conservan en su moneda original; `price_usd` se calcula en `src/transform.py`.
- Los archivos `~$...` son temporales de Office y no forman parte de los datos.
