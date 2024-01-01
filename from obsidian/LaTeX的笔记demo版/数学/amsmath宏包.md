amsmath宏包基本是在使用到数学公式的文档里，都要使用，重要到我想给它写一个专门的笔记。

这些选项大多都是一些对数学算子上下角标位置的规定。

amsmath的一些宏包选项：
* centertags （默认）编号的公式占用多行时，编号垂直居中。
* tbtags 编号的公式分占多行时，编号在第一行左侧（leqno时）或最后一行的右侧时（reqno时）
* sumlimits （默认）显示公式中，巨算符等的上下标在正上正下方
* nosumlimits 显示公式中，求和号的上下标在角标的位置
* intlimits 类似sumlimits，作用于积分符号
* nointlimits （默认）与intlimits作用相反
* namelimits （默认）类似于sumlimits，作用于lim，max等文字算子
* nonamelimits 与namelimits相反

mathtools对amsmath宏包进行了拓展。

