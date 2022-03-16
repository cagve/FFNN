# Beamer
## Presentación de euclides
* Objetivo: Ayudar a Euclides a crear una presentación para que pueda presentar
  su último hallazgo: Existen infinitos primos

### Pasos
1) Creamos un nuevo documento con la clase Beamer
```
\documentclass{beamer}

\begin{document}
\end{document}
```

2) Añadimos en el preámbulo algunos paquetes que vamos a necesitar
```
\usepackage[spanish]{babel}
\usepackage{graphicx}
\usepackage{hyperref}
\usepackage[utf8]{inputenc}
```
3) Creamos la primera diapositiva dentro del documento, que será la de la
   portada.
```
\begin{document}
	\begin{frame}
		\titlepage
	\end{frame}
\end{document}
```
4) Vamos a crear una segunda portada que incluya el índice. Para poner título a
   la diapositiva utilizamos `\frametitle{Resumen}`
```
\begin{frame}
	\tableofcontents
\end{frame}
```
5) Añadimos algunas secciones como de costumbre. IMP: FUERA DE LOS ENTORNOS
   FRAME
```
\section{Motivación}
\subsection{Punto de partida}
```
6) Creamos una diapositiva en la subsección punto de partida simple que incluya: 
	- Título
	- Definición de los números primos
```
\section{Motivación}
\subsection{Punto de partida}
\begin{frame} 
	\frametitle{¿Qué son los números primos?}
		En matemáticas, un número primo es un número natural mayor que 1 que tiene
		únicamente dos divisores positivos distintos: él mismo y el 1.
\end{frame}
```
7) Para darle algo de sentido podemos utilizar el entorno de definición y el
comando `\alert{}` para destacar alguna palabra.
```
\begin{frame} 
	\frametitle{¿Qué son los números primos?}
	\begin{definition}
		En matemáticas, un \alert{número primo} es un número natural mayor que 1 que tiene
		únicamente dos divisores positivos distintos: él mismo y el 1.
	\end{definition}
\end{frame}
```
Otros posibles entronos predefinidos son: theorem, lemma, proof, corollary o
example.

8) Añadamos ejemplos a la diapositiva de la definición. Para ello utilizaremos
el entorno example y el entorno itemize.
```
	\begin{example}
		\begin{itemize}
			\item El 2 es un número primo \pause
			\item El 3 es un número primo \pause
			\item El 4 no es un número primo 
		\end{itemize}
	\end{example}
```
Para que sea algo más dinámico utilizamos `\pause`, lo cual nos permite
mostrar uno a uno los diferentes items de la enumeración.

9) Los entornos definidos hasta ahora son entornos predefinidos por la clase
beamer. Pero puede ocurrir que queramos utilizar entornos con títulos concretos.
Para ello utilizamos: 

```
\begin{block}{Título}
\end{block}
```

Para hacer ahora. Debemos crear una sección nueva llamada 'Resultados'. En
esta sección debemos incluir 3 diapositivas. 
1. En la primera titulada: "Hay infinitos números primos" debemos incluir tres
   bloques con títulos diferentes, en cada bloque debe aparecer una propiedad de
   los números primos(wikipedia). Deben aparecer "pausadamente"
2. En la segunda diapositiva: Debe aparecer el teorema fundamental de la
   aritmética. Para ello debemos utilizar el entorno predefinido que convenga.
3. En la última incluye una foto de agradecimiento

