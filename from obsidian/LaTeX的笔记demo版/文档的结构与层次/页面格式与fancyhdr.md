页面格式的设计也就是对页码、页眉、页脚等地方的设计。

页码的计数器是page，可以通过`\pagenumbering{roman}`设置页码的编号方式，并且这个命令会使计数器从1开始进行计数，建议在开始的时候**食用**。

book类型中`\frontmatter`命令就有控制页数编号的作用，而在report和article类中只能使用`\pagenumbering`

LaTeX提供了多种页面风格（page style）
>empty `没有页眉页脚`
>plain `没有页眉，页脚是居中的页码`
>headings `没有页脚，页眉是章节名称和页码`
>myheadings `没有页脚，页眉是页码和用户自定义的内容`

可以使用`\pagestyle{}`对整体进行页面风格的设置，也可以使用`\thispagestyle{}`命令对这面进行单独的页面风格设置。

在标准文档类型中book类使用headings风格，report和article类使用plain类
在ctex文档类默认使用headings风格。

LaTeX对一些必要的地方自动设置好了页面风格，在标题页（两种都是）使用empty风格禁止所有的页脚页眉，在不单独成页的`\maketitle`，单独成页的`\part`以及`\chapter`命令所在的页，使用的是plain风格。

myheading风格的页眉可以使用`\markright`和`\markboth`命令自定义
>单面文档(oneside)  `\markright{页眉文字}`
>双面文档(twoside)  `\markboth{左页眉}{右页眉}`

右页眉是奇数页面的页眉,左页眉是偶数页面的页眉。
因为双面文档装订号好之后刚好是右奇左偶

# fancyhdr宏包
fancyhdr提供了fancy选项（在文档那一行设置fancyhdr选项）的页面风格，把页面的页眉分成6个部分，上三下三。

这部分实在是正如其名的花哨，几乎难以在我可见的领域里用到，就不刻意去学习了。



