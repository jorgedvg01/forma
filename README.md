# Forma · De tu idea a tu equipo

Prototipo web para aprender a organizar un proyecto entre varias conversaciones de IA. El alumno concreta su idea, explora recomendaciones, aprueba las áreas del equipo y prepara los encargos que puede llevar a ChatGPT o Claude.

## Qué incluye

- Organigrama con supercoordinador, coordinadores y trabajadores.
- Tres áreas esenciales en este prototipo: diseño, funcionamiento y pruebas y calidad.
- Recomendaciones en tarjetas que se pueden aceptar o descartar.
- Aprobación de departamentos antes de preparar los trabajadores.
- Elección del número de propuestas y de lo que variará entre ellas.
- Tutorial animado, con cursor, escritura, pausa y avance por pasos.
- Exportación ZIP para ChatGPT y Claude, con plan, roles, encargos y reglas de coordinación.
- Guardado del proyecto en el navegador mediante `localStorage`.

## Estado y límites

Esta versión es un **prototipo sin IA conectada**. Las preguntas y recomendaciones se seleccionan de contenido preparado para algunos temas; todavía no existe generación adaptativa para una idea arbitraria. El reparto mostrado tiene tres departamentos y seis encargos ilustrativos.

El tutorial representa una simulación. No demuestra que una aplicación real se haya construido o probado.

La exportación descarga archivos: **no crea chats ni conecta agentes automáticamente**. El usuario debe iniciar las conversaciones y configurar un canal compatible, o trasladar manualmente los informes. Las definiciones incluidas para Claude Code son roles reutilizables, no una garantía de jerarquías anidadas ni un importador de chats de claude.ai.

El motor de ejecución, la mensajería real, la planificación adaptativa y los controles de consumo forman parte del trabajo futuro.

## Ejecutar en local

Requiere Python 3 para servir los archivos estáticos. Desde la carpeta del repositorio:

```powershell
python -m http.server 8080 --bind 127.0.0.1 --directory dist
```

Abre `http://127.0.0.1:8080/` en el navegador. No hay instalación de paquetes ni compilación.

Para comprobar la sintaxis del código con Node.js:

```powershell
node --check dist/app.js
```

## Archivos

| Ruta | Contenido |
| --- | --- |
| `dist/index.html` | Estructura y diálogo de exportación |
| `dist/styles.css` | Interfaz, tema claro/oscuro y adaptación a móvil |
| `dist/app.js` | Estado, tarjetas, tutorial, planificación y exportaciones |
| `dist/vendor/` | JSZip y Lucide, con sus avisos y licencias |
| `.openai/hosting.json` | Identificador y configuración del Site existente |

La configuración de hosting identifica el Site del propietario. Si reutilizas el código para un Site diferente, no publiques sobre ese identificador.

## Datos y exportaciones

La aplicación guarda el proyecto en el almacenamiento del navegador. Al usar dispositivos compartidos, ten en cuenta que la información puede permanecer guardada. Puedes eliminarla desde la configuración de datos del sitio del navegador.

El ZIP incluye el contenido introducido por el usuario, las ideas aceptadas, las preferencias y los encargos. Revísalo antes de compartirlo. No se requieren claves API y el código de la aplicación no envía peticiones a proveedores de IA.

## Publicación

La versión alojada está en [Sites](https://divide-coordina-construye-jorge.iesvalledelj-9029.chatgpt.site). Su acceso se gestiona por separado del repositorio de GitHub.

## Dependencias incluidas

- JSZip 3.10.1, para generar archivos ZIP en el navegador.
- Lucide 0.468.0, para los iconos.

Se conservan los avisos de los archivos distribuidos y las licencias originales en `dist/vendor/`.
