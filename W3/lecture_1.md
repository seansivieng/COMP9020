# Predicate Logic and Model Theory: Detailed Notes

## Lecture Overview
This lecture provided an in-depth revision and expansion on key concepts from predicate logic relevant to Problem Set 2. It included discussion of logical validity, models, translation heuristics, and natural deduction. The material also clarified semantic versus syntactic roles in predicate logic.

---

## Part 1: Predicate Logic Fundamentals

### Symbols Recap
- **Predicates:** Represented by uppercase letters (e.g., P, Q).
- **Constants (Names):** Lowercase letters (e.g., a, b).
- **Variables:** Also lowercase, but not tied to specific objects unless quantified.
- **Quantifiers:**
  - ∃x Px: "There exists an x such that Px" (Existential)
  - ∀x Px: "For all x, Px" (Universal)

### Logical Forms
- Translate logical formulas to English first for clarity.
- Disjunction (∨) is **true** unless both disjuncts are false.
- Example argument:
  - Premise 1: ∀x Px ∨ ∀x Qx
  - Premise 2: ¬∀x Px
  - Conclusion: ∀x Qx

  This is **valid** due to disjunctive syllogism.

---

## Part 2: Validity and Model Construction

### Validity Definition
- An argument is **valid** if it's **impossible** to make all premises true and the conclusion false.

### Heuristic for Models
1. Translate formulas into plain English.
2. Use a small domain (start with one or two elements).
3. Make the conclusion false, then attempt to make premises true.

### Example: Proving Validity
- Given ∀x (Px → Qx) and we want to test if it's equivalent to ∀x (¬Qx → ¬Px)
  - Try falsifying the second statement.
  - Observe that in every model, you can't make one true and the other false.
  - Hence, they are logically equivalent.

### Translation Tip
- Translate without assuming anything about the domain.
- Syntax-driven: Don't include semantic assumptions.

---

## Part 3: Logical Equivalences

### Useful Equivalences
| Form | Equivalent Form |
|------|-----------------|
| ∀x (Px → Qx) | ¬∃x (Px ∧ ¬Qx) |
| ¬∀x Px | ∃x ¬Px |
| ¬∃x Px | ∀x ¬Px |

### Converse, Inverse, Contrapositive
Given: ∀x (Px → Qx)
- **Contrapositive:** ∀x (¬Qx → ¬Px) ✅ Logically equivalent
- **Converse:** ∀x (Qx → Px) ❌ Not logically equivalent
- **Inverse:** ∀x (¬Px → ¬Qx) ❌ Not logically equivalent

---

## Part 4: Syntax vs Semantics

### Clarifications
- Variables **range** over objects in the domain.
- Constants (names) refer to specific domain elements.
- Truth set = extension of a predicate = set of objects satisfying the predicate.

### Distinction
- **Syntax:** Rules for forming valid formulas.
- **Semantics:** Interpretation in a model (truth values).

---

## Part 5: Natural Deduction Rules

### Universal Quantifier Elimination (∀ Elim)
- **Form:** From ∀x ϕ(x), infer ϕ(a).
- **Explanation:** If something is true for everything, it must be true for any specific thing.

### Existential Quantifier Introduction (∃ Intro)
- **Form:** From ϕ(a), infer ∃x ϕ(x).
- **Explanation:** If some specific object has a property, then something has that property.

### Existential Quantifier Elimination (∃ Elim)
- **Form:** From ∃x ϕ(x), introduce a new name **a** such that ϕ(a), where **a** is not used elsewhere.
- **Explanation:** If something exists with a property, we can give it a name and reason about it—**but only if we say nothing else about that name** beforehand.

### Universal Quantifier Introduction (∀ Intro)
- **Form:** From ϕ(a), infer ∀x ϕ(x) if **a** is arbitrary.
- **Explanation:** If a claim is true for an arbitrary object, it's true for all objects.
- **Constraint:** The name **a** must not appear in any undischarged assumption or premise.

---

## Part 6: Expanded Inference Rule Guidance

### Universal Elimination
- Use it to derive specific instances from a general rule.
- Safe to apply repeatedly to any constant.

### Existential Introduction
- Use when you have a specific instance and want to generalise it to an existence claim.
- No constraints: valid for any true instance.

### Existential Elimination (Crucial Warning)
- Only allowed when introducing a **new constant**.
- That constant must not appear in:
  - Any premises.
  - Any assumptions.
- Reason: prevents illegitimate assumptions about what exists.

### Universal Introduction (Subtle but Powerful)
- Can generalise from a particular case only if:
  - The chosen object was **arbitrary**.
  - No assumptions were made specific to that object.
  - Its name does not appear in earlier reasoning.
- Common source of error: using an object that has hidden assumptions attached.

### Tactic
- When attempting to generalise, make sure to isolate your reasoning.
- Discharge assumptions clearly if you use conditional proof.
- Always verify variable binding and quantifier scope.

---

## Part 7: Proof Strategy Tips

- Use universal elimination to apply a general rule to specific cases.
- Be cautious with existential elimination: don't reuse constants.
- To prove a universal statement, generalise from an arbitrary instance.
- Disjunctive syllogism, modus ponens, and modus tollens still apply.
- Understand scope: parentheses dictate what quantifiers bind.
- Prefer simpler models and translate to natural language to clarify.

---

## Summary
- Always identify main logical form before interpreting.
- Use concrete examples to test validity.
- Be precise with variable scope and quantifier rules.
- Practise distinguishing syntax from semantics.
- Validity = impossible for premises true and conclusion false.

This foundation underpins future work in mathematical reasoning, discrete maths, and formal logic systems.

> **Print and memorise**: Converse, Inverse, Contrapositive definitions.

> **Keep referring back** to these deduction rules throughout the course.

---
