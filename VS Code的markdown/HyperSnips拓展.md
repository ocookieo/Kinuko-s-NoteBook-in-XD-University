# HyperSnips 自动扩展

原内容请看 知乎作者：一只方橙，GitHub：OrangeX4

这个大佬非常厉害啊，我之前写LaTeX时，用过texstudio，我自己也尝试配置过一些类似的宏定义和JavaScript脚本去加速我的书写，但是没想到的是已经有前人造过轮子了，有现成的轮子就直接用了吧。

这个大佬在知乎上详细地讲解了怎么用VS Code配置Markdown和LaTeX，以及他自己制作的很多插件，按照他的内容自己一点一点配置就好了。

我这里只是为了自己查阅他制作的HyperSnips for math的相关指令而做的笔记。

# 正文

相比于原来的 HyperSnips, 最大特点是, **它只会在数学环境 <!--$...$, $$...$$, \(...\) 和 \[...\]--> 中自动展开!**

$(1+2+3+4+5)$

**调节补全优先级**：打开设置，在搜索中输入editor.snippetSuggestions，然后将选项改为top，就可以了使得插件的优先级最高。

良心提示：占位符可以通过 Tab 键向后跳转和 Shift + Tab 向前跳转。
## 数学模式
```
lm  =>  $...$

dm  =>

$$
...
$$

dis  =>  \displaystyle
```
## 上下标
```
xsr  =>  x^{2}

xtp  =>  x^{...}

x1  =>  x_1

xii  =>  x_i

xsb  =>  x_{...}
```
## 分式
```
1/  =>  \frac{1}{...}

(1 + 2)/  =>  \frac{(1+2)}{...}

//  =>  \frac{...}{...}
```
## 根号
```
hsq  =>  \sqrt{...}
```
## 巨算符
```
sum  =>  \sum_{...}

prod  =>  \prod_{<n=1>}^{<\infty>} ...

int  =>  \int

dint  =>  \int_{<-\infty>}^{<\infty>} ... \mathrm{d}x
```
## 括号
```
@)  =>  \left( ... \right)

@]  =>  \left[ ... \right]

@}  =>  \left\{ ... \right\}

@<  =>  \left< ... \right>

set  =>  \{ ... \}
```
## aligned环境
```
ali  =>
\begin{aligned}
... \\
\end{aligned}
```
<!--
如果安装了 Better Markdown & Latex Shortcuts 插件，按下 Shift + Ctrl + Alt + C 可以将行公式转为 aligned 环境。
-->
## cases环境
```
case  =>
\begin{cases}
... \\
\end{cases}
```

## 矩阵环境
```
bmat2  =>  \begin{bmatrix} ... & ... \\ ... & ... \\\end{bmatrix}

vec2  =>  \begin{pmatrix} ... \\ ... \\\end{pmatrix}
```
## 零碎的重要语法
点乘 $\cdot$, 叉乘 $\times$, 异或 $\otimes$, 直和 $\oplus$, 加减 $\pm$, 复合 $\circ$.
小于等于 $\leq$, 大于等于 $\geq$, 不等 $\neq$, 恒等 $\equiv$, 约等 $\approx$, 等价 $\cong$, 相似 $\sim$, 相似等于 $\simeq$, 点等 $\doteq$.
逻辑与 $\land$, 逻辑或 $\lor$, 逻辑非 $\lnot$, 蕴涵 $\to$, 等价 $\leftrightarrow$.
因为 $\because$, 所以 $\therefore$, 存在 $\exist$, 任意 $\forall$.
左小箭头 $\leftarrow$, 右小箭头 $\rightarrow$, 左大箭头 $\Leftarrow$, 右大箭头 $\Rightarrow$, 右长箭头 $\xrightarrow[fgh]{abcde}$.
属于 $\in$, 包含于 $\subset$, 真包含于 $\subseteq$, 交 $\cap$, 并 $\cup$, 空集 $\empty$
短向量 $\vec{x}$, 长向量 $\overrightarrow{AB}$, 上横线 $\overline{p}$.
无限 $\infty$, 极限 $\lim$, 微分 ${\rm d}$, 偏导 $\partial$, 点求导 $\dot{y}$, 点二阶导 $\ddot{y}$, 变化量 $\Delta$, 梯度 $\nabla$.
横省略 $\cdots$, 竖省略 $\vdots$, 斜省略 $\ddots$.
常见函数 $\sin$, $\cos$, $\tan$, $\arcsin$, $\arccos$, $\arctan$, $\ln$, $\log$, $\exp$.

```
**  =>  \cdot
xx  =>  \times
<=  =>  \le     
!=  =>  \neq
==  =>  \equiv
~~  =>  \thickapprox
sim  =>  \sim
land  =>  \land
lor  =>  \lor       
bec  =>  \because
thr  =>  \therefore
EE  =>  \exists
AA  =>  \forall
inn  =>  \in
sse  =>  \subseteq
sqs  =>  \sqsubseteq
cap  =>  \cap
cup  =>  \cup
empty  =>  \empty
oo  =>  \infty
lim  =>  \lim_{<n> \to <\infty>}
dd  =>  \mathrm{d}
part  =>  \frac{\partial <V>}{\partial <x>}
Delta  =>  \Delta
nabla  =>  \nabla
...  =>  \cdots
sin  =>  \sin
```

特别重要的数集、向量、矩阵符号
```
RR  =>  \mathbb{R}
NN  =>   \mathbb{N}
txt  =>  \text{...}
xbar  =>  \bar{x}
xhat  =>  \hat{x}
xhvec  =>  \vec{x}
xhdot  =>  \dot{x}
Xbb  =>  \mathbb{X}
Xbs  =>  \boldsymbol{X}
Xbm  =>  \bm{X}
Xbf  =>  \mathbf{X}
Xsf  =>  \mathsf{X}
Xcal  =>  \mathcal{X}
Xfrak  =>  \mathfrak{X}
Xrm  =>  \mathrm{X}
```