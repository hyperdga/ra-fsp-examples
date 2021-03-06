﻿/***********************************************************************************************************************
* 

* Copyright [2019] Renesas Electronics Corporation and/or its affiliates.  All Rights Reserved.


* This software is supplied by Renesas Electronics America Inc. and may only be used with products of Renesas Electronics
* Corp.
 and its affiliates (“Renesas”).  No other uses are authorized.  This software is protected under all applicable 
* laws, including copyright laws.


* Renesas reserves the right to change or discontinue this software.


* THE SOFTWARE IS DELIVERED TO YOU “AS IS,” AND RENESAS MAKES NO REPRESENTATIONS OR WARRANTIES, AND TO THE FULLEST EXTENT
* PERMISSIBLE

 UNDER APPLICABLE LAW,DISCLAIMS ALL WARRANTIES, WHETHER EXPLICITLY OR IMPLICITLY, INCLUDING WARRANTIES OF 
* MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AND NONINFRINGEMENT, WITH RESPECT TO THE SOFTWARE. TO THE MAXIMUM 
* EXTENT PERMITTED BY LAW, IN NO EVENT WILL RENESAS

 BE LIABLE TO YOU IN CONNECTION WITH THE SOFTWARE (OR ANY PERSON OR 
* ENTITY CLAIMING RIGHTS DERIVED FROM YOU) FOR ANY LOSS, DAMAGES, OR CLAIMS WHATSOEVER, INCLUDING, WITHOUT LIMITATION, ANY
* DIRECT, CONSEQUENTIAL, SPECIAL, INDIRECT, PUNITIVE, OR INCIDENTAL DAMAGES; ANY LOST PROFITS, OTHER ECONOMIC DAMAGE, 
* PROPERTY DAMAGE, OR PERSONAL INJURY; AND EVEN IF RENESAS HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH LOSS,

 DAMAGES, 
* CLAIMS OR COSTS.


************************************************************************************************************************/




1. Project Overview:


	The example project demonstrates the typical use of the SCI_I2C HAL module APIs.

	The project initializes SCI_I2C Master and IIC slave modules 
with standard rate and is made interfaced with 
	loopback mechanism. 
On power up, after establishing SDA-SCL connection, user is requested to
 press the on-board 
	push button to trigger the data transfer
. On push button pressing IIC transaction is performed and Once the 
	transfer is 
completed, 
received data is compared with the transmitted data. 
Output is displayed on the RTT viewer
	and the on-board LED state indicates
 the success of data transfer.
	
	




LED output Status on Master TX and RX data mismatch(failure) and data match(success)
	

a) Failure  - Led is set as ON


	b) Success  - Led blinks for each transaction.





Note:


* For any event or API failure appropriate messages is displayed on RTT viewer.


* Master write operation and read operation affirmative occurrence order can vary on extreme rapid "push button pressings"
  event



.

2. Hardware Settings:
 


	
	
Two jumper wires are required to establish loop back connection along IIC lines within the board with pins as 
	mentioned below.



	

	RA4M1_EK
 
	
	--------
    

	Channel 0 has been used by SCI_I2C Master and IIC Slave.

    

	1) SCI_I2C Master pins
        

	SCI0 P411 (Jumper J2 Pin 04) ----> SDA 
        

	SCI0 P410 (Jumper J2 Pin 02) ----> SCL 

    
	

	
	2) IIC Slave pins
        
	
 
	IIC0 P401 (Jumper J2 Pin 08) ----> SDA 
        

	IIC0 P400 (Jumper J2 Pin 37) ----> SCL

	RA6M3_EK
 and RA6M3G_EK 
	--------
	Channel 0 has been used by SCI_I2C Master and IIC Slave.
	1) SCI_I2C Master pins
	SCI0 P411 (Jumper J3 Pin 36) ----> SDA 
        

	SCI0 P410 (Jumper J3 Pin 35) ----> SCL

	2) Slave IIC pins
        

	IIC0 P401 (Jumper J3 Pin 09) ----> SDA 
        

	IIC0 P408 (Jumper J3 Pin 37) ----> SCL

	RA6M2_EK
    
	
	--------

	Channel 0 has been used by SCI_I2C Master and IIC Slave.
	1) SCI_I2C Master pins
	SCI0 P411 (Jumper J2 Pin 20) ----> SDA 
        

	SCI0 P410 (Jumper J2 Pin 02) ----> SCL

	2) Slave IIC pins
        

	IIC0 P401 (Jumper J4 Pin 11) ----> SDA 
    
    
	IIC0 P400 (Jumper J4 Pin 13) ----> SCL

	RA6M1_EK
    

	--------
	Channel 0 has been used by SCI_I2C Master and IIC Slave.
	1) SCI_I2C Master pins
	SCI0 P411 (Jumper J2 Pin 20) ----> SDA 
        

	SCI0 P410 (Jumper J4 Pin 14) ----> SCL

	2) Slave IIC pins
        

	IIC0 P401 (Jumper J1 Pin 0) ----> SDA 
     
   
	IIC0 P400 (Jumper J1 Pin 01) ----> SCL
	
	RA2A1_EK
    

	--------
  
 

    
	Channel 0 has been used by SCI_I2C Master and IIC Slave.
	1) SCI_I2C Master pins
	SCI0 P302 (Jumper J2 Pin 04) ----> SDA 
        

	SCI0 P301 (Jumper J2 pin 02) ----> SCL

	2) Slave IIC pins
        

	IIC0 P401 (Jumper J1 Pin 03) ----> SDA 
      
  
	IIC0 P000 (Jumper J1 Pin 01) ----> SCL 

 

  


	    

	
		





Note :  
* For the functioning of SCI_I2C Master and IIC Slave on all the boards except for EK-RA6M3/EK-RA6M3G, external pull 
  up resistors of value 3.9 or 4.7k ohms are required
 to be connected on I2C(SDA/SCL) lines.
  

* Use Switch S1 (push button) on RA6M3 and RA6M3G.