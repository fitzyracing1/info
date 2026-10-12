# info: Earthenware Shift Machine

This is a browser-based 8-bit computer simulator built around ×2. The boot check shifts 1 once and confirms the result is 2 before the system runs. Everything lives in `index.html`: open it in a browser (or via GitHub Pages) to load, step through and run programs.

## Instruction set

Each instruction is one byte: a 3-bit opcode and a 5-bit address. Memory is 32 bytes, shared by program and data.

| Op | Code | Effect |
|---|---|---|
| HALT | 000 | stop |
| LDA a | 001 | A = mem[a] |
| STO a | 010 | mem[a] = A |
| ADD a | 011 | A = A + mem[a], carry on overflow |
| SHL | 100 | A = A × 2, top bit to carry |
| JZ a | 101 | jump if A = 0 |
| JMP a | 110 | jump |
| JC a | 111 | jump if carry |
| DB n | n/a | data byte |

Built-in examples: the boot check, a ring counter (1, 2, 4 … 128), 6 × 7 by repeated adding, and 13 × 10 by shift-and-add.

The repo has no tests and no LICENSE file. Copyright (c) 2026 Joshua Almeida
