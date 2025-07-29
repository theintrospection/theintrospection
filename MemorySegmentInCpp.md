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
│ .rdata (read-only)     │
├───────────────────────┤
│ .text  (code)          │
└───────────────────────┘
Low addresses
