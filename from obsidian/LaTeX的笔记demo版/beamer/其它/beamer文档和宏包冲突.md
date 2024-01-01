# 产生错误

beamer是一个特殊的文档类型，它事先已经使用了一些宏包，使用usepackage命令调用那些宏包会产生错误。

调用文档beamer.cls文件时，amsfonts、amsmath、amssymb、amsthm、enumerate、geometry、graphics、graphicx、hyperref、ifpdf、keyval、xcolor、xxcolor、url等等

# 参数传递

例如：beamer已经调用了xcolor宏包命令，所以就不能使用`\usepackage[table]{xcolor}`

我们应该使用的是`\documentclass[xcolor=table]{beamer}`

这样就将原本想要使用的参数通过beamer传递给宏包。
