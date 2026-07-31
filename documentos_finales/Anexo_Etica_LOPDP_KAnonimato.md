# Anexo de Ética, Privacidad y Marco Legal

## Alcance del análisis

La unidad estadística es el evento de egreso hospitalario y no una persona identificable. La llave compuesta por capítulo CIE-10, provincia, sexo y rango etario representa un perfil epidemiológico sintético. No demuestra que dos eventos pertenezcan a una misma persona ni reconstruye una historia clínica real.

## Secreto estadístico y LOPDP

El proyecto emplea microdatos públicos anonimizados y aplica los principios de minimización, finalidad y reducción del riesgo de reidentificación. No utiliza nombres, números de identificación, direcciones, teléfonos ni datos de contacto. Los microdatos originales y los archivos Parquet no se incluyen en la entrega.

## Demostración del control de K-anonimato

La granularidad inicial no garantiza por sí sola K >= 50. El K mínimo original fue 1; se detectaron 8,997 grupos con menos de 50 registros, equivalentes a 170,246 eventos. Para la salida publicable se suprimen esos grupos. Después del control, el K mínimo de los grupos conservados es 50 y se mantiene el 96.8355 % de los registros.

## Limitaciones y responsabilidad

Los reingresos son aproximaciones sobre trayectorias sintéticas, no estadísticas oficiales de seguimiento individual. La coincidencia de variables no demuestra identidad. El proyecto se limita a evaluar rendimiento computacional y resultados agregados, respetando el secreto estadístico del INEC y la Ley Orgánica de Protección de Datos Personales del Ecuador.