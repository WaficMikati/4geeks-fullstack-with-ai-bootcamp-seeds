# Course Outline: JavaScript and TypeScript Fundamentals

**Title:** JavaScript and TypeScript Fundamentals
**Prerequisite:** Week 2 Day 6 - Programming Flow Mastery (pseudocode and algorithmic thinking)
**Target Audience:** Beginner developers who understand programming concepts in pseudocode and are ready to write actual code in TypeScript
**Total Lessons:** 25
**Estimated Total Length:** ~12,500 words
**Format:** Practical (44% hands-on)

---

## Course Description

This course bridges the gap between algorithmic thinking and actual code writing. Students have already learned programming fundamentals through pseudocode and flow diagrams on Day 6. Now they'll learn to express those same concepts in TypeScript—a powerful, type-safe language that builds on JavaScript.

Students will discover what JavaScript is and why TypeScript enhances it with type safety. They'll learn TypeScript's syntax rules, how to declare typed variables, work with primitive data types, and implement the control structures (conditionals and loops) they've already designed algorithmically. By the end, students will write complete TypeScript programs that solve real problems.

This course emphasizes hands-on practice: translating pseudocode into working TypeScript, using console.log() for debugging, following naming conventions, and avoiding common beginner anti-patterns like "magic code" and infinite loops.

---

## Course Philosophy

This course emphasizes:
- **Bridging concepts to code**: Applying algorithmic thinking learned on Day 6 to TypeScript syntax
- **Type safety from day one**: Understanding how TypeScript prevents errors through type checking
- **Write code, don't copy it**: Building muscle memory through manual coding practice
- **Debugging mindset**: Using console.log() as a primary debugging tool
- **Clean code habits**: const-first approach, semantic naming, strict equality, proper indentation
- **Learning to research**: Understanding that memorization isn't the goal—knowing how to find answers is

---

## Course Statistics Summary

| Section | Lessons | Estimated Words |
|---------|---------|----------------|
| 00 - Welcome to Formal Programming | 1 | ~450 |
| 01 - JavaScript and TypeScript Essentials | 3 | ~1,600 |
| 02 - Writing Your First TypeScript Code | 4 | ~2,100 |
| 03 - Variables and Type Annotations | 4 | ~2,100 |
| 04 - TypeScript Data Types and Operators | 5 | ~2,600 |
| 05 - Conditionals in TypeScript | 4 | ~2,100 |
| 06 - Loops and Iteration in TypeScript | 5 | ~2,600 |
| 07 - Mastery and Next Steps | 2 | ~1,100 |
| 08 - Your Programming Foundation | 1 | ~450 |
| **Total** | **25** | **~12,500** |

---

## Section 00: Welcome to Formal Programming

### 00.0 From Algorithms to Code: Your TypeScript Journey Begins 📖 (450 words)

**Learning Objectives:**
- Understand the transition from pseudocode to actual programming languages
- Recognize what you already know from Day 6 and what's new in this course
- Identify why TypeScript is the chosen language for learning
- Set expectations for hands-on coding practice

**Content Outline:**
- Welcome to the world of real code
- What you already know: algorithms, variables, conditionals, loops from Day 6
- What's new: translating those concepts into TypeScript syntax
- Why TypeScript over plain JavaScript
- Course structure overview: learning syntax, types, and writing actual programs
- The importance of typing code yourself (not copying)

**Transitions:**
This lesson sets the stage for understanding JavaScript and TypeScript in the next section.

**Key Principles:**
- Programming concepts you learned are language-agnostic
- Syntax is just the "grammar" for expressing algorithms
- TypeScript adds safety through type checking
- Practice builds skill faster than memorization

**Examples:**
- Pseudocode "IF age > 18" becomes TypeScript `if (age > 18)`
- Flow diagram loops become `for` and `while` loops in code
- Variables in memory diagrams become `const` and `let` declarations

---

## Section 01: JavaScript and TypeScript Essentials

### 01.0 What is JavaScript? The Language of the Web 📖 (500 words)

**Learning Objectives:**
- Define JavaScript and understand its role in web development
- Identify where JavaScript runs (browsers, servers)
- Recognize JavaScript's importance in modern web applications
- Understand JavaScript's relationship to the web ecosystem

**Content Outline:**
- JavaScript's origin and purpose: bringing interactivity to web pages
- Where JavaScript runs: browsers (client-side) and Node.js (server-side)
- JavaScript's role in the modern web: frontend, backend, full-stack
- JavaScript vs. other programming languages
- Why JavaScript is fundamental for web developers
- JavaScript's popularity and ecosystem

**Transitions:**
Understanding JavaScript sets the foundation for learning TypeScript, which builds directly on top of JavaScript.

**Key Principles:**
- JavaScript is the programming language of the web
- It's versatile: works on both client and server
- Understanding JavaScript is essential for web development
- Learning JavaScript fundamentals applies to many frameworks

**Examples:**
- Form validation in a web page (JavaScript in action)
- Interactive buttons that respond to clicks
- Dynamic content updates without page reloads
- Real-world sites built with JavaScript (Gmail, Facebook, Netflix)

---

### 01.1 What is TypeScript and Why Use It? 📖 (550 words)

**Learning Objectives:**
- Define TypeScript and its relationship to JavaScript
- Understand the key differences between JS and TS
- Recognize the benefits TypeScript provides (type safety)
- Identify when and why developers choose TypeScript

**Content Outline:**
- What is TypeScript? A superset of JavaScript
- The relationship between JavaScript and TypeScript (JS vs TS)
- Key difference: TypeScript adds static typing to JavaScript
- Benefits of TypeScript: catching errors before runtime
- TypeScript's growing adoption in the industry
- TypeScript vs. JavaScript: when to use each
- Why 4Geeks teaches TypeScript first

**Transitions:**
Now that we know what TypeScript is and why it's valuable, let's explore how it actually works under the hood.

**Key Principles:**
- TypeScript = JavaScript + Types
- All valid JavaScript is valid TypeScript
- TypeScript catches errors during development, not at runtime
- Type safety makes code more maintainable and reliable
- TypeScript compiles to JavaScript

**Examples:**
- JavaScript: `let age = 25` vs. TypeScript: `let age: number = 25`
- Catching type errors: trying to add a string to a number
- Real companies using TypeScript: Microsoft, Google, Airbnb
- How TypeScript prevents common JavaScript bugs

---

### 01.2 How TypeScript Works: Compilation and Type Checking 📖 (550 words)

**Learning Objectives:**
- Understand the TypeScript compilation process
- Recognize the role of the TypeScript compiler (tsc)
- Identify the difference between compile-time and runtime
- Understand how TypeScript code becomes JavaScript

**Content Outline:**
- How TypeScript works: the compilation process
- TypeScript compiler (tsc): converting TS to JS
- Type checking: validating types before running code
- Compile-time vs. runtime: when errors are caught
- The TypeScript development workflow
- What happens when code has type errors
- TypeScript configuration basics (tsconfig.json overview)

**Transitions:**
Understanding how TypeScript works prepares us to write our first TypeScript code with proper syntax.

**Key Principles:**
- TypeScript code doesn't run directly—it compiles to JavaScript first
- The compiler checks types and catches errors early
- Type errors prevent compilation
- Once compiled, TypeScript becomes standard JavaScript
- Development happens in .ts files, execution uses .js files

**Examples:**
- Write code.ts → Compiler checks types → Generates code.js → Browser runs code.js
- Type error example: assigning string to number variable
- Successful compilation with no errors
- Running TypeScript in development environment

---

## Section 02: Writing Your First TypeScript Code

### 02.0 Understanding Syntax: The Grammar of TypeScript 📖 (500 words)

**Learning Objectives:**
- Define what syntax means in programming
- Understand that syntax is language-specific grammar
- Recognize basic TypeScript syntax elements
- Identify common syntax rules across programming languages

**Content Outline:**
- What is syntax? The grammar rules of programming languages
- Why syntax matters: computers need precise instructions
- TypeScript syntax basics: statements, expressions, blocks
- Common syntax elements: semicolons, brackets, indentation
- Syntax vs. logic: grammar vs. meaning
- Reading TypeScript syntax: how to parse code visually
- The learning curve: syntax becomes natural with practice

**Transitions:**
Now that we understand what syntax is conceptually, let's dive into TypeScript's specific rules and structure.

**Key Principles:**
- Syntax is the "how to write" rules of a language
- Every programming language has its own syntax
- Syntax errors prevent code from compiling/running
- Consistent syntax makes code readable
- You'll learn syntax through practice, not memorization

**Examples:**
- English grammar vs. programming syntax
- Valid syntax: `let x: number = 5;`
- Invalid syntax: `let x number = 5` (missing colon)
- Different syntax, same meaning: `let x=5` vs. `let x = 5` (spacing)

---

### 02.1 TypeScript's Essential Rules and Structure 💻 (600 words)

**Learning Objectives:**
- Write valid TypeScript statements following syntax rules
- Apply proper semicolon usage in TypeScript
- Use correct indentation and code formatting
- Declare variables and statements with proper syntax

**Content Outline:**
- Essential TypeScript syntax rules
- Statements and semicolons: when and why to use them
- Blocks and curly braces: grouping code
- Indentation and whitespace: making code readable
- Comments: single-line (//) and multi-line (/* */)
- Case sensitivity: why `Variable` ≠ `variable`
- One statement per line: writing clean code
- Common syntax errors and how to fix them

**Hands-On Exercise:**
Write a simple TypeScript file with:
- Variable declarations with proper syntax
- Comments explaining each line
- Proper indentation and semicolons
- Correct use of blocks (even empty ones for practice)

**Code Examples:**
```typescript
// Valid TypeScript syntax
let message: string = "Hello";
let count: number = 10;

// Proper block structure
if (count > 5) {
    console.log(message);
}
```

**Success Criteria:**
- Code compiles without syntax errors
- Proper indentation throughout
- Semicolons used consistently
- Comments are clear and helpful

**Transitions:**
With syntax rules mastered, let's explore one of the most important debugging tools: console.log().

**Key Principles:**
- Consistency in syntax improves readability
- Indentation shows code structure
- Semicolons mark statement endings
- Comments explain "why", not "what"

---

### 02.2 Your Debugging Tool: console.log() 💻 (550 words)

**Learning Objectives:**
- Understand the purpose and importance of console.log()
- Use console.log() to display values and debug code
- Format console output with tagged logging
- Apply console.log() strategically in troubleshooting

**Content Outline:**
- What is console.log()? Your window into program execution
- Why console.log() is essential for debugging
- Basic usage: printing values to the console
- Tagged logging: console.log("Label:", value)
- Printing multiple values at once
- Logging variables at different execution points
- Using console.log() to verify logic flow
- Console.log() best practices for debugging

**Hands-On Exercise:**
Create a TypeScript program that:
- Declares several variables of different types
- Uses console.log() to print each variable with labels
- Performs calculations and logs intermediate results
- Traces program flow with strategic logging

**Code Examples:**
```typescript
let age: number = 25;
let name: string = "Maria";

// Tagged logging
console.log("User name:", name);
console.log("User age:", age);

// Multiple values
console.log("Name and age:", name, age);

// Debugging calculation
let result: number = age * 2;
console.log("Double age:", result);
```

**Success Criteria:**
- All console.log() statements execute correctly
- Output is labeled clearly
- Can trace variable values through program execution
- Understands when and why to add logging

**Transitions:**
Now let's combine our syntax knowledge and debugging tool to set up and run a complete TypeScript program.

**Key Principles:**
- console.log() is your best friend in debugging
- Always label your output for clarity
- Log at key points to verify program state
- Remove or comment out excessive logging before deployment
- Use console.log() to test assumptions about code

---

### 02.3 Setting Up Your First TypeScript Program 💻 (650 words)

**Learning Objectives:**
- Create a complete TypeScript file from scratch
- Compile TypeScript code successfully
- Run the compiled JavaScript output
- Troubleshoot basic compilation errors

**Content Outline:**
- Creating a TypeScript file (.ts extension)
- Writing a simple "Hello World" program
- Compiling with the TypeScript compiler (tsc)
- Understanding compiler output and errors
- Running the compiled JavaScript code
- The development cycle: write → compile → run → debug
- Setting up your development environment
- Common setup issues and solutions

**Hands-On Exercise:**
Step-by-step program creation:
1. Create a file called `first-program.ts`
2. Write a program that declares variables and uses console.log()
3. Compile the TypeScript file
4. Run the resulting JavaScript file
5. Modify and recompile to see the cycle

**Code Examples:**
```typescript
// first-program.ts
let greeting: string = "Hello, TypeScript!";
let year: number = 2024;
let isLearning: boolean = true;

console.log(greeting);
console.log("Year:", year);
console.log("Am I learning?", isLearning);
```

**Practice Scenario:**
Create a program that:
- Declares your name, age, and favorite programming language as typed variables
- Uses console.log() to display a personal introduction
- Compiles without errors
- Runs successfully

**Success Criteria:**
- TypeScript file created with .ts extension
- Code compiles without syntax errors
- Generated JavaScript file runs correctly
- Can repeat write-compile-run cycle independently

**Transitions:**
With our development environment working, we're ready to dive deep into TypeScript's first major concept: variables with type annotations.

**Key Principles:**
- Development is iterative: write, compile, test, refine
- Compilation errors must be fixed before running
- TypeScript (.ts) compiles to JavaScript (.js)
- Each file is a separate program unit
- Practice this cycle until it becomes automatic

---

## Section 03: Variables and Type Annotations

### 03.0 Variables in TypeScript: const, let, and var 📖 (500 words)

**Learning Objectives:**
- Understand the three variable declaration keywords in TypeScript
- Recognize the differences between const, let, and var
- Choose the appropriate keyword for different scenarios
- Apply the "const-first" best practice

**Content Outline:**
- Variable declarations: const, let, and var
- const: for values that won't change (constants)
- let: for values that will be reassigned
- var: the old way (why we avoid it)
- Scope differences between const/let and var
- Block scope vs. function scope (conceptual overview)
- The "const-first" pattern: use const by default
- When to use each keyword: decision framework

**Transitions:**
Understanding variable keywords prepares us for adding type annotations to our declarations.

**Key Principles:**
- const is your default choice—immutability prevents bugs
- Use let only when you need to reassign
- Avoid var in modern TypeScript—it has confusing scope rules
- const doesn't mean the value can't change (for objects/arrays)
- Clear variable declarations make code more predictable

**Examples:**
```typescript
// const: value won't change
const pi: number = 3.14159;

// let: value will be reassigned
let counter: number = 0;
counter = counter + 1;

// var: avoid in TypeScript
var oldStyle: number = 5; // Don't do this
```

---

### 03.1 Declaring Variables with Type Annotations 💻 (600 words)

**Learning Objectives:**
- Write variable declarations with explicit type annotations
- Understand the syntax: `variable: type = value`
- Declare variables for all primitive types
- Practice proper type annotation syntax

**Content Outline:**
- Type annotation syntax: name: type = value
- Declaring typed numbers
- Declaring typed strings
- Declaring typed booleans
- Other primitive types: symbol, null, undefined (brief introduction)
- Reading type annotations: understanding the colon syntax
- Why explicit types help catch errors
- Practice with multiple variable declarations

**Hands-On Exercise:**
Create a TypeScript program that declares:
- Personal information variables (name, age, student status)
- Each with explicit type annotations
- Use appropriate const/let for each
- Log all variables with console.log()

**Code Examples:**
```typescript
// Type annotations for primitives
const name: string = "Carlos";
const age: number = 28;
const isStudent: boolean = true;
const favoriteNumber: number = 42;

// Multiple declarations
let score: number = 0;
let level: string = "beginner";

console.log("Name:", name);
console.log("Age:", age);
```

**Success Criteria:**
- All variables have correct type annotations
- Appropriate use of const vs. let
- No type errors during compilation
- Clear, semantic variable names

**Transitions:**
While explicit type annotations are valuable, TypeScript can often infer types automatically. Let's explore how this works.

**Key Principles:**
- The colon (:) separates name from type
- Type comes before the assignment (=)
- Explicit types make code self-documenting
- Type annotations catch mistakes at compile time
- Consistent formatting improves readability

---

### 03.2 Type Inference: When TypeScript Knows Your Types 📖 (500 words)

**Learning Objectives:**
- Understand how TypeScript infers types automatically
- Recognize when type annotations can be omitted
- Choose between explicit annotations and inference
- Understand inference limitations and best practices

**Content Outline:**
- What is type inference? TypeScript's automatic type detection
- How inference works: analyzing initial values
- When types can be inferred safely
- When explicit annotations are better
- Inference with const vs. let
- Type inference for literal values
- Best practice: when to annotate explicitly
- Balancing inference with code clarity

**Transitions:**
Understanding inference helps us write cleaner code. Now let's explore best practices for variable naming and declaration.

**Key Principles:**
- TypeScript infers types from initial values
- Inference reduces redundant type annotations
- Explicit types document intent even when inference works
- For beginners, explicit types aid learning
- As you gain experience, you'll use more inference

**Examples:**
```typescript
// Explicit annotation
const age: number = 25;

// Type inference (TypeScript knows it's a number)
const age = 25;

// Both create the same typed variable
// TypeScript infers: const age: number
```

---

### 03.3 Best Practices: const-First and Semantic Naming 💻 (600 words)

**Learning Objectives:**
- Apply the const-first pattern in variable declarations
- Write semantic, descriptive variable names
- Follow lowerCamelCase naming convention
- Recognize and avoid poor naming anti-patterns

**Content Outline:**
- The const-first pattern: default to const, use let only when needed
- Semantic naming: names should reveal purpose
- lowerCamelCase convention in TypeScript
- Avoiding single-letter variables (except loop counters)
- Meaningful names vs. abbreviated names
- Constants vs. magic numbers: named values
- Variable naming anti-patterns to avoid
- Refactoring poor variable names

**Hands-On Exercise:**
Review and refactor code with poor variable names:
- Rename variables to be more semantic
- Convert let to const where possible
- Apply lowerCamelCase consistently
- Replace magic numbers with named constants

**Code Examples:**
```typescript
// Bad naming
let x = 25;
let n = "John";

// Good naming (semantic)
const userAge = 25;
const userName = "John";

// const-first pattern
const maxScore = 100; // Won't change
let currentScore = 0; // Will increase

// Named constant vs. magic number
const TAX_RATE = 0.16; // Clear meaning
let total = price * TAX_RATE; // Readable
```

**Practice Scenario:**
Create a program simulating a game character:
- Declare constants for character attributes that don't change
- Use let for attributes that will change (health, score)
- Name all variables semantically
- Apply const-first pattern throughout

**Success Criteria:**
- All variables follow lowerCamelCase
- Names clearly indicate purpose
- const used where values won't change
- No single-letter or cryptic names
- Code is self-documenting through naming

**Transitions:**
With strong variable fundamentals, we're ready to explore the type system in depth, starting with primitive data types.

**Key Principles:**
- const by default prevents accidental reassignment
- Good names eliminate the need for comments
- Consistency in naming improves code readability
- Semantic names make code self-documenting
- Refactoring names early prevents technical debt

---

## Section 04: TypeScript Data Types and Operators

### 04.0 Primitive Types: number, boolean, string, symbol, null, undefined 📖 (550 words)

**Learning Objectives:**
- Identify all primitive data types in TypeScript
- Understand the purpose and use cases for each type
- Recognize type-specific operations and limitations
- Distinguish between similar but different types

**Content Outline:**
- Overview of TypeScript's primitive types
- number: integers and decimals, no separate types
- boolean: true/false values for logical operations
- string: text data, using quotes
- symbol: unique identifiers (brief introduction)
- null: intentional absence of value
- undefined: uninitialized or missing value
- Differences between null and undefined
- Type identification: recognizing types by their values
- When to use each type

**Transitions:**
Understanding these types sets the foundation for working with them in practice. Let's apply what we've learned.

**Key Principles:**
- Each type serves a specific purpose
- TypeScript enforces type boundaries strictly
- Primitive types are the building blocks for complex data
- Understanding types prevents runtime errors
- null and undefined are different concepts

**Examples:**
```typescript
// Primitive type examples
const count: number = 42;
const price: number = 19.99;
const isActive: boolean = true;
const userName: string = "Alice";
const uniqueId: symbol = Symbol("id");
const emptyValue: null = null;
const notAssigned: undefined = undefined;
```

---

### 04.1 Working with Typed Variables 💻 (650 words)

**Learning Objectives:**
- Declare and initialize variables for each primitive type
- Perform type-appropriate operations on variables
- Recognize type errors and understand why they occur
- Practice working with numbers, strings, and booleans

**Content Outline:**
- Declaring variables for each primitive type
- Working with numbers: arithmetic operations
- Working with strings: concatenation and methods
- Working with booleans: logical contexts
- Type compatibility: what operations work with which types
- Common type errors: mixing incompatible types
- Type coercion vs. type safety
- String interpolation with template literals (brief mention)

**Hands-On Exercise:**
Create a program that uses all primitive types:
- Declare number variables and perform math operations
- Create string variables and combine them
- Use boolean variables in logical expressions
- Log all results with console.log()
- Intentionally create a type error to see compiler feedback

**Code Examples:**
```typescript
// Working with numbers
const quantity: number = 10;
const price: number = 25.50;
const total: number = quantity * price;
console.log("Total:", total);

// Working with strings
const firstName: string = "Ana";
const lastName: string = "García";
const fullName: string = firstName + " " + lastName;
console.log("Full name:", fullName);

// Working with booleans
const hasDiscount: boolean = true;
const isStudent: boolean = false;
console.log("Eligible:", hasDiscount);
```

**Practice Scenario:**
Build a simple product calculator:
- Product name (string)
- Price per unit (number)
- Quantity (number)
- In stock status (boolean)
- Calculate total price
- Display all information

**Success Criteria:**
- Correct type annotations for all variables
- Appropriate operations for each type
- No type mismatches or errors
- Clear output showing all calculations

**Transitions:**
Now that we can work with typed data, let's explore how to manipulate and transform these values using operators.

**Key Principles:**
- Types determine what operations are valid
- TypeScript prevents invalid type mixing
- Each type has specific methods and capabilities
- Type safety catches errors at compile time
- Understanding types makes debugging easier

---

### 04.2 Operators in TypeScript: Arithmetic and Assignment 📖 (500 words)

**Learning Objectives:**
- Understand and use arithmetic operators (+, -, *, /, %)
- Apply assignment operators (=, +=, -=, *=, /=)
- Recognize operator precedence and evaluation order
- Use operators correctly with typed variables

**Content Outline:**
- Arithmetic operators: addition, subtraction, multiplication, division
- The modulo operator (%) for remainders
- Assignment operator (=): storing values
- Compound assignment operators: +=, -=, *=, /=, %=
- Operator precedence: order of operations
- Using parentheses to control evaluation
- Operators with numbers: expected behavior
- Common operator mistakes and how to avoid them

**Transitions:**
Arithmetic and assignment handle calculations. Next, we'll explore operators for comparing values and making decisions.

**Key Principles:**
- Operators transform and manipulate values
- Operator precedence follows mathematical rules
- Compound operators are shortcuts for common patterns
- Clear expressions are better than complex one-liners
- Parentheses clarify intent and override precedence

**Examples:**
```typescript
// Arithmetic operators
let sum = 10 + 5;        // 15
let difference = 10 - 5;  // 5
let product = 10 * 5;     // 50
let quotient = 10 / 5;    // 2
let remainder = 10 % 3;   // 1

// Assignment operators
let score = 100;
score += 10;  // score = score + 10
score -= 5;   // score = score - 5
score *= 2;   // score = score * 2

// Precedence
let result = 2 + 3 * 4;  // 14, not 20
let clarified = (2 + 3) * 4;  // 20
```

---

### 04.3 Comparison and Logical Operators 💻 (650 words)

**Learning Objectives:**
- Use comparison operators (===, !==, <, >, <=, >=) correctly
- Apply logical operators (&&, ||, !) in expressions
- Understand strict equality vs. loose equality
- Build complex boolean expressions

**Content Outline:**
- Comparison operators: testing relationships between values
- Strict equality (===) vs. loose equality (==): always use ===
- Inequality operator (!==): not equal
- Relational operators: <, >, <=, >=
- Logical AND (&&): both conditions true
- Logical OR (||): at least one condition true
- Logical NOT (!): reversing boolean values
- Combining logical operators: compound conditions
- Short-circuit evaluation in logical operations

**Hands-On Exercise:**
Create a program that:
- Declares number and boolean variables
- Uses comparison operators to test relationships
- Combines conditions with logical operators
- Logs boolean results with labeled output
- Demonstrates strict equality importance

**Code Examples:**
```typescript
// Comparison operators
const age: number = 18;
const isAdult: boolean = age >= 18;
console.log("Is adult:", isAdult); // true

const score1: number = 85;
const score2: number = 90;
const sameScore: boolean = score1 === score2;
console.log("Same score:", sameScore); // false

// Logical operators
const hasLicense: boolean = true;
const hasInsurance: boolean = true;
const canDrive: boolean = hasLicense && hasInsurance;
console.log("Can drive:", canDrive); // true

const isWeekend: boolean = false;
const isHoliday: boolean = true;
const isDayOff: boolean = isWeekend || isHoliday;
console.log("Day off:", isDayOff); // true

// Strict equality pattern
const num: number = 5;
const text: string = "5";
console.log(num === 5);     // true
console.log(num === text);  // false (different types)
```

**Practice Scenario:**
Build an eligibility checker:
- Age requirement (>= 18)
- Valid ID status (boolean)
- Background check status (boolean)
- Determine eligibility using logical operators
- Test various combinations

**Success Criteria:**
- Correct use of strict equality (===)
- Proper logical operator combinations
- Clear boolean expressions
- No type mismatches in comparisons
- Accurate results for all test cases

**Transitions:**
We've covered the fundamental operators, but beginners often fall into common traps. Let's examine anti-patterns to avoid.

**Key Principles:**
- Always use === instead of == in TypeScript
- Logical operators enable complex decision-making
- Boolean expressions should be readable
- Parentheses clarify complex conditions
- Short-circuit evaluation can optimize code

---

### 04.4 Variable Anti-Patterns: Magic Code and Syntax Obsession 📖 (500 words)

**Learning Objectives:**
- Recognize common variable and operator anti-patterns
- Understand why these patterns cause problems
- Identify magic code and syntax obsession in practice
- Apply corrections to anti-pattern examples

**Content Outline:**
- Anti-pattern: Using "magic code" (copy-paste without understanding)
- Why magic code fails: lack of comprehension
- Anti-pattern: Syntax obsession (perfect syntax over logic)
- Why syntax obsession misses the point: logic comes first
- Anti-pattern: Inconsistent syntax and naming
- Anti-pattern: Using loose equality (==) instead of strict (===)
- Anti-pattern: Single-letter variable names without context
- Anti-pattern: Ignoring type errors and hoping they'll work
- How to recover from these anti-patterns

**Transitions:**
Having identified what not to do with variables and operators, we're ready to use them in real control structures: conditionals.

**Key Principles:**
- Understanding beats memorization
- Logic should drive syntax, not the reverse
- Consistency prevents confusion
- Type safety exists for your benefit
- Copy-paste creates technical debt

**Examples:**
```typescript
// Anti-pattern: Magic code
// Copied code without understanding
let x = y * z / (a + b) - c;  // What does this even calculate?

// Better: Semantic naming
const taxAmount = subtotal * TAX_RATE;
const totalPrice = subtotal + taxAmount;

// Anti-pattern: Syntax obsession
// Spending hours on semicolon placement
// Instead of solving the actual problem

// Better: Focus on logic first
// Write working code, refine syntax after

// Anti-pattern: Inconsistent naming
let userName = "Alice";
let user_age = 25;  // Different convention
let UserEmail = "alice@example.com";  // Wrong case

// Better: Consistent lowerCamelCase
const userName = "Alice";
const userAge = 25;
const userEmail = "alice@example.com";

// Anti-pattern: Loose equality
if (5 == "5") { }  // Dangerous type coercion

// Better: Strict equality
if (5 === 5) { }  // Type-safe comparison
```

**Key Takeaways:**
- Understand code before using it
- Logic matters more than perfect syntax initially
- Maintain consistency throughout your code
- Use strict equality and respect type boundaries
- Build understanding, don't just collect syntax rules

---

## Section 05: Conditionals in TypeScript

### 05.0 Implementing if, else if, and else in TypeScript 💻 (650 words)

**Learning Objectives:**
- Write if statements in TypeScript syntax
- Use else if for multiple conditions
- Implement else clauses for default cases
- Translate pseudocode conditionals to TypeScript

**Content Outline:**
- The if statement: testing a single condition
- TypeScript syntax: if (condition) { ... }
- Adding else: handling the alternative case
- Multiple conditions: else if chains
- Proper block structure with curly braces
- When to use single-line vs. block syntax
- Nesting if statements (brief introduction)
- From pseudocode to TypeScript: applying Day 6 knowledge

**Hands-On Exercise:**
Translate pseudocode from Day 6 into TypeScript:
- IF age >= 18 → TypeScript if statement
- IF/ELSE logic → TypeScript if/else
- Multiple conditions → TypeScript else if chains
- Write complete programs using conditionals

**Code Examples:**
```typescript
// Simple if statement
const temperature: number = 25;
if (temperature > 30) {
    console.log("It's hot outside!");
}

// if-else statement
const age: number = 16;
if (age >= 18) {
    console.log("You can vote");
} else {
    console.log("Too young to vote");
}

// if-else if-else chain
const score: number = 85;
if (score >= 90) {
    console.log("Grade: A");
} else if (score >= 80) {
    console.log("Grade: B");
} else if (score >= 70) {
    console.log("Grade: C");
} else {
    console.log("Grade: F");
}
```

**Practice Scenario:**
Create a temperature advisory system:
- Accept a temperature value
- Use if/else if/else to categorize:
  - Below 0: "Freezing"
  - 0-15: "Cold"
  - 16-25: "Comfortable"
  - Above 25: "Hot"
- Log the appropriate message

**Success Criteria:**
- Correct if/else if/else syntax
- Proper boolean conditions
- Appropriate use of blocks
- Logical condition ordering
- All cases handled correctly

**Transitions:**
If statements handle most conditional logic, but when testing a single value against many options, the switch statement provides cleaner syntax.

**Key Principles:**
- Blocks {} group multiple statements
- Conditions must evaluate to boolean
- Order matters in else if chains
- Always handle the else case when appropriate
- Clear indentation shows structure

---

### 05.1 The switch Statement for Multiple Cases 💻 (650 words)

**Learning Objectives:**
- Write switch statements in TypeScript
- Use case labels for different values
- Implement default case for unmatched values
- Understand when to use switch vs. if/else

**Content Outline:**
- The switch statement: testing one value against many options
- TypeScript syntax: switch (expression) { case value: ... }
- Case labels: matching specific values
- The break statement: preventing fall-through
- Default case: handling unmatched values
- When to use switch instead of if/else chains
- Fall-through behavior (and why to avoid it)
- Type safety in switch expressions

**Hands-On Exercise:**
Create programs using switch statements:
- Day of week converter (1-7 to day names)
- Grade converter (letter grades to numeric)
- Menu selection system
- Compare switch vs. if/else implementations

**Code Examples:**
```typescript
// Basic switch statement
const dayNumber: number = 3;
switch (dayNumber) {
    case 1:
        console.log("Monday");
        break;
    case 2:
        console.log("Tuesday");
        break;
    case 3:
        console.log("Wednesday");
        break;
    default:
        console.log("Invalid day");
}

// Switch with string cases
const command: string = "start";
switch (command) {
    case "start":
        console.log("Starting system...");
        break;
    case "stop":
        console.log("Stopping system...");
        break;
    case "restart":
        console.log("Restarting system...");
        break;
    default:
        console.log("Unknown command");
}
```

**Practice Scenario:**
Build a calculator using switch:
- Accept an operator (+, -, *, /)
- Two number operands
- Use switch to perform the operation
- Handle invalid operators with default
- Display the result

**Success Criteria:**
- Correct switch syntax
- Break statements in each case
- Default case included
- Type-safe case matching
- Clear, readable case blocks

**Transitions:**
Both if and switch help make decisions, but writing effective conditionals requires avoiding common pitfalls like deeply nested conditions.

**Key Principles:**
- switch works best for equality checks
- Always include break statements
- Default case handles unexpected values
- switch is cleaner than long if/else chains
- Each case should be simple and focused

---

### 05.2 Writing Clean Conditionals: Avoiding Arrow Code 📖 (500 words)

**Learning Objectives:**
- Recognize the "Arrow Code" anti-pattern
- Understand why excessive nesting hurts readability
- Apply guard clauses and early returns
- Refactor nested conditionals into cleaner code

**Content Outline:**
- The Arrow Code anti-pattern: excessive nesting
- Why it's called "Hadouken" code (visual shape)
- Problems with deeply nested conditionals
- Guard clauses: early exit pattern
- Return early: avoiding else after return
- Flattening conditionals: reducing nesting depth
- Extracting complex conditions into variables
- Keeping conditionals simple and readable

**Transitions:**
Clean conditional writing is important, but so is handling edge cases correctly. Let's practice comprehensive conditional logic.

**Key Principles:**
- Flat code is easier to read than nested code
- Guard clauses make intent clear
- Early returns reduce cognitive load
- Extract complex conditions to named variables
- Three levels of nesting is usually the maximum

**Examples:**
```typescript
// Arrow Code anti-pattern (bad)
if (user) {
    if (user.age >= 18) {
        if (user.hasLicense) {
            if (user.hasInsurance) {
                console.log("Can drive");
            }
        }
    }
}

// Better: Guard clauses
if (!user) return;
if (user.age < 18) return;
if (!user.hasLicense) return;
if (!user.hasInsurance) return;
console.log("Can drive");

// Better: Combined conditions
if (user && user.age >= 18 && user.hasLicense && user.hasInsurance) {
    console.log("Can drive");
}
```

---

### 05.3 Edge Cases and Conditional Logic Practice 💻 (600 words)

**Learning Objectives:**
- Identify edge cases in conditional logic
- Test boundary conditions thoroughly
- Handle all possible input scenarios
- Write robust conditional code

**Content Outline:**
- What are edge cases? Boundary and unusual inputs
- Identifying edge cases in conditionals
- Testing minimum and maximum values
- Handling null, undefined, and empty values
- Zero as a special case
- Negative numbers when expecting positive
- Writing defensive conditional code
- Creating test cases for conditionals

**Hands-On Exercise:**
Write and test conditionals that handle:
- Age validation (0, negative, very large numbers)
- String validation (empty, whitespace only, very long)
- Division operations (dividing by zero)
- Range checking (inclusive vs. exclusive boundaries)

**Code Examples:**
```typescript
// Edge case handling
function checkAge(age: number): string {
    // Edge cases first
    if (age < 0) {
        return "Invalid: negative age";
    }
    if (age === 0) {
        return "Newborn";
    }
    if (age > 150) {
        return "Invalid: unrealistic age";
    }
    
    // Normal cases
    if (age >= 18) {
        return "Adult";
    } else {
        return "Minor";
    }
}

// Testing boundary conditions
const score: number = 100;
if (score >= 90 && score <= 100) {
    console.log("Grade A");
}

// Handling division by zero
function divide(a: number, b: number): number {
    if (b === 0) {
        console.log("Error: cannot divide by zero");
        return 0;
    }
    return a / b;
}
```

**Practice Scenario:**
Create a password strength checker:
- Check if password exists (not empty)
- Minimum length requirement
- Maximum length limit
- Contains numbers
- Contains special characters
- Provide feedback for each requirement

**Success Criteria:**
- All edge cases identified and handled
- Boundary values tested
- Clear error messages for invalid inputs
- Logical condition ordering
- Robust against unexpected inputs

**Transitions:**
Mastering conditionals gives us decision-making power. Now let's add repetition with loops, allowing us to execute code multiple times.

**Key Principles:**
- Always consider edge cases when writing conditionals
- Test boundary values explicitly
- Handle errors gracefully
- Order conditions from specific to general
- Defensive coding prevents runtime errors

---

## Section 06: Loops and Iteration in TypeScript

### 06.0 The for Loop: From Pseudocode to TypeScript 💻 (650 words)

**Learning Objectives:**
- Translate for loop pseudocode into TypeScript syntax
- Understand for loop components: initialization, condition, increment
- Write for loops that count up and down
- Use for loops to repeat actions a specific number of times

**Content Outline:**
- The for loop: controlled repetition
- TypeScript syntax: for (initialization; condition; increment) { }
- Loop components explained:
  - Initialization: starting value
  - Condition: when to continue
  - Increment: how to change each iteration
- Counting upward: typical for loop pattern
- Counting downward: decrementing loops
- Loop counter variable: usually `i` for index
- From pseudocode REPEAT to TypeScript for loop
- Common for loop patterns

**Hands-On Exercise:**
Write for loops that:
- Count from 1 to 10
- Count from 10 down to 1
- Count by 2s (even numbers)
- Print a multiplication table
- Translate Day 6 loop pseudocode to TypeScript

**Code Examples:**
```typescript
// Basic for loop counting up
for (let i = 1; i <= 5; i++) {
    console.log("Count:", i);
}
// Output: 1, 2, 3, 4, 5

// Counting down
for (let i = 10; i >= 1; i--) {
    console.log("Countdown:", i);
}
// Output: 10, 9, 8, 7, 6, 5, 4, 3, 2, 1

// Counting by 2s
for (let i = 0; i <= 10; i += 2) {
    console.log("Even number:", i);
}
// Output: 0, 2, 4, 6, 8, 10

// Practical example: multiplication table
const number: number = 5;
for (let i = 1; i <= 10; i++) {
    console.log(`${number} x ${i} = ${number * i}`);
}
```

**Practice Scenario:**
Create a program that:
- Asks for a number (hardcode it for now)
- Prints that number's times table (1-12)
- Uses a for loop to generate each line
- Formats output clearly

**Success Criteria:**
- Correct for loop syntax
- Proper initialization, condition, increment
- Loop executes expected number of times
- Loop counter used correctly
- Clear output at each iteration

**Transitions:**
For loops are perfect when you know exactly how many times to repeat. But sometimes you need to loop until a condition changes—that's where while loops excel.

**Key Principles:**
- for loops are best for counted repetition
- Loop counter (i) tracks current iteration
- Condition checked before each iteration
- Increment happens after each iteration
- Semicolons separate the three components

---

### 06.1 The while Loop: Condition-Based Iteration 💻 (650 words)

**Learning Objectives:**
- Write while loops in TypeScript
- Understand when to use while instead of for
- Ensure while loops have proper exit conditions
- Avoid infinite loops

**Content Outline:**
- The while loop: repeat while condition is true
- TypeScript syntax: while (condition) { }
- When to use while vs. for
- The loop condition: what makes it stop
- Modifying the condition inside the loop
- Common while loop patterns
- Input validation loops
- Event-driven loops (conceptual)
- Preventing infinite loops

**Hands-On Exercise:**
Create while loops for:
- Number guessing game (until correct)
- Input validation (until valid)
- Countdown timer
- Accumulator pattern (sum until threshold)

**Code Examples:**
```typescript
// Basic while loop
let count: number = 1;
while (count <= 5) {
    console.log("Count:", count);
    count++;
}

// While loop for validation
let password: string = "";
while (password.length < 8) {
    console.log("Password too short");
    password = "newpassword";  // In real app, get user input
}
console.log("Valid password");

// Accumulator pattern
let sum: number = 0;
let current: number = 1;
while (sum < 100) {
    sum += current;
    current++;
}
console.log("Sum reached:", sum);

// Countdown with while
let timer: number = 10;
while (timer > 0) {
    console.log("Time remaining:", timer);
    timer--;
}
console.log("Time's up!");
```

**Practice Scenario:**
Build a simple ATM simulator:
- Start with account balance
- While balance > 0:
  - Show balance
  - Simulate withdrawal
  - Update balance
- When balance reaches 0, exit loop
- Display final message

**Success Criteria:**
- Correct while loop syntax
- Condition properly updates inside loop
- Loop exits when expected
- No infinite loops
- Clear purpose for using while over for

**Transitions:**
Both for and while have standard variations. Let's explore for..in, for..of, and do-while loops briefly.

**Key Principles:**
- while is best for condition-based repetition
- Condition must eventually become false
- Update the condition variable inside the loop
- Always have a clear exit strategy
- Use while when iteration count is unknown

---

### 06.2 Advanced Loop Variations: for..in, for..of, and do-while 📖 (500 words)

**Learning Objectives:**
- Understand for..in for iterating object properties
- Recognize for..of for iterating array elements
- Learn do-while loop behavior
- Know when each loop variation is appropriate

**Content Outline:**
- Overview of loop variations in TypeScript
- for..in loop: iterating over object keys/properties
- for..of loop: iterating over iterable values (arrays)
- do-while loop: executing at least once before checking condition
- Differences between for, for..in, and for..of
- When to use each variation
- Brief introduction (detailed coverage comes later)
- Why these variations exist

**Transitions:**
These loop variations provide flexibility, but all loops need proper control. Let's explore break and continue statements.

**Key Principles:**
- for..in is for object properties
- for..of is for array elements
- do-while executes at least once
- Choose the right loop for the task
- These are variations of the same concept

**Examples:**
```typescript
// for..in (object properties) - brief preview
const person = { name: "Ana", age: 25 };
for (let key in person) {
    console.log(key);  // Prints "name", "age"
}

// for..of (array elements) - brief preview
const numbers = [1, 2, 3, 4, 5];
for (let num of numbers) {
    console.log(num);  // Prints each number
}

// do-while (executes at least once)
let attempts: number = 0;
do {
    console.log("Attempting...");
    attempts++;
} while (attempts < 3);
```

**Note to Students:**
These loop variations will be covered in depth when working with arrays and objects. For now, understand they exist and serve specific purposes.

---

### 06.3 Loop Control Flow: break and continue 💻 (600 words)

**Learning Objectives:**
- Use break to exit loops early
- Use continue to skip current iteration
- Understand when loop control statements are appropriate
- Recognize use cases for break and continue

**Content Outline:**
- Loop control statements: break and continue
- break: exit the loop immediately
- continue: skip to next iteration
- When to use break: finding a match, error conditions
- When to use continue: filtering, skipping invalid data
- Loop control with for loops
- Loop control with while loops
- Avoiding overuse of break/continue
- Alternative patterns without break/continue

**Hands-On Exercise:**
Create programs demonstrating:
- break: find first number divisible by 7
- continue: print only odd numbers
- break in input validation (first valid input)
- continue in data filtering (skip negatives)

**Code Examples:**
```typescript
// Using break to exit early
for (let i = 1; i <= 100; i++) {
    if (i % 7 === 0) {
        console.log("First number divisible by 7:", i);
        break;  // Exit the loop
    }
}

// Using continue to skip iterations
for (let i = 1; i <= 10; i++) {
    if (i % 2 === 0) {
        continue;  // Skip even numbers
    }
    console.log("Odd number:", i);
}
// Output: 1, 3, 5, 7, 9

// Practical break example: search
const numbers: number[] = [5, 12, 8, 130, 44];
let found: boolean = false;
for (let i = 0; i < numbers.length; i++) {
    if (numbers[i] > 100) {
        console.log("Found large number:", numbers[i]);
        found = true;
        break;
    }
}

// Practical continue example: validation
for (let score of [85, -5, 92, 0, 78]) {
    if (score < 0) {
        console.log("Invalid score, skipping");
        continue;
    }
    console.log("Valid score:", score);
}
```

**Practice Scenario:**
Build a number analyzer:
- Loop through numbers 1-50
- Use continue to skip multiples of 3
- Use break to stop at first number > 40
- Count how many numbers were processed

**Success Criteria:**
- Correct use of break statement
- Proper use of continue statement
- Loop exits at correct point
- Iterations skip as expected
- Clear understanding of when to use each

**Transitions:**
With loop control mastered, let's tackle the final loop complexity: nested loops.

**Key Principles:**
- break exits the entire loop
- continue skips to next iteration
- Use sparingly—clear conditions are often better
- break is for early exit conditions
- continue is for filtering iterations

---

### 06.4 Nested Loops and Loop Anti-Patterns 📖 (500 words)

**Learning Objectives:**
- Understand nested loop structure and execution
- Write nested loops correctly
- Recognize common loop anti-patterns
- Avoid infinite loops and other pitfalls

**Content Outline:**
- Nested loops: loops inside loops
- How nested loops execute: inner loop completes for each outer iteration
- Common use cases: grids, matrices, combinations
- Loop anti-patterns to avoid:
  - Infinite loops: condition never becomes false
  - Kilometer conditions: overly complex loop conditions
  - Hardcoding limits instead of using variables
  - Modifying loop counter inside the loop body
- Writing clean nested loops
- Performance considerations (brief mention)

**Transitions:**
Understanding loops—from basic for loops to nested structures—completes our TypeScript fundamentals. Now let's apply everything we've learned.

**Key Principles:**
- Inner loop completes fully for each outer iteration
- Keep nested loops simple when possible
- Always ensure loops can exit
- Avoid modifying loop counters unpredictably
- Clear variable names for nested counters (i, j, k)

**Examples:**
```typescript
// Nested loop example: multiplication table
for (let i = 1; i <= 5; i++) {
    for (let j = 1; j <= 5; j++) {
        console.log(`${i} x ${j} = ${i * j}`);
    }
}

// Anti-pattern: Infinite loop
let counter = 0;
while (counter < 10) {
    console.log(counter);
    // Forgot to increment counter!
    // Loop never exits
}

// Anti-pattern: Kilometer condition
for (let i = 0; i < 100 && i % 2 === 0 && i !== 50 && someOtherCondition; i++) {
    // Too complex!
}

// Better: Clear, simple condition
const MAX_COUNT = 100;
for (let i = 0; i < MAX_COUNT; i++) {
    if (i % 2 !== 0) continue;  // Skip odds
    if (i === 50) break;  // Stop at 50
    console.log(i);
}

// Anti-pattern: Modifying loop counter
for (let i = 0; i < 10; i++) {
    console.log(i);
    i++;  // Don't do this! Makes loop unpredictable
}
```

**Key Takeaways:**
- Nested loops multiply iterations (outer × inner)
- Always ensure clear exit conditions
- Simple conditions are better than complex ones
- Let the loop control the counter
- Test loops with small values first

---

## Section 07: Mastery and Next Steps

### 07.0 Building Complete Programs with TypeScript 💻 (700 words)

**Learning Objectives:**
- Combine all learned concepts into complete programs
- Apply variables, conditionals, and loops together
- Write programs that solve real problems
- Debug and refine TypeScript code

**Content Outline:**
- Integrating concepts: variables + types + conditionals + loops
- Program structure: input → process → output
- Planning before coding: pseudocode first
- Writing complete TypeScript programs
- Testing your programs thoroughly
- Debugging common issues
- Refactoring for clarity
- Best practices review

**Hands-On Exercise:**
Build complete programs that combine all concepts:

**Program 1: Grade Calculator**
- Accept multiple test scores (hardcoded array for now)
- Calculate average using a loop
- Use conditionals to assign letter grade
- Display results with proper formatting

**Program 2: Number Analyzer**
- Loop through a range of numbers
- Use conditionals to identify properties (even/odd, prime, etc.)
- Count occurrences of different types
- Display summary statistics

**Program 3: FizzBuzz Classic**
- Loop from 1 to 100
- Conditionals for divisibility by 3, 5, or both
- Print "Fizz", "Buzz", "FizzBuzz", or the number
- Classic programming exercise

**Code Examples:**
```typescript
// Complete program example: Temperature Converter
const temperaturesCelsius: number[] = [0, 10, 20, 30, 40];

console.log("Temperature Conversion Report");
console.log("==============================");

for (let i = 0; i < temperaturesCelsius.length; i++) {
    const celsius: number = temperaturesCelsius[i];
    const fahrenheit: number = (celsius * 9/5) + 32;
    
    let category: string;
    if (celsius < 0) {
        category = "Freezing";
    } else if (celsius < 10) {
        category = "Cold";
    } else if (celsius < 25) {
        category = "Comfortable";
    } else {
        category = "Hot";
    }
    
    console.log(`${celsius}°C = ${fahrenheit}°F (${category})`);
}

console.log("==============================");
console.log("Conversion complete!");
```

**Practice Scenario:**
Create a shopping cart calculator:
- Array of item prices (hardcoded)
- Use loop to calculate subtotal
- Apply tax rate (use constants)
- Conditional discounts based on total
- Display itemized breakdown

**Success Criteria:**
- Program compiles without errors
- All concepts integrated correctly
- Clear, readable code structure
- Proper use of types throughout
- Logical program flow
- Tested with various inputs
- Output is formatted and clear

**Transitions:**
You've built complete programs—now let's test your comprehensive understanding of TypeScript fundamentals.

**Key Principles:**
- Plan with pseudocode before typing
- Break problems into smaller pieces
- Use meaningful variable names
- Test incrementally as you build
- Refactor for clarity after it works
- Comments explain why, not what

---

### 07.1 Testing Your TypeScript Fundamentals 🧠 (800 words)

**Learning Objectives:**
- Demonstrate mastery of TypeScript fundamentals
- Apply all concepts learned in the course
- Solve problems using appropriate TypeScript constructs
- Analyze and debug TypeScript code

**Content Outline:**
- Assessment format: scenario-based questions
- Comprehensive review of all topics covered
- Real-world problem-solving scenarios
- Code analysis and debugging challenges
- Best practices application

**Question 1: Variable Declaration and Types** (Scenario)
You're building a user profile system. Which variable declarations are correct and why?

```typescript
// Option A
const userName: string = "Maria";
let userAge: number = 25;
const isActive: boolean = true;

// Option B
var userName = "Maria";
let userAge = "25";
const isActive = 1;

// Option C
let userName: string = "Maria";
const userAge: number = 25;
let isActive: boolean = true;
```

Evaluate each option considering:
- const vs. let usage
- Type annotations
- Semantic correctness
- Best practices

**Question 2: Conditional Logic** (Scenario)
A voting system needs to check eligibility:
- Must be 18 or older
- Must be a registered voter
- Must not have active restrictions

Write the conditional logic and explain your choices for:
- Using if/else vs. switch
- Handling edge cases
- Boolean expressions

**Question 3: Loop Selection** (Scenario)
For each task, choose the most appropriate loop type and explain why:

Task A: Print multiplication table for a given number (1-12)
Task B: Process user input until they enter "quit"
Task C: Calculate sum of numbers until total exceeds 1000

Options: for loop, while loop, for..of, or break/continue

**Question 4: Code Analysis** (Debugging)
Identify and fix errors in this TypeScript program:

```typescript
let score = "85";
const maxScore: number = 100;

if (score > maxScore) {
    console.log("Score too high!");
}

for (i = 0; i < 10; i++) {
    console.log(i)
}

while (true) {
    let counter: number = 0;
    console.log(counter);
    counter++;
}
```

List all errors:
- Type mismatches
- Variable declaration issues
- Logic problems
- Infinite loops

**Question 5: Complete Program** (Synthesis)
Write a program that:
- Stores 5 product prices in appropriate variables
- Calculates the total using a loop
- Applies a 10% discount if total > 100
- Applies tax rate of 8%
- Displays itemized breakdown with proper formatting

Must include:
- Type annotations for all variables
- Appropriate const/let usage
- Clear conditional logic
- Proper loop structure
- Well-formatted output

**Question 6: Anti-Pattern Recognition**
Identify anti-patterns in this code and suggest improvements:

```typescript
var x = 10;
var y = 20;
var z = 30;

if (x > 5) {
    if (y > 15) {
        if (z > 25) {
            console.log("All conditions met");
        }
    }
}

let n = 0;
while (n < 100) {
    if (n % 2 == 0) {
        console.log(n);
    }
    n++;
}
```

Identify:
- Variable naming issues
- Arrow code pattern
- Loose equality
- var usage

**Question 7: Type Safety** (Scenario)
Explain why TypeScript prevents this code from compiling:

```typescript
const age: number = 25;
const message: string = "Age: " + age;
const isValid: boolean = age;
```

For each line:
- Is it valid TypeScript?
- What type rules apply?
- How would you fix any errors?

**Evaluation Criteria:**
- Correct TypeScript syntax (20%)
- Appropriate use of variables and types (20%)
- Proper conditional logic (20%)
- Correct loop implementation (20%)
- Best practices application (10%)
- Code quality and readability (10%)

**Score Interpretation:**
- 90-100%: Excellent mastery of TypeScript fundamentals
- 80-89%: Strong understanding, minor gaps to address
- 70-79%: Good foundation, practice specific weak areas
- Below 70%: Review core concepts, seek additional practice

**Key Assessment Notes:**
- This tests application, not memorization
- Multiple correct approaches exist for many problems
- Code quality matters as much as functionality
- Understanding trumps perfect syntax

**Transitions:**
You've demonstrated your TypeScript knowledge. Let's reflect on what you've learned and explore where to go next.

---

## Section 08: Your Programming Foundation

### 08.0 What You've Built and Where You're Going Next (450 words)

**Content Outline:**
- Course recap: your journey from pseudocode to TypeScript
- Key concepts mastered:
  - Understanding JavaScript and TypeScript's relationship
  - Writing type-safe code with annotations
  - Working with primitive data types
  - Using operators for calculations and comparisons
  - Making decisions with conditionals
  - Repeating actions with loops
  - Debugging with console.log()
  - Following best practices and avoiding anti-patterns

**Your Programming Foundation:**
You started this course with algorithmic thinking from Day 6. You could design solutions with pseudocode and flow diagrams. Now you can express those solutions in real TypeScript code. You've learned the syntax, type system, and control structures that form the foundation of programming.

**What Makes You Different:**
Unlike developers who memorize syntax, you understand the logic behind the code. You can translate problems into algorithms and algorithms into TypeScript. You write type-safe code that catches errors early. You follow best practices like const-first and semantic naming. You avoid common pitfalls like arrow code and magic numbers.

**The Concepts Are Universal:**
The fundamentals you've learned—variables, conditionals, loops—work the same way in Python, Java, C++, and every other programming language. You've learned how to think like a programmer. The syntax will change, but the logic stays the same.

**What's Next:**
Tomorrow (Day 8), you'll learn about functions—giving names to reusable blocks of code. Soon after, you'll work with arrays and objects to manage complex data. Then you'll bring your programs to life in web browsers. Everything builds on what you learned today.

**Continue Practicing:**
- Write small programs daily
- Translate pseudocode to TypeScript
- Experiment with variations
- Debug your own code before asking for help
- Review today's anti-patterns regularly
- Keep code clean and readable

**Resources for Continued Learning:**
- TypeScript documentation: typescriptlang.org
- Practice platforms for coding challenges
- 4Geeks community for questions and support
- Tomorrow's lesson on functions

**Final Thoughts:**
You've taken your first steps into real programming. The syntax felt strange at first—all those colons, brackets, and semicolons. But now you can write programs that solve actual problems. You can declare typed variables, make decisions, and repeat actions. You can debug with console.log() and follow best practices.

This is just the beginning. Every program you'll write, every application you'll build, starts with these fundamentals. You've earned this foundation. Be proud of what you've learned.

Tomorrow, we level up with functions. See you there!

---

**Note:** This is a conclusion lesson only - no theory, exercises, or assessment.