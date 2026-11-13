# Librín — Biblioteca Digital Areandina

Asistente con interfaz HTML y servidor Node/Express. Revisión del código: 13 de noviembre de 2026.

## Implementación actual

`server.js` utiliza Groq, con `GROQ_API_KEY` en el entorno y el modelo configurado `llama-3.3-70b-versatile`. La documentación anterior describía Anthropic; no coincide con el servidor actual. La disponibilidad del proveedor/modelo no se probó en esta revisión.

Dependencias declaradas: express, cors y dotenv. Requiere una versión de Node compatible con `fetch` nativo. El servidor atiende la interfaz y seis rutas POST: `/api/chat`, `/api/verificar`, `/api/reserva`, `/api/renovar`, `/api/prestamo` y `/api/soporte`.

Las operaciones bibliotecarias dependen de flujos n8n externos al repositorio. El código usa `http://localhost:5678/webhook` con rutas Librin, Librin-verificar y Librin-renovar. Confirmar esos flujos y sus permisos en el entorno autorizado antes de probar acciones.

## Preparación local

1. Clonar este repositorio e instalar las dependencias declaradas (`npm install`).
2. Configurar `GROQ_API_KEY` en un `.env` local excluido de Git. `PORT` es opcional; el valor predeterminado es 3000.
3. Preparar n8n local y revisar sus flujos con datos ficticios.
4. Ejecutar `npm start`; visitar `http://localhost:3000`.

No se ejecutaron estas instrucciones durante la centralización. No colocar claves en el frontend ni subir `.env`, datos personales o registros operativos a GitHub.

## Despliegue y pendientes

GitHub Pages sirve archivos estáticos; no ejecuta Express ni n8n. Tener una página accesible no acredita un chatbot operativo. El repositorio contiene además `chatbot_connector.php` y archivos de otras propuestas: revisar cuál implementación debe mantenerse. Validar autenticación, exposición de archivos y CORS antes de desplegar institucionalmente.

Repositorio transferido desde REKOL08 a BIBLIOTECAS-AREANDINA conservando historial, nombre y visibilidad pública. No se modificó código de aplicación ni producción.

[Inventario y evidencias de centralización](https://github.com/BIBLIOTECAS-AREANDINA/BIBLIONOVA/blob/main/docs/CENTRALIZACION_2026-11-13.md).
