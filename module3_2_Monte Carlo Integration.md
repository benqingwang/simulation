<h1>Monte Carlo Integration</h1>

我们想求积分但是不用积分方程: $I = \int_{a}^{b} g(x) \ dx$
如何用excel这样的工具，通过simulation来做到呢？我们可以利用excel产生0,1之间随机数的功能。下面就介绍如何做

<h2>把一般积分问题等价转换为在(0,1)上积分</h2>
我们得到的积分问题的X的范围是(a,b)，我们可以利用换元积分把X换为U，U是一个(0,1)之间的variable.
换的方法显而易见: 因为X是(a,b)，所以（(a-a)/(b-a), (b-a)/(b-a)就是 (0,1)，所以如果我让U = (X-a)/(b-a)，U就是(0,1)的范围。
所以 $X=(b-a)U+a$ 
因此有: 

$$
I = \int_{a}^{b} g(x) \ dx = \int_{0}^{1} g((b-a)u+a) \ d((b-a)u+a) = (b-a) \int_{0}^{1} g\left(a + (b-a)u\right) \ du
$$

<h2>创建一个estimator来估计(0,1)上的积分</h2>
我们现在创建一个estimator, 这个符号含义就是用n个observation来估计I的estimator, 就是抽n个(0,1)上的随机数，然后带入公式 $g(a+(b-a)u)$ 然后得出一个值，把n个结果平均就是我们的估计。

$$
\bar{I}_ n \equiv \frac{1}{n} \sum_{i=1}^{n} I_i = \frac{b - a}{n} \sum_{i=1}^{n} g(a + (b - a) U_i)
$$

我解释一下为什么这么做是可以得到好的估计：可以想象我们把(0,1)分成n份，然后以每份的高度也即是g(U)作为高，每份的长度也就是1/n作为宽度，得到一个长方形的面积。然后把这些小长方形加起来就是积分的值，当然n要比较大。那我们这里不是平均分n份，而是随机产生n个(0,1)之间的数字，但是我们可以想象，当n很大的时候，这和平均分n份是一样的效果，因为Excel这个产生随机数的功能就是根据(0,1)之间的uniformed distribution。

老师的解释是：根据Law of Large Numbers, 如果一个estimator能够渐近地无偏并且variance goes to zero，上面的方法就是可行的。那么怎么证明mean是无偏并且variance goes to zero呢？
简单就是求E(I_estimate) = I. 然后老师口口声声说Var(I_estimate) =0。因为公式写起来太麻烦和浪费时间，可以直接查module 3 page 14. 

<h2>进一步求confidence interval</h2>
简单说就是confidence interval就是estimator的mean加减z value乘以estimator的标准样本方差，可以直接查module 3 page 15. 

<h2>简单例子</h2>
老师这里用了一个简单例子来说明这样的估计是可以的。

$$
比如我们要求 \sin(\pi x)在（0，1）上的积分。这里我们用了简单的例子，range本来就是(0,1)
$$ 

$$
I = \int_{0}^{1} \sin(\pi x) \ dx
$$ 

如果我直接用积分计算是这样的

$$
I = \int_{0}^{1} \sin(\pi x) \ dx = -\frac{1}{\pi} (cos(\pi)x)\vert_{1}^{0} = -\frac{1}{\pi} (-1-(1))=\frac{2}{\pi} \approx 0.6366
$$ 

如果我用上面的方法就是可以抽n个随机的(0,1)之间的数，带入$sin(\pi x)$，然后计算平均值。
![image](https://github.com/benqingwang/simulation/assets/158376214/b9f89b85-2076-40ef-bf04-212542ef905e)
可见当我们的sample比较多之后，这个值稳定在6.3左右，和我用积分得到的结果一样。

我下面用老师给的4个数来展示具体的计算estimate和confidence interval的过程
![image](https://github.com/benqingwang/simulation/assets/158376214/b361b823-6ef8-4fd3-83d5-f590a6cb4c78)







