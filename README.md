# Análisis de gestión de talento y rotación de personal
## 1. 📝 INTRODUCCIÓN
El presente informe analiza la situación actual de la fuerza laboral de la organización, con especial énfasis en la retención de talento, compensación, clima organizacional, satisfacción laboral y factores asociados a la rotación de personal. Este documento proporciona una hoja de ruta estratégica para optimizar la gestión del capital humano y mitigar los riesgos asociados a la fuga de conocimiento clave.
## 2. 🔍 DEFINICIÓN DEL PROBLEMA
La organización presenta una crisis de retención caracterizada por una tasa de rotación del 16.1%, lo que se traduce en la pérdida de 237 profesionales. Este fenómeno no es aislado, sino que responde a fallas estructurales en el liderazgo y la gestión de carrera. Los desafíos principales se desglosan a continuación:
-	**Impacto financiero de la rotación:** La pérdida de talento ha generado un costo económico estimado de $2,311,792.07, afectando directamente la rentabilidad de la empresa.
-	**Fuga de capital técnico:** Existe una salida masiva en roles técnicos críticos, destacando 62 bajas en Laboratory Technician y 47 en Research Scientist, lo que compromete la capacidad de innovación en el departamento de R&D.
-	**Inestabilidad en el área de ventas:** El rol de Sales Representative enfrenta un desafío con una rotación del 39.8% y un riesgo de fuga proyectado del 96.4%.
-	**Crisis de liderazgo y bienestar:** El 28.3% del personal trabaja bajo un esquema de horas extras constantes. Esta sobrecarga, sumada a una insatisfacción con el jefe del 44.6% en áreas clave, ha situado el Índice de Bienestar en 68.79, por debajo del umbral mínimo de sostenibilidad.
-	**Estancamiento y Desconexión de Nuevos Talentos:** El 80% de los nuevos empleados en Human Resources abandonan la empresa antes de los 2 años, evidenciando una falla crítica en el proceso de integración y en las expectativas de crecimiento frente a un promedio de 4.8 años de estancamiento en niveles de mando medio.

## 3. ❓ PREGUNTAS DE NEGOCIO
Para abordar estos desafíos, el análisis se estructura en torno a las siguientes preguntas estratégicas:

**3.1 Rotación y Retención**
-	¿Cuál es la tasa de rotación actual y cómo ha evolucionado?
-	¿Qué departamentos y roles presentan mayor rotación?
-	¿Cuáles son los factores predictivos de fuga de talento?

**3.2 Compensación y Equidad**
-	¿Existe brecha salarial por género?
-	¿La compensación está alineada con el mercado y roles?
-	¿Cómo impacta la compensación en la retención?

**3.3 Satisfacción y Bienestar**
-	¿Cuál es el nivel de satisfacción laboral general?
-	¿Cómo se relaciona la satisfacción con la rotación?
-	¿El balance vida-trabajo es adecuado?

**3.4 Desarrollo Profesional**
-	¿Qué porcentaje de empleados recibe capacitación?
-	¿Cuál es el tiempo promedio sin promoción?
-	¿Existen oportunidades de crecimiento claras?

## 4. 🛠️ TECNOLOGÍAS
El proyecto integra un stack tecnológico para la gestión, transformación y visualización de datos:
-	Microsoft Power BI Desktop: Herramienta principal para modelado de datos, análisis y visualización interactiva.
-	Power Query (M): Lenguaje para transformaciones ETL y preparación de datos.
-	DAX (Data Analysis Expressions): 58 medidas calculadas para los indicadores.

## 5. ⚙️ PROCESAMIENTO DE DATOS (ETL)
El proceso ETL (Extract, Transform, Load) implementado garantiza la calidad, consistencia e integridad de los datos.
**5.1 Extracción**
Los datos se obtienen de sistemas fuente de recursos humanos, incluyendo información transaccional de empleados, evaluaciones de desempeño, registros de compensación y eventos de entrada/salida.
**5.2 Transformación**
-	Eliminación de registros duplicados y valores nulos.
-	Normalización de campos categóricos (Gender, Attrition, OverTime).
-	Creación de la dimensión de la tabla calendario.
-	Creación de otras dimensiones.
-	Creación de campo "Grupo de edad" mediante segmentación.
**5.3 Carga**
Los datos transformados se cargan en el modelo semántico.

## 6. 🏗️ MODELADO DE DATOS
El modelo implementa una arquitectura de estrella (Star Schema), considerada la mejor práctica en Business Intelligence por su simplicidad, rendimiento y facilidad de mantenimiento.
**Tabla de Hechos: FactEmpleados**
-	Métricas cuantitativas: Ingresos, tasas, antigüedad, capacitaciones.
-	Atributos descriptivos: Género, estado civil, campo educativo.
-	Indicadores comportamentales: Horas extra, viajes, rotación.
-	Llaves foráneas: JobKey, DKey, KeyEnviro, YearsSinceLastPromotion.
**Tablas Dimensionales:**
1.	DimDepartamento
2.	DimJob
3.	DimCalendario
4.	Dim_WorkEnvironment
5.	Dim_promotion
**6.2 Relaciones del Modelo**
El modelo establece 5 relaciones 1:N activas con filtrado unidireccional.

## 7. 📊 INDICADORES CLAVE DE DESEMPEÑO

**7.1 KPIs de Fuerza laboral**
-	Total Empleados
-	Empleados Activos
-	Empleados Fugados
-	Edad Promedio
-	Experiencia Promedio

**7.2 KPIs de rotación y retención**
-	% Rotación de Empleados
-	Variación Rotación MoM
-	Rotación Empleados Nuevos (<2 años)
-	Costo Estimado de Rotación
-	Empleados en Riesgo (%)

**7.3 KPIs de compensación y equidad**
-	Salario Total
-	Salario Mediano
-	Salario Promedio
-	Brecha Salarial de Género

**7.4 KPIs de satisfacción y bienestar**
-	Índice de Bienestar Global
-	% Satisfacción con el Trabajo
-	% Satisfacción Work-Life Balance (WLB)
-	% Satisfacción con el Jefe
-	% Satisfacción con el Environment
-	Insatisfacción Global (%)

**7.5 KPIs de desarrollo y capacitación**
-	Total Capacitaciones
-	% Empleados Capacitados
-	Empleados No Capacitados
-	Tiempo Promedio sin Promoción
-	Tasa de Estancamiento Crítica
-	Promedio de Años en Rol

**7.6 KPIs de horas extra y carga laboral**
-	Empleados con Horas Extras
-	% Empleados sin Horas Extras

**7.7 KPIs demográficos**
-	Total Hombres
-	Total Mujeres
-	Distancia Promedio al Trabajo
-	Empresas previas promedio

## 8. 💡 BUSINESS INSIGHTS
1. **Estructura y distribución organizacional**
La compañía cuenta con una fuerza laboral de 1,470 empleados, con una marcada especialización técnica.
-	Concentración por Departamento: El 65.4% (961 empleados) pertenece a Research & Development, seguido por Sales con el 30.3% (446 empleados).
-	Pirámide de Experiencia: La organización tiene una base joven, con más del 70% del personal en niveles Entry (543) y Junior (534).
-	Especialización: Predominan los perfiles en Life Sciences (606) y Medical (464).
2. **Análisis de Rotación y fuga de talento**
La rotación no es uniforme, sino que se concentra en roles críticos para la operación y las ventas.
-	Roles con mayor volumen de salidas: Laboratory Technician (62), Sales Executive (57) y Research Scientist (47).
-	Índices de rotación críticos: El puesto de Sales Representative lidera la deserción porcentual con un 39.8%, seguido por Laboratory Technician con 23.9%.
-	Rotación de nuevos talentos: El 34.9% de los empleados con menos de 2 años de antigüedad abandona la empresa. Este fenómeno es extremo en Human Resources (80%) y Sales Representative (56.7%).
3. **Impacto Financiero de la Rotación**
La pérdida económica por la salida de personal es un factor crítico para la rentabilidad.
-	Costo total estimado: La rotación le cuesta a la empresa $2,311,792.07.
-	Por Puesto:
o	Sales Executive: Es el rol más costoso financieramente con $592,025.87 en pérdidas.
o	Laboratory Technician: Representa un impacto de $301,056.80.
-	Inversión en Capacitación: A pesar de haber realizado 4,115 capacitaciones (cubriendo al 96.3% del personal), la alta rotación indica que la empresa está perdiendo el retorno de inversión en formación.
4. **Factores de riesgo y clima laboral**
El 58.3% de los empleados se clasifica en situación de Riesgo Clave (debido a horas extra, nivel Entry o baja antigüedad).
-	Sobrecarga de Trabajo: El 28.3% del personal realiza horas extras. En Research Scientist, esta cifra sube al 33.2%.
-	Riesgo por Puesto: Sales Representative tiene un nivel de riesgo alarmante del 96.4%, seguido por Research Scientist con un 87.7%.
-	Índice de Bienestar: Se sitúa en 68.79/100, por debajo del umbral saludable de 70, lo que confirma una insatisfacción latente.
-	Liderazgo: Existe una fuerte insatisfacción con el jefe en Sales Representative (44.6%), lo cual correlaciona directamente con su alta rotación.
5. **Compensación y desarrollo de Carrera**
-	Equidad de Género: A nivel general, las mujeres ganan un 5% más que los hombres.
-	Brecha Salarial en Dirección: Se detectó una brecha crítica en el puesto de Research Director, donde los hombres ganan un mediano de $17,584 vs. $14,275 de las mujeres (diferencia de $3,309).
-	Estancamiento (Cuello de Botella): Los Managers promedian 4.8 años sin una promoción, lo que bloquea el crecimiento de los niveles Junior y Entry.

## 9. 🖼️ VISTA DEL DASHBOARD
<img width="2103" height="1200" alt="Resumen de RRHH" src="https://github.com/user-attachments/assets/7cf39ce1-26bd-49b0-84ef-27b4f3cf946e" />
<img width="2094" height="1194" alt="Resumen de RRHH (2)" src="https://github.com/user-attachments/assets/e11f7829-c420-499d-98d2-33c94639a16b" />

## 10. 📌 CONCLUSIONES
-	**Gestión deficiente en ventas:** La insatisfacción con el jefe en Sales Representative (44.6%) supera el promedio organizacional. Esto indica que la rotación en este departamento no se debe a la carga de trabajo, sino a una cultura de liderazgo ineficiente que genera un riesgo de fuga del 96.4%.
-	**Desconexión en Recursos Humanos:** Es crítico que el departamento encargado del talento tenga una insatisfacción global del 50% y una fuga de nuevos empleados del 80%.
-	**Fuga de capital técnico:** Con 62 salidas en Laboratory Technician y 47 en Research Scientist, la empresa está perdiendo su ventaja competitiva técnica.
-	**Inversión ineficiente en formación:** Aunque se han realizado 4,115 capacitaciones, la alta rotación de nuevos (34.9%) significa que la empresa está actuando como una incubadora gratuita para la competencia, financiando el desarrollo de habilidades que luego se ejecutan en otras compañías.
-	**Estancamiento estructural:** El hecho de que los Managers pasen 4.8 años sin promoción genera un efecto para el 70% del personal Junior/Entry. Si los líderes no se mueven, el talento joven percibe falta de futuro y opta por salir antes de cumplir los 2 años.

## 11. 🌱 RECOMENDACIONES
-	**Programa de retención en Sales executive:** Dado que este rol genera la mayor pérdida individual ($592,025.87), se recomienda un esquema de bonos por permanencia o revisión de comisiones para frenar el impacto financiero inmediato.
-	**Capacitación:** Implementar formación obligatoria en liderazgo para los jefes de ventas, enfocada en reducir el 44.6% de insatisfacción.
-	**Plan de onboarding express en HR:** Realizar entrevistas de salida profundas al 80% de los empleados de Recursos Humanos que se van prematuramente para rediseñar su proceso de bienvenida y soporte.
-	**Control de burnout en R&D:** Establecer límites al Overtime en Research Scientist (33.2%). Se recomienda la contratación de personal temporal o la automatización de procesos.

