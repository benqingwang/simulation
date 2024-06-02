我们首先来看计算偏导数的原理，就是当x变化足够小的时候，y的变化除以x的变化。

$ \frac{d}{dx} f(x) \equiv f'(x) \equiv \lim_{h \to 0} \frac{f(x+h) - f(x)}{h} $
换一种说法也可以写成这样 $ f'(x) \approx \frac{f(x+h) - f(x)}{h} $
因此我们可以推理出x变化一点时候y的值是多少 $ f(x+h) \approx f(x) + h f'(x) $

我们现在解决一个实例,已知: $ f'(x) = 2f(x) $
则有 $ f(x+h) = f(x) + f'(x)*h $
如果 

