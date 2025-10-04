# minishell: Intérprete de Comandos Unix en C

> Recreación de un intérprete de comandos simple (shell) al estilo de `bash`, desarrollado en C. Proyecto del Common Core de 42 Barcelona, enfocado en la gestión de procesos, la comunicación entre procesos (IPC) y la interacción profunda con el sistema operativo Unix.

---

### Stack Tecnológico y Conceptos Clave

![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)
![Unix API](https://img.shields.io/badge/Unix%20API-Linux/macOS-yellow?style=for-the-badge)
![Process Management](https://img.shields.io/badge/Process%20Management-fork()/execve()-orange?style=for-the-badge)
![IPC](https://img.shields.io/badge/IPC-Pipes/Redirections-lightgrey?style=for-the-badge)

---

### Características Principales

*   **Ejecución de Comandos:** Muestra un prompt, lee la entrada del usuario, la parsea y ejecuta los comandos correspondientes buscando en el `PATH` del sistema.
*   **Gestión de Procesos:** Utiliza `fork()` para crear procesos hijos y `execve()` para ejecutar los programas solicitados, mientras el proceso padre (`minishell`) espera a que terminen.
*   **Pipes (`|`):** Implementación de tuberías que permiten encadenar múltiples comandos, redirigiendo la salida estándar de un proceso a la entrada estándar del siguiente.
*   **Redirecciones de I/O (`<`, `>`, `<<`, `>>`):** Capacidad para redirigir la entrada y salida estándar de los comandos hacia y desde archivos, incluyendo `heredoc` para la entrada de texto multilínea.
*   **Manejo de Señales:** Gestiona señales como `Ctrl-C` (SIGINT) y `Ctrl-\` (SIGQUIT) de forma interactiva, asegurando que el shell no se cierre inesperadamente.
*   **Variables de Entorno:** Capaz de expandir variables de entorno (ej. `$USER`) y gestionar el estado de salida de los comandos (`$?`).
*   **Comandos Integrados (Builtins):** Implementación de comandos básicos como `echo`, `cd`, `pwd`, `export`, `unset` y `exit` que se ejecutan directamente en el proceso del shell.

---

### Mi Rol y Contribuciones

> Como parte de un equipo de dos, asumí un rol de liderazgo en el diseño de la arquitectura y fui el principal responsable de la implementación de los componentes clave, incluyendo el parser, la lógica de ejecución de procesos y el sistema de pipes y redirecciones.

---

### Cómo Compilar y Ejecutar

> Importante: Este proyecto fue desarrollado en Macos Catalina (bsd), no funcionara en sistemas linux sin extensivas modificaciones.

1.  **Compilar el proyecto:**
    ```bash
    make configure
    make
    ```
2.  **Ejecutar el shell:**
    ```bash
    ./minishell
    ```
