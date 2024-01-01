``\label<⟨叠层规则⟩>{⟨标签名⟩}  

如果给定了 ⟨overlay specification⟩，那么只在指定的幻灯片中插入标签（label）。

在多张幻灯片中插入一个标签将显示“多标签（multiple labels）”警告。然而，如果没有给定叠层规则，则会自动将规则设为“1”，因此只在第一张幻灯片中插入标签。这是期望的行为，因为这对于插入了标签的幻灯片无影响，但是如果不是第一张的话，需要设置叠层规则，以避免多标签警告。

```latex
\begin{frame}  
\begin{align}  
a &= b + c \label{first}\\ % no specification neede
c &= d + e \label{second}\\% no specification needed  
\end{align}  
Blah blah, \uncover<2>{more blah blah.}  
\only<3>{Specification is needed now.\label<3>{mylabel}}  
\end{frame}
```