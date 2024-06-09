<h1>Arena入门</h1>

<h2>复习概念</h2>

<ul>
  <li>Arena takes this process-interaction “world view.”在Arena里面三个大步骤: Create (generate cust arrivals), Process (use the barber), Dispose (outta here)</li>
  <li>Arena是一个Windows产品，but there are solutions if you don’t have a Windows-based machine.</li>
  <li>entity: 一个generic customer是一个entity.这些entities会interact each other当它们竞争resources的时候</li>
  <li>processes: 这个客户Undergoes的events和activities叫processes。</li>
  <li>Modules: entities会经过a network of modules (我们叫blocks)。这些modules描述entity的behavior. 我们可以用process flowchart来表示network(下面是flowchart的例子)。比如People show up at the barber, get served (maybe after waiting in line), and then leave.</li>
</u>
![image](https://github.com/benqingwang/simulation/assets/158376214/bc4d5ecd-c6bf-4eda-856f-adf6390b033f)

<h2>如何从virtual machine使用Arena</h2>
老师提供了下载arena和使用virtual machine的选项。我选择了直接用virtual machine的arena。

![image](https://github.com/benqingwang/simulation/assets/158376214/fa9ed3d0-d9be-413a-a08c-6c803bb5e8d9)

<h2>最基本操作</h2>
<h3> Basic Template </h3>
The Basic Process panel(我的版本就是"discrete processing"）有各种modules来flowchart简单models。这课我用到的是create, process, dispose，但是没有hold，因为我没看见。老师的版本上basic process template有both modules and spreadsheets.但是我的新版本没有，新版本的spreadsheets是单独一个Data Definition的tab. 打开arena之后在左边选择"discrete processing"就能找到flow charts的标记，根据老师说的，我建立了自己第一个simulation只有create, process, dispose。</li>

![image](https://github.com/benqingwang/simulation/assets/158376214/c50658bf-d3ed-4b9b-8ea6-625f02ab3aa6)
<ul>
  <li> Create module可以 用来创造a variety of customer interarrival time distributions</li>
  <li> Process： A process module可以想成a resource（server) and 以及对应的queue. 一个process可以有下面的4种action sequences：Delay, Seize-Delay, Delay-Release, Seize-Delay-Release</li>
  <li> 添加resource： 然后我又跟着老师在process 1 添加了一个resource: Barber (delay seize release)，虽然我不知道什么意思。不过现在能在'data definition'下面的resource sheet看到Barber。运行simulation就是用右上角像录音机按键一样的Button</li>

![image](https://github.com/benqingwang/simulation/assets/158376214/12b3e818-32ed-4f30-a082-353b93f9df95)

<h3>使用spreadsheets</h3>
我们可以在spreadsheet ("Data Definition") -> Resource 来改变一个resource的servers on duty的数量（也就是我们的capacity)。我们也可以用spreadsheet -> Queue 来把一个queue从FIFO改成LIFO. 
  
<h3>如何得到advanced template</h3>

![image](https://github.com/benqingwang/simulation/assets/158376214/3e328ce2-59be-4076-b788-377dd0a0b36e)

<h3> Decide Module </h3>
Decide module有好几种方法2-Way by Chance， N-Way by Chance， 2-Way by Condition， N-Way by Condition

<h3> The Assign Module </h3>
我们可以assign values to attribue，assign values to variables，assign graphics to entities。这里我们复习一下概念。<ul>
<li>什么是attribute: 每个customer有自己的特性（比如我身高180血脂108喜欢打棒球等等）， attribute必须是数字的，当然你可以把categorical变成数字</li>
<li>什么是variable: variable是global的，不是具体到customer的。所以你改变一个variable，所有人都受影响，比如系统里的WIP变化。</li></ul>
我们可以通过Assign给一个客户分类，还能给它一个picture，当然这个picture还能再entity spreadsheet改. 

<h3> Internal Variables </h3>
Arena内部的的变量，可以在make decision或者画图的时候用。老师给了很多例子。
<ul>
  <li>TNOW = current simulated time</li>
  <li>NR(Barber) = # of resource Barber’s servers now working</li>
  <li>NQ(Process 1.Queue) = # customers in that queue</li>
  <li>Create 1.NumberOut = # of customers who have so far left the module named Create 1</li>
</ul>

例子: Suppose the associated queue below has exactly 4 customers in it. Which of the following statements is true? NQ(Barbershop.Queue) == 4 </li>

![image](https://github.com/benqingwang/simulation/assets/158376214/46069fe3-27e0-47f2-9714-a0387fea2ce8)


例子： Consider the Variable dialog box below. What does this thing do? It keeps track during run-time of the number of servers in the resource Barber who are currently working on customers.

![image](https://github.com/benqingwang/simulation/assets/158376214/db756c62-ed8c-4f69-bcef-1f7fbc43512d)

<h3> Batch/Separate </h3>
我们可以用Batch module要么merge customers together permanently (so that you can’t recover all of their original attributes, even with a Separate module) 或者 temporarily (so that you can eventually recover the original customers)。
如果我们有一个Temporary batch, 我们可以用command Split把这个batch分开来reproduce entities，而这些entities能有它们original attributes (before getting Batch’d)

<h3>Setup </h3>
如果我们想make 5 runs of the simulation, each lasting 100 hours, 我们要这么设置Run Setup menu： Set Number of Replications = 5, Replication Length = 100
