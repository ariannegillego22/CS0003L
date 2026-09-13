 **MPL1**
 
=========== 1. Assembly Lab Welcome Board ===========

root@698d6ac01b5b:/work# nano welcome_board.asm

root@698d6ac01b5b:/work# nasm -f elf32 welcome_board.asm -o welcome_board.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o welcome_board welcome_board.o

root@698d6ac01b5b:/work# ./welcome_board
Assembly Laboratory
Mode: NASM 32-bit
Status: Ready
root@698d6ac01b5b:/work# nano welcome_board.asm

root@698d6ac01b5b:/work# nasm -f elf32 welcome_board.asm -o welcome_board.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o welcome_board welcome_board.o

root@698d6ac01b5b:/work# ./welcome_board
Assembly Laboratory
Mode: Linux ELF32
Status: Ready
root@698d6ac01b5b:/work# nano welcome_board.asm

root@698d6ac01b5b:/work# nasm -f elf32 welcome_board.asm -o welcome_board.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o welcome_board welcome_board.o

root@698d6ac01b5b:/work# ./welcome_board
Assembly Laboratory
Mode: NASM 32-bit
Status: Ready!

<img width="696" height="338" alt="Screenshot 2026-09-10 at 11 04 09 PM" src="https://github.com/user-attachments/assets/e6f590b9-74dd-4b8f-9e54-3b8989fd48d6" />

CASE 1:

    section .data

        line1 db "Assembly Laboratory", 10
        len1 equ $ - line1

        line2 db "Mode: NASM 32-bit", 10
        len2 equ $ - line2

        line3 db "Status: Ready", 10
        len3 equ $ - line3

    section .text
        global _start
    
    _start:
        mov eax, 4
        mov ebx, 1
        mov ecx, line1
        mov edx, len1
        int 0x80

        mov eax, 4
        mov ebx, 1
        mov ecx, line2
        mov edx, len2
        int 0x80

        mov eax, 4
        mov ebx, 1
        mov ecx, line3
        mov edx, len3
        int 0x80

        mov eax, 1
        mov ebx, 0
        int 0x80
    
CASE 2 : 
    
    section .data

        line1 db "Assembly Laboratory", 10
        len1 equ $ - line1

        line2 db "Mode: Linux ELF32", 10
        len2 equ $ - line2

        line3 db "Status: Ready", 10
        len3 equ $ - line3

    section .text
        global _start

    _start:
        mov eax, 4
        mov ebx, 1
        mov ecx, line1
        mov edx, len1
        int 0x80

        mov eax, 4
        mov ebx, 1
        mov ecx, line2
        mov edx, len2
        int 0x80

        mov eax, 4
        mov ebx, 1
        mov ecx, line3
        mov edx, len3
        int 0x80

        mov eax, 1
        mov ebx, 0
        int 0x80
        
  CASE 3:
    
    section .data
        line1 db "Assembly Laboratory", 10
        len1 equ $ - line1

        line2 db "Mode: NASM 32-bit", 10
        len2 equ $ - line2

        line3 db "Status: Ready!", 10
        len3 equ $ - line3

    section .text
        global _start

    _start:
        mov eax, 4
        mov ebx, 1
        mov ecx, line1
        mov edx, len1
        int 0x80

        mov eax, 4
        mov ebx, 1
        mov ecx, line2
        mov edx, len2
        int 0x80

        mov eax, 4
        mov ebx, 1
        mov ecx, line3
        mov edx, len3
        int 0x80

        mov eax, 1
        mov ebx, 0
        int 0x80
---------------------------------------------------------------------------
========== 2.TOOLCHAIN STATUS SCREEN =============

root@698d6ac01b5b:/work# nano toolchain.asm

root@698d6ac01b5b:/work# nasm -f elf32 toolchain.asm -o toolchain.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o toolchain toolchain.o

root@698d6ac01b5b:/work# ./toolchain
Assembler ready
Linker ready
Program ready

root@698d6ac01b5b:/work# nano toolchain.asm

root@698d6ac01b5b:/work# nasm -f elf32 toolchain.asm -o toolchain.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o toolchain toolchain.o

root@698d6ac01b5b:/work# ./toolchain
Assembler readyLinker ready
Program ready

root@698d6ac01b5b:/work# nano toolchain.asm

root@698d6ac01b5b:/work# nasm -f elf32 toolchain.asm -o toolchain.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o toolchain toolchain.o

root@698d6ac01b5b:/work# ./toolchain
Assembler ready
Program ready

<img width="497" height="305" alt="Screenshot 2026-09-10 at 11 16 14 PM" src="https://github.com/user-attachments/assets/ab2b213a-15fe-4d75-97e1-72d072ce22a9" />


CASE 1:
    
    section .data

        message1 db "Assembler ready", 0xA
        length1 equ $ - message1

        message2 db "Linker ready", 0xA
        length2 equ $ - message2

        message3 db "Program ready", 0xA
        length3 equ $ - message3

    section .text
        global _start

    _start:

        mov eax, 4
        mov ebx, 1
        mov ecx, message1
        mov edx, length1
        int 0x80

        mov eax, 4
        mov ebx, 1
        mov ecx, message2
        mov edx, length2
        int 0x80
    
        mov eax, 4
        mov ebx, 1
        mov ecx, message3
        mov edx, length3
        int 0x80

        mov eax, 1
        mov ebx, 0
        int 0x80
  
  CASE 2:
  
      section .data

        message1 db "Assembler ready", 
        length1 equ $ - message1

        message2 db "Linker ready", 0xA
        length2 equ $ - message2

        message3 db "Program ready", 0xA
        length3 equ $ - message3

    section .text
        global _start

    _start:
   
        mov eax, 4
        mov ebx, 1
        mov ecx, message1
        mov edx, length1
        int 0x80

        mov eax, 4
        mov ebx, 1
        mov ecx, message2
        mov edx, length2
        int 0x80
    
        mov eax, 4
        mov ebx, 1
        mov ecx, message3
        mov edx, length3
        int 0x80

        mov eax, 1
        mov ebx, 0
        int 0x80

CASE 3:
       
       section .data

        message1 db "Assembler ready", 0xA
        length1 equ $ - message1

        message2 db "Linker ready", 0xA
        length2 equ $ - message2

        message3 db "Program ready", 0xA
        length3 equ $ - message3

    section .text
        global _start

    _start:
   
        mov eax, 4
        mov ebx, 1
        mov ecx, message1
        mov edx, length1
        int 0x80
    
        mov eax, 4
        mov ebx, 1
        mov ecx, message3
        mov edx, length3
        int 0x80

        mov eax, 1
        mov ebx, 0
        int 0x80

----------------------------------------------------------------------------
=========== 3. EXIT STATUS REPORTER ============

root@698d6ac01b5b:/work# nano exit_status.asm

root@698d6ac01b5b:/work# nasm -f elf32 exit_status.asm -o exit_status.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o exit_status exit_status.o

root@698d6ac01b5b:/work# ./exit_status
Task complete.
root@698d6ac01b5b:/work# echo $?
25

root@698d6ac01b5b:/work# nano exit_status.asm

root@698d6ac01b5b:/work# nasm -f elf32 exit_status.asm -o exit_status.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o exit_status exit_status.o

root@698d6ac01b5b:/work# ./exit_status
Task complete.
root@698d6ac01b5b:/work# echo $?
7

root@698d6ac01b5b:/work# nano exit_status.asm

root@698d6ac01b5b:/work# nasm -f elf32 exit_status.asm -o exit_status.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o exit_status exit_status.o

root@698d6ac01b5b:/work# ./exit_status
Task complete.

root@698d6ac01b5b:/work# echo $?
0

<img width="580" height="316" alt="Screenshot 2026-09-10 at 11 30 02 PM" src="https://github.com/user-attachments/assets/67012bec-692e-428a-a8c1-6ece630e8fc9" />


CASE 1: 
    
    section .data
        message db "Task complete.", 10
        length equ $ - message

    section .text
        global _start

    _start:
   
        mov eax, 4
        mov ebx, 1
        mov ecx, message
        mov edx, length
        int 0x80

        mov eax, 1
        mov ebx, 25
        int 0x80

CASE 2:
    
    section .data

        message db "Task complete.", 10
        length equ $ - message

    section .text
        global _start

    _start:

        mov eax, 4
        mov ebx, 1
        mov ecx, message
        mov edx, length
        int 0x80

        mov eax, 1
        mov ebx, 7
        int 0x80
        
CASE 3:

    section .data
        message db "Task complete.", 10
        length equ $ - message

    section .text
        global _start

    _start:
        mov eax, 4
        mov ebx, 1
        mov ecx, message
        mov edx, length
        int 0x80

        mov eax, 1
        mov ebx, 0
        int 0x80
-----------------------------------------------------------------------
========== 4. Three-Step Workflow Block =========

root@698d6ac01b5b:/work# nano workflow.asm

root@698d6ac01b5b:/work# nasm -f elf32 workflow.asm -o workflow.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o workflow workflow.o

root@698d6ac01b5b:/work# ./workflow
Step 1: Edit
Step 2: Assemble
Step 3: Run
root@698d6ac01b5b:/work# nano workflow.asm

root@698d6ac01b5b:/work# nasm -f elf32 workflow.asm -o workflow.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o workflow workflow.o

root@698d6ac01b5b:/work# ./workflow

Step 1: Edit
Step 2: Assemble
Step 3: Run
Step 4: Debug

root@698d6ac01b5b:/work# nano workflow.asm

root@698d6ac01b5b:/work# nasm -f elf32 workflow.asm -o workflow.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o workflow workflow.o

root@698d6ac01b5b:/work# ./workflow
Step 1: Editroot@698d6ac01b5b:/work# nano workflow.asm

root@698d6ac01b5b:/work# nasm -f elf32 workflow.asm -o workflow.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o workflow workflow.o

root@698d6ac01b5b:/work# ./workflow

Step 1: Edit
Step 2: Assemble
Step 3: Run

<img width="573" height="391" alt="Screenshot 2026-09-10 at 11 46 37 PM" src="https://github.com/user-attachments/assets/182699d2-d14e-42f2-8ad1-7406f66280ef" />


CASE 1:

    section .data
        workflow db "Step 1: Edit", 10
                 db "Step 2: Assemble", 10
                 db "Step 3: Run", 10
        workflow_len equ $ - workflow

    section .text
        global _start

    _start:
        mov eax, 4
        mov ebx, 1
        mov ecx, workflow
        mov edx, workflow_len
        int 0x80

        mov eax, 1
        mov ebx, 0
        int 0x80
  
  CASE 2:
  
    section .data
        workflow db "Step 1: Edit", 10
                 db "Step 2: Assemble", 10
                 db "Step 3: Run", 10
                 db "Step 4: Debug", 10
        workflow_len equ $ - workflow

    section .text
        global _start

    _start:
        mov eax, 4
        mov ebx, 1
        mov ecx, workflow
        mov edx, workflow_len
        int 0x80

        mov eax, 1
        mov ebx, 0
        int 0x80

CASE 3:
    
    section .data
        workflow db "Step 1: Edit", 10
                 db "Step 2: Assemble", 10
                 db "Step 3: Run", 10
        workflow_len equ $ - workflow

    section .text
        global _start

    _start:
        mov eax, 4
        mov ebx, 1
        mov ecx, workflow
        mov edx, 12
        int 0x80

        mov eax, 1
        mov ebx, 0
        int 0x80
-----------------------------------------------------------
=========== 5. REPAIR THE SYSTEM NOTICE ==============

root@698d6ac01b5b:/work# nano system_notice.asm

root@698d6ac01b5b:/work# nasm -f elf32 system_notice.asm -o system_notice.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o system_notice system_notice.o

root@698d6ac01b5b:/work# ./system_notice
System notice: READY

root@698d6ac01b5b:/work# echo $?
0
root@698d6ac01b5b:/work# nano system_notice.asm

root@698d6ac01b5b:/work# nasm -f elf32 system_notice.asm -o system_notice.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o system_notice system_notice.o

root@698d6ac01b5b:/work# ./system_notice

root@698d6ac01b5b:/work# nano system_notice.asm

root@698d6ac01b5b:/work# nasm -f elf32 system_notice.asm -o system_notice.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o system_notice system_notice.o

root@698d6ac01b5b:/work# ./system_notice
System notice: ONY
root@698d6ac01b5b:/work# nano system_notice.asm

root@698d6ac01b5b:/work# nasm -f elf32 system_notice.asm -o system_notice.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o system_notice system_notice.o

root@698d6ac01b5b:/work# ./system_notice
System notice: ON
root@698d6ac01b5b:/work# nano system_notice.asm

root@698d6ac01b5b:/work# ^C

root@698d6ac01b5b:/work# nasm -f elf32 system_notice.asm -o system_notice.o

root@698d6ac01b5b:/work# ld -m elf_i386 -o system_notice system_notice.o

root@698d6ac01b5b:/work# ./system_notice
System notice: READY

root@698d6ac01b5b:/work# echo $?
0

<img width="592" height="431" alt="Screenshot 2026-09-10 at 11 58 13 PM" src="https://github.com/user-attachments/assets/4ad7e445-f0e6-41fb-85fa-7420ba9f53b9" />


CASE 1:

    section .data
        message db "System notice: READY", 10
        length equ $ - message

    section .text
        global _start

    _start:
        mov eax, 4
        mov ebx, 1
        mov ecx, message
        mov edx, length
        int 0x80

        mov eax, 1
        mov ebx, 0
        int 0x80


CASE 2:

    section .data
        message db "System notice: READY", 10
        length equ $ - message

    section .text
        global _start

    _start:
        mov eax, 4
        mov ebx, message
        mov ecx, message
        mov edx, length
        int 0x80

        mov eax, 1
        mov ebx, 0
        int 0x80

CASE 3:
    
    section .data
        message db "System notice: ON", 10
        length equ $ - message

    section .text
        global _start

    _start:
        mov eax, 4
        mov ebx, 1
        mov ecx, message
        mov edx, length
        int 0x80

        mov eax, 1
        mov ebx, 0
        int 0x80





