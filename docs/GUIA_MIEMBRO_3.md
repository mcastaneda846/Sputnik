# Guía para Miembro 3: Contenido Principal

## Tu Misión

Eres responsable de crear el **contenido principal** de la página. Agregarás secciones con texto, párrafos e imágenes dentro de la estructura `<main>` que creó el Miembro 2.

---

## Tareas Asignadas

### 1. Crear sección de inicio/bienvenida
### 2. Agregar sección "Sobre el Proyecto"
### 3. Implementar sección del equipo
### 4. Insertar imágenes relevantes
### 5. Escribir contenido descriptivo

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

### Paso 2: Esperar a que Miembros 1 y 2 terminen

⚠️ **IMPORTANTE**: Antes de empezar, asegúrate de que los Miembros 1 y 2 hayan hecho merge de sus PRs.

```bash
# Actualizar tu repositorio local
git checkout main
git pull origin main

# Verificar que la estructura existe
cat index.html | grep "<main>"
```

### Paso 3: Crear tu rama de trabajo

```bash
# Crear tu rama desde main actualizado
git checkout -b feature/contenido
```

### Paso 4: Editar el archivo HTML

Abre `index.html` y agrega el contenido dentro de `<main>`:

```html
    <main>
        <section id="inicio">
            <h2>Bienvenidos al Challenge HTML</h2>
            <p>
                Este proyecto es un ejercicio práctico para aprender a trabajar 
                colaborativamente usando Git y GitHub. Cada miembro del equipo 
                contribuye con una parte específica del código, simulando un 
                entorno de desarrollo profesional real.
            </p>
            <p>
                A través de este challenge, aprenderás a crear ramas, hacer commits, 
                crear pull requests, revisar código de otros y resolver conflictos 
                de merge. ¡Todo esto mientras construimos una página web juntos!
            </p>
        </section>

        <section id="sobre">
            <h2>Sobre el Proyecto</h2>
            <p>
                El objetivo es construir una página web completa donde cada 
                integrante aporta diferentes elementos: estructura base, header 
                con navegación, contenido principal y footer con estilos.
            </p>
            <p>
                Este enfoque colaborativo refleja cómo funcionan los equipos de 
                desarrollo en la industria, donde múltiples desarrolladores trabajan 
                simultáneamente en diferentes características del mismo proyecto.
            </p>
            <img src="https://via.placeholder.com/600x300/667eea/ffffff?text=Trabajo+en+Equipo" 
                 alt="Ilustración de trabajo en equipo colaborativo">
        </section>

        <section id="equipo">
            <h2>Nuestro Equipo</h2>
            <p>
                Somos un equipo de 4 desarrolladores aprendiendo las mejores 
                prácticas de colaboración con control de versiones. Cada miembro 
                tiene un rol específico en este proyecto:
            </p>
            <ul>
                <li><strong>Miembro 1:</strong> Estructura HTML base</li>
                <li><strong>Miembro 2:</strong> Header y navegación</li>
                <li><strong>Miembro 3:</strong> Contenido principal</li>
                <li><strong>Miembro 4:</strong> Footer y estilos CSS</li>
            </ul>
            <img src="https://via.placeholder.com/600x300/764ba2/ffffff?text=Equipo+de+Desarrollo" 
                 alt="Equipo de desarrollo trabajando juntos">
        </section>
    </main>
```

### Paso 5: Guardar y hacer commit

```bash
# Ver los cambios
git diff

# Agregar el archivo
git add index.html

# Hacer commit
git commit -m "feat: agregar secciones de contenido principal con imágenes"

# Ver el commit
git log --oneline -3
```

### Paso 6: Subir tu rama

```bash
# Subir tu rama al repositorio remoto
git push origin feature/contenido
```

### Paso 7: Crear Pull Request

1. Ve a GitHub
2. Clic en "Compare & pull request"
3. Completa la información:

```markdown
## Descripción
Implementación del contenido principal con tres secciones: inicio, sobre el proyecto y equipo.

## Cambios realizados
- Creada sección de inicio con bienvenida
- Agregada sección "Sobre el Proyecto"
- Implementada sección del equipo con roles
- Insertadas 2 imágenes ilustrativas
- Escritos párrafos descriptivos y claros
- Usados IDs que coinciden con la navegación

## Tipo de cambio
- [x] Nueva funcionalidad
- [ ] Corrección de bug
- [ ] Documentación

## Checklist
- [x] El código funciona correctamente
- [x] He probado los cambios localmente
- [x] El código sigue las convenciones del proyecto
- [x] Los IDs coinciden con los enlaces de navegación
- [x] Las imágenes tienen atributos alt descriptivos
- [x] El contenido es claro y sin errores ortográficos

## Dependencias
- Depende de: PR de Miembro 1 (estructura base)
- Depende de: PR de Miembro 2 (header y navegación)
```

4. Asigna revisores
5. Crea el Pull Request

---

## Explicación del Código

### `<section>`
- Elemento semántico para agrupar contenido relacionado
- Cada sección debe tener un encabezado (h2, h3, etc.)
- Mejora la accesibilidad y SEO

### Atributo `id`
- Identificador único para cada sección
- Permite la navegación con enlaces de ancla
- Debe coincidir con los enlaces del Miembro 2: `#inicio`, `#sobre`, `#equipo`

### `<h2>`
- Encabezado de nivel 2 (subtítulo)
- Jerarquía: h1 (título principal) > h2 (secciones) > h3 (subsecciones)
- Importante para estructura y accesibilidad

### `<p>`
- Párrafo de texto
- Cada idea o concepto en su propio párrafo
- Mejora la legibilidad

### `<img>`
- Elemento para insertar imágenes
- `src`: URL o ruta de la imagen
- `alt`: texto alternativo (crucial para accesibilidad)

### Placeholder images
- `https://via.placeholder.com/` genera imágenes de prueba
- Formato: `ancho x alto / color-fondo / color-texto ? text=Texto`
- Útil para desarrollo, reemplazar con imágenes reales en producción

---

## Checklist de Completación

Antes de crear tu Pull Request, verifica:

- [ ] Agregaste 3 secciones dentro de `<main>`
- [ ] Cada sección tiene un `id` único
- [ ] Los IDs coinciden con la navegación: `inicio`, `sobre`, `equipo`
- [ ] Cada sección tiene un `<h2>` descriptivo
- [ ] Hay al menos 2 párrafos de contenido
- [ ] Insertaste al menos 2 imágenes
- [ ] Todas las imágenes tienen atributo `alt`
- [ ] El contenido es claro y sin errores ortográficos
- [ ] La indentación es consistente
- [ ] Todas las etiquetas están correctamente cerradas
- [ ] Hiciste commit con mensaje descriptivo
- [ ] Subiste tu rama al repositorio remoto

---

## Coordinación con el Equipo

### Dependes de:

**Miembro 1** debe haber creado la estructura base
**Miembro 2** debe haber creado el `<main>` y la navegación
- Espera a que ambos PRs sean merged
- Actualiza tu main antes de crear tu rama
- Verifica los IDs que usó Miembro 2 en la navegación

### Tu trabajo se coordina con:

**Miembro 4** agregará el footer después de tu contenido
- No cierres la etiqueta `<main>` si Miembro 4 necesita agregar algo dentro
- Comunícale cuando tu PR esté listo

### Consejos:
- Confirma con Miembro 2 los IDs de las secciones
- Puedes trabajar en paralelo con Miembro 4 (más conflictos, más aprendizaje)
- Responde rápido a comentarios de revisión

---

## Problemas Comunes

### "No encuentro la etiqueta <main>"
```bash
# Asegúrate de que Miembro 2 haya hecho merge
git checkout main
git pull origin main
cat index.html | grep "<main>"

# Si no existe, espera a que Miembro 2 termine
```

### "Los IDs no coinciden con la navegación"
```bash
# Revisa los enlaces en el header
cat index.html | grep "href=\"#"

# Asegúrate de usar los mismos IDs en tus secciones
```

### "Hay conflictos al hacer merge"
```bash
# Actualiza tu rama con main
git checkout feature/contenido
git pull origin main

# Si hay conflictos, ábrelos y resuélvelos
# Busca los marcadores: <<<<<<<, =======, >>>>>>>
# Edita el archivo para resolver
git add index.html
git commit -m "fix: resolver conflictos con main"
git push origin feature/contenido
```

### "Quiero cambiar el contenido después del commit"
```bash
# Haz los cambios en index.html
# Luego:
git add index.html
git commit -m "feat: mejorar contenido de secciones"
git push origin feature/contenido
```

---

## Recursos Adicionales

- [MDN: Elemento section](https://developer.mozilla.org/es/docs/Web/HTML/Element/section)
- [MDN: Elemento img](https://developer.mozilla.org/es/docs/Web/HTML/Element/img)
- [MDN: Atributo alt](https://developer.mozilla.org/es/docs/Web/HTML/Element/img#attr-alt)
- [Placeholder.com](https://placeholder.com/) - Servicio de imágenes de prueba
- [Unsplash](https://unsplash.com/) - Imágenes gratuitas de alta calidad

---

## Comandos Git que Usarás

```bash
# Actualizar main
git checkout main
git pull origin main

# Crear tu rama
git checkout -b feature/contenido

# Ver cambios
git diff

# Ver estado
git status

# Agregar y commit
git add index.html
git commit -m "feat: agregar secciones de contenido principal con imágenes"

# Subir cambios
git push origin feature/contenido

# Actualizar tu rama con main
git checkout feature/contenido
git pull origin main
```

---

## Tips Profesionales

1. **Contenido significativo**: Escribe texto real, no "Lorem ipsum"
2. **Alt descriptivo**: Describe qué muestra la imagen, no solo "imagen"
3. **Estructura clara**: Usa secciones para organizar el contenido
4. **IDs consistentes**: Verifica que coincidan con la navegación
5. **Prueba los enlaces**: Haz clic en la navegación para verificar que funciona

---

## Cómo Probar tu Código

```bash
# Abre el archivo en tu navegador
xdg-open index.html
```

Verifica que:
- Las 3 secciones aparecen correctamente
- Las imágenes se cargan
- Al hacer clic en la navegación, te lleva a cada sección
- No hay errores en la consola del navegador
- El texto es legible y sin errores

---

## Ideas para Mejorar

Si quieres ir más allá:

1. **Más secciones**: Agrega una sección de "Tecnologías usadas"
2. **Listas**: Usa `<ul>` o `<ol>` para enumerar puntos
3. **Énfasis**: Usa `<strong>` o `<em>` para resaltar texto
4. **Enlaces externos**: Agrega links a recursos útiles
5. **Imágenes reales**: Reemplaza placeholders con imágenes de Unsplash

Ejemplo:
```html
<section id="tecnologias">
    <h2>Tecnologías Utilizadas</h2>
    <ul>
        <li>HTML5</li>
        <li>CSS3</li>
        <li>Git & GitHub</li>
    </ul>
</section>
```

---

## Criterios de Éxito

Tu tarea está completa cuando:

- Las 3 secciones están implementadas
- Los IDs coinciden con la navegación
- El contenido es claro y descriptivo
- Las imágenes tienen alt descriptivos
- La navegación funciona correctamente
- Tu commit tiene un mensaje descriptivo
- Tu rama está en GitHub
- Has creado el Pull Request
- Tu PR ha sido revisado y aprobado
- Has hecho merge a main
- Has notificado al equipo

---

**¡El contenido es el corazón de la página! Hazlo interesante y útil.**
