<h1>利用simulation做计算</h1>

<h2>目录</h2>
<ol>
  <li>利用derivative估计函数值</li>
  <li>利用simulation计算复杂的积分问题</li>
  <li>利用simulation计算$/pi$值</li>
</ol>


<h2>Introduction</h2>
<h3> 例子背景 </h3>
<ul>
<li>一个函数 $f(x)=10\cdot e^{2x}$ ， 但是现在这个信息被隐藏了，我们不知道具体 $f(x)$ 是什么，但是知道 $f'(x)=2f(x)$ </li>
<li>现在再给你一个信息 $f(0)=10$ ，任务是估计一些小的值的函数值比如 $f(0.01)$ , $f(0.02)$ 等？</li>
</ul>

<h3>需要用的原理</h3>
导数是当x变化无限小的时候，y的变化除以x的变化: 

$$
\frac{d}{dx} f(x) \equiv f'(x) \equiv \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}
$$ 

也可以写成 $f'(x) \approx \frac{f(x+h) - f(x)}{h}$ , 或者  $f(x+h) \approx f(x) + h f'(x)$ 

<h3>实际例子</h3>
<ul>
  <li>$f'(x) = 2f(x)$</li>
  <li>$f(0)=10$</li>
</ul>
 
<h3>Approximation的过程</h3>
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
<h3>和实际值的对比</h3>
我们知道实际的函数是 $f(x)=10\cdot e^{2x}$ ，因为

$$
e^y = \sum_{\ell=0}^{\infty} \frac{y^\ell}{\ell!} \approx 1 + y \approx (1 + y)^i \text{ for small } i.
$$

所以 
<ul>
  <li>$f(0.01) = 10e^{0.02} = 10.20$</li>
  <li>$f(0.02) = 10e^{0.04} = 10.41$</li>
  <li>$f(0.03) = 10e^{0.06} = 10.62$</li>
  <li>$f(0.04) = 10e^{0.08} = 10.83$</li>
  <li>$f(0.10) = 10e^{0.20} = 12.21$</li>
</ul>

<storng>可见我们的approximation在i很小的情况下，效果不错的。</storng>
