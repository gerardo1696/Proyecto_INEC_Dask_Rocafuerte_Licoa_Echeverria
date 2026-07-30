# Contribución de Marcos Echeverría: validación Pandas-Dask

Se revisó la equivalencia funcional entre la implementación secuencial con Pandas y la implementación distribuida con Dask.

## Indicadores comparados

- Cantidad de egresos.
- Reingresos críticos entre 0 y 30 días.
- Cantidad de grupos sintéticos.
- Tasa de reingreso por provincia y año.

## Resultado

La comparación se realizó utilizando las mismas claves de provincia y año. Los resultados de Pandas y Dask presentaron diferencias iguales a cero en todos los indicadores evaluados.

La validación confirmó una coincidencia del 100 % entre ambos pipelines.
