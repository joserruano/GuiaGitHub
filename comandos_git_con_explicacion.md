
# Listado de Comandos de Git con Explicación

## Configuración de nombre y correo electrónico

Estos comandos configuran el nombre y el correo electrónico del usuario a nivel global en Git. Esta información se asocia con cada commit que hagas, lo que permite que otros desarrolladores vean quién realizó los cambios.

- **`git config --global user.name "<nombre>"`**:  
   Establece el nombre del usuario que aparecerá en cada commit realizado.
  
- **`git config --global user.email "<correo>"`**:  
   Establece el correo electrónico del usuario asociado con cada commit.

Ambos valores se aplican de manera global, lo que significa que se utilizarán en todos los repositorios Git que tengas en tu máquina. Si quisieras configurar el nombre y el correo electrónico solo para un repositorio en particular, puedes omitir la opción `--global` y ejecutar los comandos dentro de la carpeta del proyecto.

---

## Listado de Comandos de Git

1. **`git config --global --list`**  
   Muestra la configuración global de Git.

2. **`git init`**  
   Inicializa un nuevo repositorio de Git en la carpeta actual.

3. **`git add <archivo>`**  
   Agrega un archivo específico al área de preparación (staging area).

4. **`git commit -m "<mensaje>"`**  
   Realiza un commit con los cambios añadidos al área de preparación, incluyendo un mensaje descriptivo.

5. **`git mv <archivo_antiguo> <archivo_nuevo>`**  
   Renombra o mueve un archivo dentro del repositorio.

6. **`git branch <nombre_rama>`**  
   Crea una nueva rama.

7. **`git checkout <nombre_rama>`**  
    Cambia a una rama existente.

8. **`git merge <nombre_rama>`**  
    Fusiona los cambios de una rama con la rama actual.

