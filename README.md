Download Link: https://assignmentchef.com/product/solved-cs2040s-recitation-1-2
<br>
<em>Goal: </em>Think about what goes into specifying an algorithm precisely, and how to come up with appropriate metrics. In real-world problems, the correctness of your proposed algorithm depends a lot on how you formulate the problem and how your solution is justified in solving it. Feel free to be creative!

To help you develop some intuitions for this problem, you might be interested in playing with this lift simulation game: <a href="https://play.elevatorsaga.com/">https://play.elevatorsaga.com/</a><a href="https://play.elevatorsaga.com/">.</a> The only caveat here is that it is designed for Javascript programming, which is not Java — the language of instruction for this module.

Before we begin, let’s first introduce 2 important concepts. <em>Abstract Data Type </em>(ADT) is a data type specification which details the permitted values, supported operations and behaviors of the supported operations. In other words, it captures the set of behaviours from the perspective of you the programmer interacting with the data type. Sounds familiar? The Java Interface is one way to specify ADTs!

ADTs are technically different from <em>Data Structures </em>(DS), which are concrete representations of data. Typically DS details how an ADT is realized in implementation. In other words, DS is a specification from the point of view of an implementer, not a user. As an example, the stack ADT can be implemented using Array or Linked List DSes. Think of a DS as the actual Java class which implements some ADT interface(s).

One of the ADTs relevant to this problem is the <em>queue </em>which imposes a First-in-First-Out (FIFO) policy on its data membership (just like a queue in real life). The queue ADT is specified by the following semantics:

<table width="623">

 <tbody>

  <tr>

   <td width="93"><strong>Operation</strong></td>

   <td width="531"><strong>Behaviour</strong></td>

  </tr>

  <tr>

   <td width="93">enqueue(v)</td>

   <td width="531">Insert an element v at the rear of queue</td>

  </tr>

  <tr>

   <td width="93">dequeue()</td>

   <td width="531">Remove and return the frontmost item in queue. If queue is empty, return NULL</td>

  </tr>

  <tr>

   <td width="93">peek()</td>

   <td width="531">Return the frontmost item in queue without removing it. If queue is empty, returnNULL</td>

  </tr>

 </tbody>

</table>

Note that for queues, enqueue is sometimes called push or offer, dequeue is sometimes called pop or poll.

Another similar ADT is the <em>deque </em>(often pronounced “deck” so as not to be confused with dequeue) which is a double-ended queue. The deque ADT is specified by the following semantics:

<table width="623">

 <tbody>

  <tr>

   <td width="114"><strong>Operation</strong></td>

   <td width="510"><strong>Behaviour</strong></td>

  </tr>

  <tr>

   <td width="114">push front(v)</td>

   <td width="510">Insert an element v at front of deque</td>

  </tr>

  <tr>

   <td width="114">push back(v)</td>

   <td width="510">Insert an element v at the rear of deque</td>

  </tr>

  <tr>

   <td width="114">pop front()</td>

   <td width="510">Remove and return the frontmost item in deque. If deque is empty, returnNULL</td>

  </tr>

  <tr>

   <td width="114">pop back()</td>

   <td width="510">Remove and return rearmost item in deque. If deque is empty, return NULL</td>

  </tr>

  <tr>

   <td width="114">peek front()</td>

   <td width="510">Return the frontmost item of deque without removing it. If deque is empty, return NULL</td>

  </tr>

  <tr>

   <td width="114">peek back()</td>

   <td width="510">Return the rearmost item of deque without removing it. If deque is empty, return NULL</td>

  </tr>

 </tbody>

</table>

Note that for deques, push front is sometimes called push, pop front is sometimes called pop, push back is sometimes called inject and pop back is sometimes called eject.

<strong>Problem 1.a. </strong>Consider how lifts operate. What is the algorithm deciding which floor a lift should go next? Now imagine you are writing the (embedded) controller for the lift and have to implement such an algorithm. Write the pseudocode for the algorithm, being sufficiently precise in specifying exactly what the lift should do at every instance.

<em>ProTip: </em>Don’t try to solve every aspect of the problem from the get-go! Start by solving the most important aspect of the problem in the simplest scenario and come up with the most naive working solution you can think of. Thereafter, gradually build upon that basic working solution to incorporate more complexities. Be patient! Good solutions take many iterations to get right and you may even have to redefine the problem and start over when you discover deeper problem insights along the way!

<em>Guiding questions:</em>

<ul>

 <li>What is the problem you are trying to solve?</li>

 <li>What are the inputs (knowns) and outputs (unknowns)?</li>

 <li>What are some problem scenarios?</li>

 <li>What internal state does the lift need to maintain?</li>

 <li>Which DS/ADTs we have learnt so far (i.e. arrays, queues, stacks) should we use to store and manage the state?</li>

 <li>What are the invariants: the relationships between variables?</li>

 <li>What are the corner cases for your proposed algorithm and how should you handle them?</li>

 <li>What are the strengths and weakness of your proposed algorithm? Which are the ideal scenarios where it performs optimally and which are the adversarial scenarios where it will perform the worst?</li>

 <li>What is the worst time complexity of your algorithm?</li>

</ul>

<em>Did you know?  </em>In magnetic hard drives, the elevator algorithm (a.k.a. SCAN) is actually used to determine which disk sector to move the read/write arm to.       Read more at <a href="https://en.wikipedia.org/wiki/Elevator_algorithm">https: </a><a href="https://en.wikipedia.org/wiki/Elevator_algorithm">//en.wikipedia.org/wiki/Elevator_algorithm</a><a href="https://en.wikipedia.org/wiki/Elevator_algorithm">.</a>

<strong>Problem 1.b. </strong>If we want to evaluate how good our elevator algorithm is, what metrics should we use? Realize that when evaluating an algorithm, it isn’t always obvious what metrics we care about, and you have to think hard to make sure you are optimizing the right thing!

<em>ProTip: </em>The choice of metrics should provide an good measure of how well the chosen objective is met. Metrics therefore drives the solution. You may be looking at multiple metrics at once, which is in the case where you are optimizing for multiple objectives. Often times, a single total metric can be obtained by linearly combining multiple metrics via weighing the relative importance of the objectives they correspond to.

<strong>Problem 1.c.   </strong>How could you design elevators to work better? What would a better algorithm look like? What additional data or inputs would you need? How would you test your solution? If you were to simulate it, how would you program the simulator? The latter is more an exercise in OOP, so not as critical in the context of this module.

<strong>Problem 1.d. </strong>In your groups, discuss how you might implement a queue ADT in Java using an <strong>array</strong>. For now, assume that the queue will have at most <em>M </em>items. Is there anything else you want as part of your queue interface? What are the corner cases and how exactly do you want it to behave in those corner cases? What about implementing a deque with an array?