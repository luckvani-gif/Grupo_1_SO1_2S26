
Registro de uso de Inteligencia Artificial
Fecha: 19/11/2026

- Herramienta: ChatGPT.
- Tarea: Diagnóstico y resolución de problemas de sincronización horaria y certificados SSL durante la descarga de paquetes de Linux From Scratch.
- Propósito: Identificar por qué `wget` rechazaba los certificados SSL de servidores como kernel.org, pypi.org y python.org, impidiendo descargar algunos paquetes necesarios para LFS.
- Verificaciones realizadas:
  1. Se activó el servicio `chronyd` y se ejecutó `chronyc makestep`.
  2. Se verificó la sincronización mediante `chronyc tracking`, obteniendo `Leap status: Normal`.
  3. Se probó la conexión HTTPS con `wget --spider https://www.kernel.org`, obteniendo una respuesta HTTP 200 OK sin errores de certificado.
  4. Se descargaron los 17 paquetes que faltaban.
  5. Se ejecutó `md5sum -c md5sums` para comprobar la integridad de los paquetes y parches. Todos presentaron coincidencias con los valores esperados.

- Modificaciones realizadas por el grupo: Sincronización del reloj del sistema mediante NTP, descarga de los paquetes faltantes y verificación de sus checksums MD5.

