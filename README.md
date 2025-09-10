# Operating System and Security Project

## Welcome

Welcome to the "Operating System and Security" project repository! This repository hosts a project that involves exploring and exploiting vulnerabilities in ELF binaries on Linux systems. The project is divided into two parts, each focusing on different aspects of binary exploitation.

## Part 1: Hacking the Given Program (vuln)

A binary file is provided that contains a simple password check.

The program is written in a way that makes it possible to trick.

GDB (debugger) is used to look inside the program and study its memory and functions.

ASLR is turned off so memory addresses stay fixed and easier to analyze.

By sending very long input, the program crashes, showing a vulnerability.

A special input (exploit) is then crafted to overwrite memory and change what the program does, such as jumping to a hidden function that grants access.

Screenshots are collected at each step as proof of progress.

## Part 2: Making and Hacking a Custom Program

A simple C program is created with an unsafe function such as gets(), which does not check input size.

Normal input behaves fine, but very long input crashes the program, proving the presence of a buffer overflow.

The exploit is performed using the Return-to-libc technique:

Find the address of system() in the libc library.

Find the address of the string "/bin/sh" in libc.

Overwrite the program’s return address so that execution jumps to system("/bin/sh"), opening a shell.

With ASLR disabled, the exploit works reliably.

With ASLR enabled, memory addresses change every run, so the exploit only succeeds occasionally. Brute forcing (repeated attempts) is used to bypass this defense.

## Disclaimer

Please note that this project is for educational purposes only. It is not intended to encourage any malicious activities. Always use your knowledge responsibly and respect ethical boundaries.

Happy learning and exploring the world of binary exploitation in Linux systems!

