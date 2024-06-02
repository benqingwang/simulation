<h1>Monte Carlo Integration</h1>

我们想求积分但是不用积分方程: $I = \int_{a}^{b} g(x) \ dx$
如何用excel这样的工具，通过simulation来做到呢？我们可以利用excel产生0,1之间随机数的功能。下面就介绍如何做

<h2>把积分等价转换为在(0,1)上积分</h2>
我们得到的积分问题的X的范围是(a,b)，我们可以利用换元积分把X换为U，U是一个(0,1)之间的variable.
换的方法显而易见: 因为X是(a,b)，所以（(a-a)/(b-a), (b-a)/(b-a)就是 (0,1)，所以如果我让U = (X-a)/(b-a)，U就是(0,1)的范围。
所以 $X=(b-a)U+a$ 
因此有: 

$$
I = \int_{a}^{b} g(x) \ dx = \int_{0}^{1} g((b-a)u+a) \ d((b-a)u+a) = (b-a) \int_{0}^{1} g\left(a + (b-a)u\right) \ du
$$

<h2>如果积分是在(a,b)上，我们可以通过换元变为在(0,1)上</h2>


