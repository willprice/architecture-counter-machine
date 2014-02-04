# Up and Down
Increment r0 until it overflows, then we decrement r0 until 0. Then jump back to
the beginning of the program.

0: INC r0
1: JNZ 0
2: DEC r0
3: JNZ 2
4: INC r0
5: JNZ 0
