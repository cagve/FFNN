# Filosofía y nuevas tecnologías - Curso 21/22
## Clase - Miércoles 23/02
### Objetivos
* Instalar entorno básico: Miktex + Texmaker
* Crear una plantilla básica

### Instalación 
#### Miktex
La distribución que vamos a utilizar en clase es Miktex porque integra la
mayoría de los paquetes  que necesitaremos durante el curso. 
1. En [MikTex](https://miktex.org/download) descargamos la versión que encaje con nuestro sistema operativo.
2. Para una guía detallada de la instalación consúltese la [guía de instalación](https://miktex.org/howto/install-miktex)

#### Texmaker
Para escribir necesitaremos un editor de texto, no obstante, es buena opción
contemplar utilizar un IDE que nos permite integrar diferentes tareas;
compilar, editar, etc... Se puede descargar en la página oficial de
[Texmaker](https://www.xm1math.net/texmaker/download.html)

### Plantilla
La plantilla básica constará de paquetes básicos, de una portada y de
diferentes secciones. Para ello es fundamental distinguir las dos partes que
conforman cualquier documento LaTeX.
* Preámbulo: Todo documento debe empezar con el comando
  `\documentclass{article}`. A partir de aquí, en el preámbulo incluiremos todo
  lo relativo a la configuración del documento. En el caso de la plantilla
  incluiremos tanto los paquetes como el título: 
```
\documentclass[a4paper]{article}
\usepackage[utf8]{inputenc} %Permite escribir símbolos utf8

\title{Plantilla}
\author{Carlos Aguilera Ventura}
\date{\today}
```
* Cuerpo:  En esta parte vamos a escribir todo el texto que queramos que
  aparezca en el documento final. Para ello abrimos el entorno `document` que
  contendrá todo el cuerpo. Para imprimir el título utilizamos `\maketitle`
```
\begin{document}
\maketitle \newpage
Hola mundo! Esto es una plantilla

\end{document}
```

## Tabla de comandos

| Comando         | ¿Qué hace?           |
|-----------------|----------------------|
| `\\`,`\newline` | Nuevo salto de línea |
| `\maketitle`    | Imprime el título    |

