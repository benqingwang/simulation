<h1>A Single-Server Queue</h1>

<h2>Single_Server Queue的基础 - 计算平均系统内时间和平均人数</h2>
<h3>One single server queue问题有下面的假设</h3>
<ul>
  <li>客户的 arrival interval是iid (independnetly and identically distributed)</li>
  <li>客户的 service time也是 iid</li>
  <li>这个例子我们假设FIFO的服务顺序，后面我们也会看LIFO</li>
</ul>

这里面需要定义一些符号表达:
<ul>
  <li> $I_{i}$ 是第i个顾客和第i-1个顾客到达时间的差</li>
  <li> 所以 $A_{i}$ 是第i个顾客实际到达的时间: $A_{i} = I_{1} + I_{2} + ... + I_{i}$ </li>
  <li> $T_{i}$ 是第i个顾客开始被served的时间，这个时间不能早于这个顾客到达时间 $A_{i}$ ，也不能早于上一个顾客离开的时间 $D_{i-1}$ 所以 $T_{i} = Max(A_{i}, D_{i-1})$ </li>
  <li> $W_{i}^Q$ 代表顾客i在系统内的等待时间，也就是他开始得到served的时间，减去他到达时间 $W_{i}^Q = T_{i}- A_{i}$ </li>
  <li> $W_{i}$ 代表顾客在系统内的总时间，就是他离开和他到达的差 $W_{i} = D_{i}- A_{i}$ </li>
  <li> $S_{i}$ 是第i个顾客被served的时长</li>
  <li> $D_{i}$ 是第i个顾客离开的时间, 是他开始被served加上service时长: $D_{i} = T_{i} + S_{i}$  </li>

<h3>我们有2个任务:</h3>
<ul>
  <li> 求顾客(例子里有6个顾客)的平均等待时间 $\sum_{i=1}^{6} \frac{W_i Q_i}{6}$
  <li> 求系统中平均有多少人(in line + in service) </li>
</ul>

下面我们来看怎么用simulation来计算
<ul>
  <li> 顾客的平均时间$\sum_{i=1}^{6} \frac{W_i Q_i}{6}$可以就把所有人的各个步骤的时间写出来，然后计算平均值</li>

  ![image](https://github.com/benqingwang/simulation/assets/158376214/50f51635-7f8a-421e-a3e3-4f979cf80f9a)

<li>计算系统中平均多少人稍微复杂一点。</li>
  首先我们把所有event都列出来

  ![image](https://github.com/benqingwang/simulation/assets/158376214/514698eb-4973-4dbd-9c4c-d6b4c94e64e1)

  我们计算面积就是sum(人数*时间)，再除以总时间29，就是平均的系统中的人数 70/29
  ![image](https://github.com/benqingwang/simulation/assets/158376214/3f473162-9206-470e-9658-2d7d2d6104d5)

  ![image](https://github.com/benqingwang/simulation/assets/158376214/5e91af9b-30d5-4c98-bf76-452f3feeb79e)

<li>老师还给了一个LIFO的例子</li>

  ![image](https://github.com/benqingwang/simulation/assets/158376214/bf260ba0-078f-45ba-90dd-7c8a0082e611)

<h2>存货管理系统的例子</h2>
背景
<ul>
  <li> 单位货物的售价是d</li>
  <li> $I_{i}$ 第i天营业结束的时候的存货量</li>
  <li> $Z_{i}$ 第i天营业结束的进行订货的量，货物的单位成本是c, 订一次货的固定费用是K，或者总支出是 K + c*订货量  </li>
  <li> 营业结束后订货的量服从一个规则: 如果营业结束时存货还剩s以下的话就必须订货，否则必须不订 </li>
  <li> 假设这些新货会立刻送到，因此hold这些存货overnight的单位成本是h</li>
  <li> 如果营业期间客户来了但是你的货没有了，客户会生气的走开，每个缺货的量的造成penalty的损失是p </li>
  <li> 这里面唯一的随即量是每天的客户需求货量 $D_{i}$ </li>
  <li> 我们要回答的问题是，这个商店在第i天挣了多少 </li>
</ul>

现在我们计算Total Cost Calculation
<ul>
  <li> Total = Sales - Ordering Cost - Holding Cost - Penalty Cost</li>
  <li> $Sales = d * 销量 = d * min (Di, I_{i-1}+ Z_{i-1})$ </li>
  <li> 如果 $I_{i-1}<s, Ordering Cost = K + c*订货量 ， 否则 Ordering Cost =0$ </li>
  <li> Holding Cost 
  

$$
= d \min(D_i, \text{inventory at beginning of day } i)
$$

$$
- \left\{
    \begin{array}{ll}
    K + cZ_i & \text{if } I_i < s \\
    0 & \text{otherwise}
    \end{array}
    \right.
$$

$$
- hI_i - p \max(0, D_i - \text{inventory at beginning of day } i)
$$

$$
= d \min(D_i, I_{i-1} + Z_{i-1})
$$

$$
- \left\{
    \begin{array}{ll}
    K + cZ_i & \text{if } I_i < s \\
    0 & \text{otherwise}
    \end{array}
    \right.
$$

$$
- hI_i - p \max(0, D_i - (I_{i-1} + Z_{i-1})).
$$

  
  
  
  
