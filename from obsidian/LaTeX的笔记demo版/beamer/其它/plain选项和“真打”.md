plain选项会抑制（suppress）（即不显示）顶部导航区（headline）、底部导航区（footline）和侧栏  （sidebar）。

创建一个简单的帧，使该帧带有不同的顶边和底部导航区。

当某帧含有一幅填满帧的图像时，该选项很有用。

举例：某帧含有一幅填满该帧大的图像：
```latex
\begin{frame}[plain]  
\begin{centering}  
\pgfimage[height=\paperheight]{somebigimagefile}  
\par  
\end{centering}  
\end{frame}
```

