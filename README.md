# cs6700-assignment-3--hrl-and-dqn-solved
**TO GET THIS SOLUTION VISIT:** [CS6700 Assignment #3- HRL and DQN Solved](https://www.ankitcodinghub.com/product/cs6700-solved-3/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;117444&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS6700&nbsp;Assignment #3- HRL and DQN Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
&nbsp;

• You have to turn in the well-documented code along with a detailed report of the results of the experiments. Typeset your report in LATEX.

• Be precise with your explanations. Unnecessary verbosity will be penalized.

• Check the Moodle discussion forums regularly for updates regarding the assignment.

• Please start early.

1 Hierarchical Reinforcement Learning

SMDP Q-learning

For this problem, we would be referring to Sutton, Precup and Singh’s 1999 paper on ‘Between MDPs and semi-MDPs : A Framework for Temporal Abstraction in Reinforcement Learning’. Please do read the paper upto and including Section 3, it is self explanatory and a good reference leading up to the understanding and implementation of SMDP Q-learning. Section 3 of the paper first talks about SMDP planning and is a good reading exercise to build the intuition.

We would be working with a simple 4 room grid world environment (explained in the next section). Your task is to implement 1-step SMDP Q learning and intra-option Q learning on this environment.

The Environment

The environment for this task is the following grid world. The cells of the grid correspond to the states of the environment. There are four rooms numbered: 1, 2, 3 and 4. The room number 1 is the one with ‘HALLWAYS’ written in it. The second room is on the right to the first one, and so on. G1 and G2 are the goal states. States G1 and G2 give a reward of +1, transitions to all the other states give a reward of 0. The discount factor is taken to be γ = 0.9.

The actions and the options

There are four primitive actions: up, down, left and right. With probability 2/3, the actions cause the agent to move one cell in the corresponding direction. With probability 1/3, the agent instead moves in the other directions, each one with a probability 1/9. If the agent hits the wall, it remains in the same state.

There are 8 multi-step options : each one leading to a particular room’s hallway. A hallway option’s policy finds the shortest path within the room to its target hallway. The termination condition β(s) for each hallway option is zero for states s within the room and 1 for the states outside the room, including the hallway states. The initiation step I comprises the states within the room plus the non-target hallway state leading to the room.

Figure 1: 4 Room Grid World

The code for the environment is provided in this link.

SMDP Q-learning implementation

Here we implement the single step SMDP Q-learning for each of the goals, as described in section 3.2 of the paper.

A rough sketch of the algorithm is as follows: Given the set of options,

1. Execute the current selected option (e.g. use epsilon greedy Q(s,o)) to termination.

2. Compute r(s,o)

3. Update Q(st,o) using Q-learning update

Questions and deliverables

1. Visualize the learned Q values.

2. Change initial state to the centre of room 4. What do you observe?

3 [Bonus] Implement intra-option Q learning. Do you observe any improvement? Why is that so?

Note: The step function in the environment code provided is not defined for actions in pre-hallway states that do not lead the agent to a hallway state. Please fix this before proceeding.

2 (Not so) Deep RL

Overview

• This assignment requires you to implement and evaluate Q-Learning on a simple control task – the ‘CartPole’ environment.

• The Q-learning algorithm and the nuts and bolts of a Deep Q-Network have been covered in the class, and you have been provided with starter code for this task.

• You do not require a GPU (and hence, AWS) for this task; the DQN can be trained easily within a few minutes on a decent CPU.

Installation

• Install TensorFlow for your machine following the documentation. We recommend using the Virtualenv installation since it provides a virtual and isolated Python environment, incapable of interfering with or being affected by other Python programs, versions, and libraries being used by your other projects on your machine.

Implementation

• Please download the attached starter code. It is written in TensorFlow and gives a brief overview of each step and the flow of the code. While we encourage you to use the given starter template, you do not necessarily have to stick to it – use it as a reference. Feel free to make any design/flow choices that you feel is more appropriate to your methodology.

• An important component of any experiment, especially in Deep Learning, is visualization of some training signals, which serve as an indicator of the health of the experiment, and make it way easier to understand, debug, and optimize TensorFlow codes. TensorBoard, by the creators of TensorFlow, is one such suite of visualization tools. Check out the documentation of the features it offers. The starter code also uses TensorBoard. After setting up TensorBoard on your machine following the aforementioned link, you can point your favourite browser to a local link of the form http://0.0.0.0:6006 to visualize the reward per episode or episode-length. You are also free to use alternative (real-time) plotting methods of your choice.

Expectations

1. Code up the DQN with the experience replay and target network, and turn in the learning curve of episodes on the x-axis versus the average total reward of a 100episode window on the y-axis. The CartPole task is considered ‘solved’ if you get a reward of over 195 for 100 consecutive episodes.

2. Report the set of hyperparameters which work the best for you (even if you could not solve the task). Beware – the search for the right hyperparameters could take longer than the coding up itself. Note that the starter code is initialized with a decent set of hyperparameters.

3. Report any observations or inferences you make regarding the variation of certain hyperparameters like hidden layer size(s), epsilon, minibatch size.

4 [Bonus] Once you find the best set of hyperparameters, try removing the experience replay and/or the target network to see how the learning is affected. Report your observations and inferences.

Submission Guidelines

Submit a single tar/zip file containing the following files in the specified directory structure.

Use the following naming convention: rollno PA3.tar.gz or rollno PA3.zip A sample submission would look like this: rollno PA3

···

···

report.pdf

README
