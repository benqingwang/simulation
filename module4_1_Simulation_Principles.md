<h1>General Simulation Principles</h1>

<h2>目录</h2>
<ol>
  <li> Simulation Study的步骤
  Simulation Study的重要概念
  Time-Advance Mechanisms
  

<h2>1. Simulation Study的步骤</h2>
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

<h2>2. Simulation Study的重要概念</h2>
<ol>
<li>system: 系统是相互作用共同实现一个目标的 a collection of entities (比如people, machines等等)</li>
<li>model: model是对系统的抽象representation，通常含有math logical relationships描述系统的states, entities, sets, events, etc. </li>
<li>System state: 是一组足以描述系统的variable, 也就是a “snapshot” of the system. 比如在一个single-server queue, 我们可以用等待的人数和server是不是在工作描述state</li>
<li>Entities: Entities可以是permanent (比如machine)也可以是temporary的 (比如customers), 每个entity可以有各种properties or attributes (比如客户priority或者server的平均速度)</li>
<li>List: A list (or queue)是一个ordered list of associated entities (比如 a linked list, or a line of people).
<li>Event: 是一个时间点，在这点system state发生了变化。这个变化是事先不能预测的。比如，arrival event, departure event, a machine breakdown event. Event实际上是指一个事情发生的时间，但是loosely可以指发生了什么比如arrival。
<li>Activities: 指 a duration of time of specified length (aka an unconditional wait). 比如 exponential customer interarrival times 比如 constant service times。因为我们可以explicitly generate这些events, 所以它们是“specified”.</li>
<li>Conditional wait: 是 a duration of time of unspecified length. 比如customer waiting time这个我们不能直接知道。事实上，我们可以通过arrival和service times来reverseengineer the waiting times. </li>


<h2>3.Time-Advance Mechanisms</h2>
<h3>基本概念</h3>
<ul>
  <li>simulation clock是一个变量，它的值代表了simulated time (也就是说不等于real time)。</li>
  <li>Time-Advance Mechanisms 指的是 how does the clock move?</li>
  <li>Always moves forward (never goes back in time). </li>
</ul>

<h3>2种time advance的机制</h3>
• Fixed-Increment Time Advance
• Next-Event Time Advance

<h4>Fixed-Increment Time Advance</h4>
就是信息只有在固定的时间点才有，是时间点为中心的看法。
<ul>
  <li>Update the state of the system at fixed times, n*h, n = 0,1,2,…, where h is chosen appropriately.</li>
  <li>This is used in continuous-time models (e.g., differential equations) and models where data are only available at fixed times (e.g., at the end of every month).</li>
  <li>Not emphasized in this course!</li>
</ul>

<h4> Next-Event Time Advance </h4>
这个是以event为中心的观点。利用future event list (FEL)
<ul>
  <li>The clock is initialized at 0. All known future event times are determined and placed in the future events list (FEL), ordered by time.</li>
  <li>The clock advances to the most imminent event, then to the next most imminent event, etc.</li>
  <li>At each event, the system state and FEL are updated.</li>
  <li>The system state can only change at event times. Nothing really happens between events.
  <li>The simulation progresses by sequentially executing (dealing with) the most imminent event on the FEL.
</ul>

这里“dealing with”指将时钟前进至most imminent event并且update system state. 具体怎么update要看event是什么。比如对于arrival event，你要打开idle server。如果server是忙的，我们就在queque加上一个新顾客。
这里 “updating the FEL”指每次发生一个event, the simulation可能需要update FEL event的 the chronological order: 比如加入new events, 删除events, moving event around, 啥也不做。
这里有一个例子： 一个人到达queque之后，通常的simulation program回立刻着手next arrival time. 
<ul>
  <li> 如果next arrival time非常远，就把它放在FEL的最后就好 </li>
  <li> 如果next arrival 会在另一个event之前就发生，比如说next arrival会在慢吞吞的server完成现在这个顾客之前就到来， 则next arrival要安插在FEL的内部</li>
  <li> 如果现在进来的是一个丑家伙（老师自己）所有人都跑了，则我们的update FEL就是把FEL里面events删除了，哈哈哈</li>
</ul>

<h4>Efficient list processing (e.g., linked lists) for the FEL.</h4> 
• Singly and doubly linked lists intelligently store the events in an array that allows the chronological order of the events to be accessed.
• Such lists easily accommodate insertion, deletion, switching of events, etc.
• Take a Computer Science course to learn more.

老师还说要小心同时发生的event。比如一个人进来一个人出去。其实算谁先进来都可以，但是要有一个明确的rule保持一致。
每个discrete-event simulation language都maintains a FEL。商业软件都会自己处理这些。

老师给的例子
![image](https://github.com/benqingwang/simulation/assets/158376214/bfc79389-7137-4fb4-9151-7529228f57ff)


<h2>4. Two Modeling Approaches</h2>
<h3>Event-Scheduling</h3>
关注events和它们对system state的影响。它的缺点就是要keep track 所有event，然后会随着时间的推移越来越多。你可以用这个方法，if you were programming in C++ or Python from scratch.但是老师给的例子说明，这种方法coding起来是个mess，非常多的方面要update. 


<h3>process-interaction</h3>
如果我们用一个process-interation (PI) lanugage来处理generic model，我们只需要做: 
<ul>
  <li>Create customers every once in a while.</li>
  <li>Process (serve) them, maybe after waiting in line.</li>
  <li>Dispose of the customers after they’re done being processed.</li>
</ul>
这个课程就是讲PI语言。 我们需要的是关注a generic customer (entity) and 和它在这个系统里相关的the sequence of events and activities. 在任何时刻，系统可能有多名顾客，然后它们会相互作用争夺资源。用PI语言，我们就deal with generic customer而不是event bookkeeping。Event bookkeeping是simulation language本身handle的，所以老师说如果考试问Arena是什么语言要回答是PI，但是知道它们核心是event scheduling.

PI很省事，比如 A customer is generated, eventually gets served, and then leaves就是Create – Process – Dispose.

<h2>5. Simulation Languages</h2>
大概有100多种的simulation commercial languages。按照low to high level排序 FORTRAN, SIMSCRIPT, GPSS/H, Extend, Arena, Simio, Automod, AnyLogic。学校里会用 5–10种主要的，价格从1000到10万。但是也有免费的：Java, Python都有不错的package. (比如 SimPyl)，有点learning curve但是还好。选择哪种语言的考虑: 
• Cost considerations: $$, learning curve, programming costs, runtime costs, etc.
• Ease of learning: documentation, syntax, flexibility
• World view: E-S, P-I, continuous models, combination
• Features: RV generators, stats collection, debugging aids, graphics, user community

怎么学呢？Textbooks, Conferences such as the Winter Simulation Conference, Vendor short courses (at a potentially steep cost)
