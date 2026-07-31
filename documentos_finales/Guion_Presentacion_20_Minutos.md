# Guion de presentación - 20 minutos

1. Portada e integrantes - 1 min
2. Problema, fuente y secreto estadístico - 1.5 min
3. Volumen: 5,379,828 registros - 1 min
4. Homologación 2020-2024 - 1.5 min
5. Llave sintética y límites éticos - 1.5 min
6. Pipeline Pandas - 1.5 min
7. Pipeline Dask, blocksize y evaluación perezosa - 2 min
8. Data Skew: directa frente a salting - 2 min
9. Validación Pandas-Dask, diferencias cero - 1.5 min
10. Tiempo, memoria y spill-to-disk - 2 min
11. Speedup menor que uno: overhead y límites de Amdahl - 2 min
12. Pruebas de estrés con 4 y 8 workers - 1 min
13. K-anonimato antes y después - 1.5 min
14. Conclusiones y recomendaciones al INEC - 1 min

Mejor Dask: 2 workers, 89.54 s.
Speedup: 0.979.
Eficiencia: 0.489.
Spill-to-disk: 0.00 MB.

Mensaje principal:
Dask no aceleró el equipo local de dos CPU lógicas porque el overhead dominó la prueba. Las configuraciones de 4 y 8 workers son pruebas de estrés. La utilidad institucional aparece ante volúmenes mayores, presión de memoria o infraestructura con más recursos.