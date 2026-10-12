Este directorio contiene el archivo fuente `.qmd` del tutorial y su versión HTML autocontenida. Los datos utilizados no se almacenan en el repositorio: se generan localmente al ejecutar el documento.

## Reproducibilidad de los datos

Este tutorial utiliza datos sintéticos generados en R para simular los registros de envíos de una empresa ficticia durante 2025.

Los datos se generan directamente desde el archivo `.qmd`, por lo que no es necesario descargar archivos de datos adicionales.

## Requisitos

Para reproducir el tutorial se necesita:

- R.
- Quarto.
- Los paquetes de R utilizados en el documento: `duckdb`, `DBI`, `dplyr`, `readr`, `lubridate` y `ggplot2`.

Los paquetes pueden instalarse desde R con:

```r
install.packages(c("duckdb", "DBI", "dplyr", "readr", "lubridate", "ggplot2"))
```

## Datos generados

Durante la ejecución se generan:

- **5.858.848 registros** sintéticos.
- **12 archivos CSV**, uno por cada mes de 2025.
- Aproximadamente **426 MB** de archivos CSV en esta ejecución.
- Posteriormente, los mismos datos se almacenan en **12 archivos Parquet**, que ocuparon aproximadamente **61 MB** en esta ejecución.

Los archivos generados no se incluyen en el repositorio.

El volumen de datos fue elegido deliberadamente para representar un escenario en el que trabajar con múltiples archivos y millones de registros resulte relevante, manteniendo un tamaño razonable para ejecutar el tutorial en un computador personal.

## Importante al reproducir el tutorial

Al ejecutar el archivo `.qmd`, se crearán localmente las carpetas:

- `datos_csv/`
- `datos_parquet/`

Por este motivo, se recomienda disponer de espacio suficiente en disco antes de ejecutar el tutorial completo. El tiempo de ejecución dependerá de las características del computador.

El tutorial incluye, con fines comparativos, un ejemplo que muestra cómo realizar el conteo de los registros utilizando `readr` y `dplyr`. Este procedimiento requiere reunir los 5.858.848 registros en un `data.frame` de R, por lo que el bloque se muestra en el documento pero no se ejecuta automáticamente durante el renderizado (`eval: false`).

Los demás análisis y comparaciones utilizados en el tutorial se ejecutan desde el archivo `.qmd`.

Las carpetas de datos pueden eliminarse después de finalizar, ya que sus archivos pueden volver a generarse ejecutando nuevamente el código del tutorial.