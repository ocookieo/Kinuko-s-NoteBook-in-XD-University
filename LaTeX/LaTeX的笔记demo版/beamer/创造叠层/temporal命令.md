\temporal<⟨叠层规则⟩>{⟨幻灯片前文本⟩}{⟨默认文本⟩}{⟨幻灯片后文本⟩}  

该命令据当前幻灯片：是暂时处于指定的幻灯片之前、是指定的幻灯片之一、紧跟在指定的幻灯片之后这三种不同的情况而在三种不同的文本之间选择。

如果 ⟨overlay specification⟩ 不是一个区间（interval）
也就是说，如果它有一个“洞（hole）”，则该“洞（hole）”被认为是指定幻灯片之前的一部分。

举例：
```latex
\temporal<3-4>{Shown on 1, 2}{Shown on 3, 4}{Shown 5, 6, 7, ...}  
\temporal<3,5>{Shown on 1, 2, 4}{Shown on 3, 5}{Shown 6, 7, 8, ...}  
```

下面的例子是` \temporal `命令的适应情形：