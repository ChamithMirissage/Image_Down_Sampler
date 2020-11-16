# image_down_sampler_project

# Introduction
  
  The main purpose of mainting this reprository is to build a custom CISC based processor which is able to perform few arithmatic operations to 
  down sample a **256*256** size of a image. this processor id able to perform 16 different operations. The image is downloaded through the UART communication 
  and stored in the 2MB sram module embedded inside the intel ```Altera DE2-115 Development and Education Board```. Then image is downsampled by applying ``` Gaussianfilter.```
  The final size of the image is 128*128.
  
  # Processor Architecture
  
   1. 5 general purpose :R1,R2,R3,R4,R5 {16 bit register }
   2. 1 temperary register : TR{16 bitsize}
   3. 1 address register: AR {19:0}
   4: 1 instruction register: IR {19:0}
   5: 1 Data register : DR {15:0}
   6. SRAM controller : To store the downloaded image (Interfacing module to the SRAM inside the altera board )
  
![Screenshot (503)](https://user-images.githubusercontent.com/37435024/99287186-f0aff680-285f-11eb-9220-f559fed2df73.png)  

#  Instructions

|Instruction|Opcode|Size|ISA|Description|
|----|-----|-----|------|-------|
|ADD|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
|SUB|```0b000010```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA-RB|
|MUL|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
|DIV|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
|NOT|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
|LEFT_SHIF|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
|RIGHT_SHIFT|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
|BIT_AND|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
|BIT_OR|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
|CONST2REG|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
|MEM_WRITE|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
|MEM_READ|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
|JUMPZ|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
|NJUMPZ|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
|OVER|```0b000001```|16 bit|```opcode[15:10]/src_A_Bus[9:7]/src_B_bus[6:4]/destination_C_bus[3:0]```|Rc<---RA+RB|
