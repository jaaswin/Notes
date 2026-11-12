# What is SystemVerilog?

SystemVerilog is a Hardware Description and Verification Language (HDVL) used in VLSI design and Design Verification.

It is an extension of Verilog that provides additional features for designing, testing, and verifying complex digital circuits.

In simple words:

- Verilog: Used to describe digital hardware.
- SystemVerilog: Used to describe digital hardware and verify whether it works correctly.

SystemVerilog is widely used in the semiconductor industry, especially for ASIC design verification.

## 1. Why do we need SystemVerilog?

Imagine an engineer designs a digital circuit such as a processor or memory controller.

Before manufacturing the chip, engineers need to check whether the design works correctly under different conditions.

SystemVerilog helps verification engineers:

- Generate different test inputs.
- Check expected and actual outputs.
- Detect design errors.
- Verify complex digital circuits.
- Automate testing using testbenches.

## 2. Difference between Verilog and SystemVerilog

| Verilog                         | SystemVerilog                                  |
| ------------------------------- | ---------------------------------------------- |
| Hardware Description Language   | Hardware Description and Verification Language |
| Mainly used for hardware design | Used for hardware design and verification      |
| Basic data types                | Advanced data types                            |
| Limited verification features   | Advanced verification features                 |
| Supports basic testbenches      | Supports advanced testbenches                  |
| Does not have classes           | Supports object-oriented programming           |

Important: SystemVerilog is backward-compatible with Verilog, meaning it supports traditional Verilog code.

## 3. Important features of SystemVerilog

### 1. Data Types

SystemVerilog supports different data types to represent digital signals.

Examples:

- `bit`
- `logic`
- `int`
- `byte`
- `enum`

The `logic` data type is commonly used to represent digital signals.

### 2. Testbench

A testbench is a testing environment used to verify whether a digital circuit works correctly.

For example, if we design an AND gate, the testbench provides different input combinations and checks the output.

[\[Digital 회로 설계\] SystemVerilog로 Testbench 설계하기 1편](https://images.openai.com/static-rsc-4/ag7nnY3bD7Cyp39jSCG1c8p9sW_XoHhGM_vu-pbC3yIjtlL2ZQ2q0nfa5NZqCc15BDgnmRXpULcfnI8WwNYdlSK6f433zG_20jjqafnTUJIjaJRXnASDDCWv4mBzlRqH9e08G8uSMXA3sTcZobis-HUz_C2CP3BnyKAw270n8Yg?purpose=inline)

### 3. Assertions

Assertions are used to check whether certain conditions are satisfied during simulation.

For example:

If a clock signal has a rising edge and the input is 1, the output of a D flip-flop should become 1 after the appropriate simulation scheduling.

Assertions help identify unexpected behaviour.

### 4. Classes and Objects

SystemVerilog supports object-oriented programming concepts.

- Class: A blueprint for creating objects.
- Object: An instance of a class.

These features help create reusable verification environments.

### 5. Randomization

SystemVerilog can generate random test inputs automatically.

For example, instead of manually entering 100 different input combinations, we can generate random values to test the circuit.

### 6. Functional Coverage

Functional coverage helps determine whether important scenarios and conditions have been tested.

It helps verification engineers identify missing test cases.

## 4. What is a DUT in SystemVerilog?

DUT stands for Design Under Test.

It is the actual hardware design that we want to verify.

For example:

- AND gate
- Multiplexer
- Counter
- D flip-flop
- Memory controller

The testbench provides inputs to the DUT and checks its outputs.

[Exploring SystemVerilog Testbenches for VLSI Verification | Chandrakiran G posted on the topic | LinkedIn](https://images.openai.com/static-rsc-4/hPlJYPADrNSMc3kG-viFz490_y_CcijrzuQvH8i8W4zCF_wJgvb3H3LF8Fs8sH6Bd87O7fRAgeYHQ45AkCPgF5-zLZzMSe7tQZSGdm8ZPc0J0BWt2xIkdM_aqwd92lJp6LhgjKDT5L4bLzEldOdDYDj_4WyON66CFH9HCJ3J5pE?purpose=inline)

## 5. Simple SystemVerilog example

Let's take an AND gate.

Design code:

```
module and_gate(
    input logic A,
    input logic B,
    output logic Y
);

assign Y = A & B;

endmodule
```

Testbench code:

```
module and_gate_tb;

logic A, B;
wire Y;

and_gate dut(A, B, Y);

initial begin

A = 0; B = 0;
#10;

A = 0; B = 1;
#10;

A = 1; B = 0;
#10;

A = 1; B = 1;
#10;

$finish;

end

endmodule
```

Explanation:

- `module`: Defines a module.
- `logic`: Represents digital signals.
- `dut`: Instance of the design under test.
- `initial`: Executes the test sequence.
- `#10`: Waits for 10 simulation time units.
- `$finish`: Ends the simulation.

The testbench applies all four input combinations to the AND gate.

## 6. What is UVM?

Important for Design Verification

UVM stands for Universal Verification Methodology.

It is a standardized methodology built using SystemVerilog to verify complex digital designs.

It provides a structured way to create reusable verification environments.

Some important UVM components are:

- Sequence: Generates test scenarios.
- Driver: Sends stimulus to the DUT.
- Monitor: Observes DUT signals.
- Sequencer: Controls the sequence of transactions.
- Scoreboard: Compares actual and expected results.
- Agent: Groups verification components.

[#uvm #verification #axi #rtldesign #systemverilog #constrainedrandom #functionalcoverage #soc #amba #vlsi #hardwareverification #designverification #fpga #asic | Sumit kumar](https://images.openai.com/static-rsc-4/kp02S32xlagh_wiRVATqwGa9ldZM-H7G5V18BNU7jO4qoQPSlZX6w-Qjtv1gLemC1M-JHD_EDd-mxaTQVR4WFcxFG0zUwc_PIfeL_Soq4B1I6ZmQI8cuDE0O2eav1dmSWi4XUYTLdDHmUma6U5dTdz7xlnOGoBS7aokQzcdQUJs?purpose=inline)

You don't need to master UVM immediately. First understand Verilog and SystemVerilog fundamentals.

## 7. Verilog vs SystemVerilog vs UVM

| Term          | Purpose                                                                |
| ------------- | ---------------------------------------------------------------------- |
| Verilog       | Describes digital hardware                                             |
| SystemVerilog | Describes hardware and provides advanced verification features         |
| UVM           | Provides a structured methodology for SystemVerilog-based verification |

## 8. Important Edveon interview questions

Here are 10 beginner-level questions to prepare:

1. What is SystemVerilog?
2. What is the difference between Verilog and SystemVerilog?
3. What is a testbench?
4. What is DUT?
5. What is the difference between `wire`, `reg` and `logic`?
6. What is an assertion?
7. What is randomization?
8. What is functional coverage?
9. What is UVM?
10. What is the difference between verification and validation?

