---------------------------------------------------> Team Project made by Sagar Vats, Mudit Thakral and Vinit Sharma <-----------------------------------
----------------------------------------------> sagarvats4740@gmail.com, mudit.thakral98@gmail.com and vinitsharma9876@gmail.com <-------------------------
 Engineer to be

MIPS 16-BIT WITH KEYBOARD INTERFACING	(coded on XILINX ISE DESIGN SUITE 14.7)

This project is a verilog code for a 5 stage pipelined mips processor. The rar file contains the test bench too. This architeture is modified to have improved functionality, since we made 16-bit.
The code is synthesizable for SPARTAN 6 XC6SLX45 FPGA, exceededs the hardware of FPGA, though it will work on other fpga's with adequate hardware, there is no constraint file included.
The test bench is written to emulate the actual output a keyboard will give when a key is pressed.
When, rst = 0, the data from keyboard is stored in instruction memory of processor, and when rst = 1 the processor will start its operation.

PROCESSOR:

	The 5 stages of a mips processor are, Instruction Fetch(IF), Instruction decode(ID), Execution stage(EX), Memory Access(MA) and Write back(WB) stage.

	The modules for respective stages are 
						IF(pc,inst_mem),	ID(control_unit, reg_file, signextender) 	EX(alu),	MA(data_mem),	 WB(mux_wr)
	
	The latches have been made internally to achieve pipeling. Some control signals have been declared but not used now, they are available for future modifications.

	Instructions available: 
					4'b0000 : add
					4'b0001 : sub
					4'b0010 : and
					4'b0011 : or
					4'b0100 : slt
					4'b0101 : multiply
					4'b0111 : load
					4'b1000 : store
					4'b1001 : addi (i = immidiate)
					4'b1010 : subi
					4'b1011 : slti
					4'b1111 : halt
	
	The comments have been added in code for better understanding.

	instruction : opcode[msb 4bits], source [4bits], 2nd source/ immidiate data [4 bits], destination [4bits]		--- all instructions except load and store
		      opcode[msb 4bits], address / immidiate data [8 bits], destination [4bits]					--- load/ store respectively

KEYBOARD:
	The code for keyboard is specific for our application.

	An example for how to enter data from keyboard:
							addi 0000,0010,0011 {opcode rs,rt,rd}
							sw 00111111,0100 {opcode, addr/data,rd} -----lw for load and sw for store

If you need any more info,  contact us on our mail.
	
