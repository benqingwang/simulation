<h2>1. 什么是simulation?</h2>
simulation是solve model的一个方法。所以我们先看什么是model: model is a high-level representation of the operation of a real-world process. 那么solve model有3种方法：
- analytical methods: 就是通过解方程那种方式解决的.比如我从山上扔一个石头出去，我想知道它的落点，这个可以用物理公式计算出来。这种就是analytical methods。
- numerical methods: 不是closed-form的，比如预测天气，可能要用很多微积分，这种是numerical.
- simulation method: 如果这个过程有randomness，那么上面2种可能就都不好使，那么我们可以用similation. 

所以simulation的定义是: the imitation of a real-world process or system over time. 它包含: 
<li>generation of an artificial history </li>
<li>to draw inferences </li>
<li>concerning the operating characteristics of the real system that is represented.</li>
所以这里关键字是<strong>inferences</strong>，simulation的结果是一个inferences。

<h3>本课关注的model类型</h3>
<li>Discrete (vs. continuous)</li>
<li>Stochastic (vs. deterministic)</li>
<li>Dynamic (vs. static)</li>

<h2>2. simulation的应用</h2>
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

<h2> 3. simulation的优缺点</h2>
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

<h2>4. Simulation的历史</h2>
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

<h2>5. Simulation的Actual Applications</h2>
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

<h3>Health Systems的simulation</h3>
<li>Patient Flow in a Hospital</li>
<li>Hospital Room Allocation</li>
<li>Optimization of Doctor / Nurse Scheduling</li>
<li>Procurement of Supplies</li>
<li>Disease Surveillance</li>
<li>Propagation of Disease Spread</li>
<li>Humanitarian Logistics</li>

<h3>Surveilance Application</h3>
<li>Use simulation to monitor certain time series.</li>
<li>Predict issues as or before they happen.</li>
<li>Is a disease in the process ofbecoming an outbreak?</li>
<li>When is something out of theordinary occurring?</li>
<li>Take advantage of HUGE data sets.</li>

Dr. Harold Shipman的例子
这个坏人通过篡改遗嘱然后给他的病人heroin overdoses来杀死她们夺财。他篡改记录来显示这些病人需要吗啡，但是软件记录这些修改。
我们这里的目的是讲什么是surveilance application：Surveillance用sequential hypothesis tests。
<li>Null hypH0 is “no disease” (“no murder”).</li>
<li>The test statistics有非常难的分布，即使是under H0.</li>
<li>使用simulation可以近似null hypothesis的概率分布</li>
<li>如果sampling casts doubt on this distribution, then reject.</li>

<h2>6. Baby Examples</h2>
<h3>用simulation来回答问题: 至少要多少个人参加一个party才能保证至少50%的概率能有2个人同一天生日</h3>
这个问题我可以用P(至少2个人同一天生日)= 1 - P(没有任何人同一天生日)>=50%来解
转化为 P(没有任何人同一天生日)<=0.5，即P_365^n/(365^n)<=0.5，可以解出n>=23
老师用simulation来做，结果的平均值是23。我们可以用Python
import math
for n in range(20,30):
    print(f"n={n}")
    print(f"p={math.factorial(365)/math.factorial(365-n)/365**n}")
    
<h3>用simulation来估计pi的值</h3>
这个simulation解法是弄一个1*1的正方形，然后做一个内切圆。这样圆的面积就是pi*(0.5)^2 = pi/4. 
现在我们往正方形里面随机扔点点，根据概率，扔进圆圈的概率是圆的面积除以正方形的面积也就是 pi/4
所以我们拿这个概率乘以4，就可以估计pi的值。老师展示的例子很有趣，我们simulate的次数多的时候反而离真实值远一点。

<h3>用simulation来估计f(x)=sin(pi*x)的在[0,1]上的积分</h3>
<li>这个simulation的方法是Sample n个长方形。</li>
<li>每个长方形的宽度是1/n，位置是random选在的[0,1]之间的数x，高度就是sin(pi*x)。这样我们可以计算这个长方形的面积。</li>
<li>现在把n个长方形的面积加在一起得到一个total,这个total就是估计的积分值。当n很大时，这个估计的积分值就很接近理论值</li>

<h3>Good and Bad generator</h3>
这个例子展示了如果一个random generator不好的话，可能会什么样，老师的例子是个可爱多花心筒的样子

<h3>wendys 排队问题</h3>
这个例子是假设快餐店只有一个点餐台的简单情况，顾客的到来，服务的时间都是随机变量，我们可以simulate等待时间和queue长度，server utilization等等指标

<h3>股市simulation</h3>
假设t0有一定本钱，有一个portfolio里面有不同行业的return的平均值和方差，simulate 5年后我的钱

<h3>Random Walk</h3>
Take a normal step up or down every time unit and plot where you are as time progresses.
此 “random walk” converges to Brownian motion.
Einstein 和 Black+Scholes won Nobel Prizes for this research.

<h2>7. Randomness</h2>
<h3>怎么产生PNR</h3>
我们平时说的random number其实通常都是deterministic的方法产生的，所以不是真正的random，是pseudo-random number (PRN)。有很多种方法，老师这里说的是Linear Congruential Generator
步骤就是:
<ol>
<li>选一个我们常说的random seed，是个正整数</li>
<li>计算第一个PRN (pseudo数: X(i) = a*X(i-1) mod(m) 这个意思是把seed乘以a然后求除以m的余数。这里a和m一般都是很大的常数质数。mod读作modulus</li>
<li>后面的依次产生更多PRN。当然这些都是余数肯定是整数，所以我们要除以m得到一个0，1之间的数: U(i) = X(i)/m</li>   
</ol>

<p>老师给了一个简单的Pretend Example:</p>
Start with X(0) = 4 (for no reason) – Set X(i) = 5 X(i-1) mod(7) 
Then X(1) = 20 mod 7 = 6
X(2) = 2, X(3) = 3, X(4) = 1, X(5) = 5, etc.
So U(1) = X(1)/m = 6/7
U(2) = 2/7, U(3) = 3/7, etc.

<p>老师给了一个Real Example</p>
• X(i) = 16807 X(i-1) mod(2^31 -1)
• U(i) =X(i) /m
这个generator被应用于很多simulation languages，它有很多优点，比如long “cycle times”，但是也有更好的generators are out there

<h3>怎么产生其他Other RV’s</h3>
<ol>
<li> 思路就是所有这些分布的CDF (F(X))都是服从0~1上均匀分布的。比如我想能得到服从exponential distribution的随机数F(x)=1-e^(-λx)，现在我generate一个0,1之间的Ui来代表我们抽中的CDF值，就是1-e^(-λx)=U_i。变形我们有x=(-1)/λ ln(1-U_i )所以我把得到的随机数Ui带进去就是服从指数分布的x. 
<li>首先我们得到一个0，1之间的PNR： U(i) ~ Unif(0,1)</li>
<li>Apply some appropriate transformation：这是如何generate一个服从exponetial distribution的PRN: -(1/λ) ln(U(i)) ~ Exp(λ) </li>
<li>这叫做Inverse transform method，可以用于其他important distributions</li>   
<li> 还有其他更sophisticated的方法比如Box-Muller method for normals</li>
</ol>

<h2>8. Simulation Output Analysis</h2>
<p>既然simulation的input是随机的，那output就是也是random，因此output需要careful analysis。注意simulation output既不是independent也不是normal，所以我们需要用新的方法.
用快餐店的客户等待时间为例子，它不是normally distributed，通常是skewed；也不是identically distributed，通常correlated，而且patterns change during the day，所以我们不能用usual stat来分析。</p>

<p>我们有2个general cases： 一个是Terminating Simulations一个是Steady-State Simulations</p>
<ol>
<li>Terminating Simulations适用于我们想了解short-term behavior, 比如想了解一天之内客户的平均等待时间，一场pandemic里平均的感染人数。通常通过indepdent replciation来分析。每次replication的condition都是一样的，然后sample means from each replication可以被认为是iid,然后我们就可以用我们学的baby stat来分析</li>
<li>Steady-State Simulations适用于我们想了解long-term behavior，比如Long-running assembly line。我们需要明白一点，我们的initialization是有bias的，所以这个方法是要先"warm up" simulation before collecting data。Many methods for dealing with steady-state data（Batch Means， Overlapping Batch Means /Spectral Analysis， Standardized Time Series， Regeneration）。这里面batch mean的方法是【1】Make one long run (vs. many shorter reps)【2】Warm up simulation before collecting data【3】Chop remaining observations into contiguous batches【4】Sample means from each batch are approximately i.i.d. normal【5】Use classical statistics on the i.i.d. batch means</li>
</ol>
