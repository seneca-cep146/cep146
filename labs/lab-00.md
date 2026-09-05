---
title: "Lab 0: Prove Your Workshop Works"
subtitle: "Verifying Your Xcode / Visual Studio Installation with a Hello World Program"
---

# Lab 1: Prove Your Workshop Works

**Estimated time:** 20–30 minutes
**Prerequisite:** You must have already completed the setup notes ("Setting Up Your Coding Workshop") for your operating system.

## Goal

A workshop is only useful if the tools actually work. In this lab, you will write the smallest possible program — one that just prints a greeting — and get it running on your own computer. If this program runs, it proves your compiler, editor, and debugger are all correctly installed and talking to each other. Every future lab in this course depends on this working.

## What You Need

- A laptop with either **Xcode** (Mac) or **Visual Studio** (Windows) installed, per the setup notes.
- No internet connection is required for this lab itself.

## Learning Objectives

By the end of this lab, you will be able to:
1. Create a new C/C++ project inside your IDE.
2. Identify the three basic parts of a simple C/C++ program.
3. Build ("compile") and run a program.
4. Read and interpret console output.

---

## Part A — Mac Users (Xcode)

1. Open **Xcode**.
2. On the welcome screen, click **"Create New Project…"** (or go to **File → New → Project**).
3. Choose **macOS** across the top, then select **Command Line Tool**, and click **Next**.
4. Fill in:
   - **Product Name:** `HelloWorkshop`
   - **Language:** `C` (use the dropdown — if C is not listed, choose C++)
5. Click **Next**, choose a folder to save it in (e.g., Desktop), and click **Create**.
6. Xcode will open a file called `main.c` with some starter code already inside. Replace its contents with exactly this:

   ```c
   #include <stdio.h>

   int main(void) {
       printf("Hello, Workshop! My name is: [TYPE YOUR NAME HERE]\n");
       printf("My compiler is working.\n");
       return 0;
   }
   ```
7. Replace `[TYPE YOUR NAME HERE]` with your actual name, inside the quotes.
8. Press the **▶ (Play/Run)** button in the top-left corner of Xcode.
9. A console panel should appear at the bottom of the window showing your two printed lines.

---

## Part B — Windows Users (Visual Studio)

1. Open **Visual Studio**.
2. Click **"Create a new project."**
3. Search for **"Console App"**, and in the results, choose the one where the language tag on the right reads **C++**.
4. Click **Next**. Set:
   - **Project name:** `HelloWorkshop`
   - Leave the location as default, or choose your Desktop.
5. Click **Create**.
6. Visual Studio opens a file called `HelloWorkshop.cpp` with starter code. Replace its entire contents with exactly this:

   ```cpp
   #include <iostream>

   int main() {
       std::cout << "Hello, Workshop! My name is: [TYPE YOUR NAME HERE]" << std::endl;
       std::cout << "My compiler is working." << std::endl;
       return 0;
   }
   ```
7. Replace `[TYPE YOUR NAME HERE]` with your actual name, inside the quotes.
8. Press **Ctrl+F5** to run **without** debugging (this keeps the window open so you can read the output — plain **F5** will flash and close it).
9. A black console window should appear showing your two printed lines, followed by "Press any key to continue . . ."

---

## Part C — Optional: Run It Again in VS Code

*Only attempt this if you completed the optional VS Code section of the setup notes, and only after finishing Part A or B above.*

1. Open VS Code and open the folder containing your `hello.c` or `hello.cpp` file (create one if you don't have it, using the same code as above).
2. Open the built-in terminal: **Terminal → New Terminal**.
3. Compile and run:
   - **Mac:** `clang hello.c -o hello && ./hello`
   - **Windows:** Open the **"Developer Command Prompt for VS"** from the Start Menu instead of VS Code's regular terminal, then run `cl hello.cpp` followed by `hello.exe`
4. Confirm you see the same two lines of output as before.

---

## Understanding What You Just Did (Read After Running Your Program)

Look back at the code you typed. Three parts matter most right now:

| Line | Plain-language meaning |
|---|---|
| `#include <stdio.h>` or `#include <iostream>` | "Borrow a pre-built toolbox for printing text to the screen." Every program starts by borrowing tools other people already built. |
| `int main(void) { ... }` or `int main() { ... }` | "This is where the program starts running." Every C/C++ program has exactly one `main`. |
| `printf(...)` or `std::cout << ...` | "Print this text to the screen." This is the actual instruction that produced your output. |

When you clicked **Run**, three things happened automatically, in order:
1. **Compiling** — your compiler (Clang or MSVC) translated your readable code into instructions the processor understands.
2. **Linking** — the compiler attached the "toolbox" you borrowed (`stdio.h` / `iostream`) to your program.
3. **Running** — the finished program executed, and its output appeared in the console.

---

## Submission Checklist

Submit a single screenshot showing **both**:
- [ ] Your code file with your name visible in the `printf` / `std::cout` line
- [ ] The console output showing the two printed lines

Save the screenshot as `LastName_FirstName_Lab1.png` and submit it via the course portal.

---

## Troubleshooting

| Symptom | Fix |
|---|---|
| Xcode: "No such file or directory" for `stdio.h` | Confirm you chose **Command Line Tool** as the template, not something else like a macOS App |
| Visual Studio: Red squiggly lines under `std::cout` | Confirm the project language is C++, not C — check File name ends in `.cpp` |
| Nothing appears when you press Run | Make sure you saved the file first (Ctrl+S / Cmd+S) before running |
| "Build failed" error message | Check for a missing semicolon `;` at the end of a line, or a missing closing brace `}` — this is the single most common beginner mistake |

