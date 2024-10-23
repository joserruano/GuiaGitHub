
# Listado de Comandos de Git con Explicación

## Configuración de nombre y correo electrónico

### `git config --global user.name "<nombre>"` y `git config --global user.email "<correo>"`

Estos comandos configuran el nombre y el correo electrónico del usuario a nivel global en Git. Esta información se asocia con cada commit que hagas, lo que permite que otros desarrolladores vean quién realizó los cambios.

- **`git config --global user.name "<nombre>"`**:  
   Establece el nombre del usuario que aparecerá en cada commit realizado.
  
- **`git config --global user.email "<correo>"`**:  
   Establece el correo electrónico del usuario asociado con cada commit.

Ambos valores se aplican de manera global, lo que significa que se utilizarán en todos los repositorios Git que tengas en tu máquina. Si quisieras configurar el nombre y el correo electrónico solo para un repositorio en particular, puedes omitir la opción `--global` y ejecutar los comandos dentro de la carpeta del proyecto.

---

## Listado de Comandos de Git

1. **`git config --global user.name "<nombre>"`**  
   Configura el nombre de usuario global para Git.

2. **`git config --global user.email "<correo>"`**  
   Configura el correo electrónico global para Git.

3. **`git config --global --list`**  
   Muestra la configuración global de Git.

4. **`git init`**  
   Inicializa un nuevo repositorio de Git en la carpeta actual.

5. **`git add <archivo>`**  
   Agrega un archivo específico al área de preparación (staging area).

6. **`git commit -m "<mensaje>"`**  
   Realiza un commit con los cambios añadidos al área de preparación, incluyendo un mensaje descriptivo.

7. **`git mv <archivo_antiguo> <archivo_nuevo>`**  
   Renombra o mueve un archivo dentro del repositorio.

8. **`git commit --amend -m "<mensaje>"`**  
   Modifica el último commit, permitiendo cambiar el mensaje o incluir cambios adicionales.

9. **`git checkout -b <nombre_rama>`**  
   Crea una nueva rama y cambia a ella.

10. **`git checkout <nombre_rama>`**  
    Cambia a una rama existente.

11. **`git merge <nombre_rama>`**  
    Fusiona los cambios de una rama con la rama actual.

12. **`git add <archivo_con_conflicto>`**  
    Agrega un archivo que ha sido modificado para resolver un conflicto.

13. **`git commit -m "<mensaje>"`**  
    Completa un merge y documenta los cambios en caso de haber resuelto un conflicto.
