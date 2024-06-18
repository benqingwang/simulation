<h1>利用simulation做计算</h1>

<h2>目录</h2>
<ol>
  <li>利用derivative估计函数值</li>
  <li>利用simulation计算复杂的积分问题</li>
  <li>利用simulation计算 $\pi$ 值</li>
</ol>

<h2>Section 1: 利用derivative估计函数值 - Euler Estimation </h2>
我们有一个函数 

$$
f(x) = 10e^{2x}
$$

如果我们想求f(0.01), f(0.02), ... f(0.10)，可以直接带入
<ul>
  <li>$f(0.01) = 10e^{0.02} = 10.20$</li>
  <li>$f(0.02) = 10e^{0.04} = 10.41$</li>
  <li>$f(0.03) = 10e^{0.06} = 10.62$</li>
  <li>$f(0.04) = 10e^{0.08} = 10.83$</li>
  <li>$f(0.10) = 10e^{0.20} = 12.21$</li>
</ul>

但是现在假装不知道f(x)，只提供下面2个信息。
<ul>
  <li>$f'(x) = 2f(x)$</li>
  <li>$f(0)=10$</li>
</ul>
我们现在要估计f(0.01), f(0.02), ... f(0.10)要怎么办？ 

解答的方法是： 因为 $f(x+h) \approx f(x) + h f'(x)$ 所以有：
<ul>
  <li>$f(x+h) = f(x) + f'(x)h = f(x) + 2f(x)h = f(x)*(1+2h)$</li>
  <li>$f(x+2h) = f(x+h) + f'(x+h)h = f(x+h) + 2f(x+h)h = f(x+h)(1+2h)= f(x)(1+2h)(1+2h) =f(x)*(1+2h)^2$</li>
  <li>可以推理得 $f(x+i*h) = f(x)(1+2h)^i, i = 0, 1, 2, ...$ </li>
</ul>

现在带入 $f(0)=10$, 我们设定h是一个很小的数，比如0.01。这样 $f(0+i * 0.01) = f(0)(1 + 2*0.01)^i, i = 0, 1, 2, ...$ 
<ul>
  <li>$f(0.01) = f(0)(1 + 2 * 0.01)^1 =  10.20$</li>
  <li>$f(0.02) = f(0)(1 + 2 * 0.01)^2 =  10.40$</li>
  <li>$f(0.03) = f(0)(1 + 2 * 0.01)^3 =  10.61$</li>
  <li>$f(0.04) = f(0)(1 + 2 * 0.01)^4 =  10.82$</li>
  <li>$f(0.10) = f(0)(1 + 2 * 0.01)^{10} =  10.19$</li>
</ul>
所以可见我们的approximation在i很小的情况下，效果不错的。

<h2>Section 2: 利用simulation求积分</h2>
为什么要这么做呢？因为有的积分很难手动解出来。用simulation的方法求面积得到积分结果是很棒的。比如你手动试验一下这个: 

$$
\int_{0}^{1} ln(x)ln(1-x) \ dx
$$

老师这里用了一个简单例子来说明过程。

$$
比如我们要求 \sin(\pi x)在（0，1）上的积分。
$$ 

$$
I = \int_{0}^{1} \sin(\pi x) \ dx
$$ 

如果我直接用积分计算是这样的

$$
I = \int_{0}^{1} \sin(\pi x) \ dx = -\frac{1}{\pi} (cos(\pi)x)\vert_{1}^{0} = -\frac{1}{\pi} (-1-(1))=\frac{2}{\pi} \approx 0.6366
$$ 

用simulation的计算的步骤是，generate n个(0,1)之间的随机数x，计算 $sin(pi* x)$，然后求这些 $sin(pi*x)$ 的平均数，就是对积分的无偏估计。

$$
\bar{I}_ n \equiv \frac{1}{n} \sum_{i=1}^{n} I_i = \frac{1}{n} \sum_{i=1}^{n} sin(\pi x_i)
$$

我解释一下为什么这么做是可以得到好的估计：可以想象我们把(0,1)分成n份，然后以每份的高度也即是sin(pi*x)作为高，每份的长度也就是1/n作为宽度，得到一个长方形的面积。然后把这些小长方形加起来就是积分的值，当然n要比较大。那我们这里不是平均分n份，而是随机产生n个(0,1)之间的数字，但是我们可以想象，当n很大的时候，这和平均分n份是一样的效果，因为Excel这个产生随机数的功能就是根据(0,1)之间的uniformed distribution。老师的解释是：根据Law of Large Numbers, 如果一个estimator能够渐近地无偏并且variance goes to zero，上面的方法就是可行的。那么怎么证明mean是无偏并且variance goes to zero呢？简单就是求E(I_estimate) = I. 然后老师口口声声说Var(I_estimate) =0。因为公式写起来太麻烦和浪费时间，可以直接查module 3 page 14. 

用具体Excel表解释。如果我用上面的方法就是可以抽n个随机的(0,1)之间的数，带入$sin(\pi x)$，然后计算平均值。
![image](https://github.com/benqingwang/simulation/assets/158376214/b9f89b85-2076-40ef-bf04-212542ef905e)
可见当我们的sample比较多之后，这个值稳定在6.3左右，和我用积分得到的结果一样。

现在我再看看怎么计算confidence interval
简单说就是confidence interval就是estimator的mean加减z value乘以estimator的标准样本方差，可以直接查module 3 page 15. 

我下面用老师给的4个数来展示具体的计算estimate和confidence interval的过程
![image](https://github.com/benqingwang/simulation/assets/158376214/70de848e-0455-4ffb-a647-821550414801)

现在我们把情况扩大一下，因为很多积分不是就是在(0,1)之间，可能是在(a,b)之间，我只要简单换元就可以。我们可以利用换元积分把X换为U，U是一个(0,1)之间的variable. 换的方法显而易见: 因为X是(a,b)，所以（(a-a)/(b-a), (b-a)/(b-a)就是 (0,1)，所以如果我让U = (X-a)/(b-a)，U就是(0,1)的范围。所以 $X=(b-a)U+a$ 因此有: 

$$
I = \int_{a}^{b} g(x) \ dx = \int_{0}^{1} g((b-a)u+a) \ d((b-a)u+a) = (b-a) \int_{0}^{1} g\left(a + (b-a)u\right) \ du
$$

我们现在创建一个estimator, 这个符号含义就是用n个observation来估计I的estimator, 就是抽n个(0,1)上的随机数，然后带入公式 $g(a+(b-a)u)$ 然后得出一个值，把n个结果平均就是我们的估计。

$$
\bar{I}_ n \equiv \frac{1}{n} \sum_{i=1}^{n} I_i = \frac{b - a}{n} \sum_{i=1}^{n} g(a + (b - a) U_i)
$$

<h2>利用simulation计算 $\pi$ 值</h2>
我们在Module1学过用扔针头的方法来估计 $\pi$ 的值，实际种我们不能扔针，simulation的过程如下:
<ul>
  <li>产生2个(0,1)之间的随机数U1, U2，它们都服从Uniformed distribution</li>
  <li>如果U1, U2满足下面不等式，就说明这个随机试验得到一个圆内部的点。这个不等式是什么意思呢？它是一个点到圆心(1/2, 1/2)的Eulidean距离的平方，如果这个距离小于1/2或者平方小于1/4就说明这个点在圆的内部</li>
</ul>

$$
\left( U_1 - \frac{1}{2} \right)^2 + \left( U_2 - \frac{1}{2} \right)^2 \leq \frac{1}{4}
$$

<ul>  
  <li>然后我们把圆内的点数和所有点数进行对比，得到一个比例。我们知道圆和它相切的正方形的面积比例是: $\pi*r^2/(2r)^2=\frac{1}{4}\pi$ 因此，把我们得到的比例乘以4就是对 $\pi$ 的估计。下面是我做了1000次simulation的结果</li>

  ![image](https://github.com/benqingwang/simulation/assets/158376214/4eea5c6a-8936-45a4-b0a7-1ab5a50a92d3)

</ul>
