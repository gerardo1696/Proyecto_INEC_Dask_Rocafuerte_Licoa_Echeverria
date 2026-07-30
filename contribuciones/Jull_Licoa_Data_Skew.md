# C# Contribución de Jull Licoa: mitigación de Data Skew

Se revisó el problema de desbalance producido por las provincias con mayor cantidad de registros.

## Estrategias comparadas

1. Distribución directa por provincia.
2. Distribución mediante salting determinístico.

La estrategia directa podía concentrar una provincia completa en una misma partición. Para disminuir este problema se utilizó una clave con salt calculado a partir de la llave sintética.

Este procedimiento permitió distribuir los registros de las provincias más grandes entre diferentes particiones, manteniendo juntos los eventos correspondientes a una misma llave sintética.

## Validación

La estrategia con salting redujo la razón de desbalance de las particiones y mantuvo los mismos resultados agregados obtenidos mediante la estrategia directa.
