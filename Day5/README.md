# Day 5: Optimization in Synthesis
- In this session, we dive into optimization techniques in Verilog synthesis.  
- Topics include the impact of **if-else statements**, **for loops**, and **generate blocks**, along with common pitfalls like **inferred latches**.  
- Hands-on labs are provided to reinforce concepts through practical coding examples.

## 1.🔹 If-Else Statements in Verilog
**Definition:**
if-else statements are conditional constructs used in Verilog to make decisions based on input values. They allow different blocks of code to execute depending on whether a condition is true or false.
**Behavior:**
- if → Executes when the condition is true.
- else if → Checks the next condition if the previous one was false.
- else → Executes when none of the above conditions are true.

**Syntax**
```verilog
if (condition) begin
   // statements executed if condition is true
end
else begin
   // statements executed if condition is false
end
```
**🔹 Nested If-Else Syntax:**
```verilog
if (condition1) begin
   // executes if condition1 is true
end
else if (condition2) begin
   // executes if condition1 is false AND condition2 is true
end
else if (condition3) begin
   // executes if previous conditions are false AND condition3 is true
end
else begin
   // executes if none of the conditions are true
end
```
## 2.Inferred Latches in Verilog
- An inferred latch is unintentionally created during synthesis when a combinational always block does not assign values to an output under all possible conditions.
- The synthesis tool inserts a latch to "remember" the previous value whenever the signal is not explicitly updated.
- This is usually undesired, because latches can cause timing issues and unpredictability in hardware.

### Example of Inferred Latch:
```verilog
module inferred_latch_if (
  input  a,
  input  b,
  output reg y
);
always @(*) begin
  if (a)
    y = b; // Missing else -> when a=0, y is not assigned -> latch inferred
end
endmodule
```
**Problem:**
- When a = 1, y gets assigned b.
- But when a = 0, no assignment happens.
- Synthesizer assumes y must hold its old value → latch inferred.

**Solution 1:** Add an else
```verilog
always @(*) begin
  if (a)
    y = b;
  else
    y = 1'b0;   //  y always gets a value
end
```

**Solution 2:** Default Assignment
```verilog
always @(*) begin
  y = 1'b0;     // default assignment
  if (a)
    y = b;
end
```

## 3. Labs for If-Else and Case Statements
### Lab 1: Incomplete If Statement
```verilog
module incomp_if (input i0, input i1, input i2, output reg y);
always @(*) begin
    if (i0)
        y <= i1;
end
endmodule
```
![ALT](Images/incomplete_if1.png)

### Lab 2: Yosys Synthesis Result of Lab 1
![ALT](Images/incomplete_if_yosys.png)

### Lab3: Nested If-Else
```verilog
module incomp_if2 (input i0, input i1, input i2, input i3, output reg y);
always @(*) begin
    if (i0)
        y <= i1;
    else if (i2)
        y <= i3;
end
endmodule
```
![ALT](Images/incomp_if2.png)

### Lab4: Yosys Synthesis Result of Lab 3
![ALT](Images/incomp_if2_yosys.png)

### Lab 5: Complete Case Statement
```verilog
module comp_case (input i0, input i1, input i2, input [1:0] sel, output reg y);
always @(*) begin
    case(sel)
        2'b00 : y = i0;
        2'b01 : y = i1;
        default : y = i2;
    endcase
end
endmodule
```
![ALT](Images/comp_case1.png)


### Lab 6: Synthesis Result of Lab 5
![ALT](Images/comp_case_yosys.png)

### Lab 7: Incomplete Case Handling
```verilog
module bad_case (
    input i0, input i1, input i2, input i3,
    input [1:0] sel,
    output reg y
);
always @(*) begin
    case(sel)
        2'b00: y = i0;
        2'b01: y = i1;
        2'b10: y = i2;
        2'b1?: y = i3; // '?' is a wildcard; be careful with incomplete cases!
    endcase
end
endmodule
```
![ALT](Images/case1.png)

### Lab 8: Yosys Synthesis:
![ALT](Images/case_yosys.png)

### Lab 9: Partial Assignments in Case
```verilog
module partial_case_assign (
    input i0, input i1, input i2,
    input [1:0] sel,
    output reg y, output reg x
);
always @(*) begin
    case(sel)
        2'b00: begin
            y = i0;
            x = i2;
        end
        2'b01: y = i1;
        default: begin
            x = i1;
            y = i2;
        end
    endcase
end
endmodule
```
![ALT](Images/partial_case.png)



