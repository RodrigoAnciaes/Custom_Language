# Custom_Language


## Example:
```
int x = 21
string y 
y="fish"

if x == 21 
{
	x=1
}
else {
	x=0
}

while x<30 
{
	x=x+1
}

print(x)
print(y)
````

EBNF
```
BLOCK = { STATEMENT };
STATEMENT = [ ASSIGNMENT| ("int"|"string"), IDENTIFIER, ["=",BOOL_EXP] | PRINT | WHILE | IF ], "\n" ;
ASSIGNMENT = IDENTIFIER, "=", BOOL_EXP;
PRINT = "print", "(", BOOL_EXP, ")" ;
WHILE = "while", BOOL_EXP,["\n"], "{", ["\n"], { ( STATEMENT )}, "}";
IF = "if", BOOL_EXP,["\n"],"{", ["\n"], { ( STATEMENT ) },"}", [ "else", "{" ,["\n"], { ( STATEMENT )},"}"] ;
BOOL_EXP = BOOL_TERM, { ("or"), BOOL_TERM } ;
BOOL_TERM = REL_EXP, { ("and"), REL_EXP } ;
REL_EXP = EXPRESSION, { ("==" | ">" | "<"), EXPRESSION } ;
EXPRESSION = TERM, { ("+" | "-" ), TERM } ;
TERM = FACTOR, { ("*" | "/"), FACTOR } ;
FACTOR = NUMBER | STRING |IDENTIFIER | (("+" | "-" | "not"), FACTOR ) | "(", BOOL_EXP, ")" | "read", "(", ")" ;
IDENTIFIER = LETTER, { LETTER | DIGIT | "_" } ;
NUMBER = DIGIT, { DIGIT } ;
LETTER = ( "a" | "..." | "z" | "A" | "..." | "Z" ) ;
DIGIT = ( "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9" | "0" ) ;
STRING = ({LETTER | DIGIT | "_"});
```

## Syntax Diagram
![DS](canvas.png)
