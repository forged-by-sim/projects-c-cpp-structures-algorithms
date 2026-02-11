# 🧠 M1 – C Debugging & Output Tasks  
**Folder**: `c1-c-basics-containers/m1`  
**Focus**: Writing clean terminal output, fixing syntax errors, and formatting C strings with precision

⸻

## 🧪 Projects Completed

### ✅ Task 1: Debug a Broken Program – *Fix Dr. P’s Mistake*  
Challenge: Review a flawed `printf()` statement and correct the output.

🔧 What I Did:
- Examined the buggy code in `fix-dr-p-mistake.png`
- Found the error: single quotes (`' '`) instead of double quotes (`" "`) around a string  
- Rewrote the program to print "hello world" correctly  
- Compiled and verified the fixed output in `hello-world.c`

```c
#include <stdio.h>

int main(void) {
    printf("hello world\n");
    return 0;
}


## ✅ Task 2: Format Output with Style – Print a Poem

Challenge: Use chained printf() statements to display a poem with intentional formatting.

📝 What I Did:

Created a multi-line poem in dream-poem.c

Used \n for clean line breaks and terminal spacing

Applied C syntax to express rhythm and structure in output

#include <stdio.h>

int main(void) {
    printf("I dream of code, both day and night.\n");
    printf("With logic clear and functions tight.\n");
    printf("Braces curl, the loops align,\n");
    printf("In silent runs, the bugs resign.\n");
    return 0;
}


⸻

📁 Folder Contents
File Name	Description
hello-world.c	Corrected version of the broken Hello World task
dream-poem.c	Custom poem using printf() and line breaks
fix_dr_p_mistake.png	Screenshot of the original flawed program
prompts-hello-world-poem.txt	Brainstorming notes and poetry draft prompts

⸻

🔍 Key Skills Demonstrated

Syntax debugging and compiler error interpretation

Mastery of printf() formatting and escape characters

Structuring human-readable output in C

Attention to detail through poetic code

⸻

🪞 Reflection

These tasks were a gentle yet powerful introduction to C programming. Debugging syntax reinforced attention to small details, while writing a poem with code gave me space to play with logic and structure creatively. It reminded me that code, like poetry, is all about intention — and even in the smallest tasks, clarity matters.