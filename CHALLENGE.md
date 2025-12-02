# Guía Completa del Challenge HTML

## Objetivo del Ejercicio

Aprender el flujo de trabajo colaborativo con Git y GitHub mediante la construcción de una página HTML donde **4 personas trabajan simultáneamente**, cada una aportando una parte específica del código.

---

## Flujo de Trabajo Completo

### Paso 1: Configuración Inicial (Todos los Miembros)

Cada miembro del equipo debe realizar estos pasos:

```bash
# 1. Clonar el repositorio
git clone https://github.com/illuminaki/challenge-html
cd challenge-html

# 2. Configurar tu identidad (si no lo has hecho antes)
git config user.name "Tu Nombre"
git config user.email "tu@email.com"

# 3. Verificar que estás en la rama main
git branch
```

---

### Paso 2: Crear tu Rama de Trabajo

Cada miembro crea su propia rama según su rol:

```bash
# Asegúrate de estar en main actualizado
git checkout main
git pull origin main

# Crea tu rama según tu rol:

# Miembro 1:
git checkout -b feature/estructura-base

# Miembro 2:
git checkout -b feature/header-nav

# Miembro 3:
git checkout -b feature/contenido

# Miembro 4:
git checkout -b feature/footer-estilos
```

**Nomenclatura de ramas:**
- `feature/` = nueva funcionalidad
- `fix/` = corrección de errores
- `docs/` = documentación

---

### Paso 3: Trabajar en tu Parte

#### Para Miembro 1: Estructura Base

**Archivo:** `index.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Proyecto colaborativo de aprendizaje Git">
    <title>Challenge HTML - Proyecto Colaborativo</title>
    <link rel="stylesheet" href="assets/styles.css">
</head>
<!-- El body será agregado por otros miembros -->
</html>
```

**Commits sugeridos:**
```bash
git add index.html
git commit -m "feat: agregar estructura HTML base con DOCTYPE y head"
git push origin feature/estructura-base
```

---

#### Para Miembro 2: Header y Navegación

**Agregar dentro de `index.html`:**

```html
<body>
    <header>
        <h1>Proyecto Colaborativo con Git</h1>
        <nav>
            <ul>
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#sobre">Sobre el Proyecto</a></li>
                <li><a href="#equipo">Equipo</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <!-- El contenido será agregado por Miembro 3 -->
    </main>

    <!-- El footer será agregado por Miembro 4 -->
</body>
```

**Commits sugeridos:**
```bash
git add index.html
git commit -m "feat: agregar body con header y navegación"
git push origin feature/header-nav
```

---

#### Para Miembro 3: Contenido Principal

**Agregar dentro de `<main>`:**

```html
<main>
    <section id="inicio">
        <h2>Bienvenidos al Challenge HTML</h2>
        <p>
            Este proyecto es un ejercicio práctico para aprender a trabajar 
            colaborativamente usando Git y GitHub. Cada miembro del equipo 
            contribuye con una parte específica del código.
        </p>
    </section>

    <section id="sobre">
        <h2>Sobre el Proyecto</h2>
        <p>
            El objetivo es construir una página web completa donde cada 
            integrante aporta diferentes elementos: estructura, header, 
            contenido y footer.
        </p>
        <img src="https://via.placeholder.com/600x300" alt="Trabajo en equipo">
    </section>

    <section id="equipo">
        <h2>Nuestro Equipo</h2>
        <p>
            Somos un equipo de 4 desarrolladores aprendiendo las mejores 
            prácticas de colaboración con control de versiones.
        </p>
    </section>
</main>
```

**Commits sugeridos:**
```bash
git add index.html
git commit -m "feat: agregar secciones de contenido principal con imágenes"
git push origin feature/contenido
```

---

#### Para Miembro 4: Footer y Estilos

**1. Agregar footer en `index.html`:**

```html
<footer id="contacto">
    <div class="footer-content">
        <h3>Contacto</h3>
        <p>Email: equipo@challenge-html.com</p>
        <p>GitHub: @challenge-html-team</p>
        <p>&copy; 2024 Challenge HTML. Todos los derechos reservados.</p>
    </div>
</footer>
```

**2. Crear archivo `assets/styles.css`:**

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: #333;
}

header {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    padding: 2rem;
    text-align: center;
}

header h1 {
    margin-bottom: 1rem;
}

nav ul {
    list-style: none;
    display: flex;
    justify-content: center;
    gap: 2rem;
}

nav a {
    color: white;
    text-decoration: none;
    font-weight: bold;
    transition: opacity 0.3s;
}

nav a:hover {
    opacity: 0.8;
}

main {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
}

section {
    margin-bottom: 3rem;
}

section h2 {
    color: #667eea;
    margin-bottom: 1rem;
}

section p {
    margin-bottom: 1rem;
}

img {
    max-width: 100%;
    height: auto;
    border-radius: 8px;
    margin: 1rem 0;
}

footer {
    background: #333;
    color: white;
    text-align: center;
    padding: 2rem;
    margin-top: 3rem;
}

.footer-content h3 {
    margin-bottom: 1rem;
}
```

**Commits sugeridos:**
```bash
git add index.html assets/styles.css
git commit -m "feat: agregar footer e implementar estilos CSS completos"
git push origin feature/footer-estilos
```

---

### Paso 4: Crear Pull Request

1. **Ve a GitHub** y navega al repositorio
2. Verás un banner que dice "Compare & pull request" - haz clic
3. **Completa la información del PR:**

```markdown
## Descripción
[Describe qué cambios realizaste]

## Tipo de cambio
- [ ] Nueva funcionalidad
- [ ] Corrección de bug
- [ ] Documentación

## Checklist
- [ ] El código funciona correctamente
- [ ] He probado los cambios localmente
- [ ] El código sigue las convenciones del proyecto
```

4. **Asigna revisores:** Selecciona al menos un compañero
5. **Crea el Pull Request**

---

### Paso 5: Revisar Pull Requests de Otros

Cuando revises el PR de un compañero:

1. **Lee el código cuidadosamente**
2. **Verifica que:**
   - El código es claro y legible
   - No hay errores de sintaxis
   - Sigue las convenciones del proyecto
3. **Deja comentarios constructivos:**
   - "Excelente implementación del header"
   - "Sugerencia: podrías agregar un alt más descriptivo a la imagen"
   - "¿Por qué elegiste este color para el fondo?"
4. **Aprueba o solicita cambios**

---

### Paso 6: Hacer Merge

Una vez que tu PR está aprobado:

1. **Actualiza tu rama con main** (por si hubo cambios):
   ```bash
   git checkout feature/tu-rama
   git pull origin main
   ```

2. **Resuelve conflictos si los hay** (ver `docs/RESOLUCION_CONFLICTOS.md`)

3. **Haz el merge en GitHub:**
   - Clic en "Merge pull request"
   - Confirma el merge
   - Opcionalmente, elimina la rama

---

### Paso 7: Actualizar tu Repositorio Local

Después de que se hagan merges:

```bash
# Volver a main
git checkout main

# Traer los últimos cambios
git pull origin main

# Ver el historial
git log --oneline --graph
```

---

## Manejo de Conflictos

### ¿Qué es un conflicto?

Un conflicto ocurre cuando dos personas modifican las mismas líneas de código. Git no sabe cuál versión mantener.

### Ejemplo de conflicto:

```html
<<<<<<< HEAD
<h1>Mi Título</h1>
=======
<h1>Título del Proyecto</h1>
>>>>>>> feature/otra-rama
```

### Cómo resolverlo:

1. **Abre el archivo con conflicto**
2. **Busca los marcadores** `<<<<<<<`, `=======`, `>>>>>>>`
3. **Decide qué código mantener:**
   - Mantén uno
   - Mantén ambos
   - Crea una versión nueva
4. **Elimina los marcadores**
5. **Guarda el archivo**
6. **Haz commit:**
   ```bash
   git add archivo-con-conflicto.html
   git commit -m "fix: resolver conflicto en título"
   git push
   ```

Para más detalles, consulta `docs/RESOLUCION_CONFLICTOS.md`

---

## Orden Recomendado de Trabajo

### Opción 1: Secuencial (Menos conflictos)

1. **Miembro 1** → Crea estructura base → Merge
2. **Miembro 2** → Agrega header → Merge
3. **Miembro 3** → Agrega contenido → Merge
4. **Miembro 4** → Agrega footer y estilos → Merge

### Opción 2: Paralelo (Más conflictos, más aprendizaje)

Todos trabajan al mismo tiempo. Esto generará conflictos que deberán resolver colaborativamente.

---

## Convenciones de Commits

Usa mensajes descriptivos siguiendo esta estructura:

```
<tipo>: <descripción breve>

[cuerpo opcional con más detalles]
```

**Tipos:**
- `feat:` nueva funcionalidad
- `fix:` corrección de errores
- `docs:` cambios en documentación
- `style:` formato, espacios (no afecta funcionalidad)
- `refactor:` reestructuración de código
- `test:` agregar o modificar tests

**Ejemplos:**
```bash
feat: agregar estructura HTML base con DOCTYPE y head
feat: implementar header con navegación responsive
feat: agregar sección de contenido con imágenes
feat: crear footer con información de contacto
fix: corregir ruta de imagen en sección sobre
style: mejorar indentación en archivo HTML
```

---

## Comandos Git Esenciales

```bash
# Ver estado actual
git status

# Ver ramas
git branch

# Cambiar de rama
git checkout nombre-rama

# Crear y cambiar a nueva rama
git checkout -b nueva-rama

# Ver diferencias
git diff

# Ver historial
git log --oneline --graph --all

# Actualizar desde remoto
git pull origin main

# Subir cambios
git push origin nombre-rama

# Ver ramas remotas
git branch -r

# Eliminar rama local
git branch -d nombre-rama
```

---

## Criterios de Éxito

El ejercicio se considera completado cuando:

- Los 4 miembros han creado sus ramas
- Cada miembro ha hecho al menos 1 commit
- Se han creado 4 Pull Requests
- Todos los PR han sido revisados y aprobados
- Se han resuelto al menos 1 conflicto
- Todos los cambios están merged en `main`
- La página HTML es funcional y se ve correctamente
- Todos los miembros entienden el flujo de trabajo

---

## Solución de Problemas Comunes

### "No puedo hacer push"
```bash
# Asegúrate de estar en tu rama
git branch

# Actualiza primero
git pull origin main

# Intenta push de nuevo
git push origin tu-rama
```

### "Mi rama está desactualizada"
```bash
git checkout tu-rama
git pull origin main
# Resuelve conflictos si los hay
git push origin tu-rama
```

### "Hice commit en la rama equivocada"
```bash
# Guarda el commit
git log  # copia el hash del commit

# Vuelve a la rama correcta
git checkout rama-correcta

# Aplica el commit
git cherry-pick <hash-del-commit>
```

### "Quiero deshacer mi último commit"
```bash
# Mantener cambios
git reset --soft HEAD~1

# Descartar cambios
git reset --hard HEAD~1
```

---

## Recursos Adicionales

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)
- [Oh My Git! (Juego)](https://ohmygit.org/)
- [Learn Git Branching](https://learngitbranching.js.org/)

---

## Consejos Finales

1. **Comunícate con tu equipo** - Usa issues, comentarios en PR, o chat
2. **Haz commits frecuentes** - Es mejor muchos commits pequeños que uno grande
3. **Lee el código de otros** - Aprende de tus compañeros
4. **No tengas miedo de los conflictos** - Son oportunidades de aprendizaje
5. **Pide ayuda** - Si te atascas, pregunta
6. **Documenta tus decisiones** - En commits y comentarios de PR

---

**¡Éxito en tu aprendizaje colaborativo!**
