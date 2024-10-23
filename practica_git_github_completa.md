
# Práctica completa de Git y GitHub

## 1. Configuración inicial

Primero, configura tu nombre, correo electrónico y editor de texto. Estos datos se utilizarán en todos tus commits.

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tuemail@ejemplo.com"
```

Para verificar tu configuración global:

```bash
git config --global --list
```

**Pregunta**:  
- **¿Para qué sirve el parámetro `--global`?**  
   El parámetro `--global` aplica esta configuración a todos los repositorios en tu sistema. Si no lo usas, la configuración será específica solo para el repositorio en el que estás trabajando.

---

## 2. Primer repositorio local

En este paso, crearás el repositorio y los archivos manualmente usando el Explorador de archivos y el Bloc de notas.

### Crear el directorio y archivos manualmente:

1. **Crear la carpeta del repositorio**:
   - Abre el **Explorador de archivos**.
   - Navega a donde quieras crear el proyecto (por ejemplo, en el Escritorio o en Documentos).
   - Haz clic derecho en un espacio vacío y selecciona **Nuevo > Carpeta**.
   - Nombra la carpeta como `git-workshop`.

2. **Crear los archivos `README.md` y `Jose.txt`**:
   - Abre el **Bloc de notas**.
   - Deja el archivo vacío o escribe algo sencillo, como "Este es el archivo README" para el archivo `README.md`.
   - Haz clic en **Archivo > Guardar como...**.
   - Cambia el tipo de archivo a **Todos los archivos** en el menú desplegable.
   - Nombra el archivo como `README.md` y guárdalo en la carpeta `git-workshop`.
   - Repite el proceso para crear el archivo `Jose.txt` (puedes dejarlo vacío si lo deseas).

### Inicializar el repositorio de Git:

1. Abre la consola de Windows (cmd) y navega a la carpeta `git-workshop` donde creaste los archivos:

   ```bash
   cd C:\Users\TuNombre\Desktop\git-workshop
   ```

2. Inicializa el repositorio de Git en esa carpeta:

   ```bash
   git init
   ```

### Agregar los archivos al área de preparación y hacer el primer commit:

1. Añade los archivos creados manualmente al área de preparación:

   ```bash
   git add README.md Jose.txt
   ```

2. Realiza el primer commit:

   ```bash
   git commit -m "Primer commit con README.md y Jose.txt"
   ```

---

## 3. Correcciones básicas

Este paso lo haremos manualmente desde el Explorador de archivos.

1. **Renombrar el archivo `Jose.txt`**:
   - Abre la carpeta `git-workshop` en el **Explorador de archivos**.
   - Haz clic derecho sobre el archivo `Jose.txt` y selecciona **Renombrar**.
   - Cambia el nombre a `TuNombre.txt` (por ejemplo, `Juan.txt` si te llamas Juan).

2. **Actualizar el commit con el cambio de nombre**:

   En la consola de Windows (cmd), actualiza el commit anterior para reflejar el cambio:

   ```bash
   git add TuNombre.txt
   git commit --amend -m "Renombrado de archivo a TuNombre.txt"
   ```

---

## 4. Crear ramas

### Rama `yo++`:

1. **Crear la rama `yo++`**:
   - Abre la consola de Windows y crea la rama `yo++`:

   ```bash
   git checkout -b yo++
   ```

2. **Modificar el archivo `TuNombre.txt` manualmente**:
   - Abre el archivo `TuNombre.txt` con el **Bloc de notas**.
   - Escribe una descripción sobre ti, por ejemplo: "Me llamo Juan y me encanta programar en Git."
   - Guarda el archivo y ciérralo.

3. **Agregar y commitear los cambios**:

   En la consola, agrega el archivo al área de preparación y realiza un commit:

   ```bash
   git add TuNombre.txt
   git commit -m "Añadida descripción personal en TuNombre.txt"
   ```

### Rama `taller-info`:

1. **Crear la rama `taller-info`**:
   - Cambia de vuelta a la rama `master`:

   ```bash
   git checkout master
   ```

   - Crea la nueva rama `taller-info`:

   ```bash
   git checkout -b taller-info
   ```

2. **Modificar el archivo `README.md` manualmente**:
   - Abre el archivo `README.md` con el **Bloc de notas**.
   - Escribe una breve descripción sobre el taller, por ejemplo: "Este taller es una introducción a Git y GitHub."
   - Guarda el archivo y ciérralo.

3. **Agregar y commitear los cambios**:

   En la consola, agrega el archivo al área de preparación y realiza un commit:

   ```bash
   git add README.md
   git commit -m "Añadida información del taller en README.md"
   ```

**Pregunta**:  
- **¿Desde la rama `taller-info`, el archivo `.txt` con tu nombre tiene contenido o está vacío? ¿Por qué?**  
   El archivo `TuNombre.txt` estará vacío en la rama `taller-info`, ya que el contenido fue agregado en la rama `yo++` y aún no se han fusionado los cambios entre estas ramas.

---

## 5. Merge fast-forward de ramas

1. Cambia a la rama `master` y realiza el merge con la rama `yo++`:

   ```bash
   git checkout master
   git merge yo++
   ```

Este merge será un **fast-forward**, ya que no hay otros cambios en `master` que interfieran.

---

## 6. Merge recursive de ramas

1. Permanece en la rama `master` y realiza el merge con la rama `taller-info`:

   ```bash
   git merge taller-info
   ```

Este merge utilizará el algoritmo de merge recursivo.

---

## 7. Aparición de conflictos al realizar merge

En este paso, modificaremos manualmente los archivos y crearemos un conflicto.

1. **Modificar `README.md` en la rama `master`**:
   - Abre `README.md` con el **Bloc de notas** y escribe algo distinto en la primera línea, por ejemplo: "Modificación en master."
   - Guarda el archivo y ciérralo.

2. **Agregar y commitear los cambios en `master`**:

   ```bash
   git add README.md
   git commit -m "Modificada la primera línea de README.md en master"
   ```

3. **Modificar `README.md` en la rama `taller-info`**:
   - Cambia a la rama `taller-info`:

   ```bash
   git checkout taller-info
   ```

   - Abre `README.md` con el **Bloc de notas** y escribe algo distinto en la primera línea, por ejemplo: "Modificación en taller-info."
   - Guarda el archivo y ciérralo.

4. **Agregar y commitear los cambios en `taller-info`**:

   ```bash
   git add README.md
   git commit -m "Modificada la primera línea de README.md en taller-info"
   ```

5. **Intentar un merge y crear un conflicto**:

   Cambia de nuevo a la rama `master` e intenta hacer un merge con `taller-info`:

   ```bash
   git checkout master
   git merge taller-info
   ```

---

## 8. Resolución de conflictos de merge

1. **Resolver el conflicto manualmente**:
   - Abre el archivo `README.md` con el **Bloc de notas**.
   - Verás las marcas del conflicto (`<<<<<<<`, `=======`, `>>>>>>>`).
   - Elimina los marcadores y deja el contenido final que desees.
   - Guarda el archivo y ciérralo.

2. **Agregar y completar el merge**:

   ```bash
   git add README.md
   git commit -m "Resolución del conflicto en README.md"
   ```

---

## 9. Primer repositorio en GitHub

1. Crea un nuevo repositorio en GitHub llamado `tu-nombre-intro-git` desde la interfaz de GitHub en [GitHub.com](https://github.com).

---

## 10. Subir los cambios a GitHub con GitHub Desktop

1. **Abrir GitHub Desktop** y añadir el repositorio local.
   - Selecciona **File > Add Local Repository**.
   - Busca la carpeta `git-workshop` y selecciónala.

2. **Publicar el repositorio**:
   - Haz clic en **Publish repository** y asegúrate de que el nombre del repositorio sea `tu-nombre-intro-git`.

3. **Subir las ramas `yo++` y `taller-info`**:
   - Cambia a la rama `yo++` en el menú desplegable de ramas de GitHub Desktop.
   - Haz clic en **Publish branch** para subir la rama `yo++`.
   - Repite el proceso para la rama `taller-info`.
