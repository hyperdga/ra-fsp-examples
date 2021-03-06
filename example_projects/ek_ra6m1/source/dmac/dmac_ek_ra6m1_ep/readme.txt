/***********************************************************************************************************************
* Copyright [2019] Renesas Electronics Corporation and/or its affiliates.  All Rights Reserved.
* This software is supplied by Renesas Electronics America Inc. and may only be used with products of Renesas Electronics Corp.
* and its affiliates (“Renesas”).  No other uses are authorized.  This software is protected under all applicable laws, 
including copyright laws.
* Renesas reserves the right to change or discontinue this software.
* THE SOFTWARE IS DELIVERED TO YOU “AS IS,” AND RENESAS MAKES NO REPRESENTATIONS OR WARRANTIES, AND TO THE FULLEST EXTENT 
* PERMISSIBLE UNDER APPLICABLE LAW,DISCLAIMS ALL WARRANTIES, WHETHER EXPLICITLY OR IMPLICITLY, INCLUDING WARRANTIES OF 
* MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AND NONINFRINGEMENT, WITH RESPECT TO THE SOFTWARE.  TO THE MAXIMUM 
* EXTENT PERMITTED BY LAW, IN NO EVENT WILL RENESAS BE LIABLE TO YOU IN CONNECTION WITH THE SOFTWARE (OR ANY PERSON OR 
* ENTITY CLAIMING RIGHTS DERIVED FROM YOU) FOR ANY LOSS, DAMAGES, OR CLAIMS WHATSOEVER, INCLUDING, WITHOUT LIMITATION, 
* ANY DIRECT, CONSEQUENTIAL, SPECIAL, INDIRECT, PUNITIVE, OR INCIDENTAL DAMAGES; ANY LOST PROFITS, OTHER ECONOMIC DAMAGE, 
* PROPERTY DAMAGE, OR PERSONAL INJURY; AND EVEN IF RENESAS HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH LOSS,
* DAMAGES, CLAIMS OR COSTS.
 **********************************************************************************************************************/

Project Overview:

This example project demonstrates basic functionalities of DMAC driver on Renesas RA MCUs based on Renesas FSP. AGT is 
configured to generate a 100 milli second interrupt to DMAC transfer0. DMAC transfer0(runs in Normal mode) transfers 
data(i.e. , I/O mode of the port pin and output value) from source array to port control register(LED) for specified 
number of counts(60). DMAC transfer0 alters the state of the LED and stops. DMAC transfer1 is configured to transfer 
32-bit data from a GPT counter register to the destination array. Interrupt generated when user pushbutton is pressed, 
triggers the IRQ and initiates DMAC transfer1. GPT timer continuous to run. DMAC transfer2 is configured to transfer 
32-bit data(in repeat mode) from the source array to port control register(LED). As a result, pressing the user pushbutton 
transfer the GPT current timer value to destination array. And on providing 1 as RTT input, destination array's data 
is displayed on RTTviewer.

Note: 
1. On starting or reseting the board, at times the dmac transfer operation takes more time. Due to this the led blinking 
frequency decreases/pauses. Please reset the board in that case, and it will run as expected.
2. Use Switch S1 (push button) on RA6M3 and RA6M3G. 
3. LED blinking pauses in-between and then continues on RA6M3 and RA6M3G.
