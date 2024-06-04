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
<h3>system</h3>
A system is __a collection of entities__ (people, machines, etc.) that interact together to accomplish a goal.

<h3>model</h3>
A model is an abstract representation
of a system, usually containing math /
logical relationships describing the
system in terms of states, entities,
sets, events, etc. (terms that we’ll
define below).
<h3>system state</h3>
System state: A set of variables that
contains enough information to
describe the system. Think of the state
as a “snapshot” of the system.
E.g., in a single-server queue, all you
might need to describe the state are:
LQ(t) = # of people in queue at time t
B(t) = 1 [0] if server is busy [idle] at
time t.
<h3>entities</h3>
Entities can be permanent (like a
machine) or temporary (e.g.,
customers), and can have various
properties or attributes (e.g., priority of
a customer or average speed of a
server).
<h3>list</h3>
A list (or queue) is an ordered list of
associated entities (for instance, a
linked list, or a line of people).

<h3>event</h3>
An event is a point in time at which
the system state changes (and
which can’t be predicted with
certainty beforehand).
Examples: an arrival event, a
departure event, a machine
breakdown event.
“Event” technically means the time
that a thing happens, but loosely
refers to “what” happens (an
arrival).

<h3>activities</h3>
An activity is a duration of time of
specified length (aka an
unconditional wait).
Examples include:
• exponential customer interarrival
times
• constant service times
We can explicitly generate those
events, so they are “specified”.

<h3>conditional wait</h3>
A conditional wait is a duration of
time of unspecified length.
E.g., a customer waiting time — we
don’t know that directly. In fact, we
just know arrival and service times
and will use those to reverseengineer
the waiting times.











<h2></h2>
<h2></h2>
<h2></h2>
