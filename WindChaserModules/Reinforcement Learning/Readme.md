This is the code for Q learning on managing user electricity scheduling.

## Motivation
Introduce a decision-making pipeline considering forecasts, stochastic process and interaction between users(agents) and electricity price(environments).

## Implementation
For detailed methods and algorithmic implementations, please refer to the technical documentation under DOCs repository.

### Functions

sample_next_action(available_act, current_state, p): *Use epsilon greedy method to update the actions based on Q-value.*


available_actions(state): *Every step check the states to decide if some of the actions are available*

reward(action, state, p_signal): *Define the reward function: composed of price costs plus the user utility function to  denote the user's satisfication level of delayed electricity service*

update_state(current_state, action): *Update the current electricity usage state based on current state and current chosen action*

## References
[1] Sutton, Richard S., and Andrew G. Barto. Reinforcement learning: An introduction. Vol. 1. No. 1. Cambridge: MIT press, 1998.

[2] O'Neill, Daniel, et al. "Residential demand response using reinforcement learning." Smart Grid Communications (SmartGridComm), 2010 First IEEE International Conference on. IEEE, 2010.
