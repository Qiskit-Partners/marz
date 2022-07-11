# marz

Marz is a **m**easurement **a**nd **r**eset simplification routine that collapses measure + reset pairs of operations on into a single measurement followed by a control-x gate.  This optimization is suitable for use on IBM Quantum systems, where the reset operation is performed by a meausrement followed by a conditional x-gate.  `marz` therefore saves one measurement per operation pair.  Because measurements are the operations with the largest error rates on IBM Quantum systems, and each measurement takes ~2 CNOT gates worth of time, this optimization reduces error rates and can reduce the duration of quantum circuits (dephasing) that impliment qubit reuse.


## Usage

Marz is really easy to use as it has a single function:

```python

import marz

optim_circ = marz.collapse_meas_reset_pairs(input_circ)
```

One can also pass a list of circuits and get a list of optimized circuits back.
