---
layout: home
title: FPGA VGA Driver Project
tags: fpga vga verilog
categories: demo
---

Hello! This is my page for my fpga-vga-driver project.

## **Template VGA Design**
### **Project Set-Up**
We were given some code templates to start such as colour stripes/cycle, VGATop, Constarints file and Testbench! Setting up and running the cycle project was quite simple. We added a 25Mhz clk frequency (Using Clk wiz in IP catalog) which is used in the sync. Then simply run simulation, see if timing is correct, run synthesis and implementation to view the hardware design of our code, adn finally generate a bitstream and program our board. With cycle, it displayed a few colours changing about twice a second. 

I also created another project for colour stripes, included files from moodle (removed colourCycle), and set up IP as before. Some other changes were necessary for the colour stripes to be displayed. The instantiation needed to be changed to "ColourStripes u_colour_stripes" instead of ColourCycle... as well as adding .row(row) and .col(col) to the instantiation. Now stripes is displayed after programming the board. 


<img width="1131" height="624" alt="image" src="https://github.com/user-attachments/assets/b1a8cf5e-bd37-45f6-a3fa-c9fc8e8b325b" />

### **Template Code**
Outline the structure and design of the Verilog code templates you were given. What do they do? Include reference to how a VGA interface works. Guideline: 2/3 short paragraphs, consider including screenshot(s).
### **Simulation**
Explain the simulation process. Reference any important details, include a well-selected screenshot of the simulation. Guideline: 1/2 short paragraphs.
### **Synthesis**
Describe the synthesis and implementation processes. Consider including 1/2 useful screenshot(s). Guideline: 1/2 short paragraphs.
### **Demonstration**
Perhaps add a picture of your demo. Guideline: 1/2 sentences.

## **My VGA Design Edit**
Introduce your own design idea. Consider how complex/achievabble this might be or otherwise. Reference any research you do online (use hyperlinks).
### **Code Adaptation**
Briefly show how you changed the template code to display a different image. Demonstrate your understanding. Guideline: 1-2 short paragraphs.
### **Simulation**
Show how you simulated your own design. Are there any things to note? Demonstrate your understanding. Add a screenshot. Guideline: 1-2 short paragraphs.
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
