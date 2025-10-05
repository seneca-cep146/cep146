
### Lab 6

### Exercise 1: Essay Project with GitHub (20 minutes)

## Introduction
Your instructor will 
- Show how Git tracks changes over time in a writing project.
- Show how students can contribute to a shared resource.
  

**Goal:** Practice seeing changes and history using both methods.

**Setup:**
1. **Create new repository** on GitHub called "my-essay"
2. **Clone it** to your computer: `git clone [your-repo-link]`

**Steps:**
```bash
# Create essay with multiple commits
echo "Essay Title: The Impact of Social Media" > essay.txt
git add essay.txt
git commit -m "Add essay title"
git push origin main

echo "Introduction: Social media has changed how we communicate..." >> essay.txt
git add essay.txt
git commit -m "Add introduction paragraph"
git push origin main

echo "Body: Studies show that social media usage..." >> essay.txt
git add essay.txt
git commit -m "Add body paragraph with research"
git push origin main
```

**Practice Both Methods:**

**Command Line:**
```bash
git log --oneline
git diff HEAD~2 HEAD
```

**Remember:**
- **HEAD~2** = "2 saves ago"
- **HEAD** = "Current save"
- This shows what changed between 2 saves ago and now

**GitHub Website:**
1. Go to your repository on GitHub
2. Click "3 commits"
3. Click on each commit to see changes
4. Notice how GitHub shows your essay growing over time!

**Questions:**
- Which method helps you understand your changes better?
- Can you see how your essay developed over time?

### Exercise 2: Collaboration Practice (25 minutes)

**Goal:** Practice forking and contributing.

**Setup:**
Instructor creates a "class-resources" repository with a simple file:

```
# Class Resources

## Study Tips
- Take notes during lectures
- Review material weekly

## Useful Links
- [Course website]
- [Library resources]
```

**Student Tasks:**

1. **Fork the repository** (click Fork button)
2. **Add your own study tip:**
   - Click pencil icon to edit
   - Add something like "Form study groups with classmates"
   - Commit with message "Add study group tip"
3. **Create pull request:**
   - Click "Pull Request"
   - Explain your addition
   - Submit for review

**Learning Points:**
- How easy it is to contribute using GitHub website
- How changes are tracked and reviewed
- How everyone can benefit from shared knowledge

### Exercise 3: Fix a Mistake Practice (15 minutes)

**Scenario:** You committed wrong information and need to fix it.

**Setup:**
```bash
echo "The capital of Canada is Toronto" > facts.txt
git add facts.txt
git commit -m "Add Canada fact"
git push origin main
```

**Fix Using GitHub Website:**
1. **Go to your repository** on GitHub
2. **Click on facts.txt**
3. **Click pencil icon** to edit
4. **Change** "Toronto" **to** "Ottawa"
5. **Commit** with message "Correct Canada's capital city"

**Observe:**
- Your mistake is still in history (click "2 commits" to see)
- Current version is correct
- Clear record of what was wrong and how you fixed it

---
## Lab Rubric

**Total Points: 2 marks**

For this lab to be considered complete, students must successfully demonstrate Git history tracking, collaboration workflows, and mistake correction through three progressive exercises.

## Detailed Expectations:

### Exercise 1 Requirements (Essay Project):
- GitHub repository "my-essay" created and properly cloned
- Essay.txt file with at least 3 commits showing progressive development (title, introduction, body)
- Evidence of using both command line (`git log --oneline`, `git diff HEAD~2 HEAD`) and GitHub website to view history
- Answers to reflection questions about which method helps understand changes better

### Exercise 2 Requirements (Collaboration Practice):
- Successfully forked the instructor's "class-resources" repository
- Added meaningful study tip through GitHub web interface
- Created pull request with clear explanation of addition
- Demonstrated understanding of collaborative workflow and contribution process

### Exercise 3 Requirements (Fix Mistake Practice):
- Created facts.txt with intentional error (Toronto as Canada's capital)
- Successfully corrected mistake using GitHub web interface (changed to Ottawa)
- Demonstrated understanding that mistake remains in history while current version is correct
- Evidence of proper commit message for correction

## Assessment Rubric:

| Criteria | Poor - 0 marks | Fair - 1 mark | Good - 2 marks |
|---|---|---|---|
| Lab Completion | Completed only 1 exercise or failed to demonstrate core concepts (missing repository creation, no evidence of history tracking, or unsuccessful collaboration/correction workflows) | Successfully completed 2 out of 3 exercises with most deliverables present, but missing some evidence of proper Git workflow understanding (e.g., incomplete commit history, missing pull request, or superficial reflection responses) | Successfully completed all 3 exercises demonstrating: progressive commit history, successful collaboration through forking/pull requests, mistake correction workflow, and thoughtful reflection on Git tools and methods |
