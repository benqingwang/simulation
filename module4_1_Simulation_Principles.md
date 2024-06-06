<h1>General Simulation Principles</h1>
<h2>Simulation Study的步骤</h2>
<ol>
  <li>Problem Formulation: 也就是statement of problem：比如利润太低怎么办，顾客抱怨等待时间太长怎么解决</li>
  <li>Objectives and Planning: 指具体要解决的问题：雇多少工人？buffer space to insert in the assembly line?</li>
  <li>Model Building是art也是science: M/M/k queueing model? Need physics equations?</li>
  <li>Data Collection: 要多少什么样的data? Continuous? Discrete? 具体要什么样data?考虑budget</li>
  <li>Coding: 决定用什么language来写program. Simulation有大体2种Modeling paradigm (Event-Scheduling, Process-Interaction): 一共100s of languages out there。老师说Process-Interaction好，Event-scheduling太麻烦。Arena就是process-interaction的语言。虽然它内部隐藏是event-scheduling，但是考试问你要说是Processs-interaction</li>
  <li>Verification: code正确吗？如果不行，回到coding步骤</li>
  <li>Validation：Model行吗？如果不行回到步骤3 modeling和步骤4 data collection.</li>
  <li>Experimental Design: 怎么设计试验才能有效的回答我们的问题（统计上考虑，时间/预算)</li>
  <li>Run Experiments: 运行Production, often substantial. 可能需要大量时间</li>
  <li>Output Analysis: 统计分析，估计relevant measures of performance。通常和iterative with step 8 (Experimental Design) and step 9 (Production Runs)。Almost always need more runs</li>
  <li>Make Reports, Implement, and make management happy</li>

</ol>

<h2>Simulation Study的重要概念</h2>

<ol>
<li>system: 系统是相互作用共同实现一个目标的 a collection of entities (比如people, machines等等)</li>
<li>model: model是对系统的抽象representation，通常含有math logical relationships描述系统的states, entities, sets, events, etc. </li>
<li>System state: 是一组足以描述系统的variable, 也就是a “snapshot” of the system. 比如在一个single-server queue, 我们可以用等待的人数和server是不是在工作描述state</li>
<li>Entities: Entities可以是permanent (比如machine)也可以是temporary的 (比如customers), 每个entity可以有各种properties or attributes (比如客户priority或者server的平均速度)</li>
<li>List: A list (or queue)是一个ordered list of associated entities (比如 a linked list, or a line of people).
<li>Event: 是一个时间点，在这点system state发生了变化。这个变化是事先不能预测的。比如，arrival event, departure event, a machine breakdown event. Event实际上是指一个事情发生的时间，但是loosely可以指发生了什么比如arrival。
<li>Activities: 指 a duration of time of specified length (aka an unconditional wait). 比如 exponential customer interarrival times 比如 constant service times。因为我们可以explicitly generate这些events, 所以它们是“specified”.</li>
<li>Conditional wait: 是 a duration of time of unspecified length. 比如customer waiting time这个我们不能直接知道。事实上，我们可以通过arrival和service times来reverseengineer the waiting times. </li>











<h2></h2>
<h2></h2>
<h2></h2>
