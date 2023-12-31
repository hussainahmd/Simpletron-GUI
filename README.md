# Simpletron-GUI

This repo contains the implementation of Simpletron with GUI using javaFX. It loads a text file containing instructions to be executed.
The list of instructions is listed below.

You can either execute the progam in one go or execute it instruction by instruction.


Here is a preview of the program:


![Screenshot (59)](https://github.com/hussainahmd/Simpletron/assets/101217726/50faf2c5-00b5-48bd-a522-88a71236019a)

• How to run?

Compile:
javac --module-path "path to javafx-sdk\lib" --add-modules javafx.controls,javafx.fxml Simpletron.java

Execute:
java --module-path "path to javafx-sdk\lib" --add-modules javafx.controls,javafx.fxml Simpletron.java


• What is Simpletron?

SIMPLETRON is a computer (through the technique of software-based simulation) on which you can execute your machine-language programs.
The Simpletron runs programs written in the only language it directly understands: Simpletron Machine Language (SML).

The Simpletron is equipped with a 100-word memory, and these words are referenced by their location numbers 00, 01, …, 99.
Before running an SML program, we must load, or place, the program into memory. The first instruction (or statement) of every SML program is always placed
in location 00. The simulator will start executing at this location.

Each location in the Simpletron’s memory may contain an instruction, a data value used by a program or an unused (and so undefined) area of memory.

• The first two digits of each SML instruction are the operation code specifying the operation to be performed.
• The last two digits of an SML instruction are the operand—the address of the memory location containing the word to which the operation applies.

SML operation codes are summarized below:


→ Input/output operations:

• final int READ = 10;                     Read a word from the keyboard into a specific location in memory.

• final int WRITE = 11;                    Write a word from a specific location in memory to the screen.


→ Load/store operations:

• final int LOAD = 20;                     Load a word from a specific location in memory into the accumulator.

• final int STORE = 21;                    Store a word from the accumulator into a specific location in memory.


→ Arithmetic operations:

• final int ADD = 30;                     Add a word from a specific location in memory to the word in the accumulator.

• final int SUBTRACT = 31;                Subtract a word from a specific location in memory from the word in the accumulator.

• final int DIVIDE = 32;                  Divide a word from a specific location in memory into the word in the accumulator.

• final int MULTIPLY = 33;                Multiply a word from a specific location in memory by the word in the accumulator.


→ Transfer-of-control operations:

• final int BRANCH = 40;                 Branch to a specific location in memory.

• final int BRANCHNEG = 41;              Branch to a specific location in memory if the accumulator is negative.

• final int BRANCHZERO = 42;             Branch to a specific location in memory if the accumulator is zero.

• final int HALT = 43;                   Halt. The program has completed its task.


Example:


Instructions from the text file: 1007 1008 2007 3008 2109 1109 4300 0000 0000


The above SML program  reads two numbers from the keyboard and computes and displays their sum.


The instruction +1007 reads the first number from the keyboard and places it into location 07 (which has been initialized to 0).
Then instruction +1008 reads the next number into location 08.
The load instruction, +2007, puts the first number into the accumulator, and the add instruction, +3008, adds the second number to the number in the accumulator. All SML arithmetic instructions leave their results in the accumulator.
The store instruction, +2109, places the result back into memory location 09, from which the write instruction, +1109, takes the number and displays it (as a signed four-digit decimal number). The halt instruction, +4300, terminates execution.

