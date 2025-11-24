
### Lab 11

### Exercise 1: Resume Screening AI Bias Analysis (Solo, 25 minutes)

#### Complete Dataset: TechCorp Resume Screening Results

**Background:** TechCorp's AI system screens resumes for software engineering positions. The AI gives each resume a score from 1-100, and anyone scoring 70+ gets an interview invitation.

**The Data:**
```
MALE CANDIDATES (50 total)
Names: Michael, John, David, James, Robert, William, Richard, Joseph, Thomas, Christopher, Daniel, Matthew, Anthony, Mark, Steven, Andrew, Joshua, Kenneth, Kevin, Brian, George, Timothy, Ronald, Edward, Jason, Jeffrey, Ryan, Jacob, Gary, Nicholas, Eric, Jonathan, Stephen, Larry, Justin, Scott, Brandon, Benjamin, Samuel, Gregory, Alexander, Patrick, Jack, Dennis, Jerry, Tyler, Aaron, Henry, Douglas, Peter

Scores: 78, 85, 67, 82, 79, 88, 65, 77, 83, 86, 69, 81, 74, 89, 76, 84, 71, 80, 87, 75, 68, 82, 78, 85, 79, 83, 77, 86, 72, 88, 81, 74, 85, 79, 87, 76, 83, 80, 78, 84, 73, 86, 82, 77, 89, 75, 81, 85, 79, 88

Actually Qualified (based on human expert review): 38 out of 50
```

```
FEMALE CANDIDATES (50 total)
Names: Mary, Patricia, Jennifer, Linda, Elizabeth, Barbara, Susan, Jessica, Sarah, Karen, Nancy, Lisa, Betty, Helen, Sandra, Donna, Carol, Ruth, Sharon, Michelle, Laura, Sarah, Kimberly, Deborah, Dorothy, Lisa, Nancy, Karen, Betty, Helen, Sandra, Maria, Ruth, Sharon, Michelle, Laura, Carol, Donna, Kimberly, Deborah, Dorothy, Susan, Jessica, Elizabeth, Barbara, Patricia, Jennifer, Linda, Mary, Betty

Scores: 65, 72, 58, 69, 66, 75, 61, 68, 74, 77, 62, 71, 67, 78, 64, 73, 59, 70, 76, 66, 63, 69, 65, 72, 68, 74, 67, 75, 61, 77, 70, 66, 73, 68, 76, 64, 72, 69, 65, 74, 62, 75, 71, 67, 78, 63, 70, 73, 68, 76

Actually Qualified (based on human expert review): 35 out of 50
```

#### Student Worksheet

**Step 1: Basic Statistics**
Calculate the following for both groups:

1. **Interview Rate (AI Decision):**
   - Males scoring 70+: _____ out of 50 = _____%
   - Females scoring 70+: _____ out of 50 = _____%

2. **Actual Qualification Rate (Human Expert):**
   - Males actually qualified: 38 out of 50 = 76%
   - Females actually qualified: 35 out of 50 = 70%

**Step 2: Bias Analysis**
3. **AI Accuracy by Group:**
   - For males: How many qualified candidates did the AI correctly identify?
   - For females: How many qualified candidates did the AI correctly identify?
   - AI Accuracy for males: _____%
   - AI Accuracy for females: _____%

4. **False Negatives (Qualified but Rejected):**
   - Males: How many qualified men were scored below 70?
   - Females: How many qualified women were scored below 70?

**Step 3: Impact Assessment**
5. **Real-world Impact:**
   - If TechCorp hires 20 people, how many would likely be male vs female based on AI recommendations?
   - Is this proportional to the actual qualification rates?

**Step 4: Reflection Questions**
6. What evidence of bias do you see in this AI system?
7. How might this bias have developed during programming/training?
8. What would you recommend to fix this system?

### Exercise 2: AI Decision Transparency Testing (Pairs, 30 minutes)

#### Complete Scenario Package

**Setup:** One student plays "AI System," the other plays "User." The AI System has information cards, the User has question cards.

#### Round 1: Black Box AI System (10 minutes)

**Scenario:** College Scholarship AI System

**AI System Information Card:**
```
DECISION: Sarah Miller - SCHOLARSHIP DENIED
Your job: You can only say "The AI system has determined you do not qualify for this scholarship." 
You cannot explain why or provide any details.
```

**User Question Card (Sarah Miller):**
```
You are Sarah Miller, a student who applied for a scholarship.
Your stats: 3.8 GPA, 2 years volunteer work, part-time job, first-generation college student
You just found out you were denied. Ask the AI system:

1. Why was I denied?
2. What can I do to improve my chances?
3. Was my application reviewed fairly?
4. Can I appeal this decision?
5. What criteria are used for selection?

Record how you feel during this conversation.
```

#### Round 2: Transparent AI System (10 minutes)

**AI System Information Card:**
```
DECISION: Sarah Miller - SCHOLARSHIP DENIED
REASONING: The AI system uses these factors (in order of importance):
1. GPA (40% weight) - Sarah scored 76/100 (3.8/4.0 GPA)
2. Standardized Test Scores (30% weight) - Sarah scored 45/100 (missing SAT scores)
3. Volunteer Work (20% weight) - Sarah scored 85/100 (2 years volunteering)
4. Leadership Experience (10% weight) - Sarah scored 20/100 (no leadership roles listed)
OVERALL SCORE: 61/100 (Scholarship threshold: 75/100)

You can explain these details and suggest improvements.
```

**User Question Card (Same as Round 1):**
```
Ask the same questions as Round 1, but now record:
- How the answers differ
- Whether you understand the decision better
- If you feel the process was fairer
- What specific actions you could take
```

#### Round 3: Role Switch with New Scenario (10 minutes)

**New Scenario:** Medical AI Diagnosis Assistant

**AI System Information Card:**
```
DECISION: Patient shows 78% probability of having Type 2 Diabetes
REASONING: Based on analysis of:
- Blood glucose levels (elevated - 185 mg/dL, normal <140)
- BMI (32.5 - obese category)
- Age (45 - moderate risk factor)
- Family history (diabetes in both parents - high risk)
- Physical activity (reported as "sedentary" - risk factor)
- Symptoms reported (excessive thirst, frequent urination - classic signs)

RECOMMENDATION: Consult with doctor for confirmatory tests and treatment options.
NOTE: This is a diagnostic aid, not a final diagnosis.
```

**User Question Card:**
```
You are a patient who used a health app that suggested you might have diabetes.
Ask about:
1. How certain is this diagnosis?
2. What specific factors led to this conclusion?
3. What should I do next?
4. Could this be wrong?
5. What would happen if I change my lifestyle?

Compare this interaction to the scholarship experience.
```

#### Reflection Worksheet

**After completing all rounds, answer:**

1. **Emotional Impact:**
   - How did you feel in Round 1 vs Round 2?
   - Which interaction felt more fair? Why?

2. **Understanding:**
   - In which scenario did you better understand the decision?
   - What specific information was most helpful?

3. **Trust:**
   - Which AI system would you trust more? Why?
   - How did transparency affect your confidence in the system?

4. **Actionability:**
   - In which scenario could you take specific action to improve your situation?
   - Why is this important for AI systems?

5. **Programming Implications:**
   - As a future professional, why should programmers build explainable AI?
   - What challenges might programmers face in making AI transparent?
   - How could lack of transparency become an ethical problem?

**Group Discussion Questions:**
- Should all AI systems be required to explain their decisions?
- Are there situations where transparency might be harmful?
- How detailed should explanations be for different types of decisions?

---
# Lab Rubric

## Lab Requirements:
- **Exercise 1** requires completion of all calculation steps (1-4) and thoughtful responses to reflection questions (6-8)
- **Exercise 2** requires participation in all three role-playing rounds and completion of the reflection worksheet with meaningful analysis

## Grading Criteria (Total: 2 marks)

| Criteria | Poor - 0 marks | Fair - 1 mark | Good - 2 marks |
|---|---|---|---|
| **Lab Completion** | Major portions incomplete (missing entire exercises or most calculations/reflections) **OR** answers lack depth and understanding (single sentence responses, vague answers that don't address the questions) | Successfully completed most calculations and role-playing activities but reflection portions show limited depth or miss key insights about AI bias and transparency | Successfully completed all calculations, participated fully in role-playing exercises, and provided thoughtful reflections that demonstrate clear understanding of AI bias, transparency issues, and their ethical implications |

## Additional Notes:
- Both exercises must show evidence of engagement with the core concepts of AI bias analysis and the importance of transparency in AI decision-making systems
- Quality of reflection and analysis is as important as completion of calculations and activities
