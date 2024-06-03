<h1>A Single-Server Queue</h1>

One single server queue问题有下面的假设
<ul>
  <li>客户的 arrival interval是iid (independnetly and identically distributed)</li>
  <li>客户的 service time也是 iid</li>
  <li>这个例子我们假设FIFO的服务顺序，后面我们也会看LIFO</li>
</ul>

这里面需要定义一些符号表达:
<ul>
  <li> Ii是第i个顾客和第i-1个顾客到达时间的差</li>
  <li> Di是第i个顾客离开的时间 </li>
  <li> 所以Ai是第i个顾客实际到达的时间: $A_{i} = I1 + I2 + ... + Ii$ </li>
  <li> Ti是第i个顾客开始被served的时间，这个时间不能早于这个顾客到达时间Ai，也不能早于上一个顾客离开的时间所以Ti = Max(Ai, Di-1)</li>
  
