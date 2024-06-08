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


