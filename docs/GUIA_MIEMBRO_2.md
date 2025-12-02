# Guía para Miembro 2: Header y Navegación

## Tu Misión

Eres responsable de crear el **body, header y sistema de navegación** de la página. Construirás sobre la estructura base que creó el Miembro 1.

---

## Tareas Asignadas

### 1. Agregar la etiqueta `<body>`
### 2. Crear el header con título principal
### 3. Implementar barra de navegación
### 4. Preparar la estructura para el contenido

---

## Paso a Paso

### Paso 1: Configurar tu entorno

```bash
# Clonar el repositorio
git clone <URL_DEL_REPOSITORIO>
cd challenge-html

# Configurar tu identidad
git config user.name "Tu Nombre"
git config user.email "tu@email.com"
```

### Paso 2: Esperar a que Miembro 1 termine

⚠️ **IMPORTANTE**: Antes de empezar, asegúrate de que el Miembro 1 haya hecho merge de su PR.

```bash
# Actualizar tu repositorio local
git checkout main
git pull origin main

# Verificar que index.html existe
ls -la index.html
```

### Paso 3: Crear tu rama de trabajo

```bash
# Crear tu rama desde main actualizado
git checkout -b feature/header-nav
```

### Paso 4: Editar el archivo HTML

Abre `index.html` y agrega el body con header y navegación:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Proyecto colaborativo de aprendizaje Git">
    <meta name="author" content="Equipo Challenge HTML">
    <meta name="keywords" content="HTML, CSS, Git, GitHub, Colaboración">
    <title>Challenge HTML - Proyecto Colaborativo</title>
    <link rel="stylesheet" href="assets/styles.css">
</head>
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
</html>
```

### Paso 5: Guardar y hacer commit

```bash
# Ver los cambios
git diff

# Agregar el archivo
git add index.html

# Hacer commit
git commit -m "feat: agregar body con header y navegación"

# Ver el commit
git log --oneline -3
```

### Paso 6: Subir tu rama

```bash
# Subir tu rama al repositorio remoto
git push origin feature/header-nav
```

### Paso 7: Crear Pull Request

1. Ve a GitHub
2. Clic en "Compare & pull request"
3. Completa la información:

```markdown
## Descripción
Implementación del body, header con título principal y sistema de navegación.

## Cambios realizados
- Agregada etiqueta `<body>`
- Creado `<header>` con título principal
- Implementada barra de navegación con 4 enlaces
- Agregada estructura `<main>` para contenido
- Dejados comentarios para Miembros 3 y 4

## Tipo de cambio
- [x] Nueva funcionalidad
- [ ] Corrección de bug
- [ ] Documentación

## Checklist
- [x] El código funciona correctamente
- [x] He probado los cambios localmente
- [x] El código sigue las convenciones del proyecto
- [x] La navegación usa enlaces de ancla (#)
- [x] He dejado comentarios para guiar a otros miembros

## Dependencias
- Depende de: PR de Miembro 1 (estructura base)
```

4. Asigna revisores
5. Crea el Pull Request

---

## Explicación del Código

### `<body>`
- Contenedor principal de todo el contenido visible
- Todo lo que el usuario ve va dentro del body

### `<header>`
- Sección de encabezado de la página
- Generalmente contiene logo, título y navegación
- Elemento semántico HTML5

### `<h1>`
- Título principal de la página
- Solo debe haber uno por página
- Importante para SEO y accesibilidad

### `<nav>`
- Elemento semántico para navegación
- Indica a los navegadores y lectores de pantalla que es un menú

### `<ul>` y `<li>`
- Lista no ordenada para los elementos del menú
- Estructura semántica correcta para navegación

### Enlaces de ancla (`#inicio`, `#sobre`, etc.)
- Permiten navegación dentro de la misma página
- Deben coincidir con los `id` de las secciones que creará Miembro 3

### `<main>`
- Contenedor del contenido principal
- Solo debe haber uno por página
- Elemento semántico HTML5

---

## Checklist de Completación

Antes de crear tu Pull Request, verifica:

- [ ] El body está correctamente abierto después del `</head>`
- [ ] El header contiene un h1 descriptivo
- [ ] La navegación tiene 4 enlaces
- [ ] Los enlaces usan formato de ancla (#)
- [ ] La etiqueta `<main>` está presente
- [ ] Dejaste comentarios para Miembros 3 y 4
- [ ] Todas las etiquetas están correctamente cerradas
- [ ] La indentación es consistente
- [ ] Hiciste commit con mensaje descriptivo
- [ ] Subiste tu rama al repositorio remoto

---

## Coordinación con el Equipo

### Dependes de:

**Miembro 1** debe terminar primero
- Espera a que su PR sea merged
- Actualiza tu main antes de crear tu rama

### Tu trabajo es base para:

**Miembro 3** necesita la estructura `<main>` que creaste
- Los enlaces de navegación deben coincidir con sus secciones
- Comunícale los IDs que usaste: `#inicio`, `#sobre`, `#equipo`, `#contacto`

**Miembro 4** necesita saber dónde agregar el footer
- Dejaste un comentario indicando dónde va

### Consejos:
- Comunica al equipo cuando tu PR esté listo
- Coordina con Miembro 3 sobre los IDs de las secciones
- Responde rápido a comentarios de revisión

---

## Problemas Comunes

### "El archivo index.html no existe"
```bash
# Asegúrate de que Miembro 1 haya hecho merge
git checkout main
git pull origin main
ls -la index.html

# Si no existe, espera a que Miembro 1 termine
```

### "Hay conflictos al hacer merge"
```bash
# Actualiza tu rama con main
git checkout feature/header-nav
git pull origin main

# Si hay conflictos, ábrelos y resuélvelos
# Luego:
git add index.html
git commit -m "fix: resolver conflictos con main"
git push origin feature/header-nav
```

### "Olvidé actualizar main antes de crear mi rama"
```bash
# Actualiza tu rama con los últimos cambios
git checkout feature/header-nav
git pull origin main

# Resuelve conflictos si los hay
```

### "Quiero cambiar los enlaces de navegación"
```bash
# Haz los cambios en index.html
# Luego:
git add index.html
git commit -m "feat: actualizar enlaces de navegación"
git push origin feature/header-nav
```

---

## Recursos Adicionales

- [MDN: Elemento header](https://developer.mozilla.org/es/docs/Web/HTML/Element/header)
- [MDN: Elemento nav](https://developer.mozilla.org/es/docs/Web/HTML/Element/nav)
- [MDN: Enlaces de ancla](https://developer.mozilla.org/es/docs/Web/HTML/Element/a#linking_to_an_element_on_the_same_page)
- [HTML5 Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp)

---

## Comandos Git que Usarás

```bash
# Actualizar main
git checkout main
git pull origin main

# Crear tu rama
git checkout -b feature/header-nav

# Ver cambios
git diff

# Ver estado
git status

# Agregar y commit
git add index.html
git commit -m "feat: agregar body con header y navegación"

# Subir cambios
git push origin feature/header-nav

# Actualizar tu rama con main
git checkout feature/header-nav
git pull origin main
```

---

## Tips Profesionales

1. **Navegación accesible**: Usa elementos semánticos (`<nav>`, `<header>`)
2. **Enlaces descriptivos**: El texto del enlace debe ser claro
3. **Consistencia**: Mantén el estilo de indentación del Miembro 1
4. **Comentarios útiles**: Guía a los siguientes miembros
5. **Prueba local**: Abre el HTML en el navegador antes de hacer commit

---

## Cómo Probar tu Código

```bash
# Abre el archivo en tu navegador
# En Linux:
xdg-open index.html

# O simplemente abre el archivo con tu navegador favorito
```

Verifica que:
- El título aparece correctamente
- Los 4 enlaces de navegación están visibles
- No hay errores en la consola del navegador

---

## Criterios de Éxito

Tu tarea está completa cuando:

- El body está correctamente implementado
- El header tiene un título atractivo
- La navegación tiene 4 enlaces funcionales
- La estructura main está preparada
- Los comentarios guían a otros miembros
- Tu commit tiene un mensaje descriptivo
- Tu rama está en GitHub
- Has creado el Pull Request
- Tu PR ha sido revisado y aprobado
- Has hecho merge a main
- Has notificado al equipo

---

**¡Tu header será lo primero que vean los usuarios! Hazlo atractivo.**
