# Plan de pruebas de HuellApp

HuellApp · Pudú Tech · Borrador 0.1 · 27 de octubre de 2026

El plan organiza la comprobación del alcance sobre versiones identificadas. Su registro operativo es el Excel QA existente; los casos añadidos o ajustados deben vincularse a requisitos e issues sin sobrescribir resultados históricos.

## Alcance y niveles

| Nivel | Qué comprobar | Registro |
| --- | --- | --- |
| Revisión estática | Requisitos, permisos, migraciones y configuración declarada. | Archivo y commit; no se cuenta como prueba ejecutada del producto. |
| API e integración | Identidad, permisos, datos, errores y persistencia entre componentes. | Petición saneada, estado, resultado y versión. |
| Sistema | Recorridos por rol y sus alternativas. | Caso, pasos, entorno y evidencia. |
| Validación con usuarios | Lenguaje, secuencia y adecuación al trabajo de Huella. | Acta con observación, decisión y responsable. |
| Regresión | Funciones afectadas después de una corrección o cambio. | Versión corregida, resultado y evidencia de repetición. |

## Preparación y criterios de entrada

Fijar commit de frontend y backend, URL del despliegue y versión de migraciones. Preparar cuentas de prueba por rol, datos ficticios y actividades con horarios controlados. Confirmar servicios necesarios y conservar los datos iniciales para comparar cambios. No usar información personal real en capturas públicas.

## Recorridos prioritarios

Crear cuenta desde Directiva, completar habilitación, crear actividad y asignación, responder participación y consultar la programación. Después probar asistencia, cambios y reconfirmación, ticket de salida y seguimiento. El correo debe probarse con un buzón controlado y distinguir el aviso interno de la recepción externa.

## Pruebas negativas necesarias

Probar credenciales inválidas y perfiles inactivos; consultas sin sesión y con rol insuficiente; acceso a registros de otro usuario; duplicados; campos inválidos; respuestas fuera de plazo; edición concurrente; rechazo y reconfirmación; denegación GPS y errores de proveedor. Para autorización API, una URL abierta en el navegador sin Bearer token prueba ausencia de autenticación, no el permiso de un Monitor autenticado.

## Resultados y defectos

Aprobado exige resultado observado, evidencia, fecha, responsable, rol, entorno y versiones. Bloqueado identifica su causa y siguiente acción. Fallido vincula el hallazgo y conserva el comportamiento observado. Pendiente indica que no hay un resultado de ejecución registrado. La gravedad se revisa por impacto y no se deduce del código HTTP por sí solo.

## Salida y aceptación

La entrega debe satisfacer el DoD ratificado. Se propone exigir todos los flujos comprometidos comprobados y ningún defecto crítico o alto que los impida, salvo tratamiento expresamente acordado. Los indicadores se calcularán sobre un plan definido; no se transformará el número de issues cerradas en cobertura de pruebas.

## Automatización y evidencia

El repositorio contiene pruebas SQL y tests de backend, cuya presencia no acredita ejecución. El frontend no declara un script npm test en el package.json revisado. Se documentará el comando realmente utilizado, sus dependencias y resultado cuando se ejecuten pruebas, sin inventar salidas exitosas.

## Fuentes y documentos relacionados

F2: acuerdos de trabajo ratificados por Matías y acta propia actualizada; F3: código develop d2b651f42703 del 20/10/2026; F5: registro QA con modificación del 18/10/2026. Identificación y límites en Fuentes y revisión del índice del paquete.
