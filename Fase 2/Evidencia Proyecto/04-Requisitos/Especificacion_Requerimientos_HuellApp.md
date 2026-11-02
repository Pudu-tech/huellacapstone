# Especificación de requerimientos de HuellApp

HuellApp · Pudú Tech · Borrador 0.1 · 27 de octubre de 2026

Esta especificación descompone las capacidades acordadas en requisitos verificables. Los identificadores HU-RF son propios de esta revisión; no sustituyen silenciosamente los RF históricos ni los números de GitHub.

## Contexto y actores

La aplicación apoya la operación de Fundación Huella. Directiva, Coordinador y Monitor son roles de negocio. SUPERADMIN es un perfil técnico. Los permisos efectivos deben contrastarse con la matriz acordada y con el servidor, sin deducirlos únicamente del menú visible.

## Referencias históricas y límites

El SRS histórico combina requisitos de Huella con ejemplos de una plantilla ajena al dominio. Esta revisión excluye esos ejemplos y conserva una correspondencia explícita. Los recordatorios a dos días, un día y dos horas, y el límite genérico de tres segundos aparecen como antecedentes, no como resultados medidos ni como condiciones ratificadas para esta versión.

## Requisitos funcionales

### HU RF 01 Autenticación y permisos

Una cuenta activa debe acceder a las funciones autorizadas por su rol. El servidor debe rechazar operaciones sin credenciales válidas o sin permiso.

Actores: Directiva, Coordinador y Monitor. Precondición: Cuenta activa con rol; probar también cuenta inactiva y sin sesión.

Criterio de aceptación: Inicio válido muestra el perfil correcto; acceso no autorizado no devuelve ni altera datos.

Trazabilidad: issues 1-10,49; Histórico RF-01. Estado documental: Código disponible y QA parcial.

### HU RF 02 Invitación y habilitación de cuentas

Crear el perfil e invitar a su titular, asociando la habilitación a una identidad de autenticación y al rol definido.

Actores: Directiva o administrador autorizado. Precondición: Correo de prueba controlado, identidad única y permiso de gestión.

Criterio de aceptación: Perfil e identidad quedan relacionados; la invitación permite completar el acceso y no habilita funciones de otro rol.

Trazabilidad: issues 1,19; Histórico RF-01. Estado documental: Flujo declarado probado; conciliar evidencia.

### HU RF 03 Gestión de colegios

Registrar, consultar y mantener los colegios usados en la planificación, respetando validaciones y dependencias.

Actores: Usuario con permiso institucional. Precondición: Catálogos requeridos disponibles.

Criterio de aceptación: No se duplican identificadores válidos y los cambios conservan relaciones o informan su restricción.

Trazabilidad: issues 11-18; Necesidades operativas y alcance actual. Estado documental: Código disponible; validación integral pendiente.

### HU RF 04 Gestión de cursos y salas

Relacionar los cursos y salas con el colegio correspondiente para planificar actividades.

Actores: Usuario con permiso institucional. Precondición: Colegio habilitado y nivel válido.

Criterio de aceptación: La consulta distingue colegio y curso; no acepta relaciones inexistentes o no autorizadas.

Trazabilidad: issues 11-18,21; Necesidades operativas y alcance actual. Estado documental: Código disponible; validación integral pendiente.

### HU RF 05 Gestión de contactos

Mantener contactos de colegios y vincularlos a actividades cuando corresponda.

Actores: Usuario con permiso institucional. Precondición: Colegio y datos de contacto autorizados.

Criterio de aceptación: El contacto queda asociado al colegio correcto y solo es consultado o editado por perfiles autorizados.

Trazabilidad: issues 18,20,22; Alcance actual. Estado documental: Código disponible; validación pendiente.

### HU RF 06 Planificación de actividades

Crear y editar espacios de reflexión y otros tipos acordados, con fecha, horario, ubicación y contexto aplicables.

Actores: Directiva y Coordinador según permiso. Precondición: Tipo permitido y datos institucionales requeridos.

Criterio de aceptación: La actividad válida se conserva; una edición relevante informa y trata la reconfirmación según regla acordada.

Trazabilidad: issues 23-25,27,39; Histórico RF-02 descompuesto. Estado documental: Código disponible; reglas por ratificar.

### HU RF 07 Asignación de participantes

Vincular participantes con una actividad y distinguir su respuesta de su asistencia.

Actores: Usuario con permiso de gestión. Precondición: Actividad y usuarios habilitados.

Criterio de aceptación: La asignación aparece al participante correcto; no se crean duplicados incompatibles ni se marca asistencia al asignar.

Trazabilidad: issues 24-27; Histórico RF-02 descompuesto. Estado documental: Flujo declarado probado; conciliar evidencia.

### HU RF 08 Respuesta a una participación

Permitir aceptar o rechazar la participación propia y aplicar las reglas de plazo y de cambios.

Actores: Monitor o participante asignado. Precondición: Participación propia y plazo aplicable.

Criterio de aceptación: La respuesta se registra para el participante correcto; aceptar confirma participación y no acredita ejecución ni asistencia.

Trazabilidad: issues 29,32; Histórico RF-02 descompuesto. Estado documental: Flujo declarado probado; completar casos negativos.

### HU RF 09 Consulta de la programación

Mostrar las actividades que el usuario puede consultar con sus fechas, estado y detalle necesario.

Actores: Monitor, Coordinador y Directiva según permiso. Precondición: Usuario autenticado y actividad visible según permiso.

Criterio de aceptación: El usuario encuentra la actividad asignada y su detalle sin acceder a información ajena no autorizada. La vista de calendario exacta se ratifica.

Trazabilidad: issues 28,32; Histórico RF-02 descompuesto. Estado documental: Lista y detalle en código; vista visual por ratificar.

### HU RF 10 Avisos y recordatorios

Gestionar avisos de participación y definir cuáles recordatorios temporales se incluyen en la primera entrega.

Actores: Participantes y usuarios autorizados. Precondición: Canal, eventos, destinatarios y configuración acordados.

Criterio de aceptación: La prueba distingue aviso creado, intento, envío y recepción; horarios de recordatorio se acuerdan antes de aceptar.

Trazabilidad: issues 31; Histórico RF-04 sujeto a nueva validación. Estado documental: Mecanismo de correo disponible; alcance y entrega pendientes.

### HU RF 11 Asistencia con ubicación

Registrar estado de asistencia asociado a la participación y conservar ubicación informada por el dispositivo; regularizar con autorización y motivo.

Actores: Participante y administrador autorizado. Precondición: Participación aceptada, ventana temporal y permiso GPS cuando corresponda.

Criterio de aceptación: Se respetan autoría y ventana temporal; la ubicación no se usa como prueba infalible de presencia. Fallas del proveedor de dirección no invalidan coordenadas válidas.

Trazabilidad: issues 30,32; Acuerdo actualizado de alcance. Estado documental: Código y reglas disponibles; prueba integral pendiente.

### HU RF 12 Ticket de salida

Registrar la actividad realizada y sus datos de cierre mediante el ticket de salida.

Actores: Monitor y roles de consulta a definir. Precondición: Campos, evidencia, autoría, permisos y condición de cierre acordados.

Criterio de aceptación: Guardar y consultar un ticket válido vinculado a la actividad; impedir cierre incompleto o duplicado según regla que se apruebe.

Trazabilidad: issues 33-36; Histórico RF-02 descompuesto. Estado documental: Comprometido; definición e implementación por comprobar.

### HU RF 13 Seguimiento y reportes

Consultar el estado de actividades y participación y los reportes mínimos acordados, sin atribuir una evaluación de desempeño no definida.

Actores: Coordinador y Directiva según permiso. Precondición: Indicadores, filtros, visibilidad y fuentes especificados.

Criterio de aceptación: La consulta coincide con registros de origen y distingue no informado, ausente y no aplicable.

Trazabilidad: issues 37,38,40; Histórico RF-03 acotado a validar. Estado documental: Alcance detallado y validación pendientes.

### HU RF 14 Auditoría operativa

Conservar y consultar los eventos de gestión y autenticación definidos, con actor, acción y referencia temporal.

Actores: Usuario con permiso de auditoría. Precondición: Catálogo de eventos y permisos de consulta definidos.

Criterio de aceptación: Un evento controlado es trazable y no expone secretos; los eventos no definidos no se presumen cubiertos.

Trazabilidad: issues 10,41; Alcance actualizado. Estado documental: Módulo en código; cobertura y validación pendientes.

### HU RF 15 Perfil personal

Consultar y actualizar los datos de perfil permitidos, separando cambios de identidad o rol que requieren permiso administrativo.

Actores: Usuario autenticado. Precondición: Perfil existente y campos editables definidos.

Criterio de aceptación: El usuario modifica solo los campos permitidos y no eleva su rol ni altera datos ajenos.

Trazabilidad: issues 1,19; Histórico RF-05. Estado documental: Código y migración 055; validación pendiente.

## Reglas transversales y excepciones

La creación y edición deben informar datos inválidos sin dejar operaciones parciales. Una sesión válida no concede todos los permisos. Las consultas vacías se distinguirán de un fallo del servicio. Las ediciones relevantes y los cambios de estado deben mantener trazabilidad y evitar respuestas desactualizadas o duplicadas. Las reglas exactas del ticket, recordatorios y reportes deben cerrarse con Huella.

## Validación y control

Cada requisito se relacionará con al menos un criterio y un caso de QA de la misma versión. Las relaciones propuestas en la planilla se validarán antes de declarar cobertura. Toda eliminación o ampliación requiere evaluar impacto y registrar la decisión; no se elimina un requisito solo porque aún no esté implementado.

## Fuentes y documentos relacionados

F1: informes oficiales 1.4, 1.5, 2.4 y guía 2.6; F2: acuerdos de trabajo ratificados por Matías y acta propia actualizada; F3: código develop d2b651f42703 del 20/10/2026; F4: 49 issues consultadas el 27/10/2026; F6: necesidades y SRS históricos de Huella. Identificación y límites en Fuentes y revisión del índice del paquete.

## Validación pendiente

Ratificar reglas abiertas y matriz de permisos con Huella; revisar cada criterio antes de adoptar esta línea base.
