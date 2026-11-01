# b0-p02 · Casa · Manual de soporte

- **Alumno:** Lautaro Martin Casquet
- **Módulo:** Sistemas Operativos en Red (SOR) · 2.º SMR · 2026-2027
- **Bloque:** B0 — Prerrequisitos
- **Fase / ejercicio:** Fase 0.8 · B0.P02 · Casa · Manual de soporte
- **Fecha de entrega:** 01/11/2026
- **Repositorio:** sor-manual-soporte-casa

---

## 🎯 Qué se pedía

Crear desde cero un manual de soporte técnico y llevar su historial con Git y GitHub. Había que trabajar en una bóveda de Obsidian nueva (Boveda_Manual_Casa) con Git solo en 01_Proyecto y las grabaciones fuera del repositorio. El manual se guardaba en tres versiones (manual inicial, corrección del procedimiento de conexión y ampliación con dos procedimientos nuevos y una imagen), se subía a un repositorio propio por SSH, se consultaba el primer commit para volver después a main y se cerraba la bitácora en un cuarto commit tras subir el vídeo.

## ⌨️ Comandos y pasos importantes

- `git --version`, `git config --global user.name`, `git config --global user.email` — comprueban que Git está instalado y que el autor de los commits soy yo.
- `ssh -T git@github.com` — comprueba que GitHub me reconoce por SSH; el saludo debe llevar mi usuario.
- `pwd` — confirma que estoy en Boveda_Manual_Casa/01_Proyecto antes de inicializar.
- `git init` y `git branch -M main` — crean el repositorio solo en 01_Proyecto y fijan la rama main.
- `git remote add origin git@github.com:Lauta-Martin-SMR/sor-manual-soporte-casa.git` y `git remote -v` — registran y comprueban el remoto SSH de mi cuenta.
- `git status` — muestra la rama y qué archivos son nuevos, modificados o están preparados.
- `git diff` — compara el disco con el índice y enseña las líneas cambiadas de archivos ya seguidos.
- `git add <archivo>` — prepara un archivo concreto para el siguiente commit.
- `git diff --cached` y `git diff --cached --stat` — revisan lo que está preparado antes de guardar.
- `git commit -m "mensaje"` — guarda una versión en el historial local.
- `git push -u origin main` (la primera vez) y `git push` — suben los commits a GitHub.
- `git check-ignore -v <archivo>` — demuestra qué regla de .gitignore excluye un archivo.
- `git log --oneline` — lista los commits con su código corto.
- `git switch --detach <código>` — consulta un commit antiguo sin tocar el historial.
- `git switch main` — vuelve a la rama principal con todos los commits.

## 🛠️ Qué he hecho

1. Creé la bóveda Boveda_Manual_Casa fuera de OneDrive y de las carpetas de SOR, con 00_Grabaciones y 01_Proyecto (con 00_Bitacora y manual/procedimientos).
2. Comprobé Git, mi identidad y la conexión SSH antes de empezar el proyecto.
3. Creé los archivos iniciales: .gitignore (con `*.mp4`, `*.mkv`, `*.mov`, `.DS_Store` y `Thumbs.db`), la bitácora, README.md y el procedimiento sin-conexion.md.
4. Inicialicé Git solo en 01_Proyecto, dejé la rama en main, creé el repositorio vacío sor-manual-soporte-casa en mi cuenta y lo conecté como origin por SSH.
5. Hice los commits revisando antes con status y diff, y subí cada uno con push.
6. Amplié el manual con los procedimientos de impresora y de sonido, los enlaces nuevos en el README y la imagen diagnostico.png. Añadí dos clips MP4 locales que quedaron ignorados por .gitignore y no se subieron.
7. Consulté el historial con `git log --oneline`, visité un commit antiguo con `git switch --detach` y volví a main con `git switch main`.
8. Grabé todo el proceso, lo subí a YouTube como No listado en su lista de reproducción y completé esta bitácora con los enlaces reales.

El resultado final está en GitHub, pero mi historial no quedó como pedía la práctica. Lo explico en el apartado siguiente.

## 🚩 Qué me ha fallado y cómo lo he resuelto

- **Error SSH:** `Permission denied (publickey)`. GitHub no tenía mi clave pública. La añadí a mi cuenta y volví a ejecutar `ssh -T git@github.com`, que ya me saludó con mi usuario.
- **Nombres de archivo mal puestos:** Obsidian creó algunos archivos con nombres planos y extensión duplicada (`.md.md`, `gitignore..md`) y los subí así en un commit. Lo corregí en el commit siguiente, pero el historial quedó desordenado. La próxima vez comprobaré los nombres reales y las extensiones antes de ejecutar `git add`.
- **Primer commit equivocado:** el primer commit se llama «Añadir impresora sonido e imagen manual» en lugar de guardar solo el manual inicial. Mezclé la versión inicial con la ampliación.
- **Corrección sin commit propio:** el procedimiento sin-conexion.md quedó igual en todos los commits, así que no existe en el historial la versión en la que el cable es la primera comprobación.
- **Mensaje del último commit:** lo llamé «Completar bitacora y actualizar README» en lugar de «Completar bitacora y enlace del video de casa».

Los avisos `LF will be replaced by CRLF` que salieron al hacer `diff` y `add` no son un error, solo informan de los finales de línea de Windows.

## 🤔 Respuestas a las preguntas

**1. ¿Por qué Git se inicializa solo en 01_Proyecto y la grabación queda fuera?** Porque 01_Proyecto contiene lo que se quiere versionar y entregar: el manual, el README y la bitácora. La bóveda también tiene la configuración de Obsidian (.obsidian) y las grabaciones en 00_Grabaciones, que son pesadas y no son parte del producto. Con Git solo en 01_Proyecto el historial y GitHub contienen únicamente el trabajo.

**2. ¿Qué muestran status y diff antes de preparar la corrección del procedimiento? Cita la instrucción anterior y la nueva.** `git status` debe mostrar solo manual/procedimientos/sin-conexion.md como modificado y sin preparar. `git diff` muestra con `-` las líneas retiradas y con `+` las añadidas. Antes la primera instrucción era «Abre el navegador y prueba la página interna» y la segunda «Comprueba visualmente que el cable de red está conectado». Después, la primera debe ser la del cable y la segunda la del navegador. En mi repositorio este cambio no quedó guardado en un commit propio, así que esta respuesta explica lo que debía mostrar el diff y no un resultado que haya conservado.

**3. ¿Por qué un archivo nuevo aparece en status pero no en el diff de README.md?** Un archivo nuevo aún no está bajo seguimiento de Git, así que `status` lo lista como sin seguimiento (`??`). `git diff` solo compara archivos que ya están en el índice, como README.md, que sí aparece cuando se modifica. El archivo nuevo entra en las comparaciones después de `git add`, ya con `diff --cached`.

**4. ¿Qué preparo con cada add y qué compruebo con diff --cached antes del commit?** Cada `git add <archivo>` coloca en el índice ese archivo concreto, sin crear commit ni subir nada. Con `git diff --cached` (y `--stat`) compruebo exactamente qué entrará en el commit: que estén solo los archivos previstos y que no haya archivos ajenos ni vídeos ignorados.

**5. ¿Qué demuestra check-ignore y qué comprobé además para saber que los clips existen?** `git check-ignore -v` enseña qué regla de .gitignore (`*.mp4`) y en qué línea excluye cada clip, y así demuestra que Git no los va a subir. Eso no prueba que existan, así que además comprobé en el gestor de archivos que seguían en el disco y los reproduje para ver que eran vídeos reales. Tampoco aparecen en `status` ni en GitHub.

**6. ¿Qué diferencias concretas observé en el manual del primer commit y qué recuperé al volver a main?** Al visitar el primer commit con `git switch --detach` HEAD queda separado y los archivos seguidos son los de esa versión. La práctica esperaba ver ahí el procedimiento con el navegador primero y sin los procedimientos nuevos ni la imagen. En mi caso, como sin-conexion.md es igual en todos los commits y mi primer commit ya incluía parte de la ampliación, esa diferencia no se aprecia en mi historial. Al hacer `git switch main` recuperé la rama con todos los commits, el árbol de trabajo limpio y los archivos más recientes.

**7. ¿Qué aporta un historial cuando dos técnicos necesitan conocer el procedimiento vigente?** Cada commit guarda una versión del manual con autor, fecha y mensaje. Los dos técnicos pueden saber cuál es la versión vigente (la última de main, la misma que hay en GitHub), qué decía una versión anterior y qué cambió entre una y otra con `git diff` o `git log`. Así no se tiene que preguntar a nadie ni mezclar copias del archivo. Para que sirva, los commits deben estar ordenados y con mensajes que digan qué cambió, y en mi historial eso falló en parte.

**8. ¿Por qué commit y push son acciones diferentes y qué miré en GitHub?** `git commit` guarda la versión solo en mi ordenador. `git push` envía esos commits al remoto origin en GitHub. Un `status` limpio no demuestra que el push haya llegado, por eso abro el repositorio en GitHub y miro que estén los commits, que los archivos tengan el contenido esperado, que se vean los enlaces y la imagen, y que los vídeos ignorados no aparezcan.

**9. ¿Qué pasos repetiría para corregir otra instrucción y cuáles se hicieron una sola vez?** Para corregir otra instrucción repetiría este ciclo: editar y probar el archivo en Obsidian, `git status`, `git diff -- <archivo>`, `git add <archivo>`, `git diff --cached`, `git commit -m "mensaje exacto"`, `git push`, `git status` y comprobar el cambio en GitHub. Hice una sola vez la comprobación de Git, identidad y SSH, la creación de la bóveda y las carpetas, `git init`, `git branch -M main`, la creación del repositorio vacío en GitHub, `git remote add origin` y el primer `git push -u origin main`.

## 🔗 Enlaces

- **Repositorio:** [https://github.com/Lauta-Martin-SMR/sor-manual-soporte-casa](https://github.com/Lauta-Martin-SMR/sor-manual-soporte-casa)
- **Bitácora en GitHub:** [https://github.com/Lauta-Martin-SMR/sor-manual-soporte-casa/blob/main/00_Bitacora/b0-p02-casa-manual-soporte.md](https://github.com/Lauta-Martin-SMR/sor-manual-soporte-casa/blob/main/00_Bitacora/b0-p02-casa-manual-soporte.md)
- **Vídeo:** [https://youtu.be/L5Ch_RR3KyE](https://youtu.be/L5Ch_RR3KyE)
- **Playlist:** [https://www.youtube.com/playlist?list=PLIWj32AjmaaY](https://www.youtube.com/playlist?list=PLIWj32AjmaaY)

## 💭 Dudas / a repasar

- Cómo corregir un mensaje de commit equivocado que ya está subido sin forzar el push ni borrar el historial.
- Cómo evitar que Obsidian cree archivos con extensión duplicada o sin extensión, y cómo ver las extensiones reales antes de hacer `git add`.
- Repasar el orden correcto de los tres commits del producto y que la corrección del procedimiento vaya en un commit propio.
- Repasar la diferencia entre `git diff` y `git diff --cached` con un archivo nuevo, uno modificado y uno ignorado.