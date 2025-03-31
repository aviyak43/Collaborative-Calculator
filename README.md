# Collaborative-Calculator 🧮
Git Workshop Game

## **Objective**
Your team will collaboratively build a Python-based calculator using Git. Each team member will implement a different mathematical operation, using branches to manage changes. The goal is to **successfully merge all features into a working calculator while resolving any merge conflicts that arise.**

---

## **Game Rules & Steps**

### **1. Set Up the Project**
1. One team member forks this GitHub repository (click “Fork”, top right corner) and shares it with the team.
2. Clone the repository:
   ```bash
   git clone <your-forked-repo-url>
   cd <repo-folder>
   ```
3. Create a base `calculator.py` file with the following starter code:
   ```python
   def calculate(operation, a, b):
       pass  # To be implemented by the team
   
   if __name__ == "__main__":
       op = input("Enter operation (+, -, *, /): ")
       a = float(input("Enter first number: "))
       b = float(input("Enter second number: "))
       result = calculate(op, a, b)
       print(f"Result: {result}")
   ```
4. Commit and push the initial setup:
   ```bash
   git add calculator.py
   git commit -m "Initial project setup"
   git push origin main
   ```

---

### **2. Assign Branches & Tasks**
Each team member creates a new branch and implements one operation:
- **Student 1:** Addition (`feature-addition`)
- **Student 2:** Subtraction (`feature-subtraction`)
- **Student 3:** Multiplication (`feature-multiplication`)
- **Student 4:** Division (`feature-division`)

Example:
```bash
git checkout -b feature-addition
```

Modify `calculate()` to handle your assigned operation:
```python
def calculate(operation, a, b):
    if operation == "+":
        return a + b
```
Commit and push your changes:
```bash
git add calculator.py
git commit -m "Added addition functionality"
git push origin feature-addition
```

---

### **3. Merge & Resolve Conflicts**
1. Switch to `main` and pull the latest changes:
   ```bash
   git checkout main
   git pull origin main
   ```
2. Merge each branch into `main` (one at a time):
   ```bash
   git merge feature-addition
   ```
3. If a merge conflict occurs, follow the **Conflict Resolution Guide**.
4. Once all operations are merged and conflicts resolved, commit the final version.

---

### **4. Expanding the Calculator (Optional Challenges)**
If your team finishes early, expand your calculator with:
- **Exponentiation (`a^b`)**
- **Modulo (`a % b`)**
- **Square root (`√a`)**
- **Memory functions (store & recall results)**
- **Error handling (e.g., prevent division by zero)**
- **Unit tests using `pytest`**
- **A simple CLI menu or GUI**

---

### **5. Final Submission Requirements**
By the end of the session, your team should submit a **link to your GitHub repository** containing:\
✅ **Final `calculator.py` file** with all implemented operations.\
✅ **A brief `README.md`** explaining how the calculator works.\
✅ **A Git log (`git log --oneline`)** showing your commit history.\
✅ **Proof of successful merges** (no unresolved conflicts).

Push the final version to GitHub and share the repository link with the workshop instructor.

---

### **6. Winning Criteria**
Teams will be judged based on:\
🏆 **Completeness** (all operations work correctly).\
🏆 **Code quality** (clean, structured, and readable code).\
🏆 **Conflict resolution** (efficient and well-handled merges).\
🏆 **Extra features** (bonus points for creativity!).\
🏆 **Git usage** (proper branching, commits, and merges).

Good luck, and may the best team win! 🚀


