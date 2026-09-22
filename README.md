# info — Earthenware Shift Machine

An 8-bit computer simulator built around ×2. Every shift moves the accumulator one bit left; the boot check shifts 1 once and confirms we have 2 before the system runs.

Open `index.html` in a browser (or enable GitHub Pages) to load, step through, and run programs.

## Instruction set

Each instruction is one byte: a 3-bit opcode and a 5-bit address. Memory is 32 bytes, shared by program and data.

| Op | Code | Effect |
|---|---|---|
| HALT | 000 | Stop |
| LDA a | 001 | A = mem[a] |
| STO a | 010 | mem[a] = A |
| ADD a | 011 | A = A + mem[a], carry on overflow |
| SHL | 100 | A = A × 2, top bit to carry |
| JZ a | 101 | Jump if A = 0 |
| JMP a | 110 | Jump |
| JC a | 111 | Jump if carry |
| DB n | — | Data byte |

## Example programs

- Boot check: ×2 must give 2, then `ready = 1`
- Ring counter: 1, 2, 4 … 128
- 6 × 7 by repeated adding (42)
- 13 × 10 with shift-and-add (130)
