# COMP9020 Lecture Study Notes: Predicate Logic and Proof Methods

## 🎥 Lecture Context

- **Instructor anecdote:** Students plagiarised a plagiarised YouTube video.
- **Lesson:** Be cautious about online sources—especially for math and logic. Always verify with trusted materials like textbooks.

---

## 📚 Advice for Learning

- **YouTube vs. Textbooks:**
  - Programming videos can be quickly validated (code compiles or doesn’t).
  - Math videos often contain errors that are hard for beginners to detect.
- **Recommendation:** Focus on the set textbooks and do exercises. Understanding takes effort; watching videos is not a substitute.

---

## 🔍 Transition from Formal to Informal Proofs

- We've done the most **abstract part**: formal logic (machine code equivalent).
- Now moving to **semi-formal reasoning** (closer to Python-level abstraction).
- Under the hood, the same logical principles apply.

---

## 🧠 Review: Types of Proofs

### Direct Proof
- Start from premises.
- Apply inference rules until conclusion is reached.
- **Example:** Proving even + even = even using substitution and factoring.

### Indirect Proofs
#### 1. Contraposition
- Prove: `A → B` by proving `¬B → ¬A`.

#### 2. Contradiction (Reductio ad absurdum)
- Assume the negation of what you want to prove.
- Derive a contradiction.

---

## 🔣 Formal Language Concepts

### The Equality Relation (`=`)
- Not a connective.
- Formally, a **two-place relation** `R²` with:
  - Reflexivity: `a = a`
  - Symmetry: `a = b → b = a`
  - Transitivity: `a = b ∧ b = c → a = c`

### Predicates
- One-place: Properties (e.g., is_even, is_prime)
- Two-place or more: Relations (e.g., less_than, equals)

### Functions
- Are relations.
- All functions are predicates, but not all predicates are functions.

---

## 🧾 Definitions

### Even:
> `n` is even iff ∃k ∈ ℤ such that `n = 2k`

### Odd:
> `n` is odd iff ∃k ∈ ℤ such that `n = 2k + 1`

### Prime:
> `n > 1` is prime iff ∀r, s ∈ ℤ:  
> if `n = r * s`, then `r = 1 ∧ s = n` or `r = n ∧ s = 1`

### Composite:
> `n` is composite iff ∃r, s ∈ ℤ with `1 < r < n` and `1 < s < n` such that `n = r * s`

---

## 🧪 Proof Examples

### Example 1: -23 is odd  
- Use the definition: `-23 = 2*(-12) + 1`, so it's odd.

---

## ✳️ Constructive vs Non-Constructive Proofs

| Type              | Description                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| Constructive      | You show an example or derive a value.                                     |
| Non-Constructive  | You assume the opposite and show contradiction or derive existence from axioms. |

---

## 🧪 Example Proofs

### 1. Even + Even = Even

**Let:**  
- `m = 2r`, `n = 2s`  
**Then:**  
- `m + n = 2r + 2s = 2(r + s) = 2t`, where `t = r + s` ∈ ℤ  
- So, `m + n` is even.

### 2. Rational + Rational = Rational

**Let:**  
- `r = a/b`, `s = c/d`, `a, b, c, d ∈ ℤ`, `b, d ≠ 0`  
**Then:**  
- `r + s = (ad + bc) / bd`  
- Let `p = ad + bc`, `q = bd` → `r + s = p/q`, with `p, q ∈ ℤ`, `q ≠ 0`  
- So, result is rational.

---
## 🧪 Nonconstructive Existential Proof Example

### Claim

From:  
1. `∃x (P(x) ∧ Q(x))`  
Prove:  
`∃x P(x) ∧ ∃x Q(x)`

---

### Why This is Valid

We are given that there **exists at least one object** for which **both** `P` and `Q` are true. From that, we want to conclude that:

- There **exists some x** for which `P(x)` is true  
- And there **exists (possibly another) x** for which `Q(x)` is true  

The two `∃x` on the right-hand side **do not need to refer to the same x**, so it's okay if they’re instantiated separately.

---

### Strategy

This is a **nonconstructive proof** because:

- We never explicitly name a concrete `x` for which `P(x)` and `Q(x)` are true separately.
- We use existential instantiation **temporarily**, and then existential generalisation again at the end.

---

### Step-by-Step Proof (Natural Deduction Style)

1. `∃x (P(x) ∧ Q(x))`  (premise)  
2. Let `a` such that `P(a) ∧ Q(a)` (Existential Instantiation)  
3. `P(a)`   (∧-Elimination)  
4. `Q(a)`   (∧-Elimination)  
5. `∃x P(x)`   (Existential Generalisation)  
6. `∃x Q(x)`   (Existential Generalisation)  
7. `∃x P(x) ∧ ∃x Q(x)` (∧-Introduction)

✔️ Q.E.D.

--- 

## ❌ Disproving a Universal Conditional

**Claim:** ∀x ∀y: `x² = y² → x = y`  
**Counterexample:**  
- `x = 1`, `y = -1` → `1² = (-1)²`, but `1 ≠ -1`  
- So, the statement is false.

---

## ⚠️ Vacuous Truths

A statement like ∀x ∈ D: P(x) → Q(x) is **vacuously true** if no `x ∈ D` satisfies P(x).

---

## 🔢 Arithmetic Concepts

### Div and Mod:
- `n div d` = quotient (integer division)
- `n mod d` = remainder  
**Example:** `23 div 6 = 3`, `23 mod 6 = 5`  
- Because `6×3 + 5 = 23`

---

## 🟣 Proof: Consecutive Integers Have Opposite Parity

**Case 1:** `n = 2k` (even) → `n+1 = 2k+1` (odd)  
**Case 2:** `n = 2k+1` (odd) → `n+1 = 2k+2 = 2(k+1)` (even)

---

## 🚫 Proof by Contradiction: No Greatest Integer

**Assume:** There exists a greatest integer `n`  
**Then:** Let `m = n + 1`, which is also an integer  
- `m > n`, contradicting `n` being the greatest  
✅ ∴ No greatest integer exists

---

## 💻 Applications in Computer Science

- Logic and proofs → Basis for **program verification**
- **Specification logic**: annotate code with logical rules
- If the logical proof of the spec is valid → the code is **correct by design**

---

## 📝 Summary

- You've now mastered the foundations: **formal logic, rules of inference, direct/indirect proofs**
- You're equipped to reason about abstract math and also to **verify real-world software**
- Keep practicing! Upcoming topics will build on these techniques

e