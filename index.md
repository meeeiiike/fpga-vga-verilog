---
layout: home
title: FPGA VGA Driver Project
tags: fpga vga verilog
categories: demo
---

Hello! This is my page for my fpga-vga-driver project.

## **Template VGA Design**
### **Project Set-Up**
We were given some code templates to start such as colour stripes/cycle, VGATop, Constarints file and Testbench! These templates got us up and running, with all the timing needed for our 640 by 480 dislpay. Using the 100Mhz Oscillator on the chip we brought that down to a 25Mhz clk frequency (Using Clk wiz in IP catalog) which is used in the sync. This is how it knows when to draw the rows and columns, and obviously for the cycle aswell its quite important. Colour Cycle uses this timing to cycle through the colours lncluded quite fast, around twice a second, while stripes divided the screen in columns of 80 pixels, each column a different colour.

With all the templates, minimal change was made, especially with the timing and sync. From what i understand from lectures and praticals: A hsync signal goes enables pixels to be drawn each row, with some deadband periods on either end (back/front porch), while the vsync signal goes high for a period of 1 frame, with the same deadbands. After 1 frame, row & col are reset to (0,0). I believe this is called 'Raster'.

// REMOVE/EDIT
<img width="1131" height="624" alt="image" src="https://github.com/user-attachments/assets/b1a8cf5e-bd37-45f6-a3fa-c9fc8e8b325b" />
//

### **Template Code**
VGA_Sync -> Controls the timing signals for our 640 by 480 display, using the 25Mhz clock set in Ip Catalog. Takes in 25Mhz clk signal, reset and outputs hsync, vsync, vid_on as well as Row and Col signals. Also defines high an low limits (deadband).

VGA_Top -> This module instantiates the ColorCycle/Stripes, sync and clk_wiz modules and assigns the rgb values only if vid_on signal is true. Takes in clk and reset, outputs hsysnc, vsync  the colours RGB signals (VGA_RED[3:0]) etc...

Colour_Stripes -> Uses the columns to define 80 pixel towers essentially of different colours, from black to white. Includes a few condtional statements to assigns values inside always block.

Colour_Cycle -> Cycle uses timing signals to change the colour displayed often. Colours are listed as variables and a counter is used to iterate through all them in a case statement.

### **Simulation**
Unfortunately, as shown in the screenshot i had some issues with my timing, aswell as my simulation. I beleive its due to my huge combinational logic in my colour module. Anyways, if i could get it working normally, i could use it to check all signals are coming in as expected. Using simulation we can make sure our display is drawing correctly using the signals coming in.
### **Synthesis**
Using Synthesis, it takes our code and creates an optimised hardware schematic diagram with the likes of registers, Look up tables flip flops etc... Then implementation takes this design and places it on the FPGA itself! This diagram shows the actual board we're using and shows all the connections!
So from what i understand, this tool is extremely useful as we can test and simulate deigns from a low level, we can sythesise to see our deisgn on hardware, then implement the design onto the Basys3 Board! 

## **My VGA Design Edit**
I decided to go with a design true to heart... i spent years of my life creating pixel art inside of video games like minecraft making pictures of characters such as mario, so it only made sense to go with mario :D 
At first i wanted to create an image similar to what i currently have, and modify it a little so i could make 2 or 3 scenes/frames i could cycle through, but unfortunately i dont think ill make it to the dynamic part of tis project, just the static mario image.
### **Code Adaptation**
Changes made involved editing and adding to the colour_stripes / cycle instantiation to accomadate the module name as well as adding variables row and col to this instantiation. Timing clk was changed in wiz_clk to create a 25Mhz signal, as well as plenty of combinational logic ( if...else if...else if...) to create my mario image!
### **Simulation**
As stated before, i seem to be having issues with simulating my design, likely due to the HEAPS of combinational logic fitting in to a 10us signal period. TODO; continue from here
### **Synthesis**
Describe the synthesis & implementation outputs for your design, are there any differences to that of the original design? Guideline 1-2 short paragraphs.
### **Demonstration**
If you get your own design working on the Basys3 board, take a picture! Guideline: 1-2 sentences.

## **More Markdown Basics**
This is a paragraph. Add an empty line to start a new paragraph.

Font can be emphasised as *Italic* or **Bold**.

Code can be highlighted by using `backticks`.

Hyperlinks look like this: [GitHub Help](https://help.github.com/).

A bullet list can be rendered as follows:
- vectors
- algorithms
- iterators

Images can be added by uploading them to the repository in a /docs/assets/images folder, and then rendering using HTML via githubusercontent.com as shown in the example below.

<img src="https://raw.githubusercontent.com/melgineer/fpga-vga-verilog/main/docs/assets/images/VGAPrjSrcs.png">
