# array宏包增加了几种列格式

* m{宽}产生固定的宽度，会自动换行，类似垂直盒子
* b{宽}垂直方向与最后一行对齐
* >{内容}把内容插入后面一列
* <{内容}把内容插入前面一列
* !{内容}作为表格线处理

还提供了`\newcolumntype`命令，可以自定义列格式。
## 使用示范
```latex
	\begin{tabular}{>{\bfseries}c|>{\itshape}c>{$}c<{$}}
		\hline
		姓名 & 得分 & \multicolumn{1}{c}{额外加分}\\ \hline
		张三 & 85 & +7\\ \hline
		李四 & 82 & 0\\ \hline
	\end{tabular}
```

**![[Pasted image 20231211221951.png]]**

```latex
	\begin{tabular}{|>{$}c<{$}|m{10em}|>{\centering\arraybackslash}c|}
		\hline
		\pi & 希腊字母，多用于表示圆周率，也常常用作变量，表示圆周率时多使用直立体。%
		 & 常用\\\hline
		\aleph & 希伯来字母的第一个，在数学中通常用来表示特殊集合的基数。 & 不常用 \\\hline 
	\end{tabular}
```

![[Pasted image 20231211222716.png]]

```latex
	\begin{tabular}{c!{$\Rightarrow$}c}
		邓子康 & 天才\\
		邓子康 & 举世无双\\
```
![[5c2fa1fb74c169cc6737b966470dd68.png]]

# 后续的修改

横行的字体等修改，可以使用tabu宏包的tabu环境，在环境中使用`\rowfont`可以对下一行的字体做一些设置。