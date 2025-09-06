# POLICY EVALUATION

## AIM
To develop a Python program to evaluate the given policy.


## PROBLEM STATEMENT
To find best policy from two policies which are defined by user using policy evaluation function. Where the mdp includes 16 states from 0-15, 0 is the starting state, assigning some 4 random state as holes and 15 is the goal state and then we need to calculate optimal state value function for each state such that we can reach goal using optimal policy using policy evaluation.


## POLICY EVALUATION FUNCTION
```
def policy_evaluation(pi, P, gamma=1.0, theta=1e-10):
    prev_V = np.zeros(len(P), dtype=np.float64)
    # Write your code here to evaluate the given policy
    while True:
      V = np.zeros(len(P))
      for s in range(len(P)):
        for prob, next_state, reward, done in P[s][pi(s)]:
          V[s] += prob * (reward + gamma *  prev_V[next_state] * (not done))
      if np.max(np.abs(prev_V - V)) < theta:
        break
      prev_V = V.copy()
    return V
```


## OUTPUT:
<img width="695" height="551" alt="image" src="https://github.com/user-attachments/assets/5568438e-bfd5-4ede-9b03-98241e951c47" />
<img width="598" height="574" alt="image" src="https://github.com/user-attachments/assets/41d2e88d-624c-4280-ad16-51f282e7f213" />
# State Value Function
<img width="570" height="380" alt="image" src="https://github.com/user-attachments/assets/20ec5a6c-502a-43c6-86a7-23abc0e5645f" />
# Best Policy
<img width="705" height="184" alt="image" src="https://github.com/user-attachments/assets/c88fd9ad-f08f-4479-90f6-cd108dd132b1" />







## RESULT:
Thus, The Python program to evaluate the given policy is successfully executed.
