# Counter machine
Implemented in ModuleSim, a simulator for the Bristol-designed build-a-comp modules.

## Setup
### Decoder
* Shifts are used to get `xCBx` to `xxCB` from the opcode `DCBA`, this is used
  to control the first stage of MUX decoding.
* LSH: `0001`, shift up by one to remove `D` giving `CBA0`
* RSH: `0010`, shift down by two to get `00CB`

#### Input MUX to Central AU
* Lower MUX: `0000`: Register 0
* Upper MUX: `0010`: Memory

#### Output DMUX from Central AU
* Lower  MUX: `0000`: Register 0
* Upper  MUX: `0010`: Memory

### Central AU
* Input B: `0001` (used to increment or decrement registers)

#### AU control
* Lower  MUX: `0000`: Add
* Middle MUX: `0110`: Subtract
* Upper  MUX: `0001`: Pass through

### Program Counter 
* MUX input: `0001`
* Input B: `0001` (used to increment instruction address)
