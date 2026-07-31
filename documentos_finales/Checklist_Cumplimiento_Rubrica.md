# Checklist de cumplimiento de la rúbrica

## Línea base secuencial
- Pandas secuencial implementado.
- Tiempo medido: 87.630245 segundos.
- Memoria pico medida: 2354.38 MB.

## Pipeline paralelo
- Lectura perezosa Dask.
- Blocksize objetivo: 128 MiB.
- Map mediante map_partitions.
- Shuffle con salting.
- Reduce y una sola materialización analítica final.

## Escalabilidad
- Workers: 1, 2, 4 y 8.
- Speedup y eficiencia calculados.
- Amdahl calculado e interpretado con sus limitaciones.
- 4 y 8 workers documentados como pruebas de estrés.

## Validación
- Coincidencia Pandas-Dask: 100 %.
- Diferencias agregadas: 0.

## Memoria y Data Skew
- RAM y spill-to-disk monitoreados.
- Reportes HTML y grafo de tareas.
- Estrategia directa comparada con salting.

## Privacidad
- K mínimo original: 1.
- Grupos con K menor que 50: 8,997.
- Registros suprimidos: 170,246.
- Salida publicable con K mínimo igual a 50.
- Porcentaje conservado: 96.8355 %.

## Comunicación
- Carta no técnica en DOCX y PDF.
- Presentación y guion.
- Anexo ético de máximo una página.
- README para Colab y entorno local.

## Elementos externos
- Verificar commits, ramas y fusiones de los tres integrantes.
- Completar CATME individualmente.