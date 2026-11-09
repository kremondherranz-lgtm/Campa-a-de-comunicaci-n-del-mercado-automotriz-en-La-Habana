# Campaña: mercado automotriz en La Habana

Paquete de datos y piezas de comunicación del estudio sobre el mercado automotriz y la demanda de vehículos eléctricos en La Habana (2026).

## Estructura

```
data/           # fuentes crudas, resultados procesados y diarios de datos
  raw/          # un archivo por fuente, sin procesar
  processed/    # encuesta limpia, informe y tablas/gráficas
  journals/     # trazabilidad de fuentes y procesamiento
Storytelling/   # guion y artículo de divulgación
infografía/     # piezas gráficas para redes
```

Cada carpeta tiene su propio `README.md` con el detalle de sus archivos.

## Contenido principal

- **Demanda:** siete exportaciones del formulario de Google (de 11 a 33 respuestas); la más reciente es la `(9)`, con 33 respuestas.
- **Oferta formal:** catálogos de MCV Comercial, Womy, Dongfeng Cuba y BDC One, más la oferta consolidada de las cuatro concesionarias.
- **Oferta informal:** 100 anuncios de Revolico.
- **Registros complementarios:** vehículos eléctricos y adquisiciones por particulares y entidades estatales.
- **Resultados:** `data/processed/INFORME_4_11_2026_con_interpretaciones.docx` y los libros de `data/processed/tablas_gráficas/`.
- **Comunicación:** `Storytelling/` (guion y artículo) e `infografía/` (infografía en dos versiones; la vigente es la del 2026-11-09).

## Estado de los datos

- `data/processed/survey.csv` corresponde a la exportación `(1)` del formulario (11 respuestas), no a la última `(9)`.
- `data/processed/unified_cars.csv` no forma parte de este paquete.
- Los scripts de procesamiento (`src/transform.py`, `src/clean_survey.py`) están en el repositorio del proyecto, fuera de esta carpeta.

Última revisión de la documentación: 2026-11-09. Ver `data/journals/2026-11-09.md`.
