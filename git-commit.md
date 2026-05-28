# 1. Buenas prácticas para hacer commits claros, entendibles y estándares

Resumen consolidado de **buenas prácticas para hacer commits claros, entendibles y estándares**, basado tanto en la guía de Commitizen (“Writing commits”) como en la especificación Conventional Commits y otras fuentes. 

---

## 1.1. ✅ Formato recomendado

Según Conventional Commits la estructura general es:

```
<type>[optional scope]: <short description>

[optional body]

[optional footer(s)]
```

([conventionalcommits.org][1])
Donde:

* `type` es obligatorio (por ejemplo: `feat`, `fix`, `docs`, etc.). ([Baeldung on Kotlin][2])
* `scope` es opcional, puesto entre paréntesis, para indicar el área afectada (por ejemplo: `(auth)`, `(api)`) ([Medium][3])
* `short description` debe ser breve, en forma imperativa (“Add”, “Fix”, etc.) ([commitizen-tools.github.io][4])
* `body` (opcional): explica *por qué* del cambio, contexto adicional. ([blog.shakiltech.com][5])
* `footer(s)` (opcional): referencias a issues, breaking changes, etc. Por ejemplo `BREAKING CHANGE: …` ([vishnuprasadkuntar.me][6])

También la guía de Commitizen refuerza estas ideas: “Keep the message short”, “Talk imperative”, “Your future self & your colleagues” deben entenderlo. ([commitizen-tools.github.io][4])

---

## 1.2. 🧩 Tipos comunes de commits

Algunos tipos muy usados y recomendados:

* `feat`: introduce una **nueva funcionalidad**. ([conventionalcommits.org][1])
* `fix`: corrige un bug. ([codingeasypeasy.com][7])
* `docs`: cambios en la documentación. ([vishnuprasadkuntar.me][6])
* `style`: formato, estilo de código, sin cambio de lógica. ([vishnuprasadkuntar.me][6])
* `refactor`: cambio de código que no agrega funcionalidad ni corrige un bug, pero mejora estructura. ([Medium][3])
* `perf`: mejoras de rendimiento. ([vishnuprasadkuntar.me][6])
* `test`: añadir o modificar tests. ([vishnuprasadkuntar.me][6])
* `chore`: tareas de mantenimiento (dependencias, build, etc.). ([codingeasypeasy.com][7])

---

## 1.3. 📏 Buenas prácticas de redacción

Aquí van reglas muy útiles para que los commits sean claros y útiles:

* Usa **tiempo imperativo** (“Add feature”, “Fix bug”, no “Added” o “Fixed”). ([GitKraken][8])
* Limita la línea de título (el header) a ~50 caracteres para máxima legibilidad. ([Developer handbook][9])
* Deja una línea en blanco entre el título y el cuerpo. ([Developer handbook][9])
* No termines el título con un punto (“.”). ([Developer handbook][9])
* Si escribes cuerpo, envuelve líneas a ~72 caracteres para que se vea bien en terminales. ([Developer handbook][9])
* Mantén los commits **atómicos**: que representen un solo cambio lógico, no múltiples cosas mezcladas. ([codingeasypeasy.com][7])
* En el cuerpo o footer explica *por qué* se hizo el cambio, no solo *qué* se hizo. ([algocademy.com][10])
* Si el cambio rompe compatibilidad, marca con `BREAKING CHANGE:` o añade `!` después del tipo (ej: `feat!: …`). ([vishnuprasadkuntar.me][6])
* Referencia issues o tickets si aplica (ej: “Fixes #123”). ([blog.shakiltech.com][5])

---

## 1.4. 🎯 Qué evitar

* Mensajes genéricos tipo “update code”, “fixed stuff”, “changes”. Evita vaguedades. ([Medium][11])
* Mezclar múltiples cambios no relacionados en un solo commit.
* Olvidar marcar cambios que rompen compatibilidad.
* Escribir título muy largo o cuerpo que sea demasiado prolijo para lo que el cambio merece.
* No usar estándar alguno (aunque tener uno ya mejora mucho).

---

## 1.5. 📌 Lista de verificación rápida antes de hacer commit

Puedes usar este checklist para tus commits:

* [ ] ¿El header sigue el formato `<type>(scope): description`?
* [ ] ¿El tipo representa bien la naturaleza del cambio? (`feat`, `fix`, etc.)
* [ ] ¿El título está en imperativo, sin punto al final, < ~50 caracteres?
* [ ] ¿Si hay cuerpo, está separado por línea en blanco del header, envuelto aprox. a 72 caracteres?
* [ ] ¿El commit es atómico (un solo objetivo lógico)?
* [ ] ¿Se explica *por qué* y/o *impacto* del cambio?
* [ ] ¿Hay referencia a issue, o marca de breaking change si aplica?
* [ ] ¿No se mezclan cambios que deberían ser varios commits?


[1]: https://www.conventionalcommits.org/en/v1.0.0-beta/?utm_source=chatgpt.com "Conventional Commits"
[2]: https://www.baeldung.com/ops/git-commit-messages?utm_source=chatgpt.com "Best Practices for Git Commit Message | Baeldung on Ops"
[3]: https://medium.com/%40danendraclever24/a-guide-to-conventional-git-commits-best-practices-for-clear-and-structured-version-control-d3a9e77342bb?utm_source=chatgpt.com "A Guide to Conventional Git Commits: Best Practices for Clear and Structured Version Control | by Danendra Clevero Ananda | Medium"
[4]: https://commitizen-tools.github.io/commitizen/tutorials/writing_commits/ "Writing commits - Commitizen"
[5]: https://blog.shakiltech.com/conventional-commits/?utm_source=chatgpt.com "Conventional Commits Simplified: The Ultimate Guide To Better Versioning And Collaboration - Shakil's Blog"
[6]: https://vishnuprasadkuntar.me/posts/git-commit-best-practices?utm_source=chatgpt.com "Vishnu Prasad K | Full Stack Developer"
[7]: https://www.codingeasypeasy.com/blog/mastering-git-commit-best-practices-tips-and-tricks-for-effective-version-control?utm_source=chatgpt.com "Mastering Git Commit: Best Practices, Tips, and Tricks for Effective Version Control | CodingEasyPeasy"
[8]: https://www.gitkraken.com/learn/git/best-practices/git-commit-message?utm_source=chatgpt.com "How to Write a Good Git Commit Message | Git Best Practices"
[9]: https://handbook.nethserver.org/commit_messages/?utm_source=chatgpt.com "Commit Messages Style Guide | Developer handbook"
[10]: https://algocademy.com/blog/how-to-write-good-commit-messages-in-git-a-comprehensive-guide/?utm_source=chatgpt.com "How to Write Good Commit Messages in Git: A Comprehensive Guide – AlgoCademy Blog"
[11]: https://medium.com/%40sharmaakhil.work/git-commit-messages-101-from-messy-to-meaningful-with-conventional-commits-5424781fbc33?utm_source=chatgpt.com "Git Commit Messages 101: From Messy to Meaningful with Conventional Commits | by sharma-akhil | Sep, 2025 | Medium"

---

## 1.6. 📝 Plantilla para commits (snippet)

```text
<type>(<scope>): <short description>

[Optional body: explain *why* the change was made, context, or implementation details.
Wrap lines at ~72 characters for readability.]

[Optional footer(s): issues, breaking changes, etc.]
```

**Explicación de cada parte:**

* `type`: tipo de commit (feat, fix, docs, style, refactor, test, chore, perf).
* `scope`: área afectada del código (ej: auth, api, ui, db). Opcional.
* `short description`: título breve, en **imperativo**, <50 caracteres, sin punto final.
* `body`: explica el *por qué*, no solo el *qué*. Opcional.
* `footer`: referencias a issues, tickets o breaking changes. Opcional.

---

## 1.7. ✅ Ejemplos CORRECTOS

1. **Funcionalidad nueva**

```text
feat(auth): add JWT authentication support

Add JWT-based authentication to the login system. This allows secure
user sessions and reduces reliance on server-side sessions.

Closes #42
```

2. **Corrección de bug**

```text
fix(api): handle null pointer in user endpoint

Previously, GET /users would crash when no users were found.
Added null checks and appropriate 404 response.
```

3. **Documentación**

```text
docs(readme): update installation instructions

Added steps for setting up the project on Windows and MacOS.
```

4. **Refactor sin cambiar funcionalidad**

```text
refactor(database): optimize query builder

Rewrote query builder to reduce redundant SQL joins.
No change in output or functionality.
```

5. **Breaking change**

```text
feat(auth)!: switch password hashing to bcrypt

Old SHA1 hashes are no longer supported. Users must reset their
passwords to log in.

BREAKING CHANGE: Password hashing algorithm changed.
```

---

## 1.8. ❌ Ejemplos INCORRECTOS

1. Mensaje vago

```text
update code
```

2. Mensaje demasiado largo o sin estructura

```text
I fixed a bunch of things in the authentication system and also changed
some code in the user service to make it work with the new database.
```

3. Mal tiempo verbal

```text
Added login feature to auth system.
```

4. Mezcla de múltiples cambios

```text
fix bug in api and add JWT authentication
```

*(Está mezclando bugfix y feature; deberían ser dos commits distintos.)*

5. Breaking change no indicado

```text
feat(auth): switch password hashing to bcrypt
```

*(Falta `!` o `BREAKING CHANGE:` en el footer.)*

---

💡 **Tip rápido:**
Siempre pregúntate: “Si alguien viera solo este commit en el futuro, ¿entiende qué se cambió, por qué y si rompe algo?” Si la respuesta es no, mejora tu mensaje.

---

## 1.9. **Beneficios de esta convención**:

* **Claridad**: Cada commit tiene un tipo claramente definido, lo que hace que el historial de commits sea fácil de leer y entender rápidamente.
* **Automatización**: Gracias a su estructura, es muy fácil generar changelogs y gestionar versiones.
* **Colaboración**: Cuando trabajas en equipo, esta estructura ayuda a que todos comprendan de inmediato qué hizo cada cambio.
* **Escalabilidad**: Si el proyecto crece, no tendrás problemas para organizar y gestionar los commits.