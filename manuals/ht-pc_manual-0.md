# The Huang Twins Personal Computer (HT-PC)



## The Instruction Set

The first 8 bytes of the ROM sets the respective 8 registers.


### The Instructions

**0x00**: No-op, does nothing.
**0x01**: CPU move, uses the A register to determine which location register to move to.
Setup:
Last nibble of A reg: source.
First nibble of A reg: destination.
**0x02**: External move, moves to output, RAM, or the 9th/10th register, known as the mover registers #1 and #2. Only the last nibble of the A register is used. The last dubit is the source.
00: RAM
01: Output
10: Mover Register #1
11: Mover Register #2
**0x03**: Add: adds the A register and B register, and puts the result into C.
**0x04**: Subtract: does C=A-B.
**0x05**: Multiply: multiplies A and B and puts the result into C.
**0x06**: Divide: does C=A/B
**0x07**: Jump: jumps to the ROM location in A.
**0x08**: Compare: compares A and B, stores flags in C.
**0x09**: Jump equal: jumps to A in ROM if C has the equal flag.
**0x0A**: Jump not equal: jumps to A in ROM if C doesn't have the equal flag.
**0x0B**: Jump greater: jumps to A in ROM if C has the greater flag.
**0x0C**: Jump lesser: jumps to A in ROM if C has the lesser flag.



## Adding/Removing RAM

To add or remove RAM, please consult your software's manual for which RAM chips are needed.