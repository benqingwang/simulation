<h1>创建随机数</h1>
<h2>用inverse transform method创建discrete随机数</h2>
<ul>
  <li>如果我想要得到1~n之间的discrete随机数（1,2,3,...,n)，我可以利用一个(0,1)之间的uniformed distribution U，然后ceiling(n*U)就是我们要的离散随机数。这里ceiling的意思就是round up，比如ceiling(7.3)=8</li>
  <li>稍微复杂一点的例子，比如discrete variable X只能选3个值: -2, 3, 4.2，概率分别是0.25, 0.1, 0.65. 那我们要怎么simulate呢？方法就是产生一个(0,1)之间的随机数，如果这个数在[0, 0.25]就认为抽中了-2，如果是(0.25, 0.35]就当抽中了3，如果(0.35,1)就当抽中了4.2. 比如如果我们抽中了0.46，就认为是simulate到了4.2。</li>
  <li>体会一下，这个方法是和上面简单的例子一样的。就是用随机的(0,1)来simulate CDF(Cumulative Distribution Function )，倒推回X值。这个方法就是叫做inverse transform method. $F(X) = U$ 因此 $X = F^{-1}(U)$ </li>
</ul>

<h2>用inverse transform method创建discrete随机数</h2>
<ul>
  <li>首先看一个theorem: 如果X是一个连续的随机变量并且cdf是F(x)。那么 $F(X)~U(0,1)$ . 这个theorem说明什么呢？ 说明如果我们能求出cdf的反函数，$X = F^{-1}(U)$ ,我们就可以把一个(0,1)之间的随机数扔进这个反函数，然后得到simulated X </li>
  <li>总结：第一步得到CDF $F(X)$ , 第二步求CDF反函数 $X = F^{-1}(U)$, 第三步带入一个(0,1)随机数 </li>
  <li>看一个例子，我有一个指数函数 $X \sim e^{\lambda}$ ，我们先找到它的CDF: $F(x) = 1 - e^{-\lambda x}$ for x>0. 令 $F(x) = 1 - e^{-\lambda x} = U$ , 解出: $X = \frac{-1}{\lambda} \ln(1 - U)$ .这个时候我扔进去一个(0,1)随机数U，得到X就是服从指数分布的随机连续变量</li>
</ul>

<h2>如何产生(0,1)随机数</h2>
<ul>
  <li> Excel: RAND ( )函数</li>
  <li> PRN (Pseudo-random numbers)  
      <ol>
        <li> 先设一个seed X0 </li>
        <li> 带入这个公式逐个产生随机整数 $X_i = 16807 X_{i-1} \mod (2^{31} - 1)$ , for i = 1, 2, ... </li>
        <li> 最后把产生的整数带入这个公式产生(0,1) 随机数 $R_i = \frac{X_i}{2^{31} - 1}$ i=1,2,... 这个肯定是个(0,1)的数，因为Xi是 $2^{31}$ 的余数 </li>  
      </ol>
  </li>
  <li> Fortran implementation: This Fortran code is an implementation of a linear congruential generator, which is a method of generating pseudo-random numbers. 我不重复了，就是老师module 3 slide 50</li>
  
  

