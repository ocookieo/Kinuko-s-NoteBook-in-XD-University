``\alt<⟨叠层规则⟩>{⟨默认文本⟩}{⟨提醒文本⟩}<⟨叠层规则⟩> `` 

只能给定一个 ⟨overlay specification⟩。只在指定的幻灯片中显示 default text（默认的文本），在其它幻灯片中显示 alternative text（提醒文本）。

常常必须给定叠层规则。

举例：`\alt<2>{On Slide 2}{Not on slide 2.}  

举例：这是 `\uncover` 的定义（definition）：

`\newcommand{\uncover}{\alt{\@firstofone}{\makeinvisible}