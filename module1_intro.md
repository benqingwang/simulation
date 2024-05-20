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
<li>Discrete (vs. continuous)</li>
<li>Stochastic (vs. deterministic)</li>
<li>Dynamic (vs. static)</li>

<h2>simulation的应用</h2>
<li>Describe / analyze real or conceptual system behavior.</li>
<li>Ask “what if” questions.</li>
<li>Aid in system design and optimization.</li>
<li>Can simulate almost anything.</li>
    <li>Customer-based systems likeManufacturing Processes, Supply Chains, Health Systems.</li>
    <li>Systems with no “customers”, e.g., stock option prices.</li>

通过simulation，
<li>我们可以知道系统能不能完成任务? </li>
<li>如果现在的系统不能完成任务，什么要调整？</li>
<li>我们还可以通过simulation得到具体的action plan</li>
<li>解决问题：比如有bottleneck，通过simulation来看怎么解决</li>
<li>解决dispute: 比如2个人有2个不同的意见，我们可以通过simulation来分析优劣</li>
<li>sell an idea: simulation比较直观有说服性。</li>

<h2>simulation的优缺点</h2>
<h3>优点</h3>
 <li>可以用来研究哪些用analytical / numerical treatment解决不了的复杂问题</li>
 <li>研究那些analytical or numerical treatment可能忽略的细节关系</li>
 <li>作为系统experimental studies的基础</li>
 <li>可以同来check其他方法的results and give credibility.</li>
 <li>减少design blunders （严重错误).</li>
 <li>很好的demo method.</li>
 <li>(有的时候) 非常简单</li>
 
<h3>缺点</h3>
 <li>(有的时候) 不简单</li>
 <li>(有的时候) 很费事很昂贵</li>
 <li>Simulations产生“random” output，所以可能会misinterpretation of results</li>
 <li>对有的问题有比simulation更好的方法</li>

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
<li>Calculates movement of parts and interaction of system components.</li>
<li>Evaluates part flow thru the system.</li>
<li>Examines conflicting demand for resources.</li>
<li>Studies contemplated changes before their introduction.</li>
<li>Prevents design blunders.

通常会问的问题包括
<li>What will be the throughput? Throughput就是类似于output就是指你系统能让多少人或者东西through</li>
<li>How can we change it?</li>
<li>Where are the bottlenecks?</li>
<li>Which is the best design?</li>
<li>What is the reliability of the system?</li>
<li>What is the impact of breakdowns? 如果系统完蛋了，后果是啥</li>

<h2>Simulation的Actual Applications</h2>
<h3>制造业和supply chain的</h3>
Manufacturing (Automobile Production Facility, Carpet Production Facility) 
Queueing Problems (Call Center Analysis, Fast Food Drive-Thru, Fast Food Drive-Thru Call Center, Airport Security Line)

现在许多supply chain工具都有simulationcapability.
<li>Use simulation to determine how much value-added a forecasting application provides.
<li>Use simulation to analyze howSC randomness or model errors affect a proposed solution. Is it robust? What’s the best solution?

<h3>更多Applications</h3>
<li>Inventory and Supply Chain Analysis</li>
<li>Financial Analysis</li>
<li>Portfolio Analysis</li>
<li>Options Pricing</li>
<li>Traffic Simulation</li>
<li>Airspace Simulation</li>
<li>Service Sector</li>
<li>Health Systems</li>

Health Systems的simulation
<li>Patient Flow in a Hospital</li>
<li>Hospital Room Allocation</li>
<li>Optimization of Doctor / Nurse Scheduling</li>
<li>Procurement of Supplies</li>
<li>Disease Surveillance</li>
<li>Propagation of Disease Spread</li>
<li>Humanitarian Logistics</li>

<h3>Surveilance Application</h3>
• Use simulation to monitor certain time series.</li>
• Predict issues as or before they happen.</li>
• Is a disease in the process ofbecoming an outbreak?</li>
• When is something out of theordinary occurring?</li>
• Take advantage of HUGE data sets.</li>

Dr. Harold Shipman的例子
这个坏人通过篡改遗嘱然后给他的病人heroin overdoses来杀死她们夺财。他篡改记录来显示这些病人需要吗啡，但是软件记录这些修改。
我们这里的目的是讲什么是surveilance application：Surveillance用sequential hypothesis tests。
- Null hypH0 is “no disease” (“no murder”).
- The test statistics有非常难的分布，即使是under H0.
- 使用simulation可以近似null hypothesis的概率分布
- 如果sampling casts doubt on this distribution, then reject.



