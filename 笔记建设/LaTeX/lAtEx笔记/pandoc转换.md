支持的种类很多，但是实际上我需要的种类其实就这么几种。
# .md转换.pdf
需要下载texlive，在使用前确定位置，比如D盘的根目录下`cd D:`。
得到的pdf文件，中文长句是无法自动换行的，因此这个转换意义不大。
```
pandoc demo.md -o demo.pdf --pdf-engine=xelatex -V mainfont='Microsoft YaHei'
```

# .tex转换.docx
```
pandoc demo.tex -o demo.docx
```