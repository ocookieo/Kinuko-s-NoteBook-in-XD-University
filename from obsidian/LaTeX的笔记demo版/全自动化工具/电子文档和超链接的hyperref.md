# hyperref宏包

ctex类型的文档或宏包类，可以添加hyperref选项，ctex宏包会自动根据编码和编译方式选择合适的选项，避免出现乱码问题。
```latex
\documentclass[hyperref,UTF8]{ctexart}
```
应用宏包后，就会在pdf处的目录和交叉引用产生超链接。
需要注意的是这个也是需要编译两遍。

## 充分使用hyperref宏包

可以给hyperref设置许多宏包选项来控制其行为，相比于直接在`\usepackage[]{hyperref}`里设置，更加推荐用`\hypersetup{}`单独设置。

hyperref的大多数选项都是使用更加现代化的 options=value 的方式进行设置，如果是布尔类型的真假值选项（值一般为true或flase），通常可以省略真的值。

这里个人推荐：如果没有特殊需求的话，建议只把colorlinks选项打开，不打开这个选项的超链接真的很丑，很难看。
![[11fa54e2d196fd587e47306848cf3a1.jpg]]

## hyperref的超链接

使用命令`\url`后面接一个网址就可生成一个超链接，如果不需要链接只需要显示网址的话，`\nolinkurl`

`href{URL地址}{名字}`可以把地址换成名字

`\hyperref[标签]{名字}`产生指向标签的超链接，这个标签就是交叉引用时产生的那个标签。

`\hypertarget{名称}{文字}`和`\hyperlink{名称}{文字}`，简单来说，一个是插旗子，一个是指向旗子，两个命令的名称一一对应，文字会正常显示，只是在`\hyperlink`命令那里会产生一个指向`\hypertarget`的超链接。

```latex
\phantomsection%自动产生一个超链接点，通常就是这么使用，为手动添加的目录项指定链接位置
\addcontentsline{toc}{section}{习题}
\section*{好多好多的习题}
```

