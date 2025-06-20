# Toggle Memory Biosensor (IPTG Triggered)

This project simulates a genetic toggle switch that can store memory of a signal — in this case, IPTG. Once triggered, the circuit flips into an ON state and stays there, even after the signal is removed. This kind of behavior is useful in biosensors, diagnostics, and environmental monitoring tools.

## Overview

The toggle switch is built using two genes that repress each other. IPTG temporarily suppresses one gene, allowing the other to rise. The result is a permanent shift in gene expression, shown through a fluorescent reporter (GFP).

### Key Components

- Gene A: Represses gene B
- Gene B: Represses gene A and activates GFP
- IPTG: The input signal that inhibits gene A
- GFP: Output signal that shows the system's memory state

## How It Works

1. At the start, gene A is active and keeps gene B off.
2. When IPTG is added, it inhibits gene A.
3. This allows gene B to rise and activate GFP.
4. Even after IPTG is removed, gene B continues to repress gene A.
5. The system stays in the ON state — memory is retained.

## What the Plot Shows

The simulation runs in three phases:
- Phase 1: No IPTG, GFP stays low.
- Phase 2: IPTG is added, GFP increases.
- Phase 3: IPTG is removed, but GFP stays high.

This confirms the memory function of the switch.

## Design Choices and Limitations

- A small leak of gene B was added to allow the switch to flip reliably.
- Parameters were tuned to make sure the flip happens cleanly without bouncing back.
- Real biological systems can be noisy, but this simulation is deterministic.

## How to Run the Simulation

1. Install requirements:
   pip install tellurium matplotlib numpy

2. Run the Python script:
   python toggle_memory_biosensor.py

This will generate a PNG plot showing the GFP levels over time.

## Future Work

- Add a reset signal to flip the system back to OFF.
- Simulate with biological noise (stochastic modeling).
- Chain with other logic gates for more advanced circuits.

## Author

This project was built as part of an independent learning track in synthetic biology, with a focus on mastering memory circuits and real-world signal processing.