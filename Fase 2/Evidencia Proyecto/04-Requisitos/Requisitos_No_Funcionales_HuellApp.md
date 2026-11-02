# Requisitos no funcionales de HuellApp

HuellApp · Pudú Tech · Borrador 0.1 · 27 de octubre de 2026

Estos requisitos describen condiciones de calidad a comprobar, no certificaciones obtenidas. Los objetivos numéricos que dependen de capacidad, servicio contratado o tolerancia del cliente deben acordarse antes de usarlos como criterio de aceptación.

## Requisitos y verificación

| ID | Categoría | Condición y verificación |
| --- | --- | --- |
| HU-RNF-01 | Autorización | Validar identidad y permiso en el servidor para cada operación protegida. Probar sin token, token inválido y token válido sin permiso; verificar ausencia de datos o cambios. |
| HU-RNF-02 | Confidencialidad | Restringir datos personales, ubicación y evidencia al propósito y roles autorizados. Revisar consultas, registros y exportaciones; definir retención y eliminación con Huella. |
| HU-RNF-03 | Integridad | Mantener relaciones válidas y operaciones consistentes ante error o repetición. Probar duplicidad, edición concurrente y fallos; revisar restricciones y transacciones. |
| HU-RNF-04 | Usabilidad y acceso | Permitir los recorridos principales con etiquetas comprensibles y controles utilizables en pantalla móvil. Prueba guiada con usuarios y revisión de teclado, foco, contraste y mensajes. No se declara certificación. |
| HU-RNF-05 | Rendimiento | Acordar tiempos aceptables para acciones críticas en una carga y conexión definidas. Medir antes de ratificar umbral. El antecedente de 3 segundos no está validado con condiciones de ensayo. |
| HU-RNF-06 | Recuperación | Disponer de un procedimiento de respaldo y restauración comprobable. Acordar RPO y RTO y ensayar restauración aislada; retención y frecuencia pendientes. |
| HU-RNF-07 | Mantenibilidad | Entregar instrucciones reproducibles, configuración separada y migraciones versionadas. Un responsable distinto prepara un entorno de prueba con el manual, sin secretos en el repositorio. |
| HU-RNF-08 | Trazabilidad | Identificar versión, actor y eventos necesarios para investigar cambios y fallas. Vincular prueba, issue, commit y despliegue; revisar catálogo de eventos y datos sensibles. |
| HU-RNF-09 | Operación de correo | Distinguir notificación pendiente, intento, envío y fallo sin duplicar acciones de negocio. Probar cola, webhook, proveedor y recuperación; no asumir recepción solo por respuesta exitosa de API. |

## Decisiones técnicas relacionadas

React separa la interfaz del backend FastAPI y Supabase aporta identidad y persistencia. Esta separación permite controles en servidor y cambios de interfaz, pero no garantiza por sí sola seguridad, disponibilidad o rendimiento. Los permisos, políticas y configuración deben probarse sobre el entorno real.

## Pendientes para aceptación

Se debe acordar volumen esperado, tiempos aceptables, navegadores soportados, retención de datos y ubicación, frecuencia de respaldos, pérdida de datos tolerable y tiempo de recuperación. Hasta entonces, la planilla conserva esos valores como pendientes, sin reemplazarlos por cero ni por metas de otro proyecto.

## Fuentes y documentos relacionados

F2: acuerdos de trabajo ratificados por Matías y acta propia actualizada; F3: código develop d2b651f42703 del 20/10/2026; F6: necesidades y SRS históricos de Huella. Identificación y límites en Fuentes y revisión del índice del paquete.

## Validación pendiente

Ratificar parámetros de rendimiento, recuperación, retención y compatibilidad.
