
# Lab 3

# Version Control Concepts 
*Experiencing Collaboration Problems and Designing Solutions*

## Introduction

Your professor will demonstrate how to create a private repository and add your teammates.  Make sure to add your prof also!


## Collaboration Chaos & System Design Challenge (Team of 2)

### Part A: Collaboration Chaos Simulation (15 minutes)

1. **Setup the Chaos** (5 minute)
   - Both students create/open the same text file: `group_poem.txt`
   - Starting content:
     ```
     Roses are red,
     Violets are blue,
     Programming is fun,
     And teamwork is too.
     ```

2. **Silent Collaboration** (5 minutes)
   - **Important: No talking allowed during this phase!**
   - Each student makes 3 changes to different parts of the poem:
     - Change some wording
     - Add a new line
     - Modify punctuation or structure
   - Save your version with your name (e.g., `group_poem_alex.txt`)
  

3. **Manual Merge Attempt**
   - Now try to combine both modified versions into one final `group_poem_final.txt`
   - Work together to create the "best" version

     Final: Roses are pink,
            Violets are blue,
            Programming is awesome,
            And technology too!!!
            We are learning Git today,

### Part B: System Design Challenge

4. **Problem Analysis**
   - Discuss what problems you encountered in Part A: When we were both editing at the same time, our work overlapped. It was hard to tell who wrote what without actually talking to each other.
     - Were changes overwritten or lost? Yes. When we tried to manually copy-paste everything into one file, some punctuation and a few lines got replaced and lost.
     - How did you decide which changes to keep? We went through it line-by-line and just talked it out to agree on which version sounded better.
     - What if you had 5 people instead of 2? It would be a complete mess. If we tried to track everything through emails or chat, we'd definitely lose a lot of work.
     - How would you track who made which changes? We can't really track it right now. The only way is to manually write our names next to the sentences we wrote.

5. **Design Your Solution**
   - Draw a diagram of how your version control system would work
   - Your system must address these requirements:
     - How do you store different versions? We store everything on a central cloud server that keeps a full timeline of every save.

     - How do you track who made changes? The system automatically tags each change with the person's username and the time they made it.

     - How do you handle conflicts when two people edit the same line? It stops the save, highlights the conflicting line in red, and makes you manually choose which version to keep.

      - How do you name/identify different versions? It uses automatic version numbers like v1.0, v1.1, v1.2 instead of us naming them manually.

      - How do you describe what changed in each version? You have to write a short one-sentence summary of what you changed before it will let you save.

      - How do you prevent people from overwriting each other's work? It won't let you upload your work until you first download the latest changes from your teammates and merge them in.

### Part C: Document Your Solution

- Create a clean diagram of your version control system on paper

- Write a brief explanation (3-4 sentences) of how your system works : Our system uses a central cloud server that saves every version of a file one after another, each with its own version number. When someone edits a file, it automatically tags their username next to the lines they changed and asks them to write a short note about what they did. If two people edit the same exact line, the system shows an error and makes you manually review it before saving.

- List the top 3 problems from Part A that your system solves :
1. Blind Overwriting: It stops teammates from accidentally erasing each other's work without any warning.
2. Lack of Tracking: You always know who wrote what because every line is tagged with the author's name.
3. History Confusion: You don't have to guess what was changed, because every update has a short written description.

- Deliverable: Submit your diagram and explanation to the instructor

### Wrap Up Quesion...
- What was the most frustrating part of the collaboration chaos? Not being able to communicate while editing. Merging everything into one final file was confusing and we kept overwriting each other.
  
- Which problem from Part A does your system design solve best? It best solves line conflicts. Instead of hunting for overlapping changes manually, the system flags them automatically.
  
- What would happen if 10 people tried to collaborate this way? Doing it manually would be impossible. People would accidentally delete files and overwrite each other's code, it would be total chaos.
  
- How does your design handle someone accidentally deleting the file? Since all versions are saved on the central server, you can just go back in the history and restore the previous version right away.

---

# Lab 3 Rubric - Version Control Concepts

**Total Points: 2 marks**

## Requirements for Completion:
* **Part A:** Complete collaboration chaos simulation with both students participating in silent editing phase and manual merge attempt
* **Part B:** Analyze problems encountered and design a version control system addressing all 6 requirements (storage, tracking, conflicts, naming, descriptions, prevention)
* **Part C:** Create clean diagram and written explanation of system design, identify top 3 problems solved
* **Wrap Up:** Answer all reflection questions demonstrating understanding of collaboration challenges

## Lab Rubric:

| Criteria | Poor - 0 mark | Fair - 1 mark | Good - 2 marks |
|---|---|---|---|
| Lab Completion | Missing major components (Part A not attempted OR no system design OR no deliverable submitted) OR answers lack depth (single sentence responses, vague answers that don't address the questions) | Completed simulation and attempted system design, but design addresses only some requirements OR reflection questions show minimal understanding OR diagram/explanation lacks clarity | Successfully completed all parts: full simulation participation, comprehensive system design addressing all 6 requirements, clear diagram with explanation, and thoughtful reflection answers |

## Detailed Expectations:

### For 2 marks (Good), teams must demonstrate:
- **Active Participation:** Both students fully engaged in Part A simulation and merge attempt
- **Comprehensive System Design:** Version control solution addresses all 6 requirements:
  - Version storage strategy
  - Change tracking mechanism
  - Conflict resolution approach
  - Version naming/identification system
  - Change description method
  - Overwrite prevention solution
- **Clear Documentation:** Professional diagram and concise explanation (3-4 sentences) that clearly communicates system design
- **Problem-Solution Connection:** Identifies top 3 problems from simulation and explains how design solves them
- **Thoughtful Reflection:** Wrap-up questions answered with insight showing understanding of collaboration challenges and scalability issues

### For 1 mark (Fair), teams show:
- **Basic Participation:** Completed simulation but limited engagement in analysis
- **Incomplete Design:** System addresses some but not all requirements, or solutions are superficial
- **Adequate Documentation:** Diagram present but unclear, or explanation lacks detail
- **Weak Problem Analysis:** Problems identified but poor connection to design solutions
- **Minimal Reflection:** Wrap-up questions answered but responses show limited understanding

### For 0 marks (Poor), teams have:
- **Missing Components:** Major parts not completed or attempted
- **No System Design:** No meaningful version control solution proposed
- **No Documentation:** Missing diagram, explanation, or deliverable not submitted
- **No Demonstration of Learning:** Shows no grasp of version control concepts or collaboration challenges

## Teamwork Expectation:
Both team members must actively participate in the simulation and contribute to the system design process. The experience of collaboration problems in Part A is essential for understanding the need for version control systems.
