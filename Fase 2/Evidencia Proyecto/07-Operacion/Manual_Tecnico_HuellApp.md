# Manual técnico de HuellApp

HuellApp · Pudú Tech · Borrador 0.1 · 27 de octubre de 2026

Este manual orienta la preparación de un ambiente de desarrollo y el traspaso técnico de la versión inspeccionada. Antes de operar un ambiente con datos de Huella deben identificarse responsables, respaldos y configuración. Los comandos de este documento no fueron ejecutados como parte de la revisión documental.

## Componentes y versiones declaradas

| Componente | Declaración en repositorio | Uso |
| --- | --- | --- |
| React y React DOM | 19.2.8 | Interfaz web. |
| TypeScript y Vite | ~6.0.2 y 8.3.0 | Compilación y desarrollo frontend. |
| Supabase JS | 2.117.0 | Sesión de usuario. |
| FastAPI y Uvicorn | 0.141.1 y 0.52.4 | API y servidor de desarrollo. |
| Pydantic y Supabase Python | 2.13.5 y 2.31.0 | Validación y acceso a servicios. |

Son versiones declaradas en archivos del commit, no una verificación de las instaladas en producción. La versión soportada de Node y Python se debe fijar con el equipo y comprobar con una instalación limpia.

## Estructura del repositorio

frontend contiene la aplicación React; backend contiene app, API, servicios y configuración; supabase contiene migraciones y pruebas SQL; docs reúne guías particulares. Revisar los archivos de despliegue y dependencias del commit que se vaya a entregar.

## Preparación de desarrollo

En una copia autorizada del código, abrir frontend e instalar las dependencias con el gestor y lockfile del proyecto. Si existe un package-lock.json consistente, usar npm ci; en otro caso el equipo debe resolver el lockfile antes de considerar reproducible la instalación.

```text
cd frontend
npm ci
npm run dev
npm run build
npm run lint
```

En backend, preparar un entorno virtual e instalar requirements.txt. Desde esa carpeta se puede iniciar el servidor de desarrollo con el módulo app.main. No activar recarga automática en producción.

```text
cd backend
python -m venv .venv
# Activar el entorno virtual según el sistema operativo
python -m pip install -r requirements.txt
python -m uvicorn app.main:app --reload
```

## Variables y secretos

El frontend utiliza VITE_API_URL, VITE_SUPABASE_URL y VITE_SUPABASE_PUBLISHABLE_KEY. El backend define SUPABASE_URL, SUPABASE_SECRET_KEY, FRONTEND_URL, APP_ENV y CORS_ORIGINS mediante Pydantic Settings. CORS_ORIGINS corresponde a una lista de orígenes; configurar su representación conforme al tipo declarado. Entregar valores privados por un canal reservado, nunca en este manual ni en GitHub.

SUPABASE_SECRET_KEY, claves de correo, GOOGLE_MAPS_API_KEY y secretos de despacho pertenecen al servidor cuando correspondan. El nombre de una variable no acredita que el servicio esté contratado o activo. Revisar app/core/config.py y los clientes reales al actualizar la versión.

## Base de datos y migraciones

Preparar un proyecto de prueba separado. Revisar README y el orden de las migraciones 001 a 055, incluidas operaciones de cambio y reconstrucción de esquema. No ejecutar de nuevo el baseline sobre una base existente. Registrar qué migraciones se aplicaron y probar permisos y relaciones antes de cargar información autorizada de Huella. No se adjunta SQL de otro proyecto.

## Correo de participación

La guía docs/correos_vercel.md describe inserciones en notificacion_envios, un Database Webhook hacia /internal/notifications/webhook y un cron de recuperación en /internal/notifications/cron. Configurar NOTIFICATION_WEBHOOK_SECRET y CRON_SECRET en backend, y las credenciales del proveedor según el código. El cron diario está documentado para 08:17 UTC en producción; no se usa como garantía de entrega inmediata. Validar eventos, autenticación del webhook y recepción con un correo controlado.

## Asistencia y dirección legible

La ubicación se solicita al usuario. Coordenadas y precisión se conservan; el proveedor de geocodificación es opcional para una dirección legible. Su fallo no debe confundirse con ausencia de coordenadas. Antes de habilitar el proveedor, revisar credenciales, restricciones, costos y tratamiento de datos.

## Despliegue y comprobación

Identificar proyectos Vercel de frontend y backend, proyecto Supabase y variables por ambiente. Vincular cada despliegue con su commit. Comprobar salud del servicio, login, CORS, permisos, migraciones y un flujo de negocio completo. Las rutas de documentación de FastAPI se deshabilitan en producción según la configuración revisada.

## Respaldo y recuperación

El traspaso debe incluir procedimiento y acceso autorizado a respaldos. Acordar frecuencia, retención, RPO y RTO. Realizar una restauración aislada y registrar fecha, versión, responsable y resultado antes de considerar comprobada la recuperación. Los alcances de Auth, archivos y configuración se deben incluir explícitamente; una copia de tablas no garantiza recuperarlos.

## Diagnóstico y límites

Ante un acceso fallido, diferenciar sesión inválida, perfil inactivo y permiso insuficiente. Ante un correo no recibido, revisar cola, intento, respuesta del proveedor y buzón. Ante un error de asistencia, revisar participación, horario y permiso GPS. Los logs deben permitir investigar sin exponer contraseñas, tokens o datos personales innecesarios.

## Fuentes y documentos relacionados

F2: acuerdos de trabajo ratificados por Matías y acta propia actualizada; F3: código develop d2b651f42703 del 20/10/2026. Identificación y límites en Fuentes y revisión del índice del paquete.

## Validación pendiente

Comprobar instalación limpia, versiones de runtime, inventario exacto de variables, restauración y despliegue de entrega.
