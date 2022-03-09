# Filosofía y nuevas tecnologías - Curso 21/22

## Instalación 
### Miktex
La distribución que vamos a utilizar en clase es Miktex porque integra la
mayoría de los paquetes  que necesitaremos durante el curso. 
1. En [MikTex](https://miktex.org/download) descargamos la versión que encaje con nuestro sistema operativo.
2. Para una guía detallada de la instalación consúltese la [guía de instalación](https://miktex.org/howto/install-miktex)

### Texmaker
Para escribir necesitaremos un editor de texto, no obstante, es buena opción
contemplar utilizar un IDE que nos permite integrar diferentes tareas;
compilar, editar, etc... Se puede descargar en la página oficial de
[Texmaker](https://www.xm1math.net/texmaker/download.html)

## Creación primera plantilla
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
## Secciones


| Comando         |
|-----------------|
| `\chapter{}`    |
| `\section{}`    |
| `\subsection{}`    |
| `\subsubsection{}`    | 
| `\paragraph{}`    | 
| `\subparagraph{}`    | 

Para imprimir el índice utilizamos `\tableofcontents`. Además, para que los
títulos salgan en español debemos añadir un paquete nuevo a la plantilla >
`\usepackage[spanish]{babel}`

## Imágenes

Necesitamos el paquete `\usepackage{graphicx}`. El comando que utilizamos es
`\includegraphics[<opciones>]{<path>}`, no obstante, la manera más adecuada es
utilizando entornos flotantes. Entre corchetes podemos utilizar alguna de estas opciones. Para ver en detalle todas las posibilidades consultar https://ctan.javinator9889.com/macros/latex/required/graphics/grfguide.pdf

|Parámetro | ¿Qué hace?|
|----------|-----------|
|angle | Rota la imagen.|
|width | Ajusta la imagen al ancho.|
|height| Ajusta la imagen a la altura.|
|scale | Escala la imagen al tamaño.|

#### Entorno flotante
```
\begin[<options>]{figure} 
\centering
\includegraphics{foto.jpg}
\caption{Primera foto}
\end{figure}

```
|Parámetro | ¿Qué hace?|
|----------|-----------|
|h| Le indicamos que ponga la imagen aquı́.|
|t| Le indicamos que lo ponga en la parte superior de la página.|
|b| Le indicamos que lo ponga en la parte inferior de la página.|
|p| Le indicamos que coloque los objetos flotantes en una página.|
|!| Le indicamos que ignore las reglas internas de posicionamiento.|

Posicionar la imagen dentro del entorno flotante

|Parámetro | ¿Qué hace?|
|----------|-----------|
|`\centering`| Centrado.|
|`\raggedleft`| Derecha.|
|`\raggedright`| Izquierda.|

* `\caption{}` > Título a la imagen

### Texto alrededor de imagen
Para poder incluir texto alrededor de una imagen necesitamos incluir el paquete
`\usepackage{wrapfig}` y crear un entorno flotante de tipo wrapfigure. Para
ello utilizamos 

```
\begin{wrapfigure}[<nlineas>]{<pos>}{<ancho>}

\end{wrapfigure}
```





