
# Lab 5

# Essential Git Commands - In-Class Labs

## Introduction
Your instructor will show Git installation, configuration, and first commit. Branching, editing, and merging will also be demostrated. 

## Exercise 1: Git Setup and First Repository
**Mode:** Individual  
**Objective:** Set up Git configuration and create your first local repository

### Step-by-Step Instructions:

1. **Verify Git Installation**
   ```bash
   git --version
   ```
   If Git isn't installed, follow the installation steps from the lecture.

2. **Configure Git Identity**
   ```bash
   git config --global user.name "Your Full Name"
   git config --global user.email "your.email@example.com"
   
   # Verify your configuration
   git config --list
   ```

3. **Create Your First Repository**
   ```bash
   # Create a new directory for your personal cookbook
   mkdir my-digital-cookbook
   cd my-digital-cookbook
   
   # Initialize Git repository
   git init
   
   # Verify .git folder was created (it's hidden)
   ls -la
   ```

4. **Create and Commit Your First Recipe**
   ```bash
   # Create your first recipe file
   echo "# My Digital Cookbook" > README.md
   echo "## Spaghetti Carbonara" > carbonara.md
   echo "**Prep Time:** 15 minutes" >> carbonara.md
   echo "**Ingredients:** pasta, eggs, bacon, parmesan cheese" >> carbonara.md
   
   # Check status
   git status
   
   # Add files to staging
   git add .
   
   # Commit with message
   git commit -m "Initial commit: Add README and carbonara recipe"
   
   # View your commit history
   git log --oneline
   ```
   
   **Expected Results:** 
   - Your `README.md` should contain: `# My Digital Cookbook`
   - Your `carbonara.md` should contain:
   ```
   ## Spaghetti Carbonara
   **Prep Time:** 15 minutes
   **Ingredients:** pasta, eggs, bacon, parmesan cheese
   ```
   
   Verify by running: `cat README.md` and `cat carbonara.md`

**Deliverable:** Take a screenshot of your terminal showing:
- Your git config output
- The result of `git log --oneline` showing your first commit
- Submit screenshot to instructor

---

## Exercise 2: Branching and Merging Workflow
**Mode:** Individual  
**Objective:** Practice creating branches, making changes, and merging

### Step-by-Step Instructions:

1. **Continue with Your Cookbook**
   ```bash
   # Make sure you're in your cookbook directory
   cd my-digital-cookbook
   
   # Check current branch
   git branch
   ```

2. **Create a Branch for Dessert Recipes**
   ```bash
   # Create and switch to new branch
   git checkout -b add-desserts
   
   # Verify you're on the new branch
   git branch
   
   # Create a dessert recipe
   echo "## Chocolate Chip Cookies" > cookies.md
   echo "**Prep Time:** 20 minutes" >> cookies.md
   echo "**Bake Time:** 12 minutes" >> cookies.md
   echo "**Ingredients:** flour, sugar, butter, chocolate chips, eggs" >> cookies.md
   ```
   
   **Expected Result:** Your `cookies.md` file should now contain:
   ```
   ## Chocolate Chip Cookies
   **Prep Time:** 20 minutes
   **Bake Time:** 12 minutes
   **Ingredients:** flour, sugar, butter, chocolate chips, eggs
   ```
   
   Verify by running: `cat cookies.md`

3. **Commit Changes on Branch** (3 minutes)
   ```bash
   # Add and commit the new recipe
   git add cookies.md
   git commit -m "Add chocolate chip cookies recipe"
   
   # Check your branch's history
   git log --oneline
   ```

4. **Create Another Branch for Appetizers**
   ```bash
   # Switch back to main
   git checkout main
   
   # Create appetizer branch
   git checkout -b add-appetizers
   
   # Create appetizer recipe
   echo "## Bruschetta" > bruschetta.md
   echo "**Prep Time:** 15 minutes" >> bruschetta.md
   echo "**Ingredients:** bread, tomatoes, garlic, basil, olive oil" >> bruschetta.md
   
   # Add and commit
   git add bruschetta.md
   git commit -m "Add bruschetta appetizer recipe"
   ```
   
   **Expected Result:** Your `bruschetta.md` file should contain:
   ```
   ## Bruschetta
   **Prep Time:** 15 minutes
   **Ingredients:** bread, tomatoes, garlic, basil, olive oil
   ```
   
   Verify by running: `cat bruschetta.md`

5. **Merge Both Branches**
   ```bash
   # Switch to main
   git checkout main
   
   # Merge desserts branch
   git merge add-desserts
   
   # Merge appetizers branch
   git merge add-appetizers
   
   # Check all files are present
   ls
   
   # View complete history
   git log --oneline --graph
   
   # Clean up branches
   git branch -d add-desserts
   git branch -d add-appetizers
   ```
   
   **Expected Results:**
   - `ls` should show: `README.md`, `carbonara.md`, `cookies.md`, `bruschetta.md`
   - All your recipe files should now be in the main branch
   - `git log --oneline --graph` should show your merge history with multiple commits

**Deliverable:** Take a screenshot showing:
- Output of `git log --oneline --graph` showing your merge history
- Output of `ls` command showing all recipe files
- Show to instructor or upload to course management system

---

## Exercise 3: GitHub Integration - Push and Pull
**Mode:** Individual  
**Objective:** Connect local repository to GitHub and practice push/pull workflow

### Step-by-Step Instructions:

1. **Create GitHub Repository**
   - Go to GitHub.com and sign in
   - Click "New repository" (green button)
   - Repository name: `my-digital-cookbook`
   - Keep it public
   - **DO NOT** initialize with README (we already have one)
   - Click "Create repository"

2. **Connect Local Repository to GitHub**
   ```bash
   # Make sure you're in your cookbook directory
   cd my-digital-cookbook
   
   # Add GitHub as remote origin (replace YOUR-USERNAME)
   git remote add origin https://github.com/YOUR-USERNAME/my-digital-cookbook.git
   
   # Verify remote connection
   git remote -v
   
   # Push to GitHub for first time
   git push -u origin main
   ```

3. **Make Changes on GitHub**
   - Go to your repository on GitHub
   - Click on `README.md`
   - Click the pencil icon (Edit)
   - Add this line at the bottom: `## Welcome to my cooking journey!`
   - Scroll down, add commit message: "Update README with welcome message"
   - Click "Commit changes"

4. **Pull Changes to Local**
   ```bash
   # Pull the changes from GitHub
   git pull origin main
   
   # Verify the changes are in your local file
   cat README.md
   
   # Check the new commit in your log
   git log --oneline -3
   ```
   
   **Expected Results:**
   - Your local `README.md` should now include the line: `## Welcome to my cooking journey!`
   - `git log --oneline -3` should show the commit you made on GitHub

5. **Complete the Push-Pull Cycle**
   ```bash
   # Make a local change
   echo "**Created by:** [Your Name]" >> README.md
   
   # Add, commit, and push
   git add README.md
   git commit -m "Add author name to README"
   git push
   ```
   
   **Expected Result:** Your final `README.md` should contain:
   ```
   # My Digital Cookbook
   ## Welcome to my cooking journey!
   **Created by:** [Your Name]
   ```
   
   Verify by running: `cat README.md`

**Deliverable:** 
- Share your GitHub repository URL with the instructor
- Take a screenshot of your repository on GitHub showing the commits
- Demonstrate the push-pull cycle by showing both GitHub and local terminal

---

## Exercise 4: Team Collaboration Simulation
**Mode:** Teams of 2  
**Objective:** Practice collaborative Git workflow with conflict resolution

### Step-by-Step Instructions:

1. **Team Setup**
   - **Partner A:** Share your GitHub cookbook repository URL with Partner B
   - **Partner B:** Clone Partner A's repository
   ```bash
   git clone https://github.com/PARTNER-A-USERNAME/my-digital-cookbook.git
   cd my-digital-cookbook
   ```

2. **Partner A - Add a New Recipe**
   ```bash
   # Create a branch for new recipe
   git checkout -b add-pizza-recipe
   
   # Add pizza recipe
   echo "## Margherita Pizza" > pizza.md
   echo "**Prep Time:** 30 minutes" >> pizza.md
   echo "**Cook Time:** 15 minutes" >> pizza.md
   echo "**Ingredients:** pizza dough, tomato sauce, mozzarella, basil" >> pizza.md
   
   # Commit and push
   git add pizza.md
   git commit -m "Add margherita pizza recipe"
   git push origin add-pizza-recipe
   ```
   
   **Expected Result:** Your `pizza.md` file should contain:
   ```
   ## Margherita Pizza
   **Prep Time:** 30 minutes
   **Cook Time:** 15 minutes
   **Ingredients:** pizza dough, tomato sauce, mozzarella, basil
   ```
   
   Verify by running: `cat pizza.md`

3. **Partner B - Add Different Recipe (Simultaneously)**
   ```bash
   # Create a branch for salad recipe
   git checkout -b add-salad-recipe
   
   # Add salad recipe
   echo "## Caesar Salad" > salad.md
   echo "**Prep Time:** 10 minutes" >> salad.md
   echo "**Ingredients:** romaine lettuce, croutons, parmesan, caesar dressing" >> salad.md
   
   # Commit and push
   git add salad.md
   git commit -m "Add caesar salad recipe"
   git push origin add-salad-recipe
   ```
   
   **Expected Result:** Your `salad.md` file should contain:
   ```
   ## Caesar Salad
   **Prep Time:** 10 minutes
   **Ingredients:** romaine lettuce, croutons, parmesan, caesar dressing
   ```
   
   Verify by running: `cat salad.md`

4. **Partner A - Merge First Recipe**
   ```bash
   # Switch to main and merge
   git checkout main
   git merge add-pizza-recipe
   git push origin main
   
   # Clean up branch
   git branch -d add-pizza-recipe
   ```

5. **Partner B - Handle Integration**
   ```bash
   # Pull latest changes from main
   git checkout main
   git pull origin main
   
   # Merge your salad branch
   git merge add-salad-recipe
   git push origin main
   
   # Clean up
   git branch -d add-salad-recipe
   ```

6. **Both Partners - Final Sync**
   ```bash
   # Both partners pull final state
   git pull origin main
   
   # Verify both recipes are present
   ls
   git log --oneline -5
   ```
   
   **Expected Results:**
   - `ls` should show all recipe files including: `pizza.md` and `salad.md`
   - `git log --oneline -5` should show commits from both partners
   - Both partners should have identical repositories

**Deliverable:** 
- **Team Submission:** Both partners show instructor the final repository with both recipes
- Take a screenshot of `git log --oneline` showing contributions from both team members
- **Bonus Challenge:** Add each other as collaborators on GitHub and demonstrate direct collaboration without cloning

---

## Quick Reference Card for Labs

### Essential Commands Used:
```bash
# Setup
git config --global user.name "Name"
git config --global user.email "email"
git init

# Daily workflow
git status
git add .
git commit -m "message"

# Branching
git branch branch-name
git checkout branch-name
git checkout -b branch-name
git merge branch-name
git branch -d branch-name

# GitHub integration
git remote add origin URL
git push -u origin main
git push
git pull
git clone URL
```
---

## Lab Rubric

**Total Points: 2 marks**

For this lab to be considered complete, students must successfully demonstrate Git fundamentals through hands-on practice. All four lab components (Lab 1-4) must show evidence of completion through required deliverables.

## Detailed Expectations:

### Exercise 1 Requirements:
- Screenshot must show working git config --global settings with student's actual name and email
- Terminal output showing git log --oneline with at least one commit containing "Initial commit: Add README and carbonara recipe"
- Evidence of successful repository initialization and first commit

### Exercise 2 Requirements:
- Screenshot showing git log --oneline --graph displaying merge history from at least 2 branches
- Terminal output of ls command showing all 4 expected files: README.md, carbonara.md, cookies.md, bruschetta.md
- Evidence of proper branching workflow with branch creation, commits, and merges

### Exercise 3 Requirements:
- Working GitHub repository URL that instructor can access
- Repository must contain all recipe files from previous labs
- Screenshot of GitHub repository showing commit history with both local and GitHub commits
- Evidence of successful push-pull workflow between local and remote repositories

### Exercise 4 Requirements:
- Team demonstration showing final repository contains contributions from both partners
- Terminal output of git log --oneline showing commits from both team members
- Both partners must have synchronized repositories with identical content (pizza.md and salad.md present)
- Evidence of successful collaborative workflow with branch management

## Lab Rubric:

| Criteria | Poor - 0 marks | Fair - 1 mark | Good - 2 marks |
|---|---|---|---|
| Lab Completion | Failed to complete more than 2 labs or missing critical deliverables (screenshots, GitHub repository, team collaboration evidence) | Successfully completed 3 out of 4 labs with most deliverables present, but missing some evidence of proper Git workflow (e.g., incomplete commit history, missing branches, or limited collaboration demonstration) | Successfully completed all 4 labs with all required deliverables demonstrating proper Git workflow including: local repository setup, branching/merging, GitHub integration, and successful team collaboration |
