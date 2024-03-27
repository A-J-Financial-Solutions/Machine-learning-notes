## LSTMs Overview

LSTMs (Long Short-Term Memory units) are a type of recurrent neural network (RNN) architecture that addresses the vanishing and exploding gradient problems typical in traditional RNNs. They are designed to remember information for long periods.

### Activation Functions

1. **Sigmoid Activation Function:**

   - Converts any value into a range between 0 and 1.
   - Equation: \( f(x) = \frac{e^x}{e^x + 1} \)

2. **Tanh (Hyperbolic Tangent) Activation Function:**
   - Maps any value into a range between -1 and 1.
   - Equation: \( f(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}} \)

### Long-Term and Short-Term Memories

- The absence of recurrent weights in certain paths of LSTMs allows long-term memories to propagate through time steps without the gradients vanishing or exploding.
- The hidden state represents short-term memories, which are modifiable through weights affecting their contribution to future states.

### LSTM Unit's Operations

1. **First State (Forget Gate):**

   - Determines the percentage of long-term memory to retain.
   - Combines previous short-term memory, current input, and a bias term.
   - Equation for the combined input: \( x=(p \* w_1)+(i \* w_2) + b \)
     - Where \(p\) is the previous short-term memory, \(i\) is the current input, \(w_1\) and \(w_2\) are weights, and \(b\) is the bias.
   - Applies a sigmoid function to this combination to determine the retention rate of long-term memory.

2. **Second State (Input Gate):**

   - Creates potential updates (potential long-term memory) by combining current input and short-term memory.
   - Determines the proportion of this potential update to apply to the actual long-term memory.

3. **Final Stage (Output Gate):**
   - Updates the short-term memory.
   - Applies the tanh function to the new long-term memory to generate potential short-term memory.
   - Uses a sigmoid function to decide the percentage of this potential to be retained.
   - The updated short-term memory also serves as the output for the LSTM unit at this stage.

### Design

![LSTM Architecture Design](../../Images/LSTM/LSTM-architecture.png)

The LSTM architecture's design, featuring gates and modulated weights, enables it to effectively capture and maintain relevant information across long sequences, making it suitable for tasks like sequence prediction, language modeling, and time series analysis.
