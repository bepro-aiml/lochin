# 🧠 Python Basics for AI/ML (Google Colab)

This project is a simple introduction to Python programming for AI/ML beginners.  
It demonstrates core concepts such as variables, data types, functions, loops, and basic logic.

🔗 **Open in Google Colab:**  
https://colab.research.google.com/drive/16UXVuYNlxijY4jPW4HRC9UQ_pNMQkPXz?usp=sharing

---

## 📌 Topics Covered

- Variables and Data Types
- Printing and Type Checking
- Functions
- Lists
- Loops (`enumerate`)
- Random Module
- Conditional Statements

---

## 🧾 Code Overview

### 1. Variables and Data Types

```python
age = 22         # integer
gpa = 3.85       # float
name = "Aziz"    # string
is_student = True # boolean
scores = [85, 92, 78, 95, 88] # list
2. Print Variable Types
print(age, type(age))
print(gpa, type(gpa))
print(name, type(name))
print(is_student, type(is_student))
print(scores, type(scores))
3. Function: Calculate Average
def calculate_average(numbers):
  total = sum(numbers)
  count = len(numbers)
  return total / count
4. Test the Function
test1 = [80, 90, 70, 85, 95]
test2 = [55, 62, 48, 71]

print("Average 1:", calculate_average(test1))
print("Average 2:", calculate_average(test2))
5. Loop with enumerate()
cities = ["Tashkent", "Samarkand", "Bukhara", "Namangan", "Fergana"]

for index, city in enumerate(cities):
  print(f"Index {index}: {city}")
6. Combine Everything (Mini Project)
import random

exam_scores = [random.randint(0, 100) for _ in range(10)]
print("Scores:", exam_scores)

avg = calculate_average(exam_scores)
print(f"Class average: {avg:.1f}")

if avg >= 60:
  print("Result: PASS")
else:
  print("Result: FAIL")
🚀 How to Use
Open the Colab link above
Run each cell step by step
Modify values and experiment
Try adding new features (e.g., grading system)
🎯 Learning Goal

By the end of this notebook, you will understand:

Basic Python syntax
How to write reusable functions
How to work with lists and loops
Simple logic used in AI/ML preprocessing
📚 Next Steps
Learn NumPy and Pandas
Start working with datasets
Try simple Machine Learning models
👨‍💻 Author

Davron Aliqulov
AI & Python Learner 🚀