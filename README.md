# Collaborative-Calculator 🧮
Git Workshop Game

## **Objective**
Your team will collaboratively build a Python-based calculator using Git. Each team member will implement a different mathematical operation, using branches to manage changes. The goal is to **successfully merge all features into a working calculator while resolving any merge conflicts that arise.**

---

## **Game Rules & Steps**

### **1. Set Up the Project**
1. One team member clones the provided template repository:
   ```bash
   git clone <provided-repo-url>
   cd <repo-folder>
   ```
2. Create a **new GitHub repository** for your team (you can name it: Collaborative-Calculator-GroupX).
3. Set the new repository as the remote origin:
   ```bash
   git remote remove origin
   git remote add origin <your-new-repo-url>
   git push -u origin main
   ```
4. Verify that local project was pushed to your own GitHub repository (open your repository page and check if the files from the cloned template have been pushed successfully)
5. Create a base `calculator.py` file with the following starter code:
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
6. Commit and push the initial setup:
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

---

# **Git Conflict Resolution Guide: Collaborative Calculator**😵‍💫🧘🏽‍♀

### **1. Understanding Merge Conflicts**
A merge conflict happens when Git cannot automatically combine changes from different branches. In this workshop, conflicts will likely occur because multiple people modify the `calculate()` function.

---

### **2. Identifying a Merge Conflict**
If a conflict occurs during a merge, Git will display an error message like:
```
CONFLICT (content): Merge conflict in calculator.py
Automatic merge failed; fix conflicts and then commit the result.
```
Now, when you open `calculator.py`, you'll see conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).

Example conflict:
```python
 def calculate(operation, a, b):
<<<<<<< feature-addition
     if operation == "+":
         return a + b
=======
     if operation == "-":
         return a - b
>>>>>>> feature-subtraction
```

---

### **3. Resolving the Conflict**
1. **Open `calculator.py` in a text editor**.
2. **Find the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)**.
3. **Manually edit the file to combine all changes** into one function:
   ```python
   def calculate(operation, a, b):
       if operation == "+":
           return a + b
       elif operation == "-":
           return a - b
       elif operation == "*":
           return a * b
       elif operation == "/":
           return a / b if b != 0 else "Error: Division by zero"
       else:
           return "Invalid operation"
   ```
4. **Remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)**.
5. **Save the file**.

---

### **4. Committing the Resolved Merge**
Once the conflict is resolved, run:
```bash
git add calculator.py
git commit -m "Resolved merge conflict in calculator.py"
git push origin main
```

---

### **5. Preventing Future Conflicts**
- **Pull the latest changes before starting:**
  ```bash
  git pull origin main
  ```
- **Communicate** with your team about which parts of the code you are working on.
- **Use smaller functions** instead of modifying the same function simultaneously.

---

### **6. (Optional) Challenge for Teams**
For an extra challenge, try to resolve a **simulated conflict**:
1. Clone the repository into two separate folders.
2. Edit `calculator.py` differently in each folder.
3. Commit and push from one folder.
4. Try to push from the other folder (it will fail).
5. Resolve the conflict manually and commit the changes.

---

By following these steps, your team will successfully merge code while learning how to handle real-world Git collaboration! 🚀


