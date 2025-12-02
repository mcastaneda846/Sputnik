# Guía para Miembro 1: Estructura Base HTML

## Tu Misión

Eres responsable de crear la **estructura base del documento HTML**. Esta es la fundación sobre la cual tus compañeros construirán el resto del proyecto.

---

## Tareas Asignadas

### 1. Crear la estructura HTML básica
- Declaración `<!DOCTYPE html>`
- Etiqueta `<html>` con atributo de idioma
- Sección `<head>` completa
- Meta tags esenciales
- Título del documento
- Enlace al archivo CSS

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

### Paso 2: Crear tu rama de trabajo

```bash
# Asegúrate de estar en main
git checkout main
git pull origin main

# Crear tu rama
git checkout -b feature/estructura-base
```

### Paso 3: Crear el archivo HTML

Crea el archivo `index.html` en la raíz del proyecto con el siguiente contenido:

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
<!-- El body será agregado por otros miembros -->
</html>
```

### Paso 4: Guardar y hacer commit

```bash
# Ver el estado
git status

# Agregar el archivo
git add index.html

# Hacer commit con mensaje descriptivo
git commit -m "feat: agregar estructura HTML base con DOCTYPE y head"

# Ver el commit
git log --oneline
```

### Paso 5: Subir tu rama

```bash
# Subir tu rama al repositorio remoto
git push origin feature/estructura-base
```

### Paso 6: Crear Pull Request

1. Ve a GitHub
2. Verás un banner "Compare & pull request" - haz clic
3. Completa la información:

```markdown
## Descripción
Estructura HTML base con DOCTYPE, etiquetas html y head completas.

## Cambios realizados
- Declaración DOCTYPE HTML5
- Etiqueta html con lang="es"
- Meta charset UTF-8
- Meta viewport para responsive
- Meta description, author y keywords
- Título del documento
- Enlace a archivo CSS

## Tipo de cambio
- [x] Nueva funcionalidad
- [ ] Corrección de bug
- [ ] Documentación

## Checklist
- [x] El código funciona correctamente
- [x] He probado los cambios localmente
- [x] El código sigue las convenciones del proyecto
- [x] He dejado comentarios para guiar a otros miembros
```

4. Asigna revisores (tus compañeros)
5. Crea el Pull Request

---

## Explicación del Código

### `<!DOCTYPE html>`
- Declara que este es un documento HTML5
- Debe ser la primera línea del archivo

### `<html lang="es">`
- Etiqueta raíz del documento
- `lang="es"` indica que el contenido está en español
- Ayuda a los lectores de pantalla y motores de búsqueda

### `<meta charset="UTF-8">`
- Define la codificación de caracteres
- UTF-8 soporta todos los caracteres especiales (ñ, á, é, etc.)

### `<meta name="viewport">`
- Hace que la página sea responsive
- Esencial para dispositivos móviles

### `<meta name="description">`
- Descripción que aparece en resultados de búsqueda
- Importante para SEO

### `<title>`
- Título que aparece en la pestaña del navegador
- También importante para SEO

### `<link rel="stylesheet">`
- Enlaza el archivo CSS que creará el Miembro 4
- La ruta `assets/styles.css` debe coincidir con la estructura del proyecto

---

## Checklist de Completación

Antes de crear tu Pull Request, verifica:

- [ ] El archivo `index.html` está en la raíz del proyecto
- [ ] Todas las etiquetas están correctamente cerradas
- [ ] La indentación es consistente (2 o 4 espacios)
- [ ] El charset es UTF-8
- [ ] El idioma está configurado en español
- [ ] El título es descriptivo
- [ ] La ruta del CSS es correcta
- [ ] Dejaste un comentario indicando dónde irá el body
- [ ] Hiciste commit con mensaje descriptivo
- [ ] Subiste tu rama al repositorio remoto

---

## Coordinación con el Equipo

### Tu trabajo es la base para:

**Miembro 2** necesita tu estructura para agregar el `<body>` y el header
- Comunícale cuando tu PR esté listo
- Tu merge debe ser el primero

**Miembro 4** usará la ruta del CSS que definiste
- Asegúrate de que la ruta sea `assets/styles.css`
- Si cambias la ruta, avísale

### Consejos:
- Crea tu PR lo antes posible
- Responde rápido a comentarios de revisión
- Una vez aprobado, haz merge inmediatamente
- Avisa al equipo cuando hayas hecho merge

---

## Problemas Comunes

### "No puedo crear el archivo"
```bash
# Asegúrate de estar en la carpeta correcta
pwd

# Debe mostrar: /ruta/a/challenge-html
# Si no, navega a la carpeta correcta
cd /ruta/a/challenge-html
```

### "Git dice que el archivo no está tracked"
```bash
# Agrega el archivo explícitamente
git add index.html

# Verifica que esté staged
git status
```

### "Mi commit no aparece en GitHub"
```bash
# Asegúrate de haber hecho push
git push origin feature/estructura-base

# Si hay error, verifica el nombre de tu rama
git branch
```

### "Quiero cambiar algo después del commit"
```bash
# Haz los cambios en el archivo
# Luego:
git add index.html
git commit --amend -m "feat: agregar estructura HTML base con DOCTYPE y head"
git push origin feature/estructura-base --force
```

---

## Recursos Adicionales

- [MDN: Estructura básica HTML](https://developer.mozilla.org/es/docs/Learn/HTML/Introduction_to_HTML/Getting_started)
- [MDN: Meta tags](https://developer.mozilla.org/es/docs/Web/HTML/Element/meta)
- [HTML5 Doctor](http://html5doctor.com/)

---

## Comandos Git que Usarás

```bash
# Ver estado
git status

# Ver diferencias
git diff

# Ver historial
git log --oneline

# Ver ramas
git branch

# Cambiar de rama
git checkout nombre-rama

# Actualizar desde main
git pull origin main

# Subir cambios
git push origin feature/estructura-base
```

---

## Tips Profesionales

1. **Indentación consistente**: Usa 2 o 4 espacios, no mezcles
2. **Comentarios útiles**: Deja comentarios para guiar a tus compañeros
3. **Commits atómicos**: Un commit = una funcionalidad completa
4. **Mensajes claros**: Usa el formato `feat:`, `fix:`, etc.
5. **Revisa antes de commit**: Lee tu código una vez más

---

## Criterios de Éxito

Tu tarea está completa cuando:

- El archivo `index.html` existe en la raíz
- La estructura HTML es válida
- Todos los meta tags están presentes
- El enlace al CSS es correcto
- Tu commit tiene un mensaje descriptivo
- Tu rama está en GitHub
- Has creado el Pull Request
- Tu PR ha sido revisado y aprobado
- Has hecho merge a main
- Has notificado al equipo

---

**¡Eres el primero! Tu trabajo es fundamental para el éxito del equipo.**
