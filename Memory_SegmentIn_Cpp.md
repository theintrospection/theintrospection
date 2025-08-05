Linux (ELF) memory layout
```
High addresses  
┌───────────────────────┐  
│       Stack            │  <- grows downward  
├───────────────────────┤  
│       (free space)     │  
├───────────────────────┤  
│       Heap             │  <- grows upward  
├───────────────────────┤  
│ .bss   (zero/uninit)   │  
│ .data  (initialized)   │  
│ .rodata (read-only)     │  
├───────────────────────┤  
│ .text  (code)          │  
└───────────────────────┘  
Low addresses  
```
Windows (PE) memory layout
```
High addr  
┌───────────────┐  
│ Stack         │ ↓ grows downward  
├───────────────┤  
│ (Free space)  │  
├───────────────┤  
│ Heap          │ ↑ grows upward  
├───────────────┤  
│ .bss          │  
│ .data         │  
│ .rdata        │  
│ .idata/.edata │  
├───────────────┤  
│ .text         │  
└───────────────┘  
Low addr  
```
 
## **Key Differences**

#### ***Read-only data***

Linux: Usually **.rodata (read-only data)** or merged with **.text**  
Windows: .rdata  

#### ***Import/export***
Linux: **.plt** / **.got** for dynamic linking  
Windows: **.idata** (import table), **.edata** (export table)  

#### ***Naming***

**.bss, .data, .text** are common across both  
Read-only data section name differs (**.rodata** vs **.rdata**)  

#### ***Heap/Stack behavior***

Conceptually identical, managed differently by OS memory allocators  
