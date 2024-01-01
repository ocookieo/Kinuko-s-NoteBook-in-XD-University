# pause命令的基本规则

如果在帧的某处放置 `\pause` 命令，只有 `\pause` 命令之前的文本会在该帧的第一张幻灯片中显示。

第二张幻灯片中的内容一直直到显示到第二个 `\pause `命令才出现，以此类推。

`\pause[⟨序号⟩]`如果给定了可选的 ⟨number⟩，则从第 ⟨number⟩  张幻灯片开始显示，会将计数器 beamerpauses 设置成该数字。该命令会在内部使用 `\onslide` 命令。建议不要这么使用，有专门干这个的命令，不要滥用pause命令。

该命令在 amsmath 环境如 align 内部无效，因为这些环境会做一些坏事。
# pause命令的作用范围

我们也可以在环境内部使用`\pause `命令，其作用持续到环境以后。
然而，在极端的情况下和在嵌套环境的深层放置 \pause 命令可能达不到预期的结果。

`\pause` 命令的作用持续到下一 `\pause`、`\onslide` 命令处，或持续到帧结束处。

这个复杂的例子将会告诉你pause命令具体是怎么回事。
```latex
\begin{frame}  
\begin{itemize}  
\item  
Shown from first slide on.  
\pause  
\item  
Shown from second slide on.  
\begin{itemize}  
\item  
Shown from second slide on.  
\pause  
\item  
Shown from third slide on.  
\end{itemize}  
\item  
Shown from third slide on.  
\pause  
\item  
Shown from fourth slide on.  
\end{itemize}  
Shown from fourth slide on.  
\begin{itemize}  
\onslide  
\item  
Shown from first slide on.  
\pause  
\item  
Shown from fifth slide on.  
\end{itemize}  
\end{frame}
```

