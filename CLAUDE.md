# CLAUDE.md — State Machine Framework

## Project Summary
Production-grade, modular state machine framework for embedded C systems. Handle-based, multi-instance, state-agnostic, zero-heap, ISR-safe. Platform-agnostic with weak-symbol HAL abstraction. Version 4.1.0 — the build-consistency release (fixed reserved `SM_EVT_TIMEOUT` id, build-wide FSM dimensions verified at `SM_Init`, atomic DIS pairs, timer-schedule lifecycle) on top of v4.0's semantic-correction release (strict-FIFO delivery, atomic transitions, bounded event drain, ms deadline-based timers).

## Build Commands
```bash
# Standard build
rm -rf build && mkdir build && cd build && cmake .. -DBUILD_EXAMPLES=ON && cmake --build .

# With tests
cmake .. -DBUILD_TESTS=ON -DBUILD_EXAMPLES=ON -DCMAKE_BUILD_TYPE=Debug && cmake --build . && ctest

# Run examples
./examples/basic_example
./examples/simulation_example
./examples/blinky_example
./examples/sensor_pipeline_example
./examples/error_recovery_example
./examples/multi_fsm_example

# Use as library in another project
add_subdirectory(path/to/state-machine-template)
target_link_libraries(your_target sm_framework)
```

## Read when

| File | Read when |
|------|-----------|
| `CLAUDE.full.md` | Architecture, conventions, TODO, session continuity |
| `Quick-Guide.md` | v4.1 quick reference |
| `README.md` | v4.1 project documentation |
| `MIGRATION.md` | v2→v3 migration guide |

Do not read CLAUDE.full.md unless the task needs project-wide architecture or conventions beyond this stub.