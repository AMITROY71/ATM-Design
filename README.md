# ATM-Design
The inputs of the FSM are taken as input to the code  and the output is taken as ‘z’. In the input, pin entered is of 4-bits and the amount
entered for both deposit and withdraw is of 16-bits which are declared as ‘Logic’. The output isdeclared as the ‘Logic’ which is of four
states 0, 1, x and z. This data type is identical to reg data type and is a user defined vector size. 
Totally three always blocks are used in the code in which two are sequential and one is combinational. Always block can be used to infer 
the combinational and sequential logic respectively. In first always block, if reset signal is set the signal will goes to ‘scan card’ 
state else goes to next state. Second always block represents the state machine operation and hence if the input signal is high, control 
signal will goes to next state else will goes to the previous state i.e. corresponding state respectively. 
The sensitivity list has ‘negedge clk’ which represents that the change takes place at every negative edge of the clock signal. Here the 
counter is installed which will be counting the entering of invalid pin. If it exceeds three times, the account gets locked and the signal
will return to initial state and resets the counter. The (ipin_count) ‘Invalid pin count’ is declared as a ‘logic’ data type is used to 
increment the count. An addition operation is used in the verify state after which the entered amount gets added with previous balance. 
Similarly, a subtraction operation is performed for withdraw operation in order to subtract the entered amount with the previous balance.
If the net balance is larger than 16-bits, then the transaction will become invalid. In third always block, the output are declared with
respect to the state. Once the balance gets updated, the output signal is made to high.
