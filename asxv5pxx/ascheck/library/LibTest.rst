ASxxxx Assembler V05.20  (ASxxxx Test Assembler)                        Page 1
Hexadecimal [16-Bits]                                 Mon Apr 09 15:22:42 2018



                              1 	.module	LibTest
                              2 	.area	LibTest
                              3 
                              4 	; Test the importation of library elements
                              5 
                              6 	.globl	lfnc02,lfnc03,lfnc10
                              7 
                              9 
                             10 	.macro	call	arg	; dumby function call
                             11 	.byte	0xFF, >arg, <arg
                             12 	.endm
                             13 
                             14 
   0000                      15 start:	Call	lfnc02		; call a library function which
        FF 00 0F
                             16 				; has no dependencies
                             17 
   0003                      18 	Call	lfnc03		; call a library function which
        FF 00 12
                             19 				; has a dependency
                             20 
   0006                      21 	Call	lfnc10		; call a library function which
        FF 00 09
                             22 				; has dependencies that have
                             23 				; dependencies
                             24 
                             25 	.end
ASxxxx Assembler V05.20  (ASxxxx Test Assembler)                        Page 2
Hexadecimal [16-Bits]                                 Mon Apr 09 15:22:42 2018

Symbol Table

    .__.$$$.       =   2710 L   |     .__.ABS.       =   0000 G
    .__.CPU.       =   0000 L   |     .__.H$L.       =   0001 L
    lfnc02             **** GX  |     lfnc03             **** GX
    lfnc10             **** GX  |   2 start              0000 R

ASxxxx Assembler V05.20  (ASxxxx Test Assembler)                        Page 3
Hexadecimal [16-Bits]                                 Mon Apr 09 15:22:42 2018

Area Table

[_CSEG]
   0 _CODE            size    0   flags C080
   2 LibTest          size    9   flags  100
[_DSEG]
   1 _DATA            size    0   flags C0C0

