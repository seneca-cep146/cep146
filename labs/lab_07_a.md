# Lab 7 - Git Exercises

---

## **Exercise 1: Personal Portfolio Conflict Simulation**

### Scenario
You're maintaining a personal portfolio website and accidentally create merge conflicts between your laptop and desktop work.

### Learning Objectives
- Understand how merge conflicts occur
- Practice creating and resolving conflicts
- Learn branch management basics

---

### Part A: Setup

Create a new repository and initial portfolio file:

```bash
# Create a new repository
mkdir my-portfolio
cd my-portfolio
git init

# Create initial portfolio file
cat > portfolio.md << 'EOF'
# My Portfolio

## About Me
Name: [Your Name]
Major: Computer Science

## Skills
- Programming: Basic
- Git: Learning

## Projects
- Project 1: TBD
- Project 2: TBD

## Contact
Email: student@university.edu
EOF

git add portfolio.md
git commit -m "Initial portfolio"
```

---

### Part B: Create a Branch (Simulating "Desktop Work")

```bash
# Create and switch to desktop branch
git checkout -b desktop-updates

# Edit portfolio.md - update Skills section
# Change the Skills section to:
```

Open `portfolio.md` in your text editor and replace the Skills section with:

```markdown
## Skills
- Programming: Python, Java
- Git: Intermediate
- Web Development: HTML, CSS
```

Save the file, then commit:

```bash
git add portfolio.md
git commit -m "Update skills from desktop"
```

---

### Part C: Simulate "Laptop Work" (Create Conflict)

```bash
# Go back to main branch
git checkout main

# Edit portfolio.md - update Skills section DIFFERENTLY
```

Open `portfolio.md` again and replace the Skills section with **different** content:

```markdown
## Skills
- Programming: C++, JavaScript
- Git: Advanced
- Database: SQL
```

Save and commit:

```bash
git add portfolio.md
git commit -m "Update skills from laptop"
```

---

### Part D: Create and Resolve the Conflict

```bash
# Try to merge desktop work
git merge desktop-updates
```

**You'll get a conflict!** Git will display:

```
Auto-merging portfolio.md
CONFLICT (content): Merge conflict in portfolio.md
Automatic merge failed; fix conflicts and then commit the result.
```

Open `portfolio.md` and you'll see conflict markers:

```markdown
## Skills
<<<<<<< HEAD
- Programming: C++, JavaScript
- Git: Advanced
- Database: SQL
=======
- Programming: Python, Java
- Git: Intermediate
- Web Development: HTML, CSS
>>>>>>> desktop-updates
```

**Your Task:** Resolve by combining BOTH sets of skills. Edit the file to look like:

```markdown
## Skills
- Programming: Python, Java, C++, JavaScript
- Git: Advanced
- Web Development: HTML, CSS
- Database: SQL
```

Remove all conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`), then:

```bash
git add portfolio.md
git commit -m "Resolve skills conflict - combine all skills"
```

---

### Verification

Check your work:

```bash
# View the merge in the log
git log --oneline --graph --all

# Should show something like:
#   *   abc1234 (HEAD -> main) Resolve skills conflict - combine all skills
#   |\
#   | * def5678 (desktop-updates) Update skills from desktop
#   * | ghi9012 Update skills from laptop
#   |/
#   * jkl3456 Initial portfolio
```

---

### Reflection Questions

Answer these questions in a document:

1. **Why did the conflict occur?**
   - What lines in the file were changed in both branches?

2. **What would have prevented this conflict?**
   - Think about timing and coordination

3. **In real life, how do you avoid conflicts when working on multiple devices?**
   - Consider git commands like `pull`, `push`, frequency of commits

4. **What was the most challenging part of resolving the conflict?**

5. **How did Git help you identify where the conflict was?**

---

## **Exercise 2: Recipe Bug Hunt with Git Bisect**

### Scenario
Your recipe collection has an error! Someone changed the baking temperature, and now cookies are burning. Use `git bisect` to find which commit introduced the wrong temperature.

### Learning Objectives
- Understand how git bisect works
- Learn binary search concepts
- Practice debugging with Git history

---

### Setup: Create Recipe History

**Copy and paste this entire block into your terminal:**

```bash
mkdir recipe-bug-hunt
cd recipe-bug-hunt
git init

# Commit 1 - Original recipe
cat > cookies.txt << 'EOF'
CHOCOLATE CHIP COOKIES
Ingredients: flour, butter, sugar, eggs, chocolate chips
Temperature: 350°F
Time: 12 minutes
EOF
git add cookies.txt
git commit -m "Commit 1: Add original recipe"

# Commit 2 - Add ingredient details
cat > cookies.txt << 'EOF'
CHOCOLATE CHIP COOKIES
Ingredients: 2 cups flour, 1 cup butter, 1 cup sugar, 2 eggs, 2 cups chocolate chips
Temperature: 350°F
Time: 12 minutes
EOF
git commit -am "Commit 2: Add ingredient amounts"

# Commit 3 - Add instructions
cat > cookies.txt << 'EOF'
CHOCOLATE CHIP COOKIES
Ingredients: 2 cups flour, 1 cup butter, 1 cup sugar, 2 eggs, 2 cups chocolate chips
Instructions: Mix butter and sugar, add eggs, mix in flour, fold in chocolate chips
Temperature: 350°F
Time: 12 minutes
EOF
git commit -am "Commit 3: Add mixing instructions"

# Commit 4 - Still good
cat > cookies.txt << 'EOF'
CHOCOLATE CHIP COOKIES
Ingredients: 2 cups flour, 1 cup butter, 1 cup sugar, 2 eggs, 2 cups chocolate chips
Instructions: Mix butter and sugar, add eggs, mix in flour, fold in chocolate chips
Temperature: 350°F
Time: 12 minutes
Yield: 24 cookies
EOF
git commit -am "Commit 4: Add yield information"

# Commit 5 - BUG INTRODUCED! Temperature changed to 450°F
cat > cookies.txt << 'EOF'
CHOCOLATE CHIP COOKIES
Ingredients: 2 cups flour, 1 cup butter, 1 cup sugar, 2 eggs, 2 cups chocolate chips
Instructions: Mix butter and sugar, add eggs, mix in flour, fold in chocolate chips
Temperature: 450°F
Time: 12 minutes
Yield: 24 cookies
EOF
git commit -am "Commit 5: Update recipe format"

# Commit 6 - Bug still there
cat > cookies.txt << 'EOF'
CHOCOLATE CHIP COOKIES
Ingredients: 2 cups flour, 1 cup butter, 1 cup sugar, 2 eggs, 2 cups chocolate chips
Instructions: Mix butter and sugar, add eggs, mix in flour, fold in chocolate chips
Temperature: 450°F
Time: 12 minutes
Yield: 24 cookies
Tips: Use parchment paper
EOF
git commit -am "Commit 6: Add baking tips"

# Commit 7 - Bug still there
cat > cookies.txt << 'EOF'
CHOCOLATE CHIP COOKIES
Ingredients: 2 cups flour, 1 cup butter, 1 cup sugar, 2 eggs, 2 cups chocolate chips
Instructions: Mix butter and sugar, add eggs, mix in flour, fold in chocolate chips
Temperature: 450°F
Time: 12 minutes
Yield: 24 cookies
Tips: Use parchment paper
Storage: Keep in airtight container
EOF
git commit -am "Commit 7: Add storage instructions"

echo "✅ Setup complete! You have 7 commits with a bug in commit 5"
```

---

### Your Mission: Use Git Bisect to Find the Bug

#### Step 1: Check the current recipe and spot the problem

```bash
cat cookies.txt
```

Look at the Temperature line - it says **450°F**. That's way too hot! It should be **350°F**.

---

#### Step 2: Start Git Bisect

```bash
git bisect start
```

---

#### Step 3: Tell Git the current version is BAD (has the bug)

```bash
git bisect bad
```

This marks the current commit (HEAD) as having the bug.

---

#### Step 4: Tell Git that 7 commits ago was GOOD (no bug)

```bash
git bisect good HEAD~7
```

This marks the first commit as working correctly.

Git will now say something like:
```
Bisecting: 3 revisions left to test after this
[commit hash] Commit 4: Add yield information
```

---

#### Step 5: Check if the current commit is good or bad

```bash
cat cookies.txt
```

Look at the Temperature line:

- **Is it 350°F (correct)?** → Type `git bisect good`
- **Is it 450°F (wrong)?** → Type `git bisect bad`

---

#### Step 6: Repeat

Git will check out another commit. Check the temperature again:

```bash
cat cookies.txt
```

Then mark it as good or bad. Keep repeating!

---

#### Step 7: Git Finds the Bug!

After a few checks, Git will tell you:

```
abc1234 is the first bad commit
commit abc1234
Author: Your Name
Date: ...

    Commit 5: Update recipe format
```

**Success!** You found the bug in Commit 5.

---

#### Step 8: Return to normal

```bash
git bisect reset
```

This takes you back to the latest commit.

---

#### Step 9: Fix the bug

Open `cookies.txt` in your text editor and change `Temperature: 450°F` back to `Temperature: 350°F`.

Then commit the fix:

```bash
git add cookies.txt
git commit -m "Fix: Correct temperature back to 350°F"
```

---

### Understanding Git Bisect

Git bisect uses **binary search** to find bugs efficiently:

```
Commits:  1 ---- 2 ---- 3 ---- 4 ---- 5 ---- 6 ---- 7
          ✅                        ❌
          GOOD                      BAD

Step 1: Check middle (commit 4) → Good ✅
Step 2: Check between 4 and 7 (commit 6) → Bad ❌
Step 3: Check between 4 and 6 (commit 5) → Bad ❌ = FOUND IT!
```

Instead of checking all 7 commits (7 checks), bisect only needed **3 checks**!

---

### Reflection Questions

Answer these questions in a document:

1. **How many times did you have to check the temperature before Git found the bug?**
   - Count how many times you typed `git bisect good` or `git bisect bad`

2. **If you had 100 commits instead of 7, about how many checks would bisect need?**
   - Hint: Binary search needs log₂(n) checks
   - For 100 commits: about 7 checks!
   - For 1000 commits: about 10 checks!

3. **How is bisect different from manually checking each commit with `git checkout`?**
   - Think about efficiency and time saved

4. **When would git bisect be most useful in real projects?**
   - Consider scenarios with many commits

5. **What information do you need to start a bisect session?**
   - What do you need to know about "good" and "bad" states?

---

### Challenge: Try It Again with More Commits!

Add 3 more commits and introduce a bug in one of them:

```bash
echo "Notes: Best served warm" >> cookies.txt
git commit -am "Commit 8: Add serving notes"

# Add your own commits 9 and 10
# Then introduce a different bug (change Time to 60 minutes)
# Use bisect to find it!
```

---

## **Lab Completion Checklist**

Submit the following:

### Exercise 1: Portfolio Conflicts
- [ ] Screenshot of `git log --oneline --graph --all` showing the merge
- [ ] Screenshot or copy of your final `portfolio.md` with combined skills
- [ ] Answers to all 5 reflection questions

### Exercise 2: Recipe Bug Hunt
- [ ] Screenshot of the git bisect output showing which commit had the bug
- [ ] Screenshot of `git log --oneline` after fixing the bug
- [ ] Answers to all 5 reflection questions
- [ ] (Optional) Challenge: Screenshot of finding a second bug

---

## **Tips for Success**

1. **Read error messages carefully** - Git tells you exactly what's wrong
2. **Take your time** - Conflicts can be confusing at first
3. **Don't panic** - You can always use `git status` to see what's happening
4. **Ask for help** - If you're stuck, ask a classmate or instructor
5. **Experiment** - You can't break anything permanently in a local repository

---

## **Common Issues & Solutions**

### Issue: "I'm in a detached HEAD state"
**Solution:** This is normal during bisect! Just continue the bisect process or use `git bisect reset` to return.

### Issue: "I deleted my conflict markers but still can't commit"
**Solution:** After removing conflict markers, you must `git add` the file before committing.

### Issue: "I lost track of where I am in the bisect"
**Solution:** Use `git bisect log` to see your bisect history, or `git bisect reset` to start over.

### Issue: "My merge shows no conflicts but the file is wrong"
**Solution:** Git only shows conflicts when the SAME lines are changed. Different sections merge automatically.

---
