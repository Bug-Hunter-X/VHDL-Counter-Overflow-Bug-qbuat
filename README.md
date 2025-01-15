# VHDL Counter Overflow Bug

This repository demonstrates a common bug in VHDL code: an integer counter that can overflow.  The `buggy_counter.vhdl` file contains the buggy code.  The counter is incremented without a check to prevent it from exceeding its maximum value (15). This can lead to unpredictable behavior.

The `fixed_counter.vhdl` file shows the corrected code with proper overflow handling.

## Bug Description
The `buggy_counter` entity is a simple counter. However, it lacks bounds checking in its increment operation. Once the `internal_count` reaches 15, incrementing it again causes it to wrap around to 0, resulting in unexpected behavior if that wasn't intended. This is an example of an integer overflow error.

## Solution
The solution involves adding a conditional statement that prevents the counter from exceeding 15. The corrected counter uses a modulo operation to ensure that it wraps around correctly, if that is intended behavior. Otherwise, an error should be handled appropriately (e.g., assert statement).
