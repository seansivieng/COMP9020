# COMP9020 Lecture Notes: Mathematical Induction, Recursion, and Deductive Reasoning

## Overview
This lecture dives into **mathematical induction**, **recursion**, and the **types of reasoning** used in logic and formal proof. It distinguishes between forms of **deductive inference**, discusses **indirect proofs**, and clarifies the confusion surrounding the term "induction".

---

## 1. Types of Reasoning

There are three major types of rigorous reasoning:

### 1.1 Deductive Reasoning
- **Truth-preserving**: Moves from true premises to a true conclusion.
- Examples include: modus ponens, conjunction introduction, etc.
- Used in **mathematical proofs**.

### 1.2 Abductive Reasoning (Inference to the Best Explanation)
- **Not** truth-preserving.
- Selects the most plausible explanation for an observation.
- Example: "I believe I’m in a lecture theatre because that explains my current experience best."

### 1.3 Inductive Reasoning
- Also **not** truth-preserving.
- Forms **justified expectations** about the future based on past experience.
- Example: "The sun has always risen; therefore, it will rise tomorrow."

### Caveat:
- **Inductive inference** in everyday language differs from **mathematical induction**, which is a form of deductive reasoning.

---

## 2. Mathematical Induction

### 2.1 What is it?
A deductive proof technique used to establish the truth of infinitely many statements.

### 2.2 Principle
To prove: \( \forall n \geq a, P(n) \)

Two steps:

#### 1. Basis Step
Prove \( P(a) \) for some base case \( a \).

#### 2. Inductive Step
Assume \( P(k) \) (Inductive Hypothesis) and show \( P(k + 1) \).

This follows a **rule of conditional proof** and **universal generalisation**.

### 2.3 Formal Structure
Given:
- \( P(a) \)
- \( \forall k \geq a, P(k) \Rightarrow P(k+1) \)

Then: \( \forall n \geq a, P(n) \)

---

## 3. Worked Example

### Claim
\[
\sum_{i=1}^{n} i = \frac{n(n + 1)}{2}
\]

### Step 1: Basis Case \( n = 1 \)
\[
1 = \frac{1(1 + 1)}{2} = 1 \Rightarrow \text{True}
\]

### Step 2: Inductive Step
Assume:
\[
\sum_{i=1}^{k} i = \frac{k(k + 1)}{2}
\]

To prove:
\[
\sum_{i=1}^{k+1} i = \frac{(k+1)(k+2)}{2}
\]

From assumption:
\[
\sum_{i=1}^{k+1} i = \left(\sum_{i=1}^{k} i\right) + (k+1) = \frac{k(k + 1)}{2} + (k + 1)
\]
\[
= \frac{k(k + 1) + 2(k + 1)}{2} = \frac{(k + 1)(k + 2)}{2}
\]
\( \Rightarrow \text{Proved} \)

---

## 4. Direct vs Indirect Proofs

### 4.1 Direct Proof
- Assume premise(s) \( P \) and prove \( Q \).
- E.g., Induction is a direct proof method using conditional proof + universal generalisation.

### 4.2 Indirect Proof

#### 4.2.1 Proof by Contrapositive
- Prove \( \neg Q \Rightarrow \neg P \) instead of \( P \Rightarrow Q \).

#### 4.2.2 Proof by Contradiction
- Assume \( \neg (P \Rightarrow Q) \) and derive a contradiction (e.g., \( \alpha \land \neg \alpha \)).

---

## 5. Constructive vs Non-Constructive Proofs

| Term                | Description                       |
|---------------------|------------------------------------|
| Constructive Proof  | Builds the object directly.        |
| Non-Constructive    | Shows existence by contradiction.  |
| Destructive Proof   | Same as non-constructive.          |

- All **proofs by contradiction** are **non-constructive**.
- **Contrapositive proofs** are indirect but **constructive**.

---

## 6. Recursion

### 6.1 What is Recursion?
A technique to define a sequence based on previous terms.

### 6.2 Structure
- **Initial Conditions**: Provide the first one or more terms.
- **Recurrence Relation**: Defines \( a_k \) in terms of earlier values.

### Example:
Given:
\[
\begin{align*}
a_0 &= 1 \\
a_1 &= 2 \\
a_k &= a_{k-1} + k \cdot a_{k-2} + 1 \text{ for } k \geq 2
\end{align*}
\]

Compute:
\[
a_2 = a_1 + 2 \cdot a_0 + 1 = 2 + 2 \cdot 1 + 1 = 5
\]
\[
a_3 = a_2 + 3 \cdot a_1 + 1 = 5 + 6 + 1 = 12
\]
\[
a_4 = a_3 + 4 \cdot a_2 + 1 = 12 + 20 + 1 = 33
\]

---

## 7. Summary Table

| Term                    | Category            | Method/Example                 |
|-------------------------|---------------------|-------------------------------|
| Mathematical Induction  | Deductive           | Direct, constructive           |
| Contrapositive Proof    | Deductive           | Indirect, constructive         |
| Proof by Contradiction  | Deductive           | Indirect, non-constructive     |
| Recursion               | Definition Technique| Based on previous sequence     |

---

## 8. Key Tips
- Induction is **deductive**, not inductive.
- Always check if your assumption is discharged when applying conditional proof.
- Avoid inferring a conjunction from an assumption.
- Use countermodels or contraposition when stuck.

---

## References
- COMP9020 Lecture Slides
- Stanford Logic Course
- "The Scandal of Deduction" by D'Agostino & Floridi
- Recursion and Fixed Point Theorems (advanced)

---

_These notes summarise the key ideas from the lecture, blending formal logic with mathematical intuition and example._

