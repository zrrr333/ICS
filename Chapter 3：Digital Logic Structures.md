# Chapter 3：Digital Logic Structures

## 3.1 MOS transistor

- MOS：金属氧化物半导体

- 分类：P型与N型

  - N型：![image-20210711231050789](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711231050789.png)![image-20210711231350007](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711231350007.png)

  - 性质：给gate提供1.2V电压，Drain和Source通路；给gate提供0V电压，Drain和Source断路

  - P型：与N型相反![image-20210711231515013](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711231515013.png)

    

## 3.2 Logic Gates

3.2.1 The NOT Gate (Inverter)

![image-20210711231757546](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711231757546.png) 



3.2.2 OR and NOR Gates

![image-20210711231911586](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711231911586.png) 

![image-20210711231933113](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711231933113.png) 

3.2.3 Why We Can’t Simply Connect P-Type to Ground

![image-20210711232326743](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711232326743.png) 

晶体管电气特性导致，有0.5V的传输电压



3.2.4 AND and NAND Gates

![image-20210711232524137](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711232524137.png) 

![image-20210711232721473](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711232721473.png) 



3.2.5 Gates with More Than Two Inputs

 ![image-20210711232754863](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711232754863.png)







## 3.3 Combinational Logic Circuits

- two kinds of logic structures：those that include the **storage of information** and those that do not.

- structures that do not store information：**decision elements** or **combinational logic structures** 
  - outputs are strictly dependent on the combination of input values right now，not any past history since no information can be stored internally in a combinational logic circuit.

3.3.1 Decoder

![image-20210711233325413](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711233325413.png) 

- have $n$ inputs and $2^n$ outputs.
- exactly **one** of its outputs is 1 and all the rest are 0s：**assert**
- function：interpret a bit pattern



3.3.2 Mux

![image-20210711233918955](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711233918955.png) 

![image-20210711233937287](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711233937287.png) 

-  $2^n$inputs and *n* select lines
-  The function of a mux is to select one of the inputs and connect it to the output.



3.3.3 A One-Bit Adder (a.k.a. a Full Adder)

![image-20210711234136773](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711234136773.png) 

 ![image-20210711234147956](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711234147956.png)

 ![image-20210711234243363](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711234243363.png)





3.3.4 The Programmable Logic Array (PLA)

![image-20210711234314726](C:%5CUsers%5Chuawei%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20210711234314726.png) 

- program the connections from AND gate outputs to OR gate inputs to implement our desired **logic functions.**



3.3.5 Logical Completeness

- the set of gates *{*AND, OR, and NOT*}* is logically complete because a barrel of AND gates, a barrel of OR gates, and a barrel of NOT gates are sufficient to build a logic circuit that carries out the specification of **any desired truth table.** so to **implement any desired logic function**





## 3.4 Basic Storage Elements

3.4.1 The R-S Latch

![image-20210713095809304](Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713095809304.png) 

 

| S    | R    | output(a) |
| ---- | ---- | --------- |
| 1    | 1    | stay      |
| 0    | 1    | 1         |
| 1    | 0    | 0         |
| 0    | 0    | unknow    |

3.4.2 The Gated D Latch

<img src="Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713100110523.png" alt="image-20210713100110523" style="zoom:67%;" /> 

- WE=0  =>  S=R=1 stay

- WE=1  =>  if D=0, then S=1, R=0, OUTPUT=0

  ​            =>  if D=1, then S=0, R=1, OUTPUT=1

- when WE=1, OUTPUT=D  



## 3.5 The Concept of Memory

3.5.1 Address Space

3.5.2 Addressability

3.5.3 A $2^2$-by-3-Bit Memory

![image-20210713100837986](Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713100837986.png) 





## 3.6 Sequential Logic Circuits

![image-20210713100922162](Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713100922162.png) 

#### 3.6.1 A Simple Example: The Combination Lock

#### 3.6.2 The Concept of State

 *The state of a system is a snapshot of all the relevant elements of the system at the moment the snapshot is taken.*

#### 3.6.3 The Finite State Machine and Its State Diagram: 必考！

- State Diagram

  - ![image-20210713102025124](Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713102025124.png) 

  -  ***Next state function***

    Next State = f(Inputs, State)

    ***Output function* (Mealy)** 

    Outputs = g(Inputs, State)

    ***Output function* (Moore)** 

    Outputs = h(State)

    ![image-20210713102559822](Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713102559822.png) 

    ![image-20210713133852853](Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713133852853.png)

- Clock

  - ![image-20210713101752806](Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713101752806.png)
  -  A clock cycle **starts** when the clock signal transitions from 0 to 1 and **ends** the next time the clock signal transitions from 0 to 1.
  - the **transition** from one state to the next occurs at the **start of each clock cycle.**

- *The Sequential Logic Circuit for the Danger Sign Controller*

  ![image-20210713102846913](Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713102846913.png) 

  - *The Combinational Logic*

     ![image-20210713102916030](Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713102916030.png)

  - *The Two Storage Elements*

    - a problem:  Since the output of a gated D latch changes **immediately** in response to its input if the Write Enable signal is asserted, it cannot be the storage element for our synchronous finite state machine. We need storage elements that allow us to **read the current state throughout the current clock cycle**, and **not write the next state values into the storage elements until the beginning of the next clock cycle.**

      <img src="Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713100110523.png" alt="image-20210713100110523" style="zoom:67%;" /> 

      

    - way: ![image-20210713103427332](Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713103427332.png)

      时钟周期的前半周期，Clock=1，Master的值不会改变，Master的值传递给Slave

      时钟周期的后半周期，Clock=0， Slave的值不变，而Master的值可能改变（由组合逻辑生成的新的状态）

## 3.7 Preview of Coming Attractions:  The Data Path of the LC-3

![image-20210713105401960](Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713105401960.png) 

 ![image-20210713105502467](Chapter%203%EF%BC%9ADigital%20Logic%20Structures.assets/image-20210713105502467.png)

是四个Master-Slave的合体