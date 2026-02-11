# 🧮 M2 – Arithmetic, Type Conversion & Static vs Dynamic Evaluation  
**Folder**: `c1-c-basics-containers/m2`  
**Focus**: Working with C expressions, debugging logic errors, and comparing data type behavior across static and dynamic contexts

⸻

## 🧪 Projects Completed

### ✅ Task 1: Debug a Broken Expression – *Fix Dr. P’s Mistake (Week 2)*  
Challenge: Correct a broken C program with type mismatches and syntax errors.

🧠 What I Did:
- Fixed type mismatches and missing semicolons  
- Validated integer-based expressions  
- Practiced identifying type-related bugs in low-level math logic  

---

### ✅ Task 2: Calculate Volume of a Sphere  
Challenge: Write a program to calculate the volume of a sphere using  
                                         `V = (4/3) * π * r³`

📐 What I Did:
- Created multiple versions: one using `float`, one with `double`, one with type casting  
- Practiced using `#define` for π  
- Explored how type casting (e.g., `4.0/3`) prevents integer division issues

---

### ✅ Task 3: Sine Calculation – Static vs Dynamic  
Challenge: Compare runtime vs hardcoded sine values using two programs.

🔍 What I Did:
- Wrote `sine-calculation.c` using `math.h` for dynamic runtime evaluation  
- Wrote `sine-static.c` using a fixed sine value approximation  
- Compared output precision between runtime and static approaches

⸻

🧠 Practice Files  
• `int-practice.txt` – Manual type checking and logic testing for integer expressions  
• `expressions-practice.txt` – Practice outputs and calculations for evaluating complex expressions  
• `expressions_thought_process.md` – Personal reflection and structured breakdown of arithmetic reasoning and conversion logic

⸻

## 📁 Folder Contents

| File Name                                        | Description                                      |
|--------------------------------------------------|--------------------------------------------------|
| `fix-dr-p-mistake.png`                          | Screenshot of broken program for debugging       |
| `volume-of-sphere.c`                            | Volume calculator using floats                   |
| `volume-of-sphere-as-double-using-ints.c`       | Volume calculator using `double` & type casting  |
| `sine-calculation.c`                            | Runtime sine calculation using `math.h`          |
| `sine-static.c`                                 | Fixed sine approximation                         |
| `int-practice.txt`                              | Integer operation experiments                    |
| `expressions-practice.txt`                      | Output-focused practice problems                 |
| `expressions_thought_process.md`                | Thought breakdown & manual calculation logic     |

⸻

## 🧠 Key Skills Practiced

- Debugging type mismatches and syntax errors  
- Using static vs dynamic values in C  
- Type casting, floating-point precision, and `#define` usage  
- Interpreting expression evaluation logic in a low-level language

⸻

## 🪞 Reflection  
This series of tasks taught me how small details in C — like integer division, implicit type promotion, or a misplaced semicolon — can dramatically affect program logic. Comparing static vs dynamic values sharpened my awareness of precision, and documenting my thought process helped clarify how I break down complex calculations before I write a single line of code.

