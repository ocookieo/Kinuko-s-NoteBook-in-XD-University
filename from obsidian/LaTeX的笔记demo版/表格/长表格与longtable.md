# 需要的使用情况

在表格内容不超过一页的情况下，推荐使用浮动体环境就好。
但是**表格内容超过一页**，就必须进行表格的分拆，即使用长表格。

# longtable语法
```latex
\begin{longtable}[水平对齐]{列格式说明}
表头，\multicolumn{2}{l}{（续表）}
\endhead
第一页表头，常常使用\caption{}
\endfirsthead
表尾，\multicolumn{3}{c}{\itshape 接下一页表格}
\endfoot
最后一页表尾，很少在这里写东西
\endlastfoot
表项 & 表项 & ……\\
表项 & 表项 & ……\\
表项 & 表项 & ……\\
\end{longtable}
```

## 使用说明
简单用法就是直接使用，不加任何end命令。
水平对齐可选用c、l、r 默认居中对齐，但是和直接使用c略有不同。
***
# ltxtable宏包（文件分开）
ltxtable宏包是longtable和tabularx的结合，使得longtable同时可以延伸和跨页。

这个用法比较特别：需要在一个单独的tex文件编写longtable环境的表格，然后在实际的tex文件里使用命令`\LTXtable{宽度}{文件名}`插入实际的表格。
```latex
% 实际tex文件，也叫主文件
\usepackage{ltxtable}
% 正文区
\LTXtable{\textwidth}{mytable}
```

```latex
\begin{longtable}{|c|X|c|}

\end{longtable}
```


# tabu宏包（仍需要longtable宏包）

tabu宏包提供的longtabu环境。

这个从效果上其实和VerbtimOut环境差不多，但是可以在正文区直接使用了，而且跳过了longtable环境的手动输入，一步到位。
```latex
% 导言区
\usepackage{longtable,tabu}
% 正文区
\begin{longtabu}to 0.5\textwidth{|X|X|}

\end{longtabu}
```

