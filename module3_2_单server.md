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

  
  
  
  
  
  
