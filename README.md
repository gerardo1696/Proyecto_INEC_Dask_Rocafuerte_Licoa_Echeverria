# Proyecto Integrador INEC - Pandas y Dask

## Integrantes

- Gerardo Rocafuerte
- Jull Licoa
- Marcos Echeverría

## Descripción

Pipeline reproducible para procesar los registros nacionales de egresos hospitalarios del INEC de 2020 a 2024. Compara una versión secuencial desarrollada con Pandas y una versión distribuida desarrollada con Dask.

## Entorno ejecutado

- Python: 3.12.13
- Pandas: 2.2.2
- PyArrow: 18.1.0
- Dask: 2026.7.0
- Entorno experimental: Google Colab con CPU

## Reproducción en Google Colab

1. Subir el notebook a Google Colab.
2. Seleccionar un entorno CPU.
3. Ejecutar las celdas en orden.
4. Autorizar el montaje de Google Drive.
5. El notebook descarga y prepara los datos cuando no existen los Parquet.
6. Ejecuta Pandas y Dask con 1, 2, 4 y 8 workers.
7. Valida que ambas versiones produzcan resultados idénticos.
8. Genera métricas, gráficas, reportes HTML, carta, anexo, presentación y ZIP.

## Reproducción en un entorno local

Requisitos:

- Python 3.8 o superior.
- Memoria suficiente para procesar los Parquet.
- Graphviz instalado para exportar el grafo de tareas.
- Acceso a los microdatos públicos del INEC.

Procedimiento:

1. Clonar o descargar el repositorio.
2. Crear un entorno virtual con `python -m venv .venv`.
3. Activarlo en Windows con `.venv\Scripts\activate`.
4. En Linux o macOS usar `source .venv/bin/activate`.
5. Instalar dependencias con `pip install -r requirements.txt`.
6. Definir la carpeta mediante `PROYECTO_INEC_DIR` o permitir que el notebook cree `Proyecto_INEC_Paralela` en el directorio actual.
7. Abrir con `jupyter notebook` y ejecutar las celdas en orden.
8. Revisar `resultados`, `figuras`, `reportes_dask` y `documentos_finales`.

## Reanudación

Cuando existen Parquet para los cinco años, el notebook omite la consulta y descarga web. Las métricas Pandas y Dask se recalculan con el código actual.

## Diseño paralelo

- Lectura perezosa con `blocksize="128MiB"` y `split_row_groups="adaptive"`.
- Fase Map mediante `map_partitions`.
- Shuffle directo y mitigación de Data Skew mediante salting.
- Una sola materialización analítica mediante `dask.compute`.
- Configuraciones de 1, 2, 4 y 8 workers.
- Medición de tiempo, RAM, spill-to-disk, speedup, eficiencia y Amdahl.
- Validación Pandas-Dask con diferencias iguales a cero.

## Interpretación del rendimiento

Las configuraciones de 4 y 8 workers son pruebas de estrés en un entorno con dos CPU lógicas. No representan configuraciones recomendadas. Un `speedup` inferior a uno indica que el overhead superó el trabajo útil en la prueba local. Dask conserva valor para procesamiento por particiones, control de memoria y escenarios con mayor volumen o infraestructura.

## Privacidad

La llave inicial no garantiza por sí sola K mayor o igual que 50. La salida publicable suprime los grupos con menos de 50 registros y documenta los grupos y eventos excluidos. Los microdatos, SAV, Parquet y temporales Dask no se incluyen en el ZIP.

## Resultado de la ejecución

- Registros procesados: 5,379,828
- Pandas: 87.630245 segundos
- Mejor Dask: 2 workers, 89.540606 segundos
- Speedup: 0.978665
- Eficiencia: 0.489332
- Spill-to-disk máximo: 0.00 MB
- Validación: diferencias iguales a cero

## Evidencia colaborativa

La carpeta `Evidencia_GitHub` debe contener evidencia real de commits de los tres integrantes, ramas de trabajo, Pull Requests o fusiones, colaboradores e historial trazable. CATME se completa individualmente en la plataforma.

## Referencias técnicas

- Dask Best Practices: https://docs.dask.org/en/stable/best-practices.html
- Dask DataFrame Best Practices: https://docs.dask.org/en/stable/dataframe-best-practices.html
- Pandas Documentation: https://pandas.pydata.org/docs/
- Repositorio: https://github.com/gerardo1696/Proyecto_INEC_Dask_Rocafuerte_Licoa_Echeverria
