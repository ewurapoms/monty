## MONTY
`Monty 0.98` is a scripting language that is first compiled into monty byte codes (Just like python). It relies on a unique stack, with specific instructions to manipulate it. **`monty`** is an interpreter built specially for the said Monty Bytecodes files.
This is a language that contains specific instructions to manipulate data information (stacks or queues), where each instruction (*called opcode*) is sent by line. Files which contains Monty byte codes usually have the `.m` extension.

Example (`file.m`):
```bash
$ cat file.m
# Pushing element to the stack
push 0
push 1
push 2
# Printing all elements
pall
push 3
push 4
pop
# Rotating the stack to the bottom
rotr
pall
rotl
# Setting FIFO
queue
push 5
# Setting LIFO
stack
push 5
$
```

## Technologies
* Interpreter: C language
* C files to be compiled with `gcc 4.8.4`
* C files are written according to the C90 standard and Betty Style
* Program tested on Ubuntu 20.04 LTS

## Usage
To compile all files:

```bash
$ gcc -Wall -Werror -Wextra -pedantic *.c -o monty
$
```

Interpreter **synopsis** below:

```bash
$ ./monty [filename]
$
```

Run interpreter as:

```bash
$ ./monty file.m

```

## Features
### Opcodes
`monty` executes the following opcodes:

| Opcode | Description |
| -------- | ----------- |
| `push` | Pushes an element to the stack |
| `pall` | Prints all the values on the stack |
| `pint` | Prints the value at the top of the stack |
| `pop` | Removes the top element of the stack |
| `swap` | Swaps the top two elements of the stack |
| `queue` | Sets the format of the data to a queue (FIFO) |
| `stack` | Sets the format of the data to a stack (LIFO) |
| `nop` | Does anything |
| `add` | Adds the top two elements of the stack |
| `sub` | Subtracts the top element of the stack from the second top element of the stack |
| `mul` | Multiplies the second top element of the stack with the top element of the stack |
| `div` | Divides the second top element of the stack by the top element of the stack |
| `mod` | Computes the rest of the division of the second top element of the stack by the top element of the stack |
| `pchar` | Prints the char at the top of the stack |
| `pstr` | Prints the string starting at the top of the stack |
| `rotl` | Rotates the stack to the top |
| `rotr` | Rotates the stack to the bottom |

Comments, indicated with `#`, are not executed by the interpreter.

When a **nonextistent opcode** is passed, the interpreter prints an error message and stops:

```bash
$ cat errorfile.m
push 1
pint
pcx
$ ./monty errorfile.m
1
L3: unknown instruction pcx
```

### Return value
Return: `monty` returns `0` for no errors. Else, `1`

## Authors
<details>
    <summary>Pomaa Ewurah-Abena Oppong</summary>
    <ul>
    <li><a href="https://medium.com/@abenapomaa">Medium</a></li>
    <li><a href="mailto:apowurah@outlook.com">e-mail</a></li>
    </ul>
</details>
<details>
    <summary>Rosina Antwi</summary>
    <ul>
    <li><a href="https://www.github.com/rosyrose1">Github</a></li>
    <li><a href="mailto:rosinaantwi96@gmail.com">e-mail</a></li>
    </ul>
</details>
