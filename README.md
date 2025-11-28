# **Portafolio de proyectos — Jaime Mora**

Este repositorio funciona como portafolio de mis proyectos de **análisis de datos, BI, automatización y RPA**.  
Por razones de confidencialidad no publico código ni datos reales, pero sí incluyo:

- Resumen del problema y la solución.
- Impacto estimado en tiempo y eficiencia.
- Enlaces a **videos demo** donde se ve la herramienta funcionando.

---

## 📊 Tableros Power BI

### 1. QuirónPrevención – Tableros de Gestión para Áreas Administrativa, Técnica y Talento Humano

**Resumen:**  
Conjunto de dashboards corporativos que integran información de:

- Nómina, horas trabajadas y productividad.
- Procesos de selección y rotación de personal.
- Indicadores técnicos y administrativos.

**Impacto:**

- Reducción significativa del tiempo dedicado a preparar reportes manuales.
- Mejor visibilidad de indicadores para directivos y jefes de área.

**Video demo:**

- [Visión general de los dashboards de QuirónPrevención](https://drive.google.com/file/d/15lLUfrAekaDmqTx58OkvGxQuGqi6KNdj/view?usp=sharing)
---

### 2. QuirónPrevención – Tableros de Gestión Dedicada al Área Técnica

**Resumen:**  
Dashboard corporativo que integran información de:

- Planeadores, control de horas y productividad.
- Rotación de personal, movimiento histórico. 
- Detalles técnicos por profesional para seguimiento.

**Impacto:**

- Reducción significativa del tiempo dedicado a preparar reportes manuales.
- Mejor visibilidad de indicadores para directivos y jefes de área.
- Consolidación de información para auditorías y almacenamiento de datos. 

**Video demo:**

- [Visión general del dashboard Área Técnica](https://drive.google.com/file/d/1Vd1U6lsfOEw3ZHSsP44NDTE1FWUky--W/view)

---

### 3. OXXO – Tablero de Ventas, Maduración e Impacto Comercial (prueba técnica)

**Resumen:**  
Tablero en Power BI desarrollado como parte de una **prueba técnica**, enfocado en analizar el
comportamiento de ventas y la maduración comercial, incluyendo:

- Evolución de ventas por tienda, región y periodo.
- Curvas de maduración de ventas (cómo evolucionan las tiendas / puntos de venta desde su apertura).
- Comparación de desempeño entre tiendas consolidadas vs. tiendas nuevas.
- Proyecciones de ventas basadas en tendencias históricas y patrones de crecimiento.

**Impacto (sobre el caso de estudio):**

- Mejor entendimiento del ciclo de maduración de las tiendas y su impacto en el resultado global.
- Soporte para decisiones sobre inversión, apertura/cierre de puntos de venta y enfoque comercial.
- Identificación de tiendas con alto potencial vs. bajo desempeño para acciones específicas.

**Video demo:**

- [Dashboard de ventas y maduración para OXXO (prueba técnica)](https://drive.google.com/file/d/1RBMm0XMN3ZDVf-98sfVlRiy-7eroCQuY/view?usp=sharing)
- [Presentación elaborada(prueba técnica)](https://drive.google.com/file/d/1RPHbthuPU5QejhE-wDRenesafDQ3l2WX/view?usp=sharing)

---

### 4. La Ascensión – Tablero de Contratos, Beneficiarios y Valor Mensual (prueba técnica)

**Resumen:**  
Tablero en Power BI desarrollado como **prueba técnica** para La Ascensión, enfocado en analizar
el portafolio de contratos de protección exequial. El modelo permite:

- Filtrar por año, mes, sucursal, plan, cobertura y estado del contrato.
- Ver el total de **contratos** y **beneficiarios** activos en el periodo.
- Analizar contratos por sucursal, planes y coberturas.
- Revisar el **valor mensual de los contratos por sucursal** y la distribución de beneficiarios por plan.

**Impacto (sobre el caso de estudio):**

- Mayor visibilidad del desempeño comercial por sucursal y tipo de plan.
- Identificación de sucursales con mayor valor mensual y concentración de contratos.
- Apoyo a decisiones sobre qué planes y coberturas impulsar en cada ciudad o canal.

**Video demo:**

- [Dashboard de contratos y beneficiarios – La Ascensión (prueba técnica)](https://drive.google.com/file/d/1DqQI-7E752Z_uMM9MpS-M1Lp5DAuLxwL/view?usp=sharing)

---

### 5. Monitor de robots RPA – Flujos de escritorio en Power Automate

**Resumen:**  
Panel de analítica nativo de Power Automate que utilizo como **tablero de monitoreo** para todos mis
robots de escritorio (Power Automate Desktop).  
Desde este panel puedo:

- Filtrar por rango de fechas, flujo de escritorio, máquina y grupo de máquinas.
- Ver el número total de ejecuciones completadas en el periodo.
- Analizar la **tasa de error** y el comportamiento diario de las ejecuciones.
- Revisar el estado de los flujos (correcta, con errores, cancelada) y su tendencia en el tiempo.

> Nota: El diseño visual del tablero es nativo de la plataforma; mi aporte está en la
> **orquestación y estandarización de los bots**, la configuración del monitoreo y el uso del panel
> para gestionar capacidad, errores y mejoras.

**Impacto:**

- Visibilidad centralizada del desempeño de todos los robots RPA.
- Detección temprana de bots con alta tasa de error para priorizar correcciones.
- Mejores decisiones sobre horarios de ejecución y distribución de carga entre máquinas.

**Video demo:**

- [Monitor de robots RPA en Power Automate Desktop](https://drive.google.com/file/d/18q8QdZdbC8nyDKtYJzTDKL613zvUXsGW/view?usp=sharing)

---

## ⚙️ Automatizaciones (Power Automate / n8n / Flujos ETL)

### 6. MotoGlanz – Bot de registro de lavados con IA (n8n + Telegram + OpenAI)

**Resumen:**  
Flujo en **n8n** que orquesta un bot de Telegram para registrar lavados de MotoGlanz usando IA:

- Recibe el mensaje desde Telegram (texto y opcionalmente foto de la moto).
- Extrae el texto del chat y valida si el mensaje trae foto (`has_photo?`).
- Si hay foto:
  - Descarga el archivo desde Telegram (`Get a file`),
  - lo sube a Google Drive (`Upload_photo`) y
  - genera la URL pública (`URL_file` / `URL_file_empty` + `Join_photo_nophoto`).
- Construye el cuerpo para la IA (`Build OpenAI Body`) y lo envía a un **AI Agent**:
  - Modelo de chat de OpenAI,
  - memoria en Postgres,
  - parser estructurado para devolver un JSON con campos como placa, tipo de lavado, fecha, valor, etc.
- El resultado se parsea (`Parse IA`), se aplican reglas (`byModo`, `val_obligatorios`) y se valida si la información está completa (`Complete_info?`).
  - Si está completa → se inserta el registro definitivo de lavado (`Insert_lavado`) y se responde al cliente con confirmación (`Answer_Complete`).
  - Si falta información → se guarda como borrador (`Insert_borrador`) y el bot responde pidiendo los datos faltantes (`Answer_Faltantes`).

**Impacto:**

- Transforma un chat informal en **registros estructurados** listos para usar en dashboards y reportes.
- Reduce el tiempo de digitación manual y los errores al registrar lavados.
- Permite que el cliente solo “hable con el bot” (y mande una foto) mientras la IA se encarga de interpretar y estructurar la información.

**Video demo:**

- [Bot de registro de lavados – n8n + Telegram + IA]()


---

### 5. ETL Automatizado para Dashboards Corporativos

**Resumen:**  

- Flujos que toman datos desde SharePoint, archivos de Excel y otras fuentes.
- Limpieza y transformación automática para modelos de Power BI.
- Notificaciones en caso de errores en la actualización.

**Impacto:**

- Proceso de actualización de dashboards prácticamente desatendido.
- Predisposición de la información lista cada día para la toma de decisiones.

**Video demo:**

- [Flujos ETL para actualización de dashboards](ENLACE_PENDIENTE)

---

### 6. Automatización de Reportes de Capacitación

**Resumen:**  

- Consolidación automática de asistencias, resultados y estados de capacitación.
- Generación de archivos listos para análisis en Power BI o Excel.
- Registro de agendamientos y cumplimientos para seguimiento histórico.

**Impacto:**

- Reducción del trabajo manual de consolidar múltiples archivos.
- Mayor trazabilidad de la formación impartida.

**Video demo:**

- [Automatización de reportes de capacitación](ENLACE_PENDIENTE)

---

## 🤖 Robots (RPA – Power Automate Desktop)

### 7. Robot de Descarga y Consolidación de Reportes Web

**Resumen:**  

- Bot que ingresa a portales web corporativos.
- Descarga periódica de archivos de reporte (por fechas, períodos o filtros).
- Consolidación en un solo archivo para análisis posterior.

**Impacto:**

- Ahorro de tiempo en tareas repetitivas de descarga.
- Menos errores al evitar la intervención manual diaria o semanal.

**Video demo:**

- [Robot de descargas y consolidación de reportes](ENLACE_PENDIENTE)

---

### 8. Robot de Generación de Calendarios Laborales (excluyendo domingos y festivos)

**Resumen:**  

- Bot que, a partir de rangos de fechas, genera listas de días hábiles.
- Exclusión de domingos y festivos según una tabla de referencia.
- Salida en formatos útiles para planificación, programación de horas o cronogramas.

**Impacto:**

- Estandarización en el cálculo de días laborables.
- Menos errores al planear cronogramas y actividades.

**Video demo:**

- [Robot de generación de calendario laboral](ENLACE_PENDIENTE)

---

### 9. Robots para Carga y Actualización Masiva de Información

**Resumen:**  

- Bots encargados de cargar o actualizar registros en sistemas internos (vía web o archivos).
- Validaciones básicas antes de subir la información.
- Uso de variables paramétricas para reutilizar el flujo en distintos escenarios.

**Impacto:**

- Disminución de tiempos en procesos de carga masiva.
- Reducción de reprocesos por errores humanos de digitación.

**Video demo:**

- [Robot de carga masiva de información](ENLACE_PENDIENTE)

---

## 📱 Aplicaciones (Power Apps, Formularios inteligentes)

### 10. App de Solicitud y Gestión de Gastos

**Resumen:**  

- Aplicación para radicar, gestionar y aprobar solicitudes de gastos.
- Manejo de roles (gestor, aprobador, administrador).
- Integración con listas de SharePoint y flujos en Power Automate.

**Impacto:**

- Menos correos dispersos y formatos manuales.
- Mayor trazabilidad del estado de cada solicitud.

**Video demo:**

- [Demo de la app de Solicitud de Gastos](ENLACE_PENDIENTE)

---

### 11. App para Registro de Asistencia y Resultados de Capacitaciones

**Resumen:**  

- Formulario donde se registran asistentes a capacitaciones.
- Captura de preguntas clave, resultados o percepciones.
- Datos listos para análisis en dashboards de formación.

**Impacto:**

- Estandarización en el registro de la información de capacitación.
- Datos limpios y consolidados desde el origen.

**Video demo:**

- [App de registro de capacitaciones](ENLACE_PENDIENTE)

---

## 📑 Macros y Herramientas en Excel/VBA

### 12. Macros para Automatización de Facturación y Consolidación de Información

**Resumen:**  

- Macros que limpian, transforman y consolidan grandes volúmenes de datos.
- Generación de archivos listos para cargar en sistemas o analizar en BI.
- Automatización de pasos repetitivos en facturación o cierre de mes.

**Impacto:**

- Reducción de horas hombre dedicadas a tareas mecánicas.
- Menos errores al trabajar con grandes cantidades de filas y columnas.

**Video demo:**

- [Macros de facturación y consolidación](ENLACE_PENDIENTE)

---

### 13. Herramientas de Soporte en Excel (plantillas inteligentes)

**Resumen:**  

- Plantillas con fórmulas y macros para controlar provisiones, gastos o estados.
- Interfaces amigables para usuarios no técnicos.
- Integración con datos provenientes de otros sistemas.

**Impacto:**

- Mejora en la calidad y consistencia de la información reportada.
- Menor dependencia de archivos improvisados o no estandarizados.

**Video demo:**

- [Plantillas y herramientas avanzadas en Excel](ENLACE_PENDIENTE)

---

## 🔬 Proyectos experimentales / en desarrollo

### 6. MotoGlanz – Bot experimental de registro de lavados con IA (n8n + Telegram + OpenAI)

**Estado:** En desarrollo (prototipo, no productivo).

**Resumen:**  
Prototipo de flujo en **n8n** para que un bot de Telegram registre lavados de MotoGlanz usando IA:

- Recibe mensajes desde Telegram (texto y opcionalmente foto de la moto).
- Extrae el texto del chat y evalúa si el mensaje trae foto (`has_photo?`).
- Si hay foto:
  - Descarga el archivo desde Telegram (`Get a file`),
  - lo sube a Google Drive (`Upload_photo`) y
  - genera una URL (`URL_file` / `URL_file_empty` + `Join_photo_nophoto`).
- Construye el cuerpo de petición para el modelo de IA (`Build OpenAI Body`) y lo envía a un **AI Agent**:
  - Modelo de chat de OpenAI,
  - memoria en Postgres,
  - parser estructurado para devolver un JSON con datos del lavado (placa, tipo, valor, etc.).
- El flujo intenta:
  - Validar la información (`byModo`, `val_obligatorios`, `Complete_info?`),
  - insertar el registro como lavado completo (`Insert_lavado`) o como borrador (`Insert_borrador`),
  - responder al usuario por Telegram con confirmación o solicitud de datos faltantes.

**Objetivo del proyecto:**

- Pasar de conversaciones informales en chat a **registros estructurados** que luego alimenten una base de datos y dashboards.
- Reducir al mínimo la digitación manual en el registro de lavados.
- Explorar la integración entre bots, n8n y modelos de IA para automatizar la operación de MotoGlanz.

**Video demo (cuando esté listo):**

- [Bot experimental de registro de lavados – n8n + Telegram + IA](ENLACE_PENDIENTE)


---

## 📌 Nota sobre confidencialidad

Los proyectos descritos están basados en experiencia real en entornos corporativos y emprendimientos propios.  
Por confidencialidad:

- No se publica código fuente.
- No se exponen datos sensibles ni información identificable.
- Algunas demos usan datos ficticios o anonimizados, manteniendo la lógica del caso real.

Este repositorio sirve como **portafolio técnico y funcional**, complementado con videos demo de cada solución.

