# The Huang Twins Personal Computer 0 (HT-PC 0)

The HT-PC 0 is an 8 bit computer designed for general purpose use. It has no built in displays, or any built in input devices (buttons, switches, keyboards, etc.). To have input and output, please refer to the list of official IO devices.

## Hardware

The HT-PC 0 is quite capable for many applications.

### Basic specifications

**CPU**: Any hertz, 8 bits.

**RAM**: 256 bytes.

**ROM**: 256 bytes.

**IO**: Very basic, 1 byte in, 1 byte out.

### Extended Specifications

#### CPU

**Bitness**: 8 bits

**Registers**: 8 conventional, 2 for IO.

**Instruction set**: RISC, partially CISC.



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

**0x06**: Divide: does C=A/B, stores remander in D.

**0x07**: Jump: jumps to the ROM location in A.

**0x08**: Compare: compares A and B, stores flags in C.

**0x09**: Jump equal: jumps to A in ROM if C has the equal flag.

**0x0A**: Jump not equal: jumps to A in ROM if C doesn't have the equal flag.

**0x0B**: Jump greater: jumps to A in ROM if C has the greater flag.

**0x0C**: Jump lesser: jumps to A in ROM if C has the lesser flag.

**0x0D**: Right shift: shifts A by B to the right.

**0x0E**: Left shift: shifts A by B to the left.

**0x0F**: NOT A: inverts A and puts it into C.

**0x10**: NOT B: inverts B and puts it into C.

**0x11**: XNOR: XNORs A and B and puts it into C.

**0x12**: AND: ANDs A and B and puts it into C.

**0x13**: OR: ORs A and B and puts it into C.

**0x14**: Jump RAM: Jumps to A in RAM.

**0x15**: Get RAM Chips: returns which RAM chips are connected in A.

**0x16**: Get RAM Location: returns the current RAM address in A.

**0x17**: Toggle use RAM for command.

**0x18**: Copy A to B.

**0x19**: Copy A to H.

**0x1A**: Copy B to A.

**0x1B**: Copy B to H.

**0x1C**: Copy C to A.

**0x1D**: Copy C to B.

**0x1E**: Copy C to H.

**0x1F**: Copy H to A.

**0x20**: Copy H to B.

**0x21**: Copy H to C.

**0x22**: Copy Mov1 to A.

**0x23**: Copy A to Mov1.

**0x24**: Copy Mov1 to B.

**0x25**: Copy B to Mov1.

**0x26**: Copy Mov1 to C.

**0x27**: Copy C to Mov1.

**0x28**: Copy Mov2 to A.

**0x29**: Use RAM for 1 command, then continue using ROM.

**0xBF to 0xFF**: Sets a register to this-0xBF.

## Adding/Removing RAM

To add or remove RAM, please consult your software's manual for which RAM chips are needed.