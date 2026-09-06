# Dual-Pump Control & Monitoring System (CODESYS v3.5)

A practical PLC (Programmable Logic Controller) automation project designed to control a dual-pump system with software interlocking, real-time runtime tracking, and an intuitive HMI (Human-Machine Interface). 

Implemented in **CODESYS v3.5** using **Ladder Diagram (LD)** for control logic and **Structured Text (ST)** for data processing and string manipulation.

---

## 🚀 Key Features

* **Interlocked Start/Stop Logic:** Prevents both pumps from running simultaneously to balance the load and satisfy industrial safety constraints. Includes a general Stop button.
* **Optimized Task Configuration:** Program execution is bound to a cyclic task with a **20ms interval**, ensuring instantaneous response to HMI inputs and precise execution.
* **Self-Resetting Pulse Generators:** Created 1-second pulse triggers using standard On-Delay Timers (`TON`) combined with edge detection (`P-Edge` / `R_TRIG`) to cleanly increment runtimes without PLC scan-cycle overhead.
* **Advanced Data Processing:** Converts raw cumulative seconds into a human-readable format (`Xm Ys`) using mathematical division (`/`), remainder operations (`MOD`), data conversion (`INT_TO_STRING`), and string concatenation (`CONCAT`).
* **HMI Visualization:** Custom interactive dashboard that displays the current operation status and separate dynamic labels for *Current Cycle Runtime* and *Total Lifetime Runtime*.

---