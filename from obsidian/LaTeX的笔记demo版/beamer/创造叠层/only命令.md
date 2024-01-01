``\only<⟨overlay specification⟩>{⟨text⟩}<⟨overlay specification⟩>``  
即：  
``\only<⟨叠层规则⟩>{⟨文本⟩}<⟨叠层规则⟩>``  

如果给定了 ⟨overlay specification⟩（虽然只给定了一个），⟨text⟩ 将被插入到指定的幻灯片中。在其它幻灯片中则会扔掉（throw away）这些文本。特别之处，它不会占用空间。

\only 需要通过叠层规则来指定内容排印的子幻灯片编号，没有显示的内容将不会占  
位。  

因为叠层规则还可以在文本后使用，所以还可以达成这样的效果。
使用范例：
```latex
\newcommand{\myblue}{\only{\color{blue}}}  
\begin{frame}  
\myblue<2> This text is blue only on slide 2.  
\end{frame}
```