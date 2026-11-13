# Misión Energía Austral · Guía de instalación

Juego de autoaprendizaje para la etapa de compensación de Educación Tecnológica (2° año, CIEU).
Tiene 4 niveles de profundidad (Reconocer, Comprender, Relacionar y Aplicar) y en cada uno aparecen los 4 temas:

1. Procesos de transformación de la energía (recurso energético, fuentes de energía)
2. Centrales de generación de energía eléctrica (funcionamiento y medios técnicos)
3. Sistemas técnicos en una central
4. Etapas del proyecto tecnológico

Cada nivel tiene: **lectura → explicación interactiva → desafío con puntaje → informe de contenidos a reforzar**.

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `index.html` | El juego completo. Es lo que subís al repositorio. |
| `Code.gs` | El script que guarda el progreso en tu planilla y crea los certificados en tu Drive. |

## Paso 1 · Crear la planilla y el script

1. Creá una planilla nueva de Google Sheets (por ejemplo: *Compensación 2° año · Misión Energía Austral*).
2. En la planilla, abrí **Extensiones › Apps Script**.
3. Borrá lo que aparece y pegá todo el contenido de `Code.gs`. Guardá (💾).
4. Arriba, elegí la función **configurar** y tocá **Ejecutar**. Aceptá los permisos (Sheets y Drive).
   Se crean las hojas *Progreso* y *Registro* y la carpeta *Certificados · Misión Energía Austral* en tu Drive.

## Paso 2 · Publicar el script como aplicación web

1. Tocá **Implementar › Nueva implementación**.
2. En el engranaje, elegí **Aplicación web**.
3. Configurá:
   - **Ejecutar como:** Yo
   - **Quién tiene acceso:** Cualquier persona
4. Tocá **Implementar** y copiá la **URL de la aplicación web** (termina en `/exec`).

> Si abrís esa URL en el navegador tiene que aparecer: *Misión Energía Austral: el servicio está activo ✔*

## Paso 3 · Conectar el juego con la planilla

Abrí `index.html` con un editor de texto, buscá esta línea (está cerca del principio del bloque de configuración):

```js
sheetsUrl: "",
```

y pegá tu URL entre las comillas:

```js
sheetsUrl: "https://script.google.com/macros/s/XXXXXXXX/exec",
```

En ese mismo bloque `CONFIG` podés cambiar el mínimo para avanzar (60), los intentos por nivel (3) y la cantidad de preguntas por nivel (10).

## Paso 4 · Subir a GitHub Pages

1. Subí `index.html` a tu repositorio (en la raíz o en una carpeta, por ejemplo `/mision-energia/`).
2. En el repositorio: **Settings › Pages › Deploy from a branch** (rama `main`, carpeta `/root`).
3. El enlace queda así: `https://TU-USUARIO.github.io/TU-REPO/` (o `/TU-REPO/mision-energia/`). Ese es el enlace para publicar en Classroom.

## Qué vas a ver en la planilla

**Hoja Progreso:** una fila por estudiante, que se actualiza sola:
nombre, estado (En curso / Finalizado), nivel actual, mejor puntaje de cada nivel, total sobre 400, porcentaje, intentos por nivel, % de dominio de cada tema, **contenidos a reforzar**, tiempo, código y **enlace al certificado PDF**.

**Hoja Registro:** cada envío con fecha y hora (sirve para ver cuándo trabajó cada estudiante).

## Reglas del juego

- Acierto al primer intento: 10 pts. Al segundo intento: 5 pts. En clasificar y ordenar, el segundo intento da puntaje parcial.
- Cada nivel vale 100 pts (10 preguntas elegidas al azar del banco, al menos 2 de cada tema). Total: 400 pts.
- Para desbloquear el siguiente nivel hacen falta 60 pts. Hay 3 intentos por nivel y se guarda el mejor.
- Si después del tercer intento no llega a 60, el nivel queda registrado y puede seguir, con los temas marcados para reforzar.
- Al terminar los 4 niveles: informe final, certificado para descargar (PDF) y copia del certificado en tu Drive.

## Datos útiles

- El progreso también queda guardado en el navegador: si el estudiante cierra la pestaña, sigue donde quedó (en la misma computadora y el mismo navegador).
- En computadoras compartidas, el pie de página tiene **“¿No sos …? Cambiar de estudiante”**.
- Si se corta internet, el juego sigue funcionando y reintenta el envío a la planilla cada minuto.
- Si modificás `Code.gs` más adelante, publicá una **nueva versión** desde *Implementar › Administrar implementaciones* para que la URL tome los cambios.
- Para editar lecturas o preguntas, todo está en el bloque `NIVELES` de `index.html` (lectura, interactivo, consejos y banco de preguntas de cada nivel).
