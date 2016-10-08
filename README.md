# Lexical_Analyzer

![dfafa16](https://cloud.githubusercontent.com/assets/16604090/19210638/78f27bf8-8cf6-11e6-8e3f-f56836dddfda.jpg)




Consider the following EBNF defining 23 token categories ⟨var⟩ through ⟨period⟩: 

⟨lowercase letter⟩ → a | b | ... | z 

⟨uppercase letter⟩ → A | B | ... | Z 

⟨letter⟩ → ⟨lowercase letter⟩ | ⟨uppercase letter⟩ 

⟨digit⟩ → 0 | 1 | ... | 9 

⟨var⟩ → ⟨uppercase letter⟩ {⟨letter⟩ | ⟨digit⟩} 

⟨functor⟩ → ⟨lowercase letter⟩ {⟨letter⟩ | ⟨digit⟩} 

⟨int⟩ → [+|−] {⟨digit⟩}+ 

⟨float⟩ → [+|−] ( {⟨digit⟩}+ "." {⟨digit⟩}  |  "." {⟨digit⟩}+  ) 

⟨floatE⟩ → ⟨float⟩ (e|E) [+|−] {⟨digit⟩}+ 

⟨if⟩ → ":−" 

⟨add⟩ → + 

⟨sub⟩ → − 

⟨mul⟩ → * 

⟨div⟩ → / 

⟨lt⟩ → "<" 

⟨le⟩ → "=<" 

⟨gt⟩ → ">" 

⟨ge⟩ → ">=" 

⟨eq⟩ → "=" 

⟨neq⟩ → "\=" 

⟨LParen⟩ → "(" 

⟨RParen⟩ → ")" 

⟨LBracket⟩ → "[" 

⟨RBracket⟩ → "]" 

⟨bar⟩ → "|" 

⟨comma⟩ → "," 

⟨period⟩ → "." 



The objective of this project is to implement a lexical analyzer that accepts the token categories plus one keyword, is, in lowercase letters only. This keyword cannot be used as ⟨var⟩ or ⟨functor⟩, but can be a part of them, like "isa", "Xis", "ABiscs". In this and the next project, we assume that ⟨var⟩, ⟨functor⟩, and the keyword "is" are case-sensitive. The implementation should be based on the above DFA. Your lexical analyzer program should clearly separate the driver and the state-transition function so that the driver will remain invariant and only state-transition functions will change from DFA to DFA. The enumerated or integer type is suggested for representation of states. 

The following keyword recognition method is adequate for this project.
      
      1. Create an additional DFA state for "is".
      
      2. The DFA initially accepts "is" as ⟨functor⟩.
      
      3. Each time the DFA accepts a string in ⟨functor⟩, check if it is "is", and if so, move the DFA to the state for "is".
