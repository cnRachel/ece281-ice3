# ECE 281 ICE 3: Ripple-Carry Adder with Top Level Design

This is a **template** repository.

[ICE 3 instructions](https://usafa-ece.github.io/ece281-book/ICE/ICE3.html)

Targeted toward Digilent Basys3. Make sure to install the [board files](https://github.com/Xilinx/XilinxBoardStore/tree/2018.2/boards/Digilent/basys3).

Tested on Vivado 2024.2

---

## GitHub Actions Testbench

The workflow uses the [setup-ghdl-ci](https://github.com/ghdl/setup-ghdl-ci) GitHub action
to run a *nightly* build of [GHDL](https://ghdl.github.io/ghdl/).

First, the workflow uses GHDL to **analyze** all `.vhd` files in `src/`.

Then it **elaborates** the entity defined by `$TB_ENTITY`

Finally, the workflow **runs** the simulation. If successful then it will quietly exit with a `0` code.
If any of the `assert` statements fail then GHDL will cease the simulation and exit with non-zero code; this will also cause the workflow to fail.
Assert statements of other severity levels will be reported, but not fail the workflow.

---

## Images and Diagrams

![Over 10‑ns intervals I applied vectors to (B,A,Cin) using an 8‑bit w_addends. The waveform shows: 0+0+0 gives S=0,Cout=0; F+F+1 gives S=F,Cout=1; 0+0+1 gives S=1,Cout=0; A+3 gives S=D,Cout=0; and E+2 gives S=0,Cout=1. This confirms correct sum, carry‑in handling, and carry‑out on overflow for a 4‑bit ripple‑carry adder.](ripple_adder_waveform.png)

![Block diagram showing how the Basys3 switches connect to the ripple_adder component and how its outputs drive the LEDs.](top_basys3_entity_sketch.png)

## Documentation

None