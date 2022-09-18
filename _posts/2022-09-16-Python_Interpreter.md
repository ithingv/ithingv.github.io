#### Python 코드가 어떻게 실행되는지 과정을 알아보자

1. command line
2. tokenize by lexer
3. parsed by ast
4. bytecode
5. interpreter runtime
6. standard library

#### Command Line


```python
s = "x = 2 + 2"
```

#### lexer


```python
import io
import pprint
import tokenize
```


```python
callable(s)
```




    False




```python
s_obj = io.StringIO(s)
```


```python
callable(s_obj)
```




    False




```python
callable(s_obj.readline)
```




    True




```python
tokenize.generate_tokens(s_obj.readline)
```




    <generator object _tokenize at 0x000001B79AEF4CF0>




```python
pprint.pprint(list(tokenize.generate_tokens(s_obj.readline)))
```

    [TokenInfo(type=1 (NAME), string='x', start=(1, 0), end=(1, 1), line='x = 2 + 2'),
     TokenInfo(type=54 (OP), string='=', start=(1, 2), end=(1, 3), line='x = 2 + 2'),
     TokenInfo(type=2 (NUMBER), string='2', start=(1, 4), end=(1, 5), line='x = 2 + 2'),
     TokenInfo(type=54 (OP), string='+', start=(1, 6), end=(1, 7), line='x = 2 + 2'),
     TokenInfo(type=2 (NUMBER), string='2', start=(1, 8), end=(1, 9), line='x = 2 + 2'),
     TokenInfo(type=4 (NEWLINE), string='', start=(1, 9), end=(1, 10), line=''),
     TokenInfo(type=0 (ENDMARKER), string='', start=(2, 0), end=(2, 0), line='')]
    

### Parser


```python
import ast
```


```python
import ast
tree = ast.parse('x = 2 + 2')
pprint.pprint(ast.dump(tree))
```

    ("Module(body=[Assign(targets=[Name(id='x', ctx=Store())], "
     'value=BinOp(left=Constant(value=2), op=Add(), right=Constant(value=2)))], '
     'type_ignores=[])')
    

### Compiler

- bytecodes = compiler(ast)
- in `Python/compile.c` -> `PyAST_CompileObject`
- PEP-0339


```python
import dis # generate byte code
import ast
tree = ast.parse('x = 2 + 2')
object_code = compile(tree, 'dummy.py', mode='exec')
dis.dis(object_code)
```

      1           0 LOAD_CONST               0 (4)
                  2 STORE_NAME               0 (x)
                  4 LOAD_CONST               1 (None)
                  6 RETURN_VALUE
    

- compact numeric codes
    - single numeric an integer
    - numeric number is used for the interpreter to execute some actions
- portable code
    - compiler will generate the same byte code in function of linux, window whatever
- one byte followed by optional parameters 
- used by a software interpreter

#### byte code keyword example

- Include/opcode.h

```c
#define POP_TOP 1
#define ROT_TWO 2
#define BINARY_ADD 23
#define BINARY_SUBTRACT 24
...

```

in `/tmp/empty.py`

```shell
#!/usr/bin/env python
# a super commet

1      0 LOAD_CONST     0(None)
       3 RETURN_VALUE

```


```python
def func(x):
    x = x + 1
    return x
```


```python
dis.dis(func)
```

      2           0 LOAD_FAST                0 (x)
                  2 LOAD_CONST               1 (1)
                  4 BINARY_ADD
                  6 STORE_FAST               0 (x)
    
      3           8 LOAD_FAST                0 (x)
                 10 RETURN_VALUE
    

### Peepholer

- bytecodes = optimizer(bytecodes)

- performs basic peephole optimizations
- removes the dead branches

in `python/peephole.c` -> `PyCode_Optimize`

### Interpreter

execution = interpreter(bytecodes)

- a virtual `stack` machine
- execute the bytecode


- custom bytecode

```c
PUSH 5
PUSH 3
PUSH 10
ADD
ADD
POP

```



```python
class Interperter:
    def __init__(self, instructions):
        self.instructions = instructions
        self.stack = []
        self.insterpreter_pointer = 0
        self.running = True
        
    
    def run(self):
        while self.running:
            self.eval(self.fetch())
            self.instruction_pointer = self.instruction_pointer + 1
        
    
    def fetch(self):
        return self.instructions[self.instruction_pointer]
    
    
    def eval(self, instructions):
        getattr(self, '_eval_{}'.format(instructions))()
    
    
    def _eval_PUSH(self):
        self.instruction_pointer = self.instruction_pointer + 1
        self.stack.append(self.instructions[self.instruction_pointer])
            
    
    def _eval_ADD(self):
        left = self.stack.pop() 
        right = self.stack.pop()
        result = left + right
        self.stack.append(result)
    
    
    def _eval_POP(self):
        value = self.stack.pop()
        print("Popped %r" % value)
        
        
    def _eval_HALT(self):
        self.running = False
```

### Frame

- Collection of information and context for a chunk of code
- Created and destroyed on the fly
- Corresponding to each call of a function
- Has a code object


### Call stack


```python
    def first():
        a = 1
        b = 2
        return a + second(b) ~ (2)
        
    def second(y):
        z = y + 3 ~ (3)
        return z
    
>> first() ~ (1)
3

```



1. main
    - Block Stack : []
    - Data Stack : []
2. first frame
    - Block Stack : []
    - Data Stack : [1]    
3. second frame
    - Block Stack : []
    - Data Stack : [2, 3]


```python

```
