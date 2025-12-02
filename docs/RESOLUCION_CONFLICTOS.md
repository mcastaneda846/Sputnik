# Guía de Resolución de Conflictos en Git

## ¿Qué es un Conflicto de Merge?

Un **conflicto de merge** ocurre cuando dos o más personas modifican las mismas líneas de código en un archivo, y Git no puede determinar automáticamente qué versión mantener.

### Ejemplo de situación:
1. **Miembro 2** agrega un header con un título
2. **Miembro 3** también agrega un header con un título diferente
3. Ambos trabajan en la misma parte del archivo `index.html`
4. Cuando intentan hacer merge, Git detecta el conflicto

---

## ¿Cómo Saber si Hay un Conflicto?

### Durante un Pull Request en GitHub:
- Verás un mensaje: "This branch has conflicts that must be resolved"
- GitHub te mostrará qué archivos tienen conflictos

### Durante un `git pull` o `git merge`:
```bash
$ git pull origin main
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```

### Verificar estado:
```bash
git status
```

Verás algo como:
```
Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   index.html
```

---

## Anatomía de un Conflicto

Cuando abres un archivo con conflictos, verás marcadores especiales:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <title>Mi Proyecto</title>
</head>
<body>
<<<<<<< HEAD
    <h1>Bienvenidos a Mi Sitio</h1>
=======
    <h1>Proyecto Colaborativo HTML</h1>
>>>>>>> feature/otra-rama
</body>
</html>
```

### Significado de los marcadores:

- `<<<<<<< HEAD`: Inicio del conflicto, tu versión actual
- `=======`: Separador entre las dos versiones
- `>>>>>>> feature/otra-rama`: Fin del conflicto, versión de la otra rama

**Entre `<<<<<<< HEAD` y `=======`**: Tu código (la rama en la que estás)
**Entre `=======` y `>>>>>>> feature/otra-rama`**: El código de la otra rama

---

## Cómo Resolver un Conflicto

### Paso 1: Identificar el conflicto

```bash
# Ver qué archivos tienen conflictos
git status

# Ver el contenido del conflicto
cat index.html
# O abre el archivo en tu editor
```

### Paso 2: Decidir qué código mantener

Tienes 4 opciones:

#### Opción A: Mantener tu versión
```html
<!-- ANTES -->
<<<<<<< HEAD
    <h1>Bienvenidos a Mi Sitio</h1>
=======
    <h1>Proyecto Colaborativo HTML</h1>
>>>>>>> feature/otra-rama

<!-- DESPUÉS -->
    <h1>Bienvenidos a Mi Sitio</h1>
```

#### Opción B: Mantener la otra versión
```html
<!-- ANTES -->
<<<<<<< HEAD
    <h1>Bienvenidos a Mi Sitio</h1>
=======
    <h1>Proyecto Colaborativo HTML</h1>
>>>>>>> feature/otra-rama

<!-- DESPUÉS -->
    <h1>Proyecto Colaborativo HTML</h1>
```

#### Opción C: Mantener ambas versiones
```html
<!-- ANTES -->
<<<<<<< HEAD
    <h1>Bienvenidos a Mi Sitio</h1>
=======
    <h1>Proyecto Colaborativo HTML</h1>
>>>>>>> feature/otra-rama

<!-- DESPUÉS -->
    <h1>Bienvenidos a Mi Sitio</h1>
    <h1>Proyecto Colaborativo HTML</h1>
```

#### Opción D: Crear una versión nueva (RECOMENDADO)
```html
<!-- ANTES -->
<<<<<<< HEAD
    <h1>Bienvenidos a Mi Sitio</h1>
=======
    <h1>Proyecto Colaborativo HTML</h1>
>>>>>>> feature/otra-rama

<!-- DESPUÉS -->
    <h1>Bienvenidos al Proyecto Colaborativo HTML</h1>
```

### Paso 3: Eliminar los marcadores

**MUY IMPORTANTE**: Debes eliminar TODOS los marcadores:
- `<<<<<<< HEAD`
- `=======`
- `>>>>>>> feature/otra-rama`

Si dejas estos marcadores, el código no funcionará.

### Paso 4: Guardar el archivo

Guarda el archivo con la resolución del conflicto.

### Paso 5: Marcar como resuelto

```bash
# Agregar el archivo resuelto
git add index.html

# Verificar que está staged
git status
```

### Paso 6: Completar el merge

```bash
# Hacer commit del merge
git commit -m "fix: resolver conflicto en título del header"

# Subir los cambios
git push origin tu-rama
```

---

## Ejemplo Completo Paso a Paso

### Escenario:
Estás en la rama `feature/contenido` y quieres actualizar con `main`:

```bash
# 1. Intentar actualizar
git checkout feature/contenido
git pull origin main

# Git responde:
# CONFLICT (content): Merge conflict in index.html
# Automatic merge failed; fix conflicts and then commit the result.

# 2. Ver el estado
git status
# Unmerged paths:
#   both modified:   index.html

# 3. Abrir el archivo
nano index.html
# O usa tu editor favorito: code index.html, vim index.html, etc.

# 4. Buscar los marcadores de conflicto
# Verás algo como:
```

```html
<main>
<<<<<<< HEAD
    <section>
        <h2>Mi Contenido</h2>
        <p>Este es mi párrafo.</p>
    </section>
=======
    <section>
        <h2>Nuestro Contenido</h2>
        <p>Este es nuestro párrafo colaborativo.</p>
    </section>
>>>>>>> main
</main>
```

```bash
# 5. Decidir qué mantener (ejemplo: combinar ambos)
```

```html
<main>
    <section>
        <h2>Nuestro Contenido Colaborativo</h2>
        <p>Este es nuestro párrafo colaborativo.</p>
    </section>
</main>
```

```bash
# 6. Guardar el archivo (Ctrl+O en nano, :wq en vim)

# 7. Marcar como resuelto
git add index.html

# 8. Verificar
git status
# All conflicts fixed but you are still merging.

# 9. Completar el merge
git commit -m "fix: resolver conflicto en sección de contenido"

# 10. Subir cambios
git push origin feature/contenido

# ¡Listo! El conflicto está resuelto.
```

---

## Resolución Colaborativa de Conflictos

### Mejor Práctica: Comunicarse

Cuando hay un conflicto:

1. **Identifica con quién tienes el conflicto**
   ```bash
   # Ver quién modificó el archivo
   git log --oneline index.html
   ```

2. **Habla con tu compañero**
   - "Hey, tenemos un conflicto en index.html"
   - "¿Qué estabas tratando de hacer?"
   - "Vamos a decidir juntos qué mantener"

3. **Decidan juntos la mejor solución**
   - No siempre es mantener tu versión
   - A veces la mejor solución es una combinación
   - O incluso una versión completamente nueva

4. **Documenta la decisión**
   ```bash
   git commit -m "fix: resolver conflicto en header - decidimos usar título combinado después de discusión con @compañero"
   ```

---

## Errores Comunes

### Error 1: Dejar los marcadores
```html
<!-- ❌ MAL -->
<<<<<<< HEAD
    <h1>Mi Título</h1>
=======
    <h1>Otro Título</h1>
>>>>>>> main
```

**Resultado**: La página mostrará literalmente esos símbolos.

**Solución**: Siempre elimina los marcadores.

### Error 2: Hacer commit sin resolver
```bash
# ❌ MAL
git commit -m "fix: resolver conflicto"
# Error: You have unmerged paths.
```

**Solución**: Primero resuelve y haz `git add`, luego commit.

### Error 3: Perder código importante
```html
<!-- ❌ MAL: Eliminar todo el código de la otra persona -->
<!-- Solo mantener tu versión sin revisar -->
```

**Solución**: Lee ambas versiones cuidadosamente antes de decidir.

### Error 4: No probar después de resolver
```bash
# ❌ MAL: Hacer commit sin probar
git add index.html
git commit -m "fix: resolver conflicto"
# Pero el código no funciona...
```

**Solución**: Siempre prueba el código después de resolver.

---

## Herramientas para Resolver Conflictos

### 1. Editor de texto
- Nano, Vim, VS Code, etc.
- Busca los marcadores manualmente
- Edita y guarda

### 2. Git mergetool
```bash
# Usar herramienta de merge
git mergetool

# Git abrirá una herramienta visual (si está configurada)
```

### 3. VS Code
- Detecta conflictos automáticamente
- Muestra botones: "Accept Current Change", "Accept Incoming Change", "Accept Both Changes"
- Muy visual y fácil de usar

### 4. GitHub (para conflictos simples)
- Algunos conflictos se pueden resolver directamente en GitHub
- Clic en "Resolve conflicts" en el PR

---

## Prevención de Conflictos

### Estrategia 1: Comunicación
- Avisa al equipo en qué estás trabajando
- Usa issues o comentarios para coordinar
- "Voy a trabajar en el header, no lo modifiquen"

### Estrategia 2: Trabajo secuencial
```bash
# Orden recomendado:
# 1. Miembro 1 → merge
# 2. Miembro 2 → merge
# 3. Miembro 3 → merge
# 4. Miembro 4 → merge
```

### Estrategia 3: Actualizar frecuentemente
```bash
# Antes de empezar a trabajar
git checkout main
git pull origin main
git checkout tu-rama
git merge main

# Cada pocas horas
git checkout tu-rama
git pull origin main
```

### Estrategia 4: Commits pequeños y frecuentes
```bash
# ✅ BIEN: Commits pequeños
git commit -m "feat: agregar título"
git commit -m "feat: agregar navegación"
git commit -m "feat: agregar estilos al header"

# ❌ MAL: Un commit gigante
git commit -m "feat: agregar todo el header con navegación y estilos"
```

### Estrategia 5: Dividir archivos
```
# En lugar de que todos editen index.html
# Podrían dividir:
- index.html (estructura)
- header.html (incluido en index)
- footer.html (incluido en index)
- styles.css (estilos)
```

---

## Comandos Útiles

```bash
# Ver archivos con conflictos
git status

# Ver el contenido del conflicto
git diff

# Abortar el merge (si quieres empezar de nuevo)
git merge --abort

# Ver quién modificó cada línea
git blame index.html

# Ver historial de un archivo
git log --oneline index.html

# Ver diferencias entre ramas
git diff main..tu-rama

# Actualizar tu rama con main
git checkout tu-rama
git merge main
# O
git pull origin main
```

---

## Ejercicio Práctico

### Simular un conflicto:

```bash
# 1. Crear dos ramas
git checkout -b rama-a
echo "<h1>Título A</h1>" > test.html
git add test.html
git commit -m "Agregar título A"

git checkout main
git checkout -b rama-b
echo "<h1>Título B</h1>" > test.html
git add test.html
git commit -m "Agregar título B"

# 2. Intentar merge
git checkout rama-a
git merge rama-b
# ¡Conflicto!

# 3. Resolver
# Edita test.html
# Decide qué título mantener
git add test.html
git commit -m "Resolver conflicto"

# 4. Limpiar
git checkout main
git branch -D rama-a rama-b
rm test.html
```

---

## Consejos Finales

1. **No tengas miedo de los conflictos** - Son oportunidades de aprendizaje
2. **Lee el código cuidadosamente** - Entiende qué hace cada versión
3. **Comunícate con tu equipo** - Dos cabezas piensan mejor que una
4. **Prueba después de resolver** - Asegúrate de que funciona
5. **Documenta tus decisiones** - En el mensaje de commit
6. **Pide ayuda si te atascas** - Es mejor preguntar que romper el código

---

## ¿Necesitas Ayuda?

Si te atascas:

1. **No entres en pánico**
2. **Lee el error cuidadosamente**
3. **Usa `git status`** para entender la situación
4. **Pide ayuda a tu equipo**
5. **Busca en Google** el mensaje de error
6. **Si todo falla**, usa `git merge --abort` y empieza de nuevo

---

## Checklist de Resolución

- [ ] Identificaste el archivo con conflicto
- [ ] Abriste el archivo y encontraste los marcadores
- [ ] Leíste ambas versiones del código
- [ ] Decidiste qué código mantener
- [ ] Eliminaste TODOS los marcadores (`<<<<<<<`, `=======`, `>>>>>>>`)
- [ ] Guardaste el archivo
- [ ] Probaste que el código funciona
- [ ] Hiciste `git add` del archivo
- [ ] Hiciste commit con mensaje descriptivo
- [ ] Hiciste push de los cambios
- [ ] Notificaste a tu equipo

---

**¡Los conflictos son parte normal del desarrollo colaborativo! Aprender a resolverlos te hace un mejor desarrollador.**
