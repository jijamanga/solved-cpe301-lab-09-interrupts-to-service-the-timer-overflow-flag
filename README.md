Download Link: https://assignmentchef.com/product/solved-cpe301-lab-09-interrupts-to-service-the-timer-overflow-flag
<br>
To become familiar with the use of <strong>interrupts </strong>to service the timer overflow flag in computer applications. Specifically, to implement a piano like keyboard program using the ATmega2560 timer1 in Normal mode and an external speaker.

<strong>Procedure:</strong>

<ol>

 <li>Write a C program for the Arduino Mega which will:

  <ol>

   <li>Monitor incoming characters from the Mega’s UART, for A, B, C, D, E, F, G, and Q, using the serial functions you wrote in the UART lab (U0Init(), kbhit(), getchar(), and putchar()).</li>

   <li>Generate a square wave on Port B.6 of the appropriate frequency depending on the key pressed, as indicated in the table below.</li>

   <li>Output logical 0 when the program first starts, and after the UART receives a ‘Q’ character</li>

   <li>Generating the square wave will not take place in the main loop of the program, but instead in the overflow Interrupt Service Routine of Timer #1.</li>

  </ol></li>

</ol>




<em>Hint: Start with the code you wrote in the Timer Lab, and make two changes: </em>

<ol>

 <li><em>Implement your own serial I/O routines U0Init(), kbhit(), getchar(), and putchar() instead of the Arduino library serial functions to read the note to be played from the UART.  </em></li>

 <li><em>Implement an ISR function for the Overflow Interrupt on Timer #1 (TIMER1 OVF) which will: a.</em><em> Stop the timer </em>

  <ol>

   <li><em>Reload the timer counter </em></li>

   <li><em>Toggle PortB.6 </em></li>

   <li><em>Restart the timer </em></li>

  </ol></li>

</ol>

<em> </em>

<ol start="2">

 <li>Connect PB6 to an oscilloscope and measure the output frequency. Note any error between the actual output frequency and the desired output frequency.</li>

 <li>Connect the lab speakers to PortB.6 with a current limiting resistor in series to play the notes so you can hear them.</li>

</ol>




<strong>BE SURE TO ALWAYS TURN OFF THE SBC POWER BEFORE CONNECTING OR DISCONNECTING ANYTHING TO IT.</strong>




<ol start="4">

 <li>Connect a sine wave signal generator to one of the lab speakers, set it to one of the musical note frequencies, and listen to it. Compare the sound of this note with the same frequency note generated from the SBC speaker. Explain why they sound different.</li>

</ol>

<table width="0">

 <tbody>

  <tr>

   <td width="63">NOTE</td>

   <td width="103">FREQUENCY</td>

  </tr>

  <tr>

   <td width="63">A</td>

   <td width="103">440 Hz</td>

  </tr>

  <tr>

   <td width="63">A#</td>

   <td width="103">466 Hz</td>

  </tr>

  <tr>

   <td width="63">B</td>

   <td width="103">494 Hz</td>

  </tr>

  <tr>

   <td width="63">C</td>

   <td width="103">523 Hz</td>

  </tr>

  <tr>

   <td width="63">C#</td>

   <td width="103">554 Hz</td>

  </tr>

  <tr>

   <td width="63">D</td>

   <td width="103">587 Hz</td>

  </tr>

  <tr>

   <td width="63">D#</td>

   <td width="103">624 Hz</td>

  </tr>

  <tr>

   <td width="63">E</td>

   <td width="103">659 Hz</td>

  </tr>

  <tr>

   <td width="63">F</td>

   <td width="103">698 Hz</td>

  </tr>

  <tr>

   <td width="63">F#</td>

   <td width="103">740 Hz</td>

  </tr>

  <tr>

   <td width="63">G</td>

   <td width="103">784 Hz</td>

  </tr>

  <tr>

   <td width="63">G#</td>

   <td width="103">831 Hz</td>

  </tr>

 </tbody>

</table>




*The Sharp notes are included in the Table for completeness. If you choose to implement all of the notes including sharps you will need to decide on an interface protocol which will distinguish between regular and sharp notes. If you choose to implement all of the notes you will receive up to 50 points (on a scale of 100) extra credit on this lab.




<strong>Important Data Sheet Resources: </strong>a)  2560 Interrupt Table <u><a href="http://ww1.microchip.com/downloads/en/devicedoc/atmel-2549-8-bit-avr-microcontroller-atmega640-1280-1281-2560-2561_datasheet.pdf%23page=101">(page 101)</a></u>

<ol>

 <li>b) 2560 Timer Interrupt Mask Register <u><a href="http://ww1.microchip.com/downloads/en/devicedoc/atmel-2549-8-bit-avr-microcontroller-atmega640-1280-1281-2560-2561_datasheet.pdf%23page=161">(page 161)</a></u></li>

</ol>