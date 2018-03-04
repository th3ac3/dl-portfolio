# Mini-CPU

**Robert Allen**

**ECEN 2350: Digital Logic, Spring 2018**

**Software: Quartus**

**Hardware: DE10-Lite Board**

### Introduction

In this project I create a mini-cpu using verilog HDL. I will design it to be able to perform some very basic arithmetic,
logical, and comparison operations with 4-bit words. The project will also be used to demonstrate my knowledge of verilog by
utilizing many of the different features and keywords that it offers. In this project there are (3 MAYBE 4) modes; arithmetic mode,
logical mode, and comparison mode. The modes can be selected by utilizing the buttons on the DE10-Lite board. Each of the modes
will have four different operations that can be done in that mode. Arithmetic mode will have addition, subtraction, multiply by
two, and divide by two operations. Logical mode will have and, or, exor, and not logical operations. Finally, comparison mode will
have equal to, greater than, less than, and max comparison operations. The different operations of each mode can be selected by
using SW8 and SW9 on the board.

The CPU modules (Arithmetic, Logical, Comparison) all take in input from Project1_top. We use keys SW0-7 to determine number input
to the modules and we use ke We then pass the results of this to the multiplexer module. We also pass KEY0-1 and SW8-9 to the
multiplexer so that it can select the result that we have selected. It then passes these values to SevenSegment to display on HEX0
and HEX1.


### Results

### Mode and Operation Truth Tables

| KEY1 KEY0 | Mode          |
|:---------:|:-------------:|
| 00        | Arithmetic    |
| 01        | Logical       |
| 10        | Comparison    |
| 11        | Magic         |

| SW9 SW8   | Arithmetic    | Logical | Comparision |
|:---------:|:-------------:|:-------:|:-----------:|
| 00        | Add           | AND     | EQUAL       |
| 01        | Subtract      | OR      | GREATER     |
| 10        | Multiply-By-2 | EXOR    | LESS-THAN   |
| 11        | Divide-By-2   | NOT     | MAX         |

### Pictures

Note:

1010 in binary is A in Hexadecimal

0111 in binary is 7 in Hexadecimal

1000 in binary is 8 in Hexadecimal

#### Arithmetic Operations 

##### Addition
![Addition]({{ "/images/add.jpg" | absolute_url }})

##### Subtraction
![Subtraction]({{ "/images/sub.jpg" | absolute_url }})

##### Multiply By 2
![Multiply By 2]({{ "/images/mult.jpg" | absolute_url }})

##### Divide By 2
![Divide By 2]({{ "/images/div.jpg" | absolute_url }})

#### Logical Operations

##### AND
![AND]({{ "/images/and.jpg" | absolute_url }})

##### OR
![OR]({{ "/images/or.jpg" | absolute_url }})

##### EXOR
![EXOR]({{ "/images/exor.jpg" | absolute_url }})

##### NOT
![NOT]({{ "/images/not.jpg" | absolute_url }})

#### Comparison Operations

##### Equal To
![Equal To]({{ "/images/equal.jpg" | absolute_url }})

##### Greater Than
![Greater Than]({{ "/images/greater.jpg" | absolute_url }})

##### Less Than
![Less Than]({{ "/images/less.jpg" | absolute_url }})

##### Max
![Max]({{ "/images/max.jpg" | absolute_url }})

#### Magic (Knight Rider Pattern)

##### Magic
<video src="images/magic.mp4" controls="controls" muted="muted" style="max-width: 100%" type="video/mp4"></video>

### Conclusion
