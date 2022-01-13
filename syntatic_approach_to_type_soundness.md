# A Syntactic Approach to Type Soundness
(Andrew K. Wright, Matthias Felleisen, 1994)

## Contents & Study Plan

1. Type Soundness (2.5)  
2. Previous Approaches to Proving Type Soundness (1) ----------- // 3.5 (1/13)  
  2-1. Proofs Based on Denotational Semantics (3)  
  2-2. Proofs Based on Structural Operational Semantics (1.5)  
  2-3. Discussion (0.5) ---------------------------------------- // 5 (1/14)  
3. Syntatic Approach to Proving Type Soundness (1.5)  
  3-1. Related Work (0.25)  
  3-2. Road Map (0.25)  
4. Functional ML (0.5)  
  4-1. Semantics (1.5)  
  4-2. Typing (3) ---------------------------------------------- // 4 (1/17)  
  4-3. Type Soundness (7.5) ------------------------------------ // 7.5 (1/18)  
5. References and Exceptions (0.5)  
  5-1. Refernce ML (1)  
    5-1-1. Semantics (2)  
    5-1-2. Typing (2.5) ---------------------------------------- // 5.5 (1/19)  
    5-1-3. Type Soundness for References (6.5) ----------------- // 6.5 (1/20)  
  5-2. Exception ML (1)  
    5-2-1. Semantics (2)  
    5-2-2. Typing (1)  
    5-2-3. Type References for Exceptions (2) ------------------ // 6 (1/21)  
  5-3. Core ML (0)  
    5-3-1. Semantics (0.9)  
    5-3-2. Typing (0.1)  
    5-3-3. Type Soundness dor Core ML (0.8)  
6. Control ML (0.2)  
  6-1. Semantics (1)  
  6-2. Typing (1) --------------------------------------------- // 4 (1/24)  
  6-3. Weak Type Soundness (2.5)  
  6-4. Strong Type Soundness (2.5)  
7. Discussion (1) --------------------------------------------- // 6 (1/25)  
  
## Daily Report

20220112 Wed.  
(1. ~ before 2-1.)  
  
1. Type Soundness
- Static type systems : to prevent type error during execution
  - sound (strongly-typed) if well typped programs cannot cause type error
- Easy to design sound type system for 'monomorphic' language
- But, with 'polymorphism' and 'type inference' is delicate
- Further, the 'incorporation of imperative features (such as references and exceeptions)' more hard
- Therfore, a formal proof of soundness is required!
  
- View: static type system = a filter that selects well-typed programs from a larger universe of untyped programs
  - eval : Programs -> Answers or {Wrong}
    - defines semantics of untyped programs
    - |> e : tau
    - the well-typed programs do not yield Wrong(type error)
  - Weak Soundness: prevents type errors
  - Strong Soundness: answer provied by the program (e) has the type tau

- Existing proof for HIndly/Milner-style type system has limitations:
  - sensitive to formulation of semantics (denotational vs. operational)
  - hard with two different languages
  - complicated, lengthy, error-prone

- We present a simple approach to the proof of soundness for HIndley/Milner-sytle polymorphic type systems
  - based on subject reduction
  - for demonstrations, developed ...
