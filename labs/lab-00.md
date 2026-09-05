---
Title: "Lab 0: Prove Your Workshop Works"
subtitle: "Verifying Your Installation with a Hello World Program in VS Code"
---

# Lab 1: Prove Your Workshop Works

**Estimated time:** 20–30 minutes
**Prerequisite:** You must have already completed the setup notes ("Setting Up Your Coding Workshop") for your operating system.

## Goal

A workshop is only useful if the tools actually work. In this lab, you will write the smallest possible program — one that just prints a greeting — and get it running on your own computer using Visual Studio Code. If this program runs, it proves your compiler and editor are correctly installed and talking to each other. Every future lab in this course depends on this working.

## What You Need

- A laptop with your OS-specific compiler (Clang for Mac or MSVC for Windows) and **VS Code** installed.
- No internet connection is required for this lab itself.

## Learning Objectives

By the end of this lab, you will be able to:
1. Create and manage a C/C++ project inside VS Code.
2. Identify the three basic parts of a simple C/C++ program.
3. Build ("compile") and run a program using terminal commands.
4. Read and interpret console output.

---

## Part A — Writing Your Program

1. Create a new folder on your computer (e.g., `lab0-workshop` on your Desktop). 
2. Open VS Code, click **File → Open Folder**, and select the folder you just created.
3. In the VS Code Explorer pane (left side), click the **New File** icon. 
4. Name the file `hello.c` (if you are learning C) or `hello.cpp` (if you are learning C++).
5. Paste the exact code below into your new file:

   **For C (`hello.c`):**
   ```c
   #include <stdio.h>

   int main(void) {
       printf("Hello, Workshop! My name is: [TYPE YOUR NAME HERE]\n");
       printf("My compiler is working.\n");
       return 0;
   }
   ```

6. Replace `[TYPE YOUR NAME HERE]` with your actual name, inside the quotes.
7. Save the file (**Ctrl+S** on Windows or **Cmd+S** on Mac).

---

## Part B — Compiling and Running

### Mac Users
1. Open the built-in terminal in VS Code: **Terminal → New Terminal**.
2. Type the following command to compile and run your code, then press Enter:
   `clang hello.c -o hello && ./hello`
3. Your terminal should display your two printed lines.

### Windows Users
*Note: The standard VS Code terminal may not link to the MSVC compiler automatically. Use the Developer Command Prompt instead.*
1. Open the Start Menu and search for **"Developer Command Prompt for VS"**. Open it.
2. Navigate to your project folder. (Use `cd Desktop\lab0-workshop` to change directories).
3. Compile your program by typing:
   `cl hello.cpp`
4. Run your finished program by typing:
   `hello.exe`
5. The window should display your two printed lines.

---

## Understanding What You Just Did

Look back at the code you typed. Three parts matter most right now:

| Line | Plain-language meaning |
|---|---|
| `#include <stdio.h>` or `#include <iostream>` | "Borrow a pre-built toolbox for printing text to the screen." Every program starts by borrowing tools other people already built. |
| `int main(void) { ... }` or `int main() { ... }` | "This is where the program starts running." Every C/C++ program has exactly one `main`. |
| `printf(...)` | "Print this text to the screen." This is the actual instruction that produced your output. |

---

## Submission Checklist

Submit a single screenshot showing **both**:
- [ ] Your code file with your name visible in the `printf` / `std::cout` line
- [ ] The terminal output showing the two printed lines successfully running

Save the screenshot as `LastName_FirstName_Lab1.png` and submit it via the course portal.
