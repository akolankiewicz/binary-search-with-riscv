# Binary Search in RISC-V with Dynamic Allocation

This repository contains the implementation of the Binary Search algorithm in RISC-V Assembly language. The project was developed as part of the Computer Organization course and includes the use of dynamic memory allocation (Heap).

## Authors
- Arthur Kolankiewicz
- Gabriel Farina

## About the Project

The program performs a search for a specific value within a sorted array. The main feature of this implementation is the use of dynamic memory allocation. The array, initially defined in the `.data` section, is copied to the Heap at runtime before the search is performed.

### Key Components
- **Dynamic Allocation:** Uses the system call (`syscall`) `sbrk` (`ecall 9`) to reserve space in the Heap.
- **Binary Search:** Implemented in the modular function `b_search`, which uses the RISC-V calling convention (saving registers on the stack) to perform the search efficiently.
- **Error Handling:** If the value is not found, the program returns `-1`. If found, it returns the index (position) of the value in the array.

## How to Run the Program

To execute this code, we recommend using the **Venus** simulator, which is widely used for RISC-V programs. Follow the step-by-step instructions below:

### Step 1: Access the Simulator
You can use the web version of Venus or the Visual Studio Code extension.
- **Web Version:** Access [Venus Web Simulator](https://venus.cs61c.org/).s.

### Step 2: Load the Code
1. In the Venus simulator, go to the **Editor** tab.
2. Copy the entire content of the `programa.riscv` file (or the provided source code file) and paste it into the editor.

### Step 3: Assemble the Code
1. After pasting the code, click on the **Simulator** tab (or the "Assemble & Simulate from Editor" button, depending on the version).
2. The simulator will translate the Assembly code into machine code. If there are no syntax errors, you are ready to run.

### Step 4: Run the Program
1. In the **Simulator** tab, click the **Run** button to execute the entire program at once.
2. Alternatively, you can use the **Step** button to execute the code line by line and observe the behavior of registers and memory.

### Step 5: Check the Result
The search result will be displayed in the simulator's console or stored in register `a1`.
- **Success Case:** If the searched value (e.g., `38`) is in the array, register `a1` will contain the corresponding index (e.g., `11`).
- **Failure Case:** If the searched value (e.g., `39`) is not in the array, register `a1` will contain the value `-1`.

## Changing Test Data
To test different scenarios, you can modify the following variables in the `.data` section of the code:
- `dados`: The array of numbers (remember: **must be sorted in ascending order**).
- `alvo`: The value you want to search for.
- `tamanho`: The number of elements in the array.

---
*Project developed for academic purposes.*
