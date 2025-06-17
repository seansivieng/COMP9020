
# COMP9020 Week 2 Lecture A Summary

## Lecture Theme: Validity in Propositional Logic and Transition to Predicate Logic

---

## Part 1: Warm-up & Framing

### Sydney Winter Analogy
- Lecturer opens with a humorous commentary on the Sydney winter: although people claim it doesn't get cold, many buildings lack insulation and heating.
- The purpose is to encourage students to question commonly accepted assumptions — a perfect lead-in to the logic course's emphasis on **truth**, **reasoning**, and **validity**.

---

## Part 2: Propositional Logic – Validity and Truth Tables

### What is Validity?
- An **argument** consists of one or more **premises** and a **conclusion**.
- An argument is **valid** if **every** truth assignment that makes **all premises true** also makes the **conclusion true**.
- If **even one** assignment makes the premises true and the conclusion false → the argument is **invalid**.

### Truth Tables
- A **truth table** lists all possible combinations of truth values for a set of propositional variables.
- It is a **mechanical** method, ideal for small numbers of variables.
- For `n` propositional atoms, we have `2^n` rows.

#### Applications:
- To determine if a formula is a **tautology** (true on all rows).
- To determine if a formula is a **contradiction** (false on all rows).
- To determine if an argument is **valid**.

### Example: Invalid Argument (from lecture)
- Premise 1: `¬P -> ¬Q`
- Premise 2: `¬¬P`
- Conclusion: `¬Q`

**Truth Table Construction:**
| P | Q | ¬P | ¬Q | ¬P -> ¬Q | ¬¬P | Conclusion ¬Q |
|---|---|----|----|----------|------|----------------|
| T | T | F  | F  | T        | T    | F              |
| T | F | F  | T  | T        | T    | T              |
| F | T | T  | F  | F        | F    | F              |
| F | F | T  | T  | T        | F    | T              |

Row 1: both premises are true (`¬P -> ¬Q` is true, `¬¬P` is true), but `¬Q` is false ⇒ contradiction ⇒ **invalid**.

---

## Part 3: Shorter Truth Table Method

### Purpose:
- Avoid writing full truth tables by seeking **counterexamples** directly.

### Strategy:
1. Assume the **conclusion is false**.
2. Try to assign values that make **all premises true**.
3. If such values exist → argument is **invalid**.

### Example:
- Premises: `P -> Q`, `¬P`
- Conclusion: `¬Q`

**Step-by-step:**
- Assume `¬Q` is **false** ⇒ `Q = true`
- `¬P` must be **true** ⇒ `P = false`
- `P -> Q` is true (since `P` is false ⇒ whole implication is true)
- All premises true, conclusion false ⇒ **invalid argument**

---

## Part 4: Natural Deduction

### Purpose:
- Allows proving conclusions from premises using **rules of inference**, closer to human reasoning.

### Common Inference Rules (with explanation):

| Rule Name         | Form                        | Description                                 |
|------------------|-----------------------------|---------------------------------------------|
| Modus Ponens     | P, P → Q ⟹ Q               | If P and P implies Q, then Q                |
| Modus Tollens    | P → Q, ¬Q ⟹ ¬P            | If P implies Q and Q is false, then P is false |
| Conjunction Elim | P ∧ Q ⟹ P (or Q)           | From a conjunction, infer either conjunct   |
| Conjunction Intro| P, Q ⟹ P ∧ Q               | Combine two statements into a conjunction   |
| Disjunction Elim | P ∨ Q, ¬P ⟹ Q              | If either P or Q is true, and P is false, then Q must be true |

### Conditional Proof (CP)
- To prove `P → Q`:
  1. **Assume `P`**
  2. **Derive `Q`**
  3. Therefore, conclude `P → Q`

### Proof by Contradiction (Reductio ad Absurdum)
- Assume `¬C` (negation of the conclusion)
- Derive a contradiction (e.g., `C ∧ ¬C`)
- Hence, `¬C` must be false ⇒ **C is true**

#### Detailed Example:
- Premise: `A ∨ (B ∧ C)`
- Conclusion: `C`
- **Assume ¬C** (for contradiction)
- Case analysis on disjunction:
  - If `A` is true, nothing about `C`
  - If `B ∧ C` is true → then **C must be true**
- Contradiction arises from `¬C` and `C` → reject `¬C`, so `C` must be true

---

## Part 5: Transition to Predicate Logic

### Why Move Beyond Propositional Logic?
- Propositional logic treats statements like `P`, `Q`, `R` as **atomic units**.
- It **doesn’t capture internal structure** (e.g., subject-predicate, individuals, generalisation).

#### Classic Example:
1. All humans are mortal
2. Socrates is a human
3. ∴ Socrates is mortal

**Propositional Logic Translation:**
- `P ∧ Q → R` — no structural connection between "Socrates" and "human"

**Predicate Logic Translation:**
- `H(x)` = "x is human"
- `M(x)` = "x is mortal"
- `s` = Socrates

**Formal Argument:**
1. `∀x (H(x) → M(x))`
2. `H(s)`
3. ∴ `M(s)` (by **universal instantiation** + **modus ponens**)

### Key Predicate Logic Concepts:
- **Predicate**: A property or relation (e.g., `Loves(x, y)`, `Tall(x)`)
- **Constant**: A specific named object (e.g., `a`, `s`, `j`) in the domain
- **Variable**: A placeholder that ranges over the domain (e.g., `x`, `y`)
- **Atomic Formula**: A predicate applied to constants/variables (e.g., `Human(s)`, `Loves(a, b)`)
- **Quantifiers**:
  - `∀x` = For all x
  - `∃x` = There exists x

---

## Part 6: Models in Predicate Logic

### Why Not Use Truth Tables?
- Truth tables assign **T/F** to **whole formulas**.
- Predicate logic statements involve **domains of objects** and **structure**.
- Need models to **interpret** the meaning of formulas with quantifiers.

### What Is a Model?
A **model M** includes:
1. A **non-empty domain D** of objects (e.g., `{1, 2, 3}`)
2. An **interpretation of constants** as specific domain elements (e.g., `a → 1`)
3. An **extension of predicates**: sets of domain objects for which the predicate is true

### Evaluating Truth in a Model
To evaluate `P(a)` in model M:
1. Identify what object `a` refers to in the domain
2. Check if that object is in the extension of predicate `P`

### Model Examples
| Model | Domain         | a refers to | P's extension | Is P(a) true? |
|--------|----------------|--------------|----------------|----------------|
| M1     | {1}            | 1            | {1}            | ✅ Yes         |
| M2     | {1}            | 1            | ∅              | ❌ No          |
| M3     | {1, 2}         | 1            | {2}            | ❌ No          |
| M4     | {1, 2, 3, 4, 5}| 4            | {1, 2, 3}      | ❌ No          |

### Terminology
- **Referent**: The object in the domain that a constant denotes
- **Extension**: The set of domain elements for which a predicate is true

### Summary
- Predicate logic uses **models** to define truth.
- Models assign **meaning** to symbols.
- Quantified statements like `∀x P(x)` are true if P holds for **every** object in the domain.
- `∃x P(x)` is true if P holds for **at least one** object in the domain.
- Unlike propositional logic, **truth depends on the model**.
