# Chapter 4:The von Neumann Model

## 4.1 Basic Components

 ![image-20210711235112504](Chapter%204The%20von%20Neumann%20Model.assets/image-20210711235112504.png)



### 4.1.1 Memory

-  today’s computer systems : **$2^{34}$** by 8 bits，$2^{34}$ distinct memory locations, each of which is capable of storing 8 bits of information.**an *address* *space*** of $2^{34}$ uniquely identifiable locations, and **an *addressability*** of eight bits.
- with *k* bits, we can represent uniquely $2^k$ items. Thus, to uniquely identify $2^{34}$ memory locations, each location must have its own 34-bit address. 
-  the memory address space of the LC-3 is $2^{16}$, and the addressability is 16 bits.
- **MDR** and **MAR** :  two characteristics of a memory location: **its address** and **the data stored there.**
- read & write : both first MAR , then MDR

### 4.1.2 Processing Unit

- The simplest processing unit:  **ALU**   Arithmetic and Logic Unit
- **word length**: the ALU normally processes data elements of a fixed size. The data elements are called **words.**

- temporary storage for storing the result: a set of **registers**( the size of each register = the size of values processed by the ALU)


### 4.1.3 Input and Output

### 4.1.4 Control Unit

- the conductor of an orchestra:  where we are within **the process of executing the program** and where we are in **the process of executing each instruction.**
- **IR:** **instruction register** :contain that instruction.
- **PC: program counter**: instruction pointer  “pointing” to the **next instruction** to be processed.



## 4.2 The LC-3: An Example von Neumann Machine

![image-20210712001643296](Chapter%204The%20von%20Neumann%20Model.assets/image-20210712001643296.png) 

- Filled-in arrowheads : data elements 

   Not-filled-in arrowheads : control signals 

- **MEMORY**: MAR contains 16 bits: the memory address space of the LC-3 is $2^{16}$memory locations. MDR contains 16 bits, each memory location contains 16 bits , **16-bit addressable**.

- **INPUT/OUTPUT**: keyboard: KBDR&KBSR  monitor: DDR&DSR

- **THE PROCESSING UNIT**: functional unit (ALU) performs arithmetic and logic operations and 8 registers (R0, … R7) for storing temporary values 

- **THE CONTROL UNIT** : FSM: clock cycle by clock cycle

  CLK、PC、IR



## 4.3 Instruction Processing

### 4.3.1 The Instruction

- the *opcode* and the *operands*

- three kinds of instructions: *operates*, *data movement*, and *control*

  - **Operate**： ADD AND NOT
  - **Data movement**： processing unit 、memory 、input/output devices
    - 要有一个概念：CPU不能直接对内存中的数据进行计算，所以只能通过数据转移指令先挪到寄存器中，再计算
  - **Control**

- An LC-3 instruction ：16 bits (one word), numbered from left to right, bit [15] to bit [0]. 

  - Bits [15:12] contain the opcode. 

  - Bits [11:0] where the operands are

  - ADD ![image-20210712003036553](Chapter%204The%20von%20Neumann%20Model.assets/image-20210712003036553.png)

    

  - AND ![image-20210712003120188](Chapter%204The%20von%20Neumann%20Model.assets/image-20210712003120188.png)

  - LD ![image-20210712003239932](Chapter%204The%20von%20Neumann%20Model.assets/image-20210712003239932.png)



### 4.3.2 The Instruction Cycle (NOT the Clock Cycle)

 The instruction cycle consists of 6 sequential *phases*, each phase requiring zero or more steps. 

![image-20210712003425675](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210712003425675.png) 

####  4.3.2.1 FETCH

Step 1: MAR <- PC, and **increment the PC.**

Step 2: MDR<- the instruction

Step 3: IR <- MDR

the amount of time taken by each machine cycle is one clock cycle. In fact, we often use the two terms interchangeably. **Step 1** takes **one** clock cycle. **Step 2** could **take one clock cycle or many clock cycles,** depending on how long it takes to access the computer’s memory. **Step 3** takes **one clock cycle**. 

#### 4.3.2.2 DECODE

Input : four-bit opcode IR [15:12]. 

Output line asserted is the one corresponding to the opcode at the input.

#### 4.3.2.3 EVALUATE ADDRESS

#### 4.3.2.4 FETCH OPERANDS

#### 4.3.2.5 EXECUTE

#### 4.3.2.6 STORE RESULT



### 4.3.3 Changing the Sequence of Execution

- Control instructions : loading the PC during the **EXECUTE** phase, wipes out the incremented PC that was loaded during the **FETCH** phase. 
- BR: ![image-20210712151413003](Chapter%204The%20von%20Neumann%20Model.assets/image-20210712151413003-1626188260504.png)
- condition code： NZP
-  <img src="Chapter%204The%20von%20Neumann%20Model.assets/image-20210713123946312.png" alt="image-20210713123946312" style="zoom: 67%;" />



### 4.3.4 Control of the Instruction Cycle

 ![image-20210712152332115](Chapter%204The%20von%20Neumann%20Model.assets/image-20210712152332115.png)

-  each state corresponds to one machine cycle of activity that takes one clock cycle to perform.

## 4.4 Our First Program: A Multiplication Algorithm

![image-20210713111821499](Chapter%204The%20von%20Neumann%20Model.assets/image-20210713111821499.png) 

 ![image-20210713124030557](Chapter%204The%20von%20Neumann%20Model.assets/image-20210713124030557.png)

.orig x3000