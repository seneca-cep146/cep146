
### Lab 8

# How a Neural Network Learns

## Objective
Simulate how a neural network learns to make decisions, gaining an intuitive understanding of weights, feedback, and pattern recognition.
---

## Time: 30–35 minutes

---

## Setup

### Step 1: Draw Your Neural Network
Create a simple network diagram:
- **Input Layer**: 3 inputs — *Food*, *Service*, *Price*
- **Middle Layer**: 1 person = "Decision Node"
- **Output Layer**: "Like" or "Dislike"

---

## Part A: Training Phase

### Step 2: Assign Roles
- 1 person = **Input Feeder** (reads restaurant scenario)
- 1 person = **Decision Node** (decides Like/Dislike)
- Others = **Observers/Trackers** (track answers, suggest updates)

### Step 3: Process 10 Training Scenarios
For each card:
1. **Input Feeder** reads the features.
2. **Decision Node** makes a prediction.
3. Reveal the correct outcome.
4. If **wrong**, place tokens on features that should have had more influence (simulating learning via weight adjustment).

Keep track of how many predictions are correct over time.

---

## Understanding and Assigning Weights

### What Are "Weights"?
In a real neural network, each input (like *Food* or *Price*) is assigned a **weight** that shows **how important** it is when making decisions. These weights change as the AI "learns" from its mistakes.

In this simulation, **you'll use colored tokens or drawn stars** to represent how important a feature is. The more tokens a feature has, the more "weight" it carries in the decision.

---

### How to Assign/Change Weights

#### Step-by-Step Weight Learning Process

1. **Read the Scenario**  
   Example:  
   - *Food*: Excellent  
   - *Service*: Poor  
   - *Price*: Moderate  
   - Real Answer: **LIKE**

2. **Make a Prediction**  
   - The "Decision Node" guesses: *Like* or *Dislike*  
   - Use the current token weights to help guide the guess  
     (e.g., "We have 2 tokens on Food, 1 on Price, none on Service — let's guess LIKE").

3. **Reveal the Correct Answer**  
   - Compare the guess to the actual answer on the card.

4. **Adjust the Weights if Wrong**  
   - If the prediction is **wrong**, discuss:
     - "Why might the customer have liked this restaurant?"
     - "Which feature(s) seem more important in this case?"

   - Then:
     - **Add a token** to features that **should have mattered more**  
     - (Optional) **Remove a token** from features that may have misled you

5. **Track Learning**  
   - Note which weights changed
   - Count correct predictions each round
   - Observe improvement over time

---

### Example Weight Tracker

| Feature     | Tokens (Weight) |
|-------------|-----------------|
| Food        | 🍗 🍗 🍗          |
| Service     | 🍽️              |
| Price       | 💰 💰            |

---

### Part B: Testing Phase (10 min)

### Step 4: New Restaurant Scenarios
Use 3 new cards (test set). Predict again using learned weights.

### Step 5: Team Comparison
Share results with other teams:
- Who improved the most?
- Which features were most important?

---

## Reflection Discussion (5–7 min)
- How did your predictions improve?
- How did "weights" (tokens) help you learn?
- What would happen with more layers or inputs?
- How does this reflect how real AI works?

---

# Scenario Cards 

---

## 🧪 Training Set (10 Cards)

### Card 1  
- **Food**: Great  
- **Service**: Poor  
- **Price**: Cheap  
- **Customer Opinion**: LIKE

### Card 2  
- **Food**: Bad  
- **Service**: Great  
- **Price**: Expensive  
- **Customer Opinion**: DISLIKE

### Card 3  
- **Food**: Good  
- **Service**: Okay  
- **Price**: Moderate  
- **Customer Opinion**: LIKE

### Card 4  
- **Food**: Poor  
- **Service**: Poor  
- **Price**: Cheap  
- **Customer Opinion**: DISLIKE

### Card 5  
- **Food**: Excellent  
- **Service**: Excellent  
- **Price**: Expensive  
- **Customer Opinion**: LIKE

### Card 6  
- **Food**: Okay  
- **Service**: Bad  
- **Price**: Moderate  
- **Customer Opinion**: DISLIKE

### Card 7  
- **Food**: Great  
- **Service**: Okay  
- **Price**: Cheap  
- **Customer Opinion**: LIKE

### Card 8  
- **Food**: Poor  
- **Service**: Excellent  
- **Price**: Expensive  
- **Customer Opinion**: DISLIKE

### Card 9  
- **Food**: Excellent  
- **Service**: Poor  
- **Price**: Moderate  
- **Customer Opinion**: LIKE

### Card 10  
- **Food**: Okay  
- **Service**: Okay  
- **Price**: Expensive  
- **Customer Opinion**: DISLIKE

---

## Test Set (3 Cards)

### Card 11  
- **Food**: Good  
- **Service**: Excellent  
- **Price**: Cheap  
- **Customer Opinion**: LIKE

### Card 12  
- **Food**: Bad  
- **Service**: Bad  
- **Price**: Expensive  
- **Customer Opinion**: DISLIKE

### Card 13  
- **Food**: Excellent  
- **Service**: Great  
- **Price**: Moderate  
- **Customer Opinion**: LIKE

---

## Lab Rubric

**Total Points: 2 marks**

For this lab to be considered complete, students must successfully demonstrate understanding of neural network learning concepts through hands-on simulation including weight adjustment, pattern recognition, and reflective analysis.

## Detailed Expectations:

### Setup and Network Diagram Requirements:
- Drew complete neural network diagram with 3 inputs (Food, Service, Price), 1 decision node, and output (Like/Dislike)
- Properly assigned team roles (Input Feeder, Decision Node, Observers/Trackers)
- Demonstrated understanding of network structure and data flow

### Part A Requirements (Training Phase):
- Successfully processed all 10 training scenario cards with proper prediction workflow
- Tracked prediction accuracy over time showing learning improvement
- Demonstrated proper weight adjustment using tokens/markers when predictions were incorrect
- Showed evidence of systematic weight learning process (adding tokens to important features after mistakes)
- Maintained weight tracker showing progression of feature importance over training rounds

### Part B Requirements (Testing Phase):
- Applied learned weights to predict outcomes for 3 new test scenarios
- Compared performance between training and testing phases
- Participated in team comparison sharing results and insights about feature importance
- Demonstrated transfer of learning from training to new scenarios

### Reflection Requirements:
- Provided thoughtful responses to all reflection questions about prediction improvement and weight learning
- Connected simulation experience to real neural network concepts
- Demonstrated understanding of how weights influence decision-making
- Showed insight into scaling concepts (more layers, more inputs) and real AI applications

## Assessment Rubric:

| Criteria | Poor - 0 marks | Fair - 1 mark | Good - 2 marks |
|---|---|---|---|
| Lab Completion | Failed to complete setup or only completed training phase without weight tracking, or missing both testing phase and reflection discussion | Successfully completed training phase (Part A) with weight tracking OR testing phase (Part B) with team comparison, but reflection portion was either non-existent or lacked depth (single sentence answers, answers that are vague or don't demonstrate understanding of neural network concepts) | Successfully completed both training phase (Part A) with proper weight adjustment tracking AND testing phase (Part B) with meaningful team comparison, plus provided thoughtful reflection demonstrating clear understanding of neural network learning principles |
