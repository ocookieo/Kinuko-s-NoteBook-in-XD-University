# visible命令

 \visible<⟨叠层规则⟩>{⟨文本⟩}  

该命令的所作所为大部分和 `\uncover` 相同。不同之处是不会显示文本（show text），从不以透明的方式显示，根本就不显示。

因此，透明设置（transparency settings）对该命令无效  

举例：``\visible<2->{Text shown from slide 2 on.}``  

# invisible命令

\invisible<⟨叠层规则⟩>{⟨文本⟩}  

该命令的效果和 `\visible` 相反。

举例：``\invisible<-2>{Text shown from slide 3 on.``