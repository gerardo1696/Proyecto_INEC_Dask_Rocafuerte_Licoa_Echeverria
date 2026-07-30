# Proyecto_INEC_Dask_Rocafuerte_Licoa_Echeverria
## Descripción

Proyecto académico de Computación Paralela para procesar los registros nacionales de egresos hospitalarios del INEC correspondientes al periodo 2020-2024.

Se implementó una línea base secuencial con Pandas y una versión distribuida con Dask. El proyecto compara tiempo de ejecución, memoria, speedup, eficiencia, Data Skew y equivalencia de resultados.

## Integrantes

- Gerardo Rocafuerte
- Jull Licoa
- Marcos Echeverría

## Distribución del trabajo

- **Gerardo Rocafuerte:** descarga de datos, homologación de variables, preprocesamiento, conversión a Parquet y pipeline secuencial con Pandas.
- **Jull Licoa:** pipeline distribuido con Dask, configuración de workers, medición de memoria, análisis de escalabilidad y mitigación de Data Skew.
- **Marcos Echeverría:** validación Pandas-Dask, evaluación de K-anonimato, revisión ética, privacidad y documentación.

## Datos procesados

- Periodo: 2020-2024.
- Registros válidos: 5.379.828.
- Cobertura: todas las provincias del Ecuador, incluida Galápagos.
- Fuente: registros públicos de egresos hospitalarios del INEC.

Los microdatos originales y los archivos Parquet no se incluyen en este repositorio.

## Metodología

1. Descarga y extracción de los archivos oficiales.
2. Homologación de variables entre años.
3. Limpieza y conversión a Parquet.
4. Procesamiento secuencial con Pandas.
5. Procesamiento distribuido con Dask.
6. Comparación de Data Skew mediante distribución directa y salting.
7. Validación de resultados Pandas-Dask.
8. Evaluación de K-anonimato con umbral K ≥ 50.
9. Cálculo de tiempo, memoria, speedup, eficiencia y Ley de Amdahl.

## Resultados principales

- Coincidencia Pandas-Dask: 100 %.
- Diferencias en indicadores agregados: 0.
- Mejor configuración Dask en el entorno utilizado: 1 worker.
- Pandas presentó un menor tiempo debido al overhead de Dask y a la disponibilidad limitada de CPU.
- La estrategia de salting redujo el desbalance de carga.

## Archivos principales

- Notebook ejecutado en formato `.ipynb`.
- `requirements.txt`.
- Carta dirigida al INEC.
- Presentación final.
- Resultados agregados en CSV.
- Gráficas de rendimiento.
- Anexo ético y evaluación de K-anonimato.

## Ejecución

1. Abrir el notebook en Google Colab.
2. Seleccionar entorno CPU.
3. Montar Google Drive.
4. Ejecutar las celdas en orden.
5. Revisar los resultados generados en la carpeta `resultados`.

## Privacidad

La llave utilizada representa un perfil epidemiológico sintético y no identifica personas. No se utilizaron nombres, números de identificación, direcciones ni datos de contacto. Los microdatos originales no se incluyen en la entrega.
