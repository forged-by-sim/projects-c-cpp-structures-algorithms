📘 Course 1 – Module 1: Introduction

Specialization: C and C++ for Everyone
Platform: Coursera – University of California, Santa Cruz
Tools Used: VS Code, GitHub, Local Compiler
Date Completed: October 6, 2025
Directory: course1-c-for-everyone-programming-fundamentals/module1-introduction

🧠 Objective of the Module

This module introduced the core structure of a C program, focusing on how a basic program is constructed, compiled, and debugged. It emphasized syntactic correctness, the main() function, #include directives, the printf() function, and proper use of semicolons and parentheses.

💻 Assignments Completed
✅ Fix Dr. P’s Mistake

Challenge: Correct a flawed Hello World program written by “Dr. P” with intentional syntax errors.

What I Did:

Reviewed the original code in Fix Dr. P’s mistake.png.

Located the syntax error: use of single quotes ' instead of double quotes " around the string in printf().

Rewrote and compiled the corrected version in hello_world.c:

#include <stdio.h>

int main(void) {
    printf("hello world\n");
    return 0;
}


Result: Successful compilation and execution of the Hello World output.

✅ Print a Poem

Challenge: Use the printf() statement to display a self-selected poem or verse.

What I Did:

Wrote a multi-line poem inside dream_poem.c using chained printf() statements with proper escape characters (\n) to format the lines cleanly.

Demonstrated line breaks and spacing inside terminal output using C syntax.

Example:

#include <stdio.h>

int main(void) {
    printf("I dream of code, both day and night,\n");
    printf("With logic clear and functions tight.\n");
    printf("Braces curl, the loops align,\n");
    printf("In silent runs, the bugs resign.\n");
    return 0;
}


📂 Folder Contents

Fix Dr. P’s mistake.png – Image of the original broken program.

hello_world.c – Fixed and compiled Hello World program.

dream_poem.c – Custom poem written in C using printf().

README_instructions.md – Original assignment prompt and directions.

🔍 Reflection

This module helped build a solid foundation in reading and correcting simple C programs. It offered a gentle start into debugging logic, taught how to interpret compiler errors, and encouraged creativity through code. Fixing syntax errors boosted my confidence in spotting common mistakes early, and writing a poem allowed for expressive formatting within technical constraints.