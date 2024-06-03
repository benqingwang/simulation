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
  <li> $D_{i}$ 是第i个顾客离开的时间 </li>
  <li> 所以 $A_{i}$ 是第i个顾客实际到达的时间: $A_{i} = I_{1} + I_{2} + ... + I_{i}$ </li>
  <li> $T_{i}$ 是第i个顾客开始被served的时间，这个时间不能早于这个顾客到达时间 $A_{i}$ ，也不能早于上一个顾客离开的时间所以 $T_{i} = Max(A_{i}, D_{i-1})$ </li>
  
