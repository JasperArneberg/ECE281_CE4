ECE281_CE4
==========
Computer Exercise 4: PRISM Assembly Language Programming

C3C Jasper Arneberg  
M6A ECE 281  
Dr. Neebel  

## Program A
######Simple Memory Manipulation: Write a program that stores the value $9 in location $B0, $8 in $C4 and $B in $CB. (Target program end: $11)

This program was a joy to work on. The most difficult part was figuring out how to use the STA command, which stores a value from the accumulator into a RAM address. I asked C3C El-Saawy for help, and he showed me how to label the memory addresses so values could be stored to them.

Note: This program meets the target end address, and it should receive a bonus point per the rubric.


## Program B
######Mathematics: Write a program that retrieves a value from location $B0, doubles it, and subtracts 4.  The result should be output to Port 2. (Target program end: $0C)

This program was a little more difficult to write than the first one was. Because PRISM doesn't have a multiply function, doubling a number consisted of adding it to itelf. Subtracting 4 also meant that I needed to add the two's complement of 4. The two's complement of 0100 ($4) is 1100 ($C). I looped the program back to the start so that it could be tested for various values in gate B0. Here are some test results verifying that it works correctly. It is important to note that an overflow error can occur for starting values that are too high.

####Results of Program B
| Value in B0 | Port 2 Output |
| :--: | :--: |
| 4 | 6 | 
| 3 | 2 |
| 7 | A |

Note: This program meets the target end address, and it should receive a bonus point per the rubric.


## Program C
######Loops: Write a program that starts by reading what is on Input Port 3 and then displaying that on Output Port 0.  One less than that should then display on Port 1 and one less than what is on Port 1 will display on Port 2.  The program then decrements what is on Port 0, then decrements what is on Port 1, then decrements what is on Port 2.  This process is continued in an infinite loop (i.e. If Input Port 3 contains a ‘2’ , Ports 0-2 will show 2,1,0, respectively.  The 2, 1, 0 will then change to 1,0,F, then 0, F, E, and so on). (Target program end: $10)

The hardest part of this program was determining what to add between the outputs. The two's complemen to of 0001 ($1) is 1111 ($F). After the three output ports had been set, 1h was added to the accumulator so that it would reset to a value of 1 less than before.

Note: This program meets the target end address, and it should receive a bonus point per the rubric.


## Documentation
C3C El-Saawy pointed out how to label RAM addresses.
