---
title: tcp/ip
date: 2022-09-04 11:22:31
tags: computer networking 
categories: cs
---
## tcp-ip shake hand 
hint: hand shake is a tool to confirm A and B,s recv and send ability
here we use I(r,s) to illustrate point i and its recv and send ability
1. first : A 2 B : a(r,s) = (0,0) ; B(r,s) = (0,0)
2. second :B 2 A :A recv a(1,1); B(1,0);
3. third :A 2 B: B recv B(1,1) compelet;

https://blog.csdn.net/qq_51577576/article/details/121426400
this is about tcp/ip hand shake

## tcp-ip shake away
def: J(r,s) as J the close recv and send state as a point 
suppose : A is client , B is server .
1. first stage: A 2 B : A(1,1) B(1,1);fin1
                B 2 A : A(1,0) B(1,1);akn
2. second stahe: B 2 A => A 2 B;fin2
                A(0,0) B(1,0) => A(0,0) B(0,0);akn 