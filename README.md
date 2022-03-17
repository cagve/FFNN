# Filosofía y nuevas tecnologías - Curso 21/22
## Índice
<!-- vim-markdown-toc GFM -->

* [Instalación](#instalación)
	* [Miktex](#miktex)
	* [Texmaker](#texmaker)
* [Creación primera plantilla](#creación-primera-plantilla)
* [Secciones](#secciones)
* [Imágenes](#imágenes)
	* [Entorno flotante](#entorno-flotante)
	* [Texto alrededor de imagen](#texto-alrededor-de-imagen)
* [Referencias cruzadas](#referencias-cruzadas)
* [Bibliografía](#bibliografía)
	* [Natbib](#natbib)
	* [Citar APA](#citar-apa)
		* [Natbib](#natbib-1)
		* [Apacite](#apacite)
	* [Citar Chicago](#citar-chicago)
* [Presentaciones](#presentaciones)
	* [Frame](#frame)
	* [Bloques](#bloques)
	* [Temas y estilo](#temas-y-estilo)
	* [Estilos genéricos](#estilos-genéricos)
* [Portada](#portada)
	* [Comandos útiles](#comandos-útiles)
	* [Colores](#colores)

<!-- vim-markdown-toc -->
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

### Entorno flotante
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

## Referencias cruzadas
La **referencia cruzada** se utiliza en un texto para hacer alusi ́on a una parte del texto, a
una tabla, o a una gráfica que se encuentra en otra parte del documento. Dos comandos

```
\label{} ------------> Crea la referencia

\ref{}   ------------> Llama a la referencia
```

**Ejemplo 1**
* Creamos un documento con dos secciones:
1. Introducción
2. Lógica modal
3. Lógica epistémica

* Creamos las etiquetas para cada sección
```
\label{sec:intro}
\label{sec:modal}
\label{sec:epistémica}
```
* Llamamos a las secciones en la primera sección

Podemos llamar a figuras, tablas, ecuaciones, enumeraciones, etc.

## Bibliografía
BIBTEX > Herramienta hermana de LATEX para la gestión de bibliografía.

* Tipo de archivo: .bib
* Sintaxis: 
  
```
@<tipo-de-documento>{<key>,
	<entrada>={<nombre>},
	<entrada>={<nombre>},
	<entrada>={<nombre>},
	<entrada>={<nombre>},
	<entrada>={<nombre>}
}
```
	* Tipos de documentos:
		* article
		* book
		* phdthesis
	* Entradas: 
		* title: 
		* author:
		* edition: 
		* pages: 
		* address: 
		* publisher: 
		* year: 
* Bibtex en latex >	  
	* \bibliographystyle{unsrt} 
	* \bibliography{mibiblio} 

### Natbib
Este paquete nos proporciona un manejo aún más preciso sobre la bibliografía.
Añade tres nuevos estilos de bibliografía:
1. plainnat
2. abbrvnat
3. unsrtnat

Añade diferentes estilos de cita
1. `\citet{}` > Cita textual
2. `\citep{}` > Cita paréntesis
Si queremos añadir información adicional podemos hacerlo entre corchetes. `\citet[chap. 2]{Descartes2022metodo}`.
Otros usos que podemos darle son:
1. `\citeauthor{}`
2. `\citeyear`

### Citar APA
#### Natbib
1. Descargamos el archivo bst en nuestra carpeta
2. `\bibliographystyle{apa}`

#### Apacite
1. Cambiamos el paquete natbib por apacite.
2. `\usepackage[natbibapa]{apacite}`
2. `\bibliographystyle{apacite}`


### Citar Chicago
1. Utilizamos el paquete `\usepackage{chicago}`
2. `\bibliographystyle{chicago}`


## Presentaciones
Para poder crear presentaciones lo primero que debemos hacer es modificar el tipo de documento para que sea tipo `beamer`.
```
\documentclass{beamer}

\usepackage[spanish]{babel}
\usepackage{graphicx}
\usepackage{hyperref}
\usepackage[utf8]{inputenc}

\begin{document}

\end{document}
```
### Frame
Para crear nuevas diapositivas se debe utilizar el entorno `frame`. Toda la
información que queramos incluir se debe realizar dentro de cada frame.
```
\begin{frame}
	\titlepage
\end{frame}
```

### Bloques
En beamer podemos generar bloques de texto. Beamer incorpora algunos entornos
por defecto como: _theorem_, _lemma_, _proof_, _corollary_ o _example_. De esta
forma si queremos incluir un nuevo ejemplo lo pondremos de la siguiente forma:
```
\begin{example}
	Esto es un ejemplo
\end{example}
```
Además de estos, podemos utilizar bloques de textos genéricos con el entorno `block`. IMP. Necesitan tener un título.
```
\begin{block}{Título del bloque}
	Esto es un bloque de texto.
\end{block}
```
### Temas y estilo
Para consultar los diferentes temas ir a [galería](https://deic.uab.cat/~iblanes/beamer_gallery/) o a [galeria2](https://hartwork.org/beamer-theme-matrix/)
Los comandos que podemos utilizar son:

| Comando            |
|--------------------|
| `\usetheme{}`      |
| `\usecolortheme{}` |
| `\usefonttheme{}`  |

### Estilos genéricos
* **Temas antiguos** bars, boxes, classic, default, lined, plain, shadow,
sidebar, sidebardark, sidebardarktab, sidebartab, split, tree,
treebars
* **Temas con navegación**: default, boxes, Bergen, Madrid,
Pittsburgh, Rochester
* **Temas en árbol:** Antibes, JuanLesPins, Montpellier.
* **Temas con TOC:** Berkeley, PaloAlto, Goettingen, Marburg,
Hannover
* **Temas con mini navegación:** Berlin, Ilmenau, Dresden, Darmstadt,
Frankfurt, Singapore, Szeged
* **Temas con títulos y subtítulos:** Copenhagen, Luebeck, Malmoe,
Warsaw

## Portada 
Hemos visto como crear una portada a partir de información genérica, sin
embargo, pueden darse casos en los que queramos hacer algo más complejo. Para
ello podemos utilizar el entorno `titlepage`. Esto nos genera un entorno
flotante en toda la página. Dentro de ella podemos introducir la información
que queramos. Para ello debemos generar bloques de texto para cada "párrafo".

### Comandos útiles

| Comando                       | Función                                              |
|-------------------------------|------------------------------------------------------|
| `\vspace{2cm}`                | Genera un espacio vertical de 2cm                    |
| `\vfill`                      | Genera un bloque en blanco hasta el siguiente bloque |
| `\rule{<longitud>}{<grosor>}` | Genera una línea con una longitud y un grosor.       |
| `\hrule`                      | Genera una línea horizontal.       |

### Colores
Para poner la página de un color debemos utilizar el paquete
`\usepackage{xcolor}`. Podemos utilizar los colores que vienen predefinidos en
el paquete ([véase](https://en.wikibooks.org/wiki/LaTeX/Colors)). Sino, podemos definir
colores utilizamos el comando
`\definecolor{<nombre>}{<tipo-de-color}{<valores>}`. 

| Comando            | Función                                                                      |
|--------------------|------------------------------------------------------------------------------|
| `\pagecolor{blue}` | Cambia el color de fondo de la página                                        |
| `\color{white}`    | Cambia el color del texto. Importante, el texto debe estar incluido entre {} |

Imaginemos que tenemos el siguiente texto y queremos colorear la primera frase.
Lo que debemos hacer es englobar entre llaves todo lo que queremos colorear.
Después añadimos el comando `\color{red}` dentro del bloque de texto.

```
{\color{red} LaTeX is a high-quality typesetting system}; it includes features designed for
the production of technical and scientific documentation. LaTeX is the de facto
standard for the communication and publication of scientific documents. LaTeX
is available as free software.
```
