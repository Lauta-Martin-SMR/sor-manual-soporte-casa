# 📘 B0.P02 · Casa · Manual de soporte

**Alumno:** Lautaro Martin Casquet
**Módulo:** Sistemas Operativos en Red (SOR)  
**Curso:** 2.º SMR · 2026-2027  
**Repositorio:** `sor-manual-soporte-casa`  
**Vídeo:** B0.P02 · Casa · Manual de soporte  
**Estado:** Práctica realizada; bitácora pendiente de revisión final.

## 📝 1. Qué se pedía

El objetivo de esta práctica era crear un manual de soporte técnico y utilizar Git y GitHub para controlar sus versiones.

El trabajo debía realizarse en una bóveda de Obsidian independiente, guardando el repositorio Git únicamente dentro de `01_Proyecto`, sin incluir las grabaciones de vídeo en el repositorio.

También se pedía crear un repositorio remoto en GitHub, conectarlo mediante SSH, realizar cambios en el manual, registrar las versiones con commits y comprobar que los cambios se habían subido correctamente.

Por último, había que consultar el historial, comprobar el estado del repositorio, grabar el procedimiento y completar esta bitácora con las evidencias y los enlaces correspondientes.

## 💻 2. Comandos y pasos importantes

Durante la práctica se trabajó con los siguientes comandos de Git:

**Comprobar la instalación y la configuración**

```
git --version
git config --global user.name
git config --global user.email
ssh -T git@github.com
```

**Inicializar y comprobar el repositorio**

```
git init
git branch -M main
git status
```

**Consultar los cambios**

```
git status --short --untracked-files=all
git diff
git diff --cached
```

**Preparar y guardar cambios**

```
git add .
git commit -m "Mensaje del commit"
```

**Conectar y sincronizar con GitHub**

```
git remote -v
git push -u origin main
git push
```

**Consultar el historial**

```
git log
git log --oneline
git switch main
```

Estos comandos se incluyen como referencia de las operaciones realizadas durante la práctica. No todos tienen por qué haberse ejecutado exactamente en este orden.

## 🛠️ 3. Qué he hecho

1. He preparado una bóveda independiente para la práctica en mi ordenador.
2. He organizado los archivos del proyecto dentro de `01_Proyecto`, manteniendo las grabaciones fuera del repositorio.
3. He comprobado la instalación de Git y la configuración de mi identidad.
4. He configurado y comprobado la conexión SSH con GitHub.
5. He creado el repositorio remoto `sor-manual-soporte-casa`.
6. He inicializado el repositorio local y lo he conectado con GitHub.
7. He creado y modificado el manual de soporte técnico.
8. He preparado los cambios y los he guardado mediante commits.
9. He subido los cambios a GitHub mediante `git push`.
10. He consultado el historial y comprobado la conexión entre el repositorio local y el remoto.

## ⚠️ 4. Qué me ha fallado y cómo lo he resuelto

- **Error SSH:** apareció `Permission denied (publickey)`. Añadí la clave pública a GitHub y comprobé la conexión con `ssh -T git@github.com`.
    
- **Organización del proyecto:** separé la carpeta del proyecto de las grabaciones para no incluir los vídeos en Git.
    
- **Comprobación de cambios:** utilicé `git status` y `git diff` para revisar los archivos antes de guardarlos.
    

## 📚 5. Respuestas a las preguntas

**1. ¿Por qué Git solo está en** `**01_Proyecto**`**?**  
Porque es la carpeta que contiene los archivos que se deben versionar, sin incluir las grabaciones.

**2. ¿Para qué sirven** `**status**` **y** `**diff**`**?**  
`status` muestra el estado de los archivos y `diff` permite consultar sus cambios.

**3. ¿Por qué un archivo nuevo no aparece en** `**diff**`**?**  
Porque todavía no está bajo seguimiento de Git.

**4. ¿Para qué sirven** `**add**` **y** `**diff --cached**`**?**  
`add` prepara los cambios y `diff --cached` permite revisarlos antes del commit.

**5. ¿Para qué sirve** `**git check-ignore**`**?**  
Para comprobar si un archivo está siendo ignorado por Git.

**6. ¿Qué aporta el historial y volver a** `**main**`**?**  
Permite consultar versiones anteriores y regresar a la rama principal.

**7. ¿Qué diferencia hay entre** `**commit**` **y** `**push**`**?**  
`commit` guarda los cambios localmente y `push` los sube a GitHub.

## 🔗 6. Enlaces y evidencias

- **Repositorio GitHub:** https://github.com/Lauta-Martin-SMR/sor-manual-soporte-casa
- **Vídeo de la práctica:** https://youtu.be/L5Ch_RR3KyE
- **Lista de reproducción:** https://www.youtube.com/playlist?list=PLIWj32AjmaaY
- **Bitácora en GitHub:** https://github.com/Lauta-Martin-SMR/sor-manual-soporte-casa/tree/main/00_Bitacora