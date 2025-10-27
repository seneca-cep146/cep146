
### Lab 7

#### **Exercise 1: Merge Conflict Resolution**

## Introduction
Your instructor will show how merge conflicts happen and how to resolve them.


**Scenario:** Recipe Collection Project

**Setup (Instructor Provides):**
- Repository with base recipe file
- Two branches with conflicting recipe modifications
- Students work in pairs

**Student Task:**
1. **Clone repository** from GitHub
2. **Create conflicting changes** on different branches
3. **Attempt to merge** using GitHub website
4. **Resolve conflicts** when they arise
5. **Complete the merge** successfully

**Example Conflict:**
```
Original Recipe: "Bake for 20 minutes"

Branch A: "Bake for 25 minutes at 350°F"
Branch B: "Bake for 20 minutes at 375°F"

Your Resolution: "Bake for 25 minutes at 375°F"
```

### **Exercise 2: Git Bisect Bug Hunt**

**Scenario:** Study Guide with Errors

**Setup (Instructor Provides):**
- Repository with 10 commits
- "Bug" introduced in commit 7 (wrong formula)
- Students use bisect to find the error

**Student Task:**
```bash
# Start bisect
git bisect start
git bisect bad                    # Current version has error
git bisect good HEAD~10          # 10 commits ago was fine

# Follow bisect process to find commit with wrong formula
# Report findings to class
```

### **Exercise 3**

**Practice Exercise:**
1. **Create a group project** repository
2. **Have team members** make conflicting changes
3. **Practice resolving conflicts** using both methods
4. **Document your experience** - what worked, what was challenging?

Remember: The best way to learn Git is by using it! Don't be afraid to experiment and make mistakes - that's how you learn.

---
# Lab Rubric

**Total Points: 2 marks**

For this lab to be considered complete, students must successfully demonstrate advanced Git concepts including merge conflict resolution, debugging with git bisect, and collaborative problem-solving through three exercises.

## Detailed Expectations:

### Exercise 1 Requirements (Merge Conflict Resolution):
- Successfully cloned instructor-provided repository with conflicting branches
- Created and demonstrated conflicting changes on different branches
- Attempted merge using GitHub website and encountered expected conflicts
- Successfully resolved merge conflicts by manually editing conflicted files
- Completed merge with appropriate commit message documenting resolution
- Demonstrated understanding of conflict markers (<<<<<<, ======, >>>>>>)

### Exercise 2 Requirements (Git Bisect Bug Hunt):
- Successfully initiated git bisect process with correct start, bad, and good commits
- Followed bisect workflow to systematically narrow down bug location
- Correctly identified commit #7 as containing the wrong formula error
- Demonstrated understanding of binary search approach to debugging
- Reported findings with specific commit hash and description of discovered error

### Exercise 3 Requirements (Group Practice):
- Created or participated in group project repository setup
- Demonstrated team collaboration with intentional conflicting changes
- Practiced resolving conflicts using both command line and GitHub web interface
- Documented experience with reflection on challenges and successful strategies
- Showed evidence of multiple conflict resolution attempts and learning from mistakes

## Assessment Rubric:

| Criteria | Poor - 0 marks | Fair - 1 mark | Good - 2 marks |
|---|---|---|---|
| Lab Completion | Completed only 1 exercise or failed to demonstrate core advanced concepts (unable to resolve conflicts, incomplete bisect process, or no evidence of collaborative problem-solving) | Successfully completed 2 out of 3 exercises with most deliverables present, but missing some evidence of advanced Git workflow mastery (e.g., conflicts resolved but poor documentation, incomplete bisect findings, or superficial group collaboration reflection) | Successfully completed all 3 exercises demonstrating: successful merge conflict resolution with proper documentation, effective use of git bisect for debugging, collaborative conflict resolution practice with thoughtful reflection on challenges and solutions |

