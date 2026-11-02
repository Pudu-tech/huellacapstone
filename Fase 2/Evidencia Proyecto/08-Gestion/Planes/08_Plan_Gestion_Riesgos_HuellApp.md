# Plan de gestión de riesgos de HuellApp

HuellApp · Pudú Tech · Borrador 0.1 · 27 de octubre de 2026

## Identificación y evaluación

Registrar un evento incierto, su causa y efecto sobre producto, plazo, datos u operación. Distinguirlo de un defecto ya observado. El registro anexo contiene riesgos propuestos a partir de las brechas detectadas, sin atribuir una probabilidad aprobada por el equipo.

## Escala propuesta

Usar probabilidad e impacto de 1 a 3, donde 1 es bajo y 3 alto. Su producto orienta el orden: 1 a 2 bajo, 3 a 4 medio y 6 a 9 alto. El equipo debe validar las valoraciones; mientras falten, el nivel queda pendiente y no se calcula como cero.

## Respuestas

Reducir ambigüedad con criterios acordados; mitigar riesgos técnicos con pruebas y revisión; reducir dependencia de una persona documentando configuración; preparar alternativas de operación cuando un proveedor falle. Una reserva económica no se fija como porcentaje automático sin una estimación y autorización.

## Riesgos principales

| ID | Evento y efecto | Respuesta propuesta |
| --- | --- | --- |
| R-01 | Alcance ambiguo de ticket y seguimiento. Construcción o aceptación tardía. | Cerrar campos, permisos y ejemplos con Huella antes de implementar. |
| R-02 | Diferencia entre código, issues y QA. Planificar sobre avance no comprobado. | Reconciliar criterio, versión y evidencia antes de cerrar. |
| R-03 | Capacidad limitada por carga académica. Retraso de integración y documentación. | Planificar con disponibilidad real y priorizar dependencias. |
| R-04 | Datos o validación de Huella no disponibles. Pruebas y entrega sin representatividad. | Solicitar datos mínimos autorizados y agendar revisiones. |
| R-05 | Permiso incorrecto o exposición de datos. Acceso indebido y pérdida de confianza. | Pruebas negativas de API, revisión de secretos y datos de evidencia. |
| R-06 | Correo o webhook mal configurado. Avisos no recibidos aunque la asignación exista. | Prueba controlada de cola, intento y recepción; registrar fallas. |

La planilla incluye además continuidad de servicios, recuperación, formalización de acuerdos y pauta académica. Cada riesgo debe tener dueño, señal de activación, acción y revisión. La materialización de un riesgo se registra como incidencia y se evalúa su impacto real.

## Seguimiento

Matías consolida la revisión con el equipo. Felipe gestiona riesgos que requieren decisión de Huella e Ignacio los controles técnicos. Revisar en cada planificación y ante cambios relevantes; registrar fecha, decisión y efecto de las acciones.

## Fuentes y documentos relacionados

F2: acuerdos de trabajo ratificados por Matías y acta propia actualizada; F3: código develop d2b651f42703 del 20/10/2026; F4: 49 issues consultadas el 27/10/2026; F5: registro QA con modificación del 18/10/2026. Identificación y límites en Fuentes y revisión del índice del paquete.

## Validación pendiente

Asignar probabilidad e impacto con el equipo y aprobar respuestas y dueños.
