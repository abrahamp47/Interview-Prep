2024-11-01 11:26

Status:

Tags:

# Backtracking

Fundamental key of Backtracking -
1. you make choices
2. you have constraints on the choices
3. you have a goal to achieve

CHOICE

We have to think about the core choice we make at each step.

### Algorithm Steps[​](https://carefree-ladka.github.io/js.enigma/docs/tutorial-basics/Backtracking#algorithm-steps "Direct link to Algorithm Steps")

1. **Choose**: Select an option from the available choices.
2. **Explore**: Move to the next state or option based on the current choice.
3. **Check**: Determine if the current state meets the constraints or criteria of the problem.
4. **Backtrack**: If the current solution path does not meet the criteria, revert to the previous state and try the next option.

```javascript
/**
 * Solve [Problem Description] using Backtracking.
 * @param {Type} [parameterName] - [Description of the parameter]
 * @return {Type} - [Description of the return value]
 */
const [functionName] = ([parameters]) => {
  const result = [];
  
  const backtrack = (currentState) => {
    // Base case: Check if current state meets the criteria
    if ([condition]) {
      result.push([solution]);
      return;
    }
    
    // Iterate through options and recurse
    for (const option of [options]) {
      if ([isValid](option)) {
        // Make a choice
        [updateState](option);
        
        // Recur to explore the next step
        backtrack([newState]);
        
        // Undo the choice (backtrack)
        [revertState](option);
      }
    }
  };

  backtrack([initialState]);
  return result;
};

// Example usage:
console.log([functionName]([testParameters]));
/* Output:
[Expected output]
*/

```
Generate All, Compute All means that backtracking is the solution



# References


