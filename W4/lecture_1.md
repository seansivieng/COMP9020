# COMP9020 Lecture Notes: Sequences, Logic, Summation, and Product Notation

---

## Week 4 Summary – Key Topics

---

## 1. Midterm Schedule and Flex Week
- Week 5 is the final week before midterm ("flex") week.
- "Flex week" is a break for students — no lectures or tutorials.
- Officially called "Flex Week" in the timetable.
- Staff refer to it as "Recharge Week" or other terms.
- Effectively, problem set deadlines are extended by a week.

---

## 2. Logic Refresher: Validity, Monotonicity, and Contradictions

### Validity:
- An argument is **valid** if **it is impossible** for all the premises to be true **and** the conclusion false.
- In classical logic, **validity is preserved** under additional premises.

### Monotonicity:
- Classical logic is **monotonic**:
  - If an argument is valid, adding **any new premise** (even irrelevant or contradictory) **cannot make it invalid**.

### Contradictions:
- Adding a contradiction (e.g. `P ∧ ¬P`) makes **any argument valid** (principle of explosion).
  - From a contradiction, **any conclusion** can be derived.
- In natural deduction:
  - From `P ∧ ¬P` you can derive `Q` (any formula).
  - Example: `P → P ∨ Q`, `¬P` → `Q`.

### Non-monotonic Logic:
- Other logics (especially in AI/CS) are **non-monotonic**.
- Adding premises can **invalidate** previously valid inferences.
- These are called **non-monotonic logics**.

---

## 3. Material Implication and Vacuous Truth

- `P → ¬P` is **not** a contradiction.
  - If `P` is false, then the implication is **vacuously true**.
  - Only false when `P` is true and `¬P` is false.
- Students were encouraged to:
  - Use truth tables to analyse conditionals.
  - Construct formulas logically equivalent to contradictions using implication.

---

## 4. Sequences

### Definitions:
- A **sequence** is a function:
  - Domain: `{m, m+1, ..., n}` or `{k ∈ ℤ | k ≥ m}`
- Written as: `a_m, a_{m+1}, ..., a_n`
- **Term**: `a_k`, **Index**: `k`
- Initial term: `a_m`, final term: `a_n`

### Infinite Sequences:
- Denoted with ellipsis ("...").
- May repeat values: e.g., `1, -1, 1, -1, ...`

### Explicit/General Formula:
- E.g. `a_k = k / (k + 1)`
- `a_k = (-1)^{k+1} / k^2` alternates sign

### Example:
- `1/1^2, -1/2^2, 1/3^2, ...` → `a_k = (-1)^{k+1} / k^2`

---

## 5. Summation Notation

### Format:
```
∑_{k=m}^{n} a_k = a_m + a_{m+1} + ... + a_n
```

- `k`: Index
- `m`: Lower limit
- `n`: Upper limit

### Examples:
1. `∑_{k=1}^{2} a_k = a_1 + a_2`
2. `∑_{k=4}^{5} 3a_k = 3a_4 + 3a_5`
3. `∑_{k=1}^{5} a_k^2 = a_1^2 + ... + a_5^2`

### Constructing from Expansion:
- E.g. `1/(n+1) + 2/(n+1) + ... + (n+1)/(n+1)`
- Write as: `∑_{i=0}^{n} (i + 1)/(n + 1)`

---

## 6. Suppressed Universal Quantifiers

- Universal quantifiers (`∀`) are often **omitted**.
- E.g. `∑_{i=0}^{n} a_i` implies `∀i ∈ [0, n]`
- Existential quantifiers (`∃`) are **not** typically suppressed.

---

## 7. Recursive Definition of Summation

- **Base Case**: `∑_{k=m}^{m} a_k = a_m`
- **Recursive Step**: `∑_{k=m}^{n} a_k = ∑_{k=m}^{n-1} a_k + a_n`

---

## 8. Product Notation

### Format:
```
∏_{k=m}^{n} a_k = a_m × a_{m+1} × ... × a_n
```

### Recursive Definition:
- Base Case: `∏_{k=m}^{m} a_k = a_m`
- Recursive Step: `∏_{k=m}^{n} a_k = ∏_{k=m}^{n-1} a_k × a_n`

---

## 9. Properties of Summation and Product

### Summation:
- `∑ (a_k + b_k) = ∑ a_k + ∑ b_k`
- `c × ∑ a_k = ∑ (c × a_k)`

### Product:
- `∏ (a_k × b_k) = ∏ a_k × ∏ b_k`
- `∏ (c × a_k) = c^n × ∏ a_k` (if `c` is constant)

---

## 10. Factorials and Combinatorics

### Factorial:
- `n! = n × (n-1) × ... × 1`
- `0! = 1` (by convention)

### Recursive Definition:
```
n! = {
  1 if n = 0,
  n × (n-1)! if n > 0
}
```

### Binomial Coefficients:
- `n choose r` = number of r-subsets from n-set
- Formula: `C(n, r) = n! / (r! (n - r)!)`
- Examples:
  - `C(2, 2) = 1`
  - `C(n+1, n) = n + 1`

---

## 11. Translation in Logic

- Break English statements into **atomic propositions**
- Avoid combining multiple ideas into one symbol

### Bad:
- `"Bob and Alice will pass"` → `P` (incorrect)

### Correct:
- `B = Bob passes`, `A = Alice passes`
- Then `B ∧ A → B ∧ A`

---

## 12. Formal Methods

### Goal:
- Annotate and verify code using logic
- Use languages like Dafny, theorem provers like Z3

### Why It Matters:
- Formal verification **guarantees** correctness
- Translation from code to logic is the **critical step**

---

## 13. Lecture Tips and Anecdotes

- Challenge the words *obviously* or *clearly* – they often hide poor understanding
- Focus on understanding and transformation, not just marks
- Learn to write and check proofs — you’ll be more valuable than “hackers”
- Verification skills will become more important as generative AI usage increases

---

**End of Lecture Notes**
