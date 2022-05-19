• 问题3-1，数字的三个内置类的名称是什么？ 数值型、整数型、复数型
• 问题3-2，用什么函数查找了因子的水平值？ level()
• 问题3-3，如何把字符串“6.283185”转换为数字？ as.numeric()
• 问题3-4，指出至少三个用于检视变量内容的函数。 mode()  class() store.mode()
• 问题3-5，如何删除用户工作区中的所有变量？rm(list=ls())

• 练习3-1，查找以下值Inf、NA、NaN和""的类、类型、模式及存储模式。
class(Inf)
class(NA)
class(NaN)
mode(Inf)
mode(NA)
mode(NaN)
storage.mode(Inf)
storage.mode(NA)
storage.mode(NaN)

• 练习3-2，随机从“dog”、“cat”、“dolphin”、 “hamster”和“goldfish”中以相等的概率生成100个宠物名。显示所得变量的前几个值，并计算每种宠物的数量。 
sam1 <- sample(c('dogcat','dolphin','hamster','goldfish'),100,replace=TRUE)
fac2 <- factor(sam)
summary(fac)      

• 练习3-3，创建一些以水果命名的变量。列出用户工作区中所有包含字母“a”的变量。
fruit <- c('lemon','litchi','litchirind','longan','longanpulp','loguat','mandarine','mango')
ls(pattern='a') 

问题4-1，你将如何创建一个包含值0、0.25、0.5、0.75、 1和1.25的向量？ vector1 <- seq(from=0,to=1.25,by=0.25)
问题4-2，描述两种命名向量元素的方式。  直接命名   names()
问题4-3，向量索引中的四种类型是什么？  数字 字符串 逻辑 单个数字 
问题4-4，一个3×4×6的数组的长度是多少？  72
问题4-5，你会用哪个操作符来执行两个矩阵的内积？ %*%  crosspord()

练习4-1，第n个三角形数表示为n * (n + 1) / 2。创建一个包含前50个三角形数的序列。R有一个内置常数letters，它包含小写的罗马字母。使用前15个英文字母来给你刚刚创建的向量命名。选择命名为元音的三角数。 
tri <- c()
for (i in c(1:50)){
  tri[i] <- i*(i+1)/2
}
names(tri) <- letters(1:15)
tri[c('a','e','i','o')]、

• 练习4-2，diag函数有几种用途，其中之一是以输入向量作为对角线来创建一个方阵。使用序列10到0到11（即11,10,...,1,0,1,...,11）创建一个21×21的矩阵。
diag(abs(seq(-10,10)))

练习5-1，创建一个列表变量，它的第一个元素包含所有从0到9的平方数，第二个元素为10至19之内的所有平方数，依此类推，最后一个元素为90到99之内的平方数。不是平方数的元素也应该被包含在内。 • 
x <- 0:99 
sqrt_x <- sqrt(x) 
is_square_number <- sqrt_x == floor(sqrt_x) 
square_numbers <- x[is_square_number] 
groups <- cut(square_numbers, seq.int(min(x), max(x), 10), include.lowest = TRUE, right = FALSE )
split(square_numbers, groups)

练习5-2，R有几个内置的数据集，其中包括由安德森和费舍尔在20世纪30年代收集和分析的iris（指鸢尾花，而不是虹膜）数据。输入iris即可看到数据集。创建一个新的数据框，它由iris数据集的数值列组成；计算各列的平均值。
iris_numeric <- iris[, 1:5] #取1：5的子集
colMeans(iris_numeric)

练习5-3，beaver1和beaver2数据集包含两个海狸的体温数据。为beaver1数据集添加一列名为id的列，其值全部为1。同样，也为beaver2添加一个id列，值全为2。垂直拼接两个数据框，并且找到所有活跃着的海狸的子集。
beaver1$id <- 1 
beaver2$id <- 2 
both_beavers <- rbind(beaver1, beaver2) #求并集
subset(both_beavers, as.logical(activ))
