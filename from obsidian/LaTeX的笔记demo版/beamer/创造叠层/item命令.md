``\item<⟨alert specification⟩>[⟨item label⟩]<⟨alert specification⟩>``

这个中文意思不好理解，放一个英文的。

`\item<⟨提醒规则⟩>[⟨条目标签⟩]<⟨提醒规则)>`

给出一个 ⟨alert specification⟩的情况：
```latex
\begin{frame}  
\begin{itemize}  
\item<1-> First point, shown on all slides.  
\item<2-> Second point, shown on slide 2 and later.  
\item<2-> Third point, also shown on slide 2 and later.  
\item<3-> Fourth point, shown on slide 3.  
\end{itemize}  
\end{frame}
```

```latex
\begin{frame}  
\begin{enumerate}  
\item<3-| alert@3>[0.] A zeroth point, shown at the very end.  
\item<1-| alert@1> The first and main point.  
\item<2-| alert@2> The second point.  
\end{enumerate}  
\end{frame}
```

![[Pasted image 20231219111849.png]]
![[Pasted image 20231219111905.png]]
![[Pasted image 20231219111834.png]]
