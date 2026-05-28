# 1. `git status`

Muestra el estado actual del repositorio.

Te dice:

* qué archivos cambiaron,
* cuáles están listos para guardar,
* cuáles no están siendo seguidos por Git.

```bash
git status
```

👉 Es probablemente el comando que más se usa.

---

# 2. `git add`

Agrega archivos al área de preparación (“staging”).

```bash
git add archivo.txt
```

Agregar todos los cambios:

```bash
git add .
```

👉 Sirve para decirle a Git:
“estos cambios quiero guardarlos en el próximo commit”.

---

# 3. `git commit`

Guarda una versión de los cambios.

```bash
git commit -m "Agrega login de usuarios"
```

👉 Un commit es como una “foto” del proyecto.

---

# 4. `git push`

Sube tus cambios al repositorio remoto (por ejemplo GitHub).

```bash
git push
```

O especificando rama:

```bash
git push origin main
```

👉 Envía tus commits a internet/equipo.

---

# 5. `git pull`

Descarga cambios del repositorio remoto y los mezcla con tu rama actual.

```bash
git pull
```

👉 Actualiza tu proyecto local.

---

# 6. `git clone`

Copia un repositorio remoto a tu computadora.

```bash
git clone https://github.com/usuario/proyecto.git
```

👉 Se usa al empezar a trabajar en un proyecto existente.

---

# 7. `git branch`

Muestra o crea ramas.

Ver ramas:

```bash
git branch
```

Crear rama:

```bash
git branch nueva-funcion
```

👉 Las ramas permiten trabajar sin romper el proyecto principal.

---

# 8. `git checkout`

Cambiar de rama.

```bash
git checkout develop
```

Crear y cambiar:

```bash
git checkout -b nueva-rama
```

👉 Muy usado antes de `git switch`.

---

# 9. `git switch`

Forma moderna de cambiar ramas.

```bash
git switch develop
```

Crear y cambiar:

```bash
git switch -c feature-login
```

👉 Más claro y recomendado actualmente.

---

# 10. `git merge`

Fusiona ramas.

```bash
git merge develop
```

👉 Une cambios de otra rama.

---

# 11. `git log`

Muestra el historial de commits.

```bash
git log
```

Versión corta:

```bash
git log --oneline
```

👉 Sirve para revisar historial.

---

# 12. `git diff`

Muestra diferencias entre cambios.

```bash
git diff
```

👉 Te deja ver exactamente qué modificaste.

---

# 13. `git fetch`

Descarga cambios remotos SIN mezclarlos.

```bash
git fetch
```

👉 Más seguro que `pull` en algunos flujos de trabajo.

---

# 14. `git reset`

Deshace cambios o commits.

Ejemplo simple:

```bash
git reset archivo.txt
```

👉 Muy potente y peligroso si no se entiende bien.



## 14.1. Deshacer un Commit en Git

En Git, puedes deshacer un commit dependiendo de si deseas conservar los cambios o descartarlos por completo. A continuación, se explican las opciones más comunes para lograrlo.

1. Deshacer el Último Commit Conservando los Cambios

    Si deseas mantener los cambios en el área de preparación (staging area) para modificarlos o hacer un nuevo commit:
    ```bash
    git reset --soft HEAD~1
    ```

    Este comando mueve el puntero al commit anterior, pero conserva los cambios en el área de preparación.

2. Deshacer el Último Commit y Mover los Cambios al Área de Trabajo

    Si prefieres quitar los cambios del área de preparación pero mantenerlos en tu directorio de trabajo:

    ```bash
    git reset --mixed HEAD~1
    ```

    Los archivos seguirán modificados, pero no estarán listos para un nuevo commit.

3. Deshacer el Último Commit y Eliminar los Cambios

    Si quieres descartar completamente los cambios realizados en el último commit:

    ```bash
    git reset --hard HEAD~1
    ```

    Precaución: Este comando elimina los cambios tanto del área de preparación como del directorio de trabajo. Úsalo con cuidado, ya que puede provocar pérdida de datos.

4. Deshacer Múltiples Commits

    Para deshacer varios commits hacia atrás desde HEAD, especifica la cantidad deseada:
    ```bash
    git reset --soft HEAD~N
    ```

    Reemplaza N con el número de commits que deseas deshacer.

    Consejos Finales

    Si ya hiciste un push al repositorio remoto, utiliza git revert en lugar de git reset para evitar conflictos con otros colaboradores.

    Siempre verifica tu historial con git log antes de ejecutar comandos destructivos como --hard.

5. Aplicar cambios al repositorio remoto después de un reset

    Si necesitas actualizar el repositorio remoto después de un reset, puedes usar:
    ```bash
    git push --force origin nombre-de-la-rama
    ```

    Ten cuidado al usar --force, ya que puede sobrescribir el historial compartido con otros colaboradores. Es recomendable comunicar cualquier cambio importante a tu equipo antes de forzar un push.

---

# 15. `git stash`

Guarda cambios temporales sin hacer commit.

```bash
git stash
```
- `show -p` para ver qué guardaste.
- `list` para ver todos los stashes guardados.

Recuperar y borrar stash:

```bash
git stash pop
```

Recuperar SIN borrar stash:

```bash
git stash apply
```

👉 Útil cuando necesitás cambiar de rama rápido.

## 15.1. NO guarda archivos nuevos por defecto
```bash
git stash -u
```
---

```bash
git stash --include-untracked
```

Eso incluye:
- archivos nuevos,
- carpetas nuevas,
- archivos no trackeados.

---

# 16. `git rebase`

Reorganiza commits o actualiza una rama.

```bash
git rebase main
```

👉 Muy usado en equipos avanzados.

---

# 17. `git rm`

Eliminar archivos usando Git.

```bash
git rm archivo.txt
```

---

# 18. `git mv`

Mover o renombrar archivos.

```bash
git mv viejo.txt nuevo.txt
```

---

# 19. `git remote`

Gestiona repositorios remotos.

Ver remotos:

```bash
git remote -v
```

Agregar remoto:

```bash
git remote add origin URL
```

---

# 20. `git init`

Inicializa un repositorio Git nuevo.

```bash
git init
```

👉 Convierte una carpeta común en un proyecto Git.

---

# Flujo típico de trabajo

Normalmente el ciclo diario es:

```bash
git pull
git status
git add .
git commit -m "mensaje"
git push
```

---

# Los 10 comandos que realmente usa la mayoría

Según experiencia común de desarrolladores y discusiones de comunidades técnicas, los más usados suelen ser:

1. `git status`
2. `git add`
3. `git commit`
4. `git push`
5. `git pull`
6. `git branch`
7. `git checkout` / `git switch`
8. `git merge`
9. `git log`
10. `git clone`

([Hostinger][1])

---

# Consejo importante

No hace falta memorizar los más de 150 comandos de Git.

Con dominar:

* `status`
* `add`
* `commit`
* `push`
* `pull`
* `branch`
* `checkout/switch`
* `merge`

ya podés trabajar profesionalmente en la mayoría de proyectos. ([Reddit][2])

---

## Recursos útiles

* [Documentación oficial de Git](https://git-scm.com/doc?utm_source=chatgpt.com)
* [GitHub Docs](https://docs.github.com/es?utm_source=chatgpt.com)
* [Tutorial de Atlassian Git](https://www.atlassian.com/es/git/tutorials?utm_source=chatgpt.com)
