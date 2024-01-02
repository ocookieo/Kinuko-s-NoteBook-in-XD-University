
```latex
\usepackage{array,tabularx}
```
# tabular和tabularx的区别
tabular环境的宽度就是各项表项相加得到的自然宽度，会浮动。
tabularx环境就是一种固定宽度的表格，相比于tabular多了一个参数。
```
\usepackage{tabularx} % 需要使用tabularx宏包。
\begin{tabularx}{宽度}[垂直对齐]{|c|X|X|X|}
	% 宽度用\textwidth表示铺满正文区域，你不用这个命令就像羊肉没有孜然
	% 环境提供了一个新的可使用的列格式说明符X。
	% 会自动延伸表项，默认左对齐，会自动换行
\end{tabularx}
```

## 改变tabularx的对齐方式
### 怎么改？

先说结论：
```latex
\newcolumntype{Y}{>{\cnetering\arraybackslash}X}
```

来把原来的左对齐改变成右对齐。

### 那为什么要这样改？

tabularx宏包依托array宏包，可以使用array宏包的机制设置对齐方式。

由于`\centering`会改变`\\`命令的定义，需要在对其命令后面加上`\arraybackslash`命令恢复。
