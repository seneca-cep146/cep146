---
title: "Setting Up Your Coding Workshop"
subtitle: "Course Notes — Installing C/C++ Compilers and VS Code"
---

# Setting Up Your Coding Workshop

---

## 1. Why Are We Doing This?

Before a mechanic can fix a car, they need a garage full of the right tools. Before you can write and run a computer program, you need a similar "workshop." In programming, that workshop is called an **IDE** — an **Integrated Development Environment**.

An IDE bundles together three things you need to turn your typed instructions into a running program:

| Tool | What it does | Car-shop analogy |
|---|---|---|
| **Text/code editor** | Where you type your program | The workbench where you write the repair plan |
| **Compiler** | Translates your human-readable code (C/C++) into instructions the computer's processor understands | The engine hoist — turns raw parts into a working engine |
| **Debugger / Runner** | Lets you run the program and find mistakes | The diagnostic scanner that tells you what's wrong |

To keep things simple and consistent, everyone in this course will use **Visual Studio Code (VS Code)** as their editor. However, VS Code is just a workbench; it does not come with a compiler. **You must install a compiler first, and then configure VS Code.**

---

## 2. What You Will Install

| Your computer | Step 1: Install Compiler | Step 2: Install Editor |
|---|---|---|
| **Mac** | Command Line Tools (Clang) | Visual Studio Code |
| **Windows** | Build Tools for Visual Studio (MSVC) | Visual Studio Code |

Follow the steps for your specific operating system below, and then complete the VS Code setup.

---

## 3. Mac Users: Installing the Compiler (Clang)

Apple provides the Clang compiler via its Command Line Tools, which avoids having to download the massive Xcode application.

1. Open the **Terminal** app (search for "Terminal" using Spotlight — the magnifying glass icon top-right of your screen).
2. Type the following and press Enter:
   `xcode-select --install`
3. If a window pops up asking to install the Command Line Tools, click **Install**.
4. **Verify It Worked:** In the same Terminal window, type:
   `clang --version`
   If you see version text appear (something like `Apple clang version 15.0.0`), your compiler is ready. 

---

## 4. Windows Users: Installing the Compiler (MSVC)

To get the Windows compiler without the full Visual Studio IDE, we will install the standalone Build Tools.

1. Open your web browser and search for **"Build Tools for Visual Studio"** on Microsoft's official download page.
2. Download and run the installer.
3. The installer will show a list of workloads. Find and check the box for **"Desktop development with C++"**.
4. Click **Install** in the bottom-right corner.
5. When it finishes, it may ask you to restart your computer. Do so if prompted.

---

## 5. All Users: Installing and Configuring VS Code

Now that your computer has a compiler, we can set up your editor.

1. Go to `https://code.visualstudio.com/` and click the **Download** button matching your operating system.
2. Run the installer, accepting the default options.
3. Open VS Code.
4. On the left sidebar, click the **Extensions** icon (it looks like four squares, with one detached).
5. Search for **"C/C++"** (make sure the publisher is Microsoft) and click **Install**.

You are now ready to write and run code! Proceed to Lab 0.
