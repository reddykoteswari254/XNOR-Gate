# XNOR Gate Using Verilog

## Overview

This project implements a 2-input XNOR (Exclusive-NOR) gate using Verilog HDL.

An XNOR gate produces a logic `1` when both input signals are the same. It produces a logic `0` when the inputs are different.

## Objective

The objective of this project is to:

* Design an XNOR gate using Verilog HDL.
* Create a Verilog testbench.
* Simulate all possible input combinations.
* Verify the output using the XNOR truth table.
* Observe the simulation waveform using a VCD file.

## XNOR Logic

The Boolean expression for an XNOR gate is:

```text
Y = ~(A ^ B)
```

Where:

* `A` = First input
* `B` = Second input
* `Y` = XNOR output

## Truth Table

| A | B | Y |
| - | - | - |
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

## Files

```text
xnor-gate-verilog/
│
├── README.md
├── xnor_gate.v
├── xnor_gate_tb.v
├── simulation/
│   └── waveform.vcd
└── output/
    └── simulation_output.txt
```

## Verilog Module

The XNOR gate is implemented using the XOR operator followed by a NOT operation.

```verilog
module xnor_gate (
    input A,
    input B,
    output Y
);

assign Y = ~(A ^ B);

endmodule
```

## Simulation

This project can be simulated using tools such as:

* Icarus Verilog
* GTKWave
* EDA Playground
* ModelSim

### Using Icarus Verilog

Compile the design and testbench:

```bash
iverilog -o xnor_sim xnor_gate.v xnor_gate_tb.v
```

Run the simulation:

```bash
vvp xnor_sim
```

A waveform file named `waveform.vcd` will be generated.

## View Waveform

Open the waveform using GTKWave:

```bash
gtkwave waveform.vcd
```

Add the signals `A`, `B`, and `Y` to the waveform window.

## Expected Simulation Output

```text
Time = 0 | A = 0 | B = 0 | Y = 1
Time = 10000 | A = 0 | B = 1 | Y = 0
Time = 20000 | A = 1 | B = 0 | Y = 0
Time = 30000 | A = 1 | B = 1 | Y = 1
```

The exact displayed time may depend on the simulator and timescale settings.

## Result

The XNOR gate was successfully designed and simulated using Verilog HDL. The simulation confirms that the output is `1` when both inputs are equal and `0` when the inputs are different.

## Applications

XNOR gates are commonly used in:

* Digital comparators
* Equality checking circuits
* Error detection circuits
* Arithmetic and logic circuits
* Digital communication systems

## Author

**Koteswari Reddy**

## License

This project is created for educational and academic purposes.
