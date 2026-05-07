# Custom Unix Shell

A Bash-inspired Unix shell written in C as part of the Hive Helsinki curriculum.

This project was built to deepen my understanding of Unix systems programming, process management, parsing, and inter-process communication.
The goal was not only to recreate basic shell behavior, but also to better understand how shells work internally at the system level.

---

## 📌 Project Goals

Through this project, I wanted to strengthen my understanding of:

- Process creation and management
- File descriptors and redirections
- Pipes and inter-process communication
- Parsing and tokenization
- Signal handling
- Environment variable management
- Memory management in C

---

## ⚙️ Features

- Execute commands using absolute, relative, and `$PATH` resolution
- Pipe support (`|`)
- Input/output redirections (`<`, `>`, `>>`, `<<`)
- Environment variable expansion (`$VAR`)
- Built-in commands:
  - `echo`
  - `cd`
  - `pwd`
  - `export`
  - `unset`
  - `env`
  - `exit`
- Signal handling (`Ctrl-C`, `Ctrl-D`, `Ctrl-\`)

---

## 🛠 Technical Approach

One of the main focuses of this project was designing a clean parsing flow.

I implemented a lexer and parser to process user input into executable commands while handling quotes, pipes, and redirections correctly.
I chose this structure because separating tokenization from execution made debugging and feature expansion significantly easier.

For process execution, we used `fork()`, `execve()`, and `wait()` to manage child processes and command execution.
Pipes were implemented using file descriptor duplication and inter-process communication through `pipe()`.

Signal handling was another important part of the project, especially reproducing shell-like behavior during interactive execution and heredoc handling.

---

## 🚧 Challenges

Some of the biggest challenges during development were:

- Managing memory correctly across multiple execution flows
- Handling edge cases in parsing and quoting
- Synchronizing pipes and child processes
- Reproducing Bash-like behavior for signals and exit statuses

Debugging these issues significantly improved my understanding of low-level system behavior and process lifecycle management.

---

## 📚 What I Learned

This project gave me practical experience working close to the operating system level.

I developed a much stronger understanding of:
- Unix process management
- Parsing architecture
- File descriptor manipulation
- Signals and process synchronization
- Debugging complex C applications

It also taught me how important code structure and modular design are in larger C projects.

---
