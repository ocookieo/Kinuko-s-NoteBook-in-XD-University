
性质上比较特殊，好像这种图，LaTeX独占？

既然这样的还是有必要学一下的

说是做笔记但是就是直接copy代码就是了。

但是说实在的，有一点tikz基础的都能通过代码直接学会怎么画。

# 代码部分

```latex
\usetikzlibrary {mindmap}
\tikz[large mindmap,concept color=red!50]
\node [concept] {Root concept}
child[grow=right] {node[concept] {Child concept}};
```
![[Pasted image 20231223232227.png]]

```latex
\usetikzlibrary {mindmap}
\begin{tikzpicture}[mindmap,concept color=blue!80]
\node [concept] {Root concept};
\node [extra concept] at (10,0) {extra concept};
\end{tikzpicture}
```
![[Pasted image 20231223232300.png]]

```latex
\usetikzlibrary {mindmap}
\tikz
[root concept/.append style={concept color=blue!80},
level 1 concept/.append style={concept color=red!50},
mindmap]
\node [concept] {Root concept}
child[grow=30] {node[concept] {child}}
child[grow=0 ] {node[concept] {child}};
```
![[Pasted image 20231223232508.png]]

```latex
\usetikzlibrary {mindmap}
\tikz[mindmap,concept color=blue!80]
\node [concept] {Root concept}
child[concept color=red,grow=30] {node[concept] {Child concept}}
child[concept color=orange,grow=0] {node[concept] {Child concept}};
In order to have a concept color which changes with the hierarchy level, a tiny
```
![[Pasted image 20231223232548.png]]

```latex
\usetikzlibrary {mindmap}
\tikz[mindmap,text=white,
root concept/.style={concept color=blue},
level 1 concept/.append style=
{every child/.style={concept color=blue!50}}]
\node [concept] {Root concept}
child[grow=30] {node[concept] {child}}
child[grow=0 ] {node[concept] {child}};
```
![[Pasted image 20231223232624.png]]\

```latex
\usetikzlibrary {backgrounds,mindmap}
\begin{tikzpicture}
[root concept/.append style={concept color=blue!20,minimum size=2cm},
level 1 concept/.append style={sibling angle=45},
mindmap]
\node [concept] {Root concept}
[clockwise from=45]
child { node[concept] (c1) {child}}
child { node[concept] (c2) {child}}
child { node[concept] (c3) {child}};
\begin{pgfonlayer}{background}
\draw [concept connection] (c1) edge (c2)
edge (c3)
(c2) edge (c3);
\end{pgfonlayer}
\end{tikzpicture}
```
![[Pasted image 20231223232721.png]]

```latex
\usetikzlibrary {mindmap}
\begin{tikzpicture}
\path[mindmap,concept color=black,text=white]
node[concept] {Computer Science}
[clockwise from=0]
% note that `sibling angle' can only be defined in
% `level 1 concept/.append style={}'
child[concept color=green!50!black] {
node[concept] {practical}
[clockwise from=90]
child { node[concept] {algorithms} }
child { node[concept] {data structures} }
child { node[concept] {pro\-gramming languages} }
child { node[concept] {software engineer\-ing} }
}
%note that the `concept color' is passed to the `child'(!)
child[concept color=blue] {
node[concept] {applied}
[clockwise from=-30]
child { node[concept] {databases} }
child { node[concept] {WWW} }
}
child[concept color=red] { node[concept] {technical} }
child[concept color=orange] { node[concept] {theoretical} };
\end{tikzpicture}
```
![[Pasted image 20231223233459.png]]

```latex
\usetikzlibrary {mindmap}
\begin{tikzpicture}
[mindmap,concept color=blue!80,
every annotation/.style={fill=red!20}]
\node [concept] (root) {Root concept};
\node [annotation,right] at (root.east)
{The root concept is, in general, the most important concept.};
\end{tikzpicture}
```
![[Pasted image 20231223233553.png]]

# 代码之外的一些可选项
## 大小调节
	 /tikz/small mindmap (style, no value)
This style includes the mindmap style, but additionally changes the default size of concepts, fonts and distances so that a medium-sized mindmap will fit on an A5 page (A5 pages are half as large as A4pages).

Mindmaps with small mindmap will also fit onto a standard frame of the beamer package

简单讲就是用于beamer很合适，个人觉得a4的论文用这个大小也很合适，正常的水文用默认的大小刚刚好，下面几个emmm，难堪大用，根本在a4之上放不下啊？
![[Pasted image 20231223235731.png]]

	/tikz/large mindmap (style, no value)
This style includes the mindmap style, but additionally changes the default size of concepts, fonts and
distances so that a medium-sized mindmap will fit on an A3 page (A3 pages are twice as large as A4
pages).

	/tikz/huge mindmap (style, no value)
This style causes concepts to be even bigger and it is best used with A2 paper and above.

```latex
% 开始连线
\path (theo) to[circle connection bar switch color=from (green!70!black) to (orange)] (prac);
\path (theo) to[circle connection bar switch color=from (green!70!black) to (blue!50!black)] (app);
\path (tec) to[circle connection bar switch color=from (red!70!black) to (blue!50!black)] (app);
```