<h1>A Single-Server Queue</h1>

One single server queue问题有下面的假设
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

我们有2个任务:
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



  
  
  
  
