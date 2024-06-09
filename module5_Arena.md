我们再来重复一下概念，Arena takes this process-interaction “world view.”
<ul>
  <li>一个generic customer是一个entity</li>
  <li>这个客户Undergoes的events和activities叫processes</li>
  <li>这些entities会interact each other当它们竞争resources的时候</li>
  <li>entities会经过a network of modules (我们叫blocks)。这些modules描述entity的behavior. 我们可以用process flowchart来表示network(下面是flowchart的例子)。比如People show up at the barber, get served (maybe after waiting in line), and then leave.</li>
  <li>在Arena里面三个大步骤: Create (generate cust arrivals), Process (use the barber), Dispose (outta here)</li>
</u>

![image](https://github.com/benqingwang/simulation/assets/158376214/bc4d5ecd-c6bf-4eda-856f-adf6390b033f)


<h2>从virtual machine使用Arena</h2>
我选择了直接用virtual machine的arena。打开arena之后在左边选择"discrete processing"就能找到flow charts的标记，根据老师说的，我建立了自己第一个simulation只有create, process, dispose。

![image](https://github.com/benqingwang/simulation/assets/158376214/fa9ed3d0-d9be-413a-a08c-6c803bb5e8d9)

然后我又跟着老师在process 1 添加了一个resource: Barber (delay seize release)，虽然我不知道什么意思。不过现在能在'data definition'下面的resource sheet看到Barber。运行simulation就是用右上角像录音机按键一样的Button

![image](https://github.com/benqingwang/simulation/assets/158376214/12b3e818-32ed-4f30-a082-353b93f9df95)

如何得到advanced template
![image](https://github.com/benqingwang/simulation/assets/158376214/3e328ce2-59be-4076-b788-377dd0a0b36e)

8.1 Decide Module
9.1 The Assign Module
<ul><li>assign values to attribue</li><li>assign values to variables</li><li>assign graphics to entities</li></ul>
什么是attribute: 每个customer有自己的特性（比如我身高180血脂108喜欢打棒球等等）， attribute必须是数字的，当然你可以把categorical变成数字
什么是variable: variable是global的，不是具体到customer的。所以你改变一个variable，所有人都受影响，比如系统里的WIP变化。
10. 

习题
<ol>
  <li>What is the name of Arena’s primary modeling approach “world view”? Process-Interaction</li>
  <li>Arena is a Windows product, but there are solutions if you don’t have a Windows-based machine.True </li>
  <li>The Basic Process panel contains various modules that can be used to flowchart simple models.True</li>
  <li>Which modules appear on the Basic Process panel?: 我觉得是create, process, dispose，但是没有hold，因为我没看见 </li>
  <li>TRUE or FALSE? The Basic Process template contains both modules and spreadsheets.我知道老师的是在一起，但是我的新版本没有，所以我还是要回答False</li>
  <li>What does the above icon represent? Create</li>

  ![image](https://github.com/benqingwang/simulation/assets/158376214/abc0e1e1-dc0b-49bc-a59f-1baf084abb16)

  <li>TRUE or FALSE? A Create module allows you the use a variety of customer interarrival time distributions.True</li>
  <li>Which of the following action sequences can you find in a Process module?Delay, Seize-Delay, Delay-Release, Seize-Delay-Release。我选All of the above</li>
  <li>TRUE or FALSE? A process is generally considered to consist of both a resource and its associated queue.True</li>
  <li>TRUE or FALSE? You can change the number of servers on duty (i.e., the capacity) for a resource using the Resource spreadsheet.True</li>
  <li>TRUE or FALSE? You can change a queue discipline from FIFO to LIFO with one click by using the Queue spreadsheet.True</li>
  <li>Which is the only functionality of the Decide module that is 𝑛𝑜𝑡 offered?: 瞎编的是2-Way by Choice，很明显你不能手动choice，所以有的是 2-Way by Chance， N-Way by Chance， 2-Way by Condition， N-Way by Condition</li>
  <li>下面哪个不是attribute? The system’s work in process。判断的依据就是attribute是具体于一个entity，variable是对于系统的，所以系统的WIP是variable不是attribute </li>
  <li>What is the module icon below: Assign</li>

![image](https://github.com/benqingwang/simulation/assets/158376214/af2d5314-a6a1-4f79-8a5a-70f53de1991b)

<li>Where can you set or change a customer’s picture? Assign module和assign spreadsheet都可以</li>
<li>Suppose the associated queue below has exactly 4 customers in it. Which of the following statements is true? NQ(Barbershop.Queue) == 4 </li>

![image](https://github.com/benqingwang/simulation/assets/158376214/46069fe3-27e0-47f2-9714-a0387fea2ce8)


<li>Consider the Variable dialog box below. What does this thing do? It keeps track during run-time of the number of servers in the resource Barber who are currently working on customers.

![image](https://github.com/benqingwang/simulation/assets/158376214/db756c62-ed8c-4f69-bcef-1f7fbc43512d)

老师给了其他例子
<ul>
  <li>TNOW = current simulated time</li>
  <li>NR(Barber) = # of resource Barber’s servers now working</li>
  <li>NQ(Process 1.Queue) = # customers in that queue</li>
  <li>Create 1.NumberOut = # of customers who have so far left the module named Create 1</li>
</ul>
</li>
<li>TRUE or FALSE? You can use the Batch module to either merge customers together permanently (so that you can’t recover all of their original attributes, even with a Separate module) or temporarily (so that you can eventually recover the original customers).True</li>
<li>TRUE or FALSE? If you have a Temporary batch, then you can use the command Split Existing Batch to reproduce entities having their original attributes (before getting Batch’d).True</li>
<li>If I wanted to make 5 runs of the simulation, each lasting 100 hours, what would I do in the Run Setup menu? Set Number of Replications = 5, Replication Length = 100</li>
</ol>

