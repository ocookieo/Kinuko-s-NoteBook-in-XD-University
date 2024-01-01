
```latex
\usepackage{booktabs}
```

# 线宽的设置

以下的命令都可以带上一个参数调整它们的线宽。
* `\toprule` 顶部粗线 0.08em
* `\midrule` 中间的细分割线 0.05em
* `\bottomrule` 底部的粗线 0.08em
* `\cmidrule` 比中间的分割线更细，可以指定横线的行 0.03em


以下是可以调整的命令。
* `\heavyrulewidth`
* `\lightrulewidth`
* `cmidrulewidth`
* `aboverulesep`
* `belowrulesep`
* `\abovetopsep`和`\belowbottomsep`

# cmidrule命令的使用方法
`\cmidrule{lr}{2-3}`语法类似`\cline{1-5}`， l 和 r 参数表示间距的表格线可以向内缩减一定的距离， l{距离} 和 r{距离} 也可以使用。

要使用cmidrule画出双线需要使用如下操作：
`\cmidrule{lr}{2-3}\morecmidrules\cmidrule{lr}{2-3}`
通过这种方式可以产生合适的线距。

