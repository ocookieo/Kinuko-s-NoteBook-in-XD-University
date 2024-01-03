`\usepackage{tikz}`就可以使用tikz的大部分功能。
建议在实际画图的过程中积极使用macro简化我们的作图
# 环境
使用tikzpicture环境，或者是使用`\tikz`命令（适合画一个简单的符号）

# 综合应用
```
\usepackage{tikz}
\usepackage{siunitx}

\begin{figure}[ht]
		\centering
		\begin{tikzpicture}[scale=1.5]
			\newcommand\idegree{120}
			%左边的单位圆
			\begin{scope}[xshift=-2cm]
			\draw[->](-1.2,0)--(1.2,0);
			\draw[->](0,-1.2)--(0,1.2);
			\draw[thick](0,0)circle(1);
			\coordinate[label=P](P)at(\idegree:1);
			\draw(P)--(0,0);
			\coordinate[label=below:$P_0$] (P0) at(P|-0,0);
			\draw(P0)--(P);
			\fill[fill=gray,fill opacity=0.3](0,0)--(1,0)arc(0:120:1)--cycle;
			\filldraw[fill=gray,fill opacity=0.5](0,0)--(0.3,0)arc(0:120:0.3)--cycle;
			\node[right] at (60:0.3){\ang{\idegree}}; 
			\end{scope}
			%右边的函数图像
			\draw[thick,domain=0:rad(210)] plot(\x,{sin(\x r)});
			\draw[->](0,0)--({rad(210)},0);
			\draw[->](0,-1.2)--(0,1.2);
			\foreach \t in {0,90,180}{ 
				\draw({rad(\t)},-0.05)--({rad(\t)},0.05); 
				\node[below,outer sep=2pt,fill=white,font=\small] at ({rad(\t)},0) {\ang{\t}};
			}
			\foreach \y in {-1,1} {
				\draw (-0.05,\y)--(0.05,\y); 
			}
			\coordinate[label=above:$Q$] (Q) at ({rad(\idegree)},{sin(\idegree)});
			\coordinate[label=below:$Q_0$](Q0) at (Q|-0,0);
			\draw (Q)--(Q0);
			\draw[dashed] (P)--(Q);
	\end{tikzpicture}
	\end{figure}
```
![[Pasted image 20231206223614.png]]