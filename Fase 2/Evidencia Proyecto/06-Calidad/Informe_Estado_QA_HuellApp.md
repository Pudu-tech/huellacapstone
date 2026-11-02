# Informe del estado registrado de QA de HuellApp

HuellApp · Pudú Tech · Borrador 0.1 · 27 de octubre de 2026

El registro revisado contiene 318 casos y muestra cobertura de ejecución parcial. Este informe lee el archivo con modificación del 18 de octubre de 2026; no vuelve a ejecutar pruebas ni valida los enlaces privados de evidencia.

## Resultados registrados

| Resultado | Cantidad | Interpretación |
| --- | --- | --- |
| Aprobado | 16 | Resultado informado en la planilla; debe conservar su versión y respaldo. |
| Bloqueado | 3 | Casos académicos de issue 45 dependientes de pauta o definición. |
| Pendiente | 299 | No presentan ejecución concluida en la columna de resultado. |
| Fallido | 0 | No hay filas con este resultado; no implica ausencia de defectos. |
| Total | 318 | Incluye comprobaciones de producto y de entrega académica. |

Los 16 aprobados se distribuyen entre tareas académicas de la issue 45, estructura de usuarios de la issue 2, pantalla de acceso de la issue 6 y casos de autenticación de la issue 9. No constituyen una tasa de calidad del producto ni acreditan el cierre del alcance completo.

## Hallazgos a revisar

| ID y caso | Situación registrada | Acción recomendada |
| --- | --- | --- |
| HA-001 / QA-06-03 | Un fallo de conexión se informa como credenciales incorrectas. Estado Nuevo, gravedad Baja según el archivo. | Repetir con fallo de red controlado y verificar que el mensaje permita entender el problema sin revelar datos. |
| HA-002 / QA-09-09 | Se observó HTTP 401 al abrir /users esperando 403. Estado Nuevo, gravedad Baja según el archivo. | Confirmar si se envió un token válido de Monitor. Sin él, 401 no demuestra fallo de autorización. Repetir petición autenticada antes de confirmar el defecto. |

La presentación de un JSON por una API tampoco exige una página HTML de error. Deben separarse contrato API y respuesta de la interfaz. Esta precisión no cambia el hallazgo original ni su evidencia; propone revisar la interpretación antes de asignar una corrección.

## Diferencias temporales

La planilla vincula las issues 1 a 47 al corte anterior. El snapshot consultado el 27 de octubre contiene 49 issues. El código de referencia es del 20 de octubre; no se asume que sea la versión probada el 18. Las pruebas afectadas por cambios posteriores requieren una repetición identificable.

## Trabajo prioritario

Registrar los cinco flujos que Matías declaró probados con su versión y evidencia; completar casos negativos; comprobar correo de asignación; repetir autorización API correctamente; completar asistencia, ticket y seguimiento. El flujo declarado probado por el usuario y el estado Pendiente de una fila deben conciliarse sin modificar resultados por inferencia.

## Fuentes y documentos relacionados

F3: código develop d2b651f42703 del 20/10/2026; F4: 49 issues consultadas el 27/10/2026; F5: registro QA con modificación del 18/10/2026. Identificación y límites en Fuentes y revisión del índice del paquete.
