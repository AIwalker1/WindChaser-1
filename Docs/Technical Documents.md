In this file we note the basic algorithms for our project.

## Q-Learning
### Reward function
Suppose an agent is refered to one electricity user, who can make decision at each time slot to whether use electricity or not based on his 
judgement on the electricity price right now. He his an objective of minimizing the energy costs through a period of time. Suppose it has a 
state at time $t$ which is denoted by $s_t$, representing how much more electricity he need to use by the end of day. Every time he also needs
to make a decision $a_t \in {0,1}$, which represents his action at each time slot to use electricity of not (in future work, we will consider
change $a_t$ as a continuous variable to denote how much energy it uses at each time). There is also also price signal $p_t$ which
is a stochastic process (for simplicity, we can start from Markov process). Then based on price signal, the user needs to decide if he or she
wants to consume energy at current time slot.

We design the reward function $r(s_t, a_t)$ based on price signal and utility function $U(s_t, a_t)$ which denotes the user's satisfication
level on delaying previous set schedule. For instance, we user's utility is large if it's his/her dinner time and wants to use microware.
Yet the schedule for the washer has a flexible schedule which has a smaller utility. Then we have 

$r(s_t,a_t)=p_t*a_t+U(s_t,a_t)$

### Q table and updates
We start by initializing the table to be uniform (all zeros), and then as we observe the rewards we obtain for various actions, 
we update the table accordingly. We will update the table using the Bellman Equation

$Q(s_t, a_t)=  Q(s_t; a_t) + \alpha [r(s_t; a_t; s_t+1) + \gamma \max_\alpha Q(s_{t+1}; a) - Q(s_t; a_t)]$