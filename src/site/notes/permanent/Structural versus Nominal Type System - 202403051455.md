---
{"dg-publish":true,"permalink":"/permanent/structural-versus-nominal-type-system-202403051455/","tags":["📖"],"created":"2024-03-05T14:54:35.157-06:00","updated":"2024-03-05T16:01:18.648-06:00"}
---

# Structural versus Nominal Type System

From ChatGPT:

The terms "structural type system" and "nominal type system" refer to different approaches used in programming languages to determine type compatibility and relationships between types.

1. **Nominal Type System:**
    
    - In a nominal type system, types are explicitly declared and identified by their names or labels.
    - Type compatibility is determined based on the names or labels of the types, regardless of their structure or content.
    - Types with different names, even if their structures are identical, are considered distinct and incompatible.
    - Examples of languages with nominal type systems include Java and C#. In these languages, explicit type declarations are required, and types are compared based on their declared names.
2. **Structural Type System:**
    
    - In a structural type system, types are based on their actual structure or shape, rather than explicit names or labels.
    - Types are considered compatible if they have the same structure, regardless of whether they are explicitly declared as the same type.
    - Types with different names but the same structure are treated as compatible in a structural type system.
    - Languages like TypeScript and OCaml incorporate structural typing, allowing for more flexibility and code reuse based on the structure of types.

## References

1. **[[Benjamin C. Pierce\|Benjamin C. Pierce]]:** ["Types and Programming Languages"](https://www.amazon.com/Types-Programming-Languages-MIT-Press/dp/0262162091) 
   - This is a comprehensive and widely used book that covers the theory and practice of type systems in programming languages. It's suitable for both beginners and those with more advanced knowledge.

2. **[[Michael L. Scott\|Michael L. Scott]]:** ["Programming Language Pragmatics"](https://www.elsevier.com/books/programming-language-pragmatics/scott/978-0-12-410409-9)
   - This book provides a broad overview of programming languages, including discussions on type systems and their role in language design. It covers both theoretical concepts and practical considerations.

3. **[[David A. Schmidt\|David A. Schmidt]]:** ["Types and Programming Constructs"](https://www.amazon.com/Programming-Constructs-Essential-Computers-David/dp/0471430690)
   - Schmidt's book is focused on the role of types in programming languages and how they influence the design and implementation of software. It covers both traditional and modern type systems.

4. **[[Robert Harper\|Robert Harper]]:** ["Practical Foundations for Programming Languages"](https://www.cs.cmu.edu/~rwh/plbook/)
   - Harper's book delves into the theoretical foundations of programming languages, including type systems. It's a more advanced text that explores topics such as formal semantics and type theory.

5. **[[Luca Cardelli\|Luca Cardelli]]:** ["Types in Programming Languages"](https://lucacardelli.name/Papers/TypesAndProgrammingLanguages.pdf)
   - This classic paper by Luca Cardelli provides a foundational overview of types in programming languages. It's a good starting point for understanding the fundamental concepts.

6. **[[Benjamin C. Pierce\|Benjamin C. Pierce]]:** ["Advanced Topics in Types and Programming Languages"](https://www.amazon.com/Advanced-Topics-Types-Programming-Languages/dp/0262162288)
   - This collection of essays explores advanced topics related to types and programming languages. It's a sequel to Pierce's "Types and Programming Languages" and provides deeper insights into various aspects of type systems.

7. **[[Dan Grossman\|Dan Grossman]]:** [Online Resources: Stanford University course "Programming Languages"](https://www.youtube.com/playlist?list=PLTpr42JPvMvr6P2wbGW9WNGGQF5uKRJL)
   - This Stanford University course covers type systems and programming languages. You can find lecture videos and materials on platforms like YouTube or the course's official website.