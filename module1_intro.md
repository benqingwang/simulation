<h2>什么是simulation?</h2>
simulation是solve model的一个方法。所以我们先看什么是model: model is a high-level representation of the operation of a real-world process. 那么solve model有3种方法：
- analytical methods: 就是通过解方程那种方式解决的.比如我从山上扔一个石头出去，我想知道它的落点，这个可以用物理公式计算出来。这种就是analytical methods。
- numerical methods: 不是closed-form的，比如预测天气，可能要用很多微积分，这种是numerical.
- simulation method: 如果这个过程有randomness，那么上面2种可能就都不好使，那么我们可以用similation. 

所以simulation的定义是: the imitation of a real-world process or system over time. 它包含: 
<li>generation of an artificial history </li>
<li>to draw inferences </li>
<li>concerning the operating characteristics of the real system that is represented.</li>
所以这里关键字是<strong>inferences</strong>，simulation的结果是一个inferences。

<h2>本课关注的model类型</h2>
- Discrete (vs. continuous)
– Stochastic (vs. deterministic)
– Dynamic (vs. static)

<h2>simulation的应用</h2>
- Describe / analyze real or conceptual system behavior.
- Ask “what if” questions.
- Aid in system design and optimization.
- Can simulate almost anything.
    Customer-based systems likeManufacturing Processes, Supply Chains, Health Systems.
    Systems with no “customers”, e.g., stock option prices.

通过simulation，
- 我们可以知道系统能不能完成任务? 
- 如果现在的系统不能完成任务，什么要调整？
- 我们还可以通过simulation得到具体的action plan
- 解决问题：比如有bottleneck，通过simulation来看怎么解决
- 解决dispute: 比如2个人有2个不同的意见，我们可以通过simulation来分析优劣
- sell an idea: simulation比较直观有说服性。

<h2>simulation的优缺点</h2>
<h3>优点</h3>
 - 可以用来研究哪些用analytical / numerical treatment解决不了的复杂问题
 - 研究那些analytical or numerical treatment可能忽略的细节关系
 - 作为系统experimental studies的基础
 - 可以同来check其他方法的results and give credibility.
 - 减少design blunders （严重错误).
 - 很好的demo method.
 - (有的时候) 非常简单
 
<h3>缺点</h3>
 - (有的时候) 不简单
 - (有的时候) 很费事很昂贵
 - Simulations产生“random” output，所以可能会misinterpretation of results
 - 对有的问题有比simulation更好的方法

<h2>Simulation的历史</h2>
【1】据老师说，最早例子是1777 – Buffon’s Needle Problem – a new spin on things。Suppose we have a floor made of parallel strips of wood, each the same width, and we drop a needle onto the floor. What is the probability that the needle will lie across a line between two strips?
【2】Early 1900’s – Beer and Student’s t distribution：用英国监狱犯人的index finger长度做的simulation
【3】1946 – Ulam, Metropolis, von Neumann, and the H-Bomb 氢弹研究
【4】1960’s – Industrial Applications （–Manufacturing – Queueing Models）
【5】Development of Simulation Languages
    – Easy-to-use modeling tools
    – Graphics
【6】Rigorous Theoretical Work
    – Computational algorithms
    – Probabilistic and statistical methods

制造业是simulation的一个origin
Simulation is the technique of choice
• Calculates movement of parts and interaction of system components.
• Evaluates part flow thru the system.
• Examines conflicting demand for resources.
• Studies contemplated changes before their introduction.
• Prevents design blunders.

通常会问的问题包括
• What will be the throughput? Throughput就是类似于output就是指你系统能让多少人或者东西through
• How can we change it?
• Where are the bottlenecks?
• Which is the best design?
• What is the reliability of the system?
• What is the impact of breakdowns? 如果系统完蛋了，后果是啥

<h2>Simulation的Actual Applications</h2>
<h3>制造业和supply chain的</h3>
Manufacturing (Automobile Production Facility, Carpet Production Facility) 
Queueing Problems (Call Center Analysis, Fast Food Drive-Thru, Fast Food Drive-Thru Call Center, Airport Security Line)

现在许多supply chain工具都有simulationcapability.
– Use simulation to determine how much value-added a forecasting application provides.
– Use simulation to analyze howSC randomness or model errors affect a proposed solution. Is it robust? What’s the best solution?

<h3>更多Applications</h3>
• Inventory and Supply Chain Analysis
• Financial Analysis
• Portfolio Analysis
• Options Pricing
• Traffic Simulation
• Airspace Simulation
• Service Sector
• Health Systems

Health Systems的simulation
• Patient Flow in a Hospital
• Hospital Room Allocation
• Optimization of Doctor / Nurse Scheduling
• Procurement of Supplies
• Disease Surveillance
• Propagation of Disease Spread
• Humanitarian Logistics

<h3>Surveilance Application</h3>
• Use simulation to monitor certain time series.
• Predict issues as or before they happen.
• Is a disease in the process ofbecoming an outbreak?
• When is something out of theordinary occurring?
• Take advantage of HUGE data sets.

Dr. Harold Shipman的例子
这个坏人通过篡改遗嘱然后给他的病人heroin overdoses来杀死她们夺财。他篡改记录来显示这些病人需要吗啡，但是软件记录这些修改。
我们这里的目的是讲什么是surveilance application：Surveillance用sequential hypothesis tests。
- Null hypH0 is “no disease” (“no murder”).
- The test statistics有非常难的分布，即使是under H0.
- 使用simulation可以近似null hypothesis的概率分布
- 如果sampling casts doubt on this distribution, then reject.



