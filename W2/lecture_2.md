# COMP9020 Lecture A – Week 1 Wednesday Summary

## 📋 Exam Policy

- **No electronic devices allowed** during exams (smartphones, smartwatches, tablets).
- Anyone caught with one will be removed and reported to Academic Integrity.
- A prior exam used an **analog clock via document camera**; some students could not read it, highlighting a basic skills gap.

---

## 🔄 Recap of Natural Deduction (Propositional Logic)

### Overview

- Natural deduction allows **proving arguments are valid**.
- It's **non-mechanical**, unlike truth tables – you must **think and choose rules**.
- Much faster and more scalable than truth tables for large problems.

### Types of Proof

- **Direct Proof**: Start from premises and derive the conclusion.
- **Indirect Proof (Proof by Contradiction)**: Assume ¬P (negation of the conclusion), derive a contradiction (e.g., `Q ∧ ¬Q`).

### Contradiction in Logic

- Explicit contradiction: a formula of the form `P ∧ ¬P`.

---

## 🔁 Propositional Logic Limitations

- Propositional logic can't capture argument **structure within atomic statements**.
- Example: “All humans are mortal” cannot be properly analyzed in propositional logic.

---

## ➕ Introduction to Predicate Logic (First-Order Logic)

### Motivation

Predicate logic allows us to **look inside atomic propositions** using:

- **Constants** (a, b, c, ..., r)
- **Predicates** (P, Q, R, ...)
- **Variables** (x, y, z, ...)

### Notation

- **Predicates**: Denote properties or relations (e.g., `Px` = x is P).
- **Constants**: Refer to individual objects in the domain (e.g., `a` might refer to Donald Trump).
- **Variables**: Used for quantification (`x`, `y`, `z`, ..., `s` to `z` specifically).
- Constants cannot be used inside quantifiers.

---

## 🔠 Syntax and Semantics in Predicate Logic

### Syntax

- Well-formed formulas (wffs) use quantifiers, logical connectives, and parentheses for scope.
- **Variables must be bound** to form meaningful statements (closed wffs).

### Semantics

- **Models (M)** consist of:
  - A **non-empty domain** (set of objects),
  - Assignments of **references to constants**,
  - **Extensions** (sets of domain elements) for predicates.

### Examples

- `∀x Px` is true iff every element in the domain is in the extension of P.
- `∃x Px` is true iff at least one element in the domain is in the extension of P.
- A predicate's extension can be the **empty set**, unlike the domain.

---

## ⚖️ Bound vs Free Variables

| Concept        | Explanation                                                             |
| -------------- | ----------------------------------------------------------------------- |
| Free Variable  | A variable not under the scope of a quantifier.                         |
| Bound Variable | A variable within the scope of a quantifier.                            |
| Open formula   | A well-formed formula that contains at least one free variable.         |
| Closed formula | A well-formed formula where all variables are bound (a full statement). |
| Constants      | Neither bound nor free. Cannot appear in quantifiers.                   |

### Examples

- `∀x (Px ∧ Qx)` → closed wff (all variables bound).
- `∀x Px ∧ Qx` → open formula (scope of quantifier limited to `Px` only).

➡ Scope of quantifier is limited by parentheses.

---

## 🔁 Logical Equivalences Involving Quantifiers

| Formula   | Equivalent to |
| --------- | ------------- |
| `∀x P(x)` | `¬∃x ¬P(x)`   |
| `∃x P(x)` | `¬∀x ¬P(x)`   |

These are **duals**. A quantifier’s dual can be defined using negation and the other quantifier.

---

## ⚙️ Logical Connectives in Predicate Logic (Model Semantics)

Each connective is defined in terms of **model truth conditions**:

- **Negation (`¬φ`)**: True in model M iff φ is false in M.
- **Conjunction (`φ ∧ ψ`)**: True iff both φ and ψ are true in M.
- **Disjunction (`φ ∨ ψ`)**: True iff at least one of φ or ψ is true.
- **Conditional (`φ → ψ`)**: True iff either φ is false or ψ is true.
- **Biconditional (`φ ↔ ψ`)**: True iff φ and ψ have the same truth value.

---

## 🔍 Understanding Quantifiers in Models

- `∀x P(x)` is **true in a model M** iff **every object in the domain** satisfies `P(x)`.
- `∃x P(x)` is **true in a model M** iff **at least one object in the domain** satisfies `P(x)`.

### Vacuous Truth

- `∀x P(x)` is true in a model if the extension of P is the entire domain.
- If **no object satisfies P**, `∃x P(x)` is **false**.

---

## 🧠 Subtle Distinctions

### Example 1: `∀x (P(x) ∨ Q(x))`

- Every object is either P or Q.

### Example 2: `∀x P(x) ∨ ∀x Q(x)`

- Either all objects are P or all are Q.

➡ These are **not logically equivalent**.

---

## ✅ Validity in Predicate Logic

- An argument is **valid** iff **no model exists** in which the premises are true and the conclusion is false.
- Finding a **countermodel** (i.e., one where premises are true and conclusion false) proves **invalidity**.
- Proving **no such model can exist** proves **validity**.

---

## 🧪 Examples from Lecture

# 🔍 In-Depth Analysis of Quantified Logic Examples

---

## ✅ Background: Validity in Predicate Logic

An argument is **valid** if:

> There is **no model** in which the premises are true and the conclusion is false.

If you **can** find such a model (a **countermodel**), then the argument is **invalid**.

---

## 🔎 Example 1 – Invalid Argument

**Premise:**  
∃x P(x) ∧ ∃x Q(x)  
**Conclusion:**  
∃x (P(x) ∧ Q(x))

### 🧠 Intuition:

- Premise says: “Some x is P” and “Some (possibly different) x is Q.”
- Conclusion says: “There exists **one x** that is both P and Q.”

### 🧪 Countermodel:

Let the **domain** be {1, 2}

Define:

- P = {1}
- Q = {2}

Then:

- ∃x P(x) is true (x = 1)
- ∃x Q(x) is true (x = 2)

✅ Premise is **true**  
❌ But: ∃x (P(x) ∧ Q(x)) is **false** because no single x is both in P and Q.

### ✅ Therefore:

Premises true + conclusion false ⇒ **Invalid**

---

## 🔎 Example 2 – Valid Argument

**Premise:**  
∃x (P(x) ∧ Q(x))  
**Conclusion:**  
∃x P(x) ∧ ∃x Q(x)

### 🧠 Intuition:

- Premise says: “There exists an x such that both P and Q hold.”
- Then x must be in both P and Q → P(x) is true, Q(x) is true

### ✅ Therefore:

- ∃x P(x) is true (same x)
- ∃x Q(x) is true (same x)

✅ Both parts of the conclusion follow  
✅ No countermodel exists ⇒ **Valid**

---

## 🔎 Example 3 – Invalid Quantified Argument

**Premises:**

1. ∀x (P(x) ∨ Q(x))
2. ¬∀x P(x)  
   **Conclusion:**  
   ∀x Q(x)

### 🧠 Intuition:

- Premise 1: Every x is either P or Q.
- Premise 2: Not every x is P.
- Conclusion: Every x is Q?

This doesn't logically follow — the "either-or" doesn’t force Q to always be true.

### 🧪 Countermodel:

Let domain = {1, 2}

Define:

- P = {1}
- Q = {2}

Then:

- ∀x (P(x) ∨ Q(x)) is true:

  - x=1: P(1)=true ⇒ P(1) ∨ Q(1) = true
  - x=2: Q(2)=true ⇒ P(2) ∨ Q(2) = true

- ¬∀x P(x) is true:

  - P(2) is false, so not all x satisfy P

- ∀x Q(x) is false:
  - Q(1) = false

### ✅ Therefore:

Premises true + conclusion false ⇒ **Invalid**

---

## ✅ Summary Table

| Example | Premises True? | Conclusion False? | Valid? |
| ------- | -------------- | ----------------- | ------ |
| 1       | Yes            | Yes               | ❌ No  |
| 2       | Yes            | No                | ✅ Yes |
| 3       | Yes            | Yes               | ❌ No  |

---

---

## 🧩 Meta Concepts

- **Predicate logic** = First-order logic (quantifies over objects only).
- **Second-order logic** allows quantifying over predicates, sets, etc. (not covered in COMP9020).
- **Gödel’s incompleteness theorem**: First-order logic cannot capture all truths of arithmetic with consistency.

---

## 🔑 Key Takeaways

- Constants ≠ variables. Constants refer, variables range.
- All variables must be **bound** to make a proper logical statement.
- **Parentheses control scope** of quantifiers.
- Think in terms of **models**, not just truth tables.
- **Validity** means no countermodel exists.
- Practice identifying **bound vs free variables** and checking **model truth**.

---

## 🧠 Tips from Lecturer

- Double-check your answers before submitting.
- Deadlines are strict – late submissions only for genuine emergencies.
- Practice **time management**, **logical thinking**, and **disciplined reasoning**.
