# Contribución de Jull Licoa: pipeline Dask

Se revisó la implementación distribuida del proyecto mediante Dask.

## Actividades realizadas

- Revisión de la lectura perezosa de los archivos Parquet.
- Configuración de LocalCluster y Client.
- Ejecución de pruebas con 1, 2, 4 y 8 workers.
- Medición del tiempo de procesamiento.
- Medición de la memoria utilizada por los workers.
- Revisión de las fases de carga, redistribución y reducción.
- Análisis del overhead producido por la creación de procesos, la comunicación y el shuffle.

## Resultado

Las pruebas demostraron que incrementar la cantidad de workers no garantiza una reducción del tiempo cuando el equipo dispone de pocos núcleos físicos. 
En Google Colab, Pandas presentó un menor tiempo, mientras que Dask permitió evaluar la distribución del procesamiento y el consumo de recursos.
