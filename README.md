# tajamar-tech-projects
# Gestión Automatizada de Contratos (RRHH) - Solución Power Platform

Solución desarrollada en Microsoft Power Platform para la gestión integral
del ciclo de vida de contratos laborales.  
Incluye automatización documental, aprobaciones multinivel y trazabilidad
completa del proceso.

# Problemática 

En departamentos de RRHH:

- Procesos manuales en la generación de contratos
- Demoras en aprobaciones.
- Falta de trazabilidad.
- Ausencia de control multinivel con respecto a aprobaciones.

Esta solución digitaliza y estandariza el proceso.


# Arquitectura de la solución

Modelado de datos en Dataverse

Creación de la aplicación  con model-driven

Automatización de flujos de aprobación multinivel mediante Power Automate

Generación automática de contratos (borrador) en Word

Conversión a PDF tras aprobación final

Integración con SharePoint para almacenamiento  y trazabilidad documental



# Flujo de la aplicación

Creación del contrato en la Model-Driven.
Cambio de estado  para generar el borrador en una plantilla de word 
Pendiente de aprobación del responsable de RRHH.
Aprobación multinivel.
Validación del responsable
Generación automática de contrato en PDF
Envío del contrato contrato al candidato
Recepción y validación del contrato firmado
Almacenamiento en SharePoint
Transferencia a biblioteca definitiva
Registro en bitácora para auditoría



# Tecnologías utilizadas

Microsoft Power Apps

Microsoft Power Automate

Microsoft Dataverse

Microsoft SharePoint

Word Online (Business)

# Documentación

 [Automatizaciones](Documentation/images/gestion-contratos/flujos.md)
