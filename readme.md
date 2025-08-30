# 📊 Cybersecurity Attack Dataset

## 📌 Descripción del propósito del dataset  
El **Cybersecurity Attack Dataset** ha sido creado con el objetivo de proporcionar una visión integral y estructurada del panorama actual de la ciberseguridad. Su propósito principal es servir como una herramienta de referencia tanto para principiantes que buscan introducirse en el mundo de la seguridad digital, como para profesionales e investigadores que requieren un recurso sólido para el análisis, la enseñanza y la planificación estratégica.  

Este dataset reúne más de **14,000 registros distribuidos en 15 columnas**, donde se documentan ataques, vulnerabilidades y escenarios de investigación en **26 dominios de la ciberseguridad**, que van desde las amenazas más comunes en aplicaciones web hasta riesgos emergentes en áreas como **inteligencia artificial, blockchain, satélites y computación cuántica**.  

Más allá de almacenar información, busca convertirse en un **puente entre el conocimiento técnico y la aplicación práctica**, fomentando la educación, el desarrollo de defensas más efectivas y la anticipación a amenazas futuras en un entorno tecnológico en constante evolución.  

---

## 📌 Explicación de los pasos de limpieza y transformación  

Con el fin de garantizar la calidad y confiabilidad del análisis, se realizaron procesos de limpieza y normalización iniciales sobre el dataset. Entre las principales acciones destacan:  

1. **Validación de esquema y carga segura**  
   - Se confirmó la presencia de las 16 columnas originales y se validaron los tipos de datos.  
   - `ID` se trató como numérico entero y el resto como texto para mantener homogeneidad.  

2. **Eliminación de columna con alta ausencia de datos**  
   - Se eliminó la **columna 15**, que solo contenía 46 valores no nulos.  
   - Mantenerla hubiera distorsionado las estadísticas globales al introducir ruido y sesgos.  

3. **Normalización de nombres y formatos**  
   - Conversión de títulos de columnas a `snake_case`.  
   - Estandarización de mayúsculas/minúsculas y limpieza de caracteres no deseados en campos categóricos y de texto.  

4. **Tratamiento de valores faltantes**  
   - Se conservaron `NaN` en columnas descriptivas para evitar supuestos no justificados.  
   - En campos categóricos críticos se imputó el valor **“Unknown”** para mantener consistencia en los análisis.  

5. **Depuración de duplicados**  
   - Se eliminaron registros repetidos empleando como llave compuesta (`title`, `attack_type`, `target_type`).  
   - Se retuvo la versión más completa y documentada de cada escenario.  

6. **Creación de vectores para `detection_method`**  
   - El campo fue tokenizado y transformado en vectores multietiqueta.  
   - Esto facilita correlaciones entre métodos de detección y tipos de ataque, y habilita usos posteriores en modelos de machine learning.  

7. **Procesamiento de listas y texto**  
   - En **`tags`** se unificaron separadores y se eliminaron duplicados.  
   - En **`tools_used`** y **`attack_steps`** se aplicó tokenización para análisis de frecuencia y métricas.  
   - Se generó la variable `n_attack_steps` (número de pasos por registro).  

8. **Controles de calidad post–limpieza**  
   - Validación de integridad de `ID` como clave única.  
   - Revisión de distribución balanceada por `category`.  
   - Comprobación de consistencia general del dataset final.  

> Resultado: un dataset **estructurado, confiable y analíticamente sólido**, listo para extraer patrones, evaluar impacto y explorar tendencias en detección y mitigación.  

---

## 📌 Principales hallazgos del análisis  
*(Se completará una vez finalizado el análisis práctico de los datos.)*  

---

## 📌 Insights y conclusiones relevantes  

El **Cybersecurity Attack Dataset** ofrece un panorama amplio que permite extraer conclusiones estratégicas y educativas sobre la evolución de las amenazas digitales. Entre los principales insights que se anticipan destacan:  

- **Diversidad de amenazas en múltiples dominios**  
  Desde ataques comunes en aplicaciones web hasta riesgos emergentes en áreas como IA, blockchain, satélites y computación cuántica.  

- **Relación entre vulnerabilidades y técnicas de ataque**  
  El cruce entre debilidades y técnicas documentadas facilita identificar patrones recurrentes en vectores de ataque.  

- **Importancia de la detección temprana**  
  La vectorización de `detection_method` permitirá descubrir qué técnicas resultan más eficaces contra distintos tipos de ataque.  

- **Aplicabilidad en entornos corporativos**  
  El dataset puede apoyar programas de capacitación, ejercicios de simulación, desarrollo de defensas y priorización de riesgos.  

- **Puente entre teoría y práctica**  
  Su enfoque estructurado lo convierte en un recurso accesible y de alto valor tanto para estudiantes como para profesionales y responsables de seguridad.  
