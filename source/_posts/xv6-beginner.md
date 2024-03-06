---
title: xv6_beginner
date: 2022-07-26 21:55:19
tags: os 
categories: computer science
---
# The XV6 is a os lab for beginner who is fool about the operating system

<!-- more -->


### Here is my learning road 
#### trap
before we get into trap, we should know what we have.
the CPU src :

def: trap is a process that computer get into kernel mod for syscall or intr or exceptions.
##### working stream
1. ecall
    0. if trap is intr and sie is clear than exit
    0. clear sie to unuse intr
    1. User mode-> supervisor mode
    2. Let sepc = pc
    3. Let pc = stvec
    4. Jump to pc
    7. set scause for the reason of trap
    8. save current mod in spp 
2. uservec
    1. save the current scene
    2. load kpagetable kstack cpuid into register 
    3. jump to usertrap to continue
3. usertrap
    1. do the logic for each situation
    2. store sepc (mybe sepc and stvec will be change)
4. usertrapret
    1. save trapframe : kpage, kstack, cpuid
    2. load stvec,sepc(supervisor mode register)
5. userret
    1. recover current scene
    2. upage, ustack store to register
    3. sret : inverse ecall