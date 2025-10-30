# MPMC---ASSIGNMENT--1

Write an assembly language program in 8086 to reverse the elements of an array and store the reversed array in another memory location.

Algorithm:

Start the program.

Initialize the data segment.

Define an array ARR1 in memory.

Reserve equal space for another array ARR2 where reversed data will be stored.

Initialize SI to point to the last element of ARR1.

Initialize DI to point to the first element of ARR2.

Set CX register with the number of array elements.

Copy elements from ARR1 (in reverse order) to ARR2 (forward order).

Stop the program execution using HLT.

End the program.

Program
```
DATA SEGMENT
    ARR1 DB 10H, 20H, 30H, 40H, 50H     ; Source array
    ARR2 DB 5 DUP(?)                     ; Destination array for reversed data
    N EQU 5                              ; Number of elements in array
DATA ENDS

CODE SEGMENT
ASSUME DS:DATA, CS:CODE

START:
    MOV AX, DATA
    MOV DS, AX              ; Initialize data segment

    LEA SI, ARR1            ; Load address of ARR1
    LEA DI, ARR2            ; Load address of ARR2
    MOV CX, N               ; Load count = 5
    ADD SI, N-1             ; Point SI to last element of ARR1

REVERSE_LOOP:
    MOV AL, [SI]            ; Load element from ARR1
    MOV [DI], AL            ; Store into ARR2
    DEC SI                  ; Move to previous element in ARR1
    INC DI                  ; Move to next element in ARR2
    LOOP REVERSE_LOOP       ; Repeat until CX = 0

    HLT          
           ; Stop execution
CODE ENDS
END START
```
OUTPUT

<img width="640" height="428" alt="ASS 1" src="https://github.com/user-attachments/assets/5de448aa-7f6c-47a1-9264-8750e9cb8a33" />
<img width="999" height="634" alt="11ass" src="https://github.com/user-attachments/assets/d751cdc8-7833-4103-b612-67d943c31a9c" />

Result:

The elements of the array were successfully reversed and stored in another memory location using 8086 assembly language.


