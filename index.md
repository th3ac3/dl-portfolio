# Mini-CPU

**Robert Allen**

**ECEN 2350: Digital Logic, Spring 2018**

**Software: Quartus**

**Hardware: DE10-Lite Board**

### Introduction

In this project I create a mini-cpu using verilog HDL. I will design it to be able to perform some very basic arithmetic, logical, and comparison operations with 4-bit words. The project will also be used to demonstrate my knowledge of verilog by utilizing many of the different features and keywords that it offers. In this project there are four modes; arithmetic mode, logical mode, comparison mode and magic mode. The modes can be selected by utilizing the buttons on the DE10-Lite board. Each of the modes, except magic, will have four different operations that can be done in that mode. Arithmetic mode will have addition, subtraction, multiply by two, and divide by two operations. Logical mode will have and, or, exor, and not logical operations. Comparison mode will have equal to, greater than, less than, and max comparison operations. The different operations of each mode can be selected by using SW8 and SW9 on the board.

![Block Diagram]({{ "/images/block_diagram.png" | absolute_url }})

### Results

The CPU modules (Arithmetic, Logical, Comparison, Magic) all take in input from Project1_top. We use switches SW0-7 to determine number input to the modules. CLK is used in the magic module to determine timing of the Knight Rider display. KEY0 and KEY1 are used to select which logic module to use. Switches SW8 and SW9 are used to select which operation within the logic module we would like to use. You can see the mapping for this in the truth table below. We then pass the results of logic modules selection to the multiplexer module. We also pass in our displays HEX0 and HEX1 as well as our LEDS LEDR0-9. The binary output of the logic modules will be displayed on the seven segment displays and the LEDs. SevenSegment is responsible for mapping our binary number into a hexadecimal digit on the displays.

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

X gets it's value from switches SW7-4

Y gets it's value from switches SW3-0

Z gets it's value form switches SW7-0

#### Arithmetic Operations

x = 0xA y = 0x7 z = 0xA7

##### Addition
![Addition]({{ "/images/add.jpg" | absolute_url }})

##### Subtraction
![Subtraction]({{ "/images/sub.jpg" | absolute_url }})

##### Multiply By 2
![Multiply By 2]({{ "/images/mult.jpg" | absolute_url }})

##### Divide By 2
![Divide By 2]({{ "/images/div.jpg" | absolute_url }})

#### Logical Operations

x = 0xA y = 0x7 z = 0xA7

##### AND
![AND]({{ "/images/and.jpg" | absolute_url }})

##### OR
![OR]({{ "/images/or.jpg" | absolute_url }})

##### EXOR
![EXOR]({{ "/images/exor.jpg" | absolute_url }})

##### NOT
![NOT]({{ "/images/not.jpg" | absolute_url }})

#### Comparison Operations

x = 0x8 y = 0x7

##### Equal To
![Equal To]({{ "/images/equal.jpg" | absolute_url }})

##### Greater Than
![Greater Than]({{ "/images/greater.jpg" | absolute_url }})

##### Less Than
![Less Than]({{ "/images/less.jpg" | absolute_url }})

##### Max
![Max]({{ "/images/max.jpg" | absolute_url }})

#### Magic (Knight Rider Pattern)

<video src="images/magic.mp4" controls="controls" muted="muted" style="max-width: 100%" type="video/mp4"></video>

### Conclusion

This was a very interesting project. It was interesting to think about how to do each operation given the unique constraints that each was under. Probably one of the hardest parts was determining the output of max bit by bit rather than by comparing the numbers using > and <. Another difficult challenge was making everything in the Logical module use continuous assignment. This made it difficult to select which opertion in the module should be outputed from the module. We ended up using the operation passed in from SW8 and SW9 and expanding them to masks to filter out results from operations that weren't selected. If I had to do something differently next time I would likely not have a multiplexer module. That module was not doing anything that couldn't have more simply been done in the Project1_top module. It only served to complicate the design.
