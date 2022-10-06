# Textbook Link

http://www.djnutte.com/pdf/Fall%202020%20Concepts%20of%20Programming%20Languages%2012th%20Edition%20.pdf

# What is a language?

## Syntax

Describe what a program **looks** like. 

Specified using **regular expressions** and **context-free grammars**

## Semantics

Describes what a program **means**.

Specified using *axiomatic, operational or denotational* semantics.

## Regular Expressions

A unified representation for a set of strings. Constructed with
- `a` A character
- `ε` The empty string denoted
- `.` Concatenation 
  - a.B => aB
- `|` "Or" 
  - A|B => "A", "B"
- `*` Kleene star (zero or more)
  - B* => "", "B", "BB", "BBB", ....
- `+` one or more
  - c+ => "c", "cc", "ccc", ...
- `[]` selects any char
  - [abc] => "a", "b", "c"
- `[]+` subcomoment with 1 or more instance
  - [ab]+ => "a", "b", "aa", "ab", "aba", "ba", ...
- `-` defines a range
  - [0-9] digits
  - [A-Z] uppercase letters

## Lexeme, Token, & Pattern

**Lexeme:** 

A sequence of characters in the source program with the lowest level of syntactic meanings.

**Token:** 

- A category of lexemes
- A lexeme is an instace of a token
- Basic building blocks of programs

**Examples**

Token | Lexeme Example
--- | ---
keyword | `if else`
comparison | `<=, !=, ==`
number | `0`
id | `pi, score d2`

**Pattern:**

- Description of the form of lexemes
- Specified with regular expressions
- Pattern for identifies is `letter(letter|digit|_)*`
  
## Context Free Grammar

Uses **BNF** notation
- **Terminals:** basic symbols which form strings
- **Non-Terminals:** syntaxtic variables to impose the structure
  - Ex: <exp>, <stmt>
- **Start-Symbol:** a *non-terminal* you always start with
- **Production:** Rules for how to replace non-terminals
  - Ex: <if_stmt> -> if <expr> then <stmt> | if <expr> then <stmt> else <stmt>
  
- **Derivation:** Repeatedly applying rules to nonterminals gives us a string only terminals.
- **Sentence:** A string with only terminals
- **Sentinal Form:** A string with terminals and non-terminals
- **Left recursion:** Recursion occurs on the left
  - Ex: E -> E + T | T
- **Right recursion:** Recursion occurs on the right
  - Ex: E -> T | T + E
- **Leftmost derivation:** Derivation using the left-most non-terminal.
  - Creates a *left-sentinal form*
- **Rightmost derivation:** Derivation using the right-most non-terminal.
  - Creates a *right-sentintal form*
- *Note* some derivations are neither left not right
- 