# COMPILER-DESIGN-BASICS

COMPANY: CODTECH IT SOUTION 

NAME: SHWET KAMAL

INTERN ID: CT04DF161

DOMAIN: C++

DURATION: 4 WEEKS

MENTOR: NEELA SONTASH

Mini Arithmetic Expression Compiler Using Recursive Descent Parsing in C++

This application implements a Mini Arithmetic Expression Compiler using the technique of recursive descent parsing in C++. It allows a user to enter mathematical expressions in string format and computes their result accurately, following proper operator precedence and handling nested parentheses. The tool demonstrates core concepts of parsing, expression evaluation, and modular design in C++.

Purpose and Objective

The purpose of this application is to build a system that can evaluate arithmetic expressions such as:

3 + 4 * (2 - 1)

The primary objective is to convert human-readable expressions into executable logic through parsing and computation. This requires the breakdown of expressions into subcomponents, identification of operands and operators, and correct application of arithmetic rules.

Core Concepts and Methodology

 1. Recursive Descent Parsing
    
This technique is a top-down parsing method where each grammar rule is implemented by a dedicated function. The grammar supported in this application includes:

expression → term { ('+' | '-') term }

term       → factor { ('*' | '/') factor }

factor     → number | '(' expression ')'

Each rule corresponds to a function:

parseExpression() handles + and -.

parseTerm() handles * and /.

parseFactor() handles numbers and parentheses.

This approach provides a clear and modular structure for parsing arithmetic syntax.

 2. Token Processing
    
Two key functions handle the reading of characters from the input string:

peek() looks at the next character without removing it from the stream.

get() reads and consumes the next character.

By using these functions, the parser can efficiently navigate through the input while constructing numbers and identifying operators.

 3. Whitespace and Error Handling
    
Whitespace characters are ignored using the skipWhitespace() function, allowing for flexible input formatting (e.g., 3+4 or 3 + 4).

Error conditions such as missing parentheses or invalid characters are detected and reported using throw statements with standard exceptions. These are caught in the main program to prevent crashes and display meaningful error messages.

Program Flow

The user enters an arithmetic expression.

The expression is passed to the evaluate() method of the Parser class.

The expression is parsed recursively and evaluated in real-time.

The result is displayed, or an error is reported if the expression is invalid.

This clear input-process-output flow ensures maintainability and readability of the code.

Sample Evaluations

Input Expression	Computed Result
3 + 4 * (2 - 1)	7
(1 + 2) * 3	9
10 / 2 + 3 * 4	17
5 + 3.5 * 2 - (1 + 1)	10

The output confirms that the parser respects operator precedence and handles floating-point arithmetic.

Practical Applications

This tool is highly useful for:

Learning how interpreters and calculators function internally.

Understanding parsing strategies used in language compilers.

Building custom mini-languages, formula evaluators, or scripting engines.

While the current version supports basic operations, the architecture allows easy extension.

Conclusion

This arithmetic expression evaluator provides a clear example of how recursive parsing and arithmetic logic can be combined to build a functioning mini-compiler in C++. It emphasizes key programming principles such as recursion, error handling, and modular design. The program serves as a foundational model for more advanced parsing and compiler-related applications, and demonstrates how high-level input can be interpreted and executed with precision.
