## Libraries:

Standard imports : 

```c++
#include <iostream>
#include <string>
#include<string.h>
#include<stdio.h>
#include<stdlib.h>
#include <typeinfo>
```



## Structures :

Switch case : 

```c++
switch (var) {
  case label1:
    // statements
    break;
  case label2:
    // statements
    break;
  default:
    // statements
    break;
}
```

[source](https://www.arduino.cc/reference/tr/language/structure/control-structure/switchcase/)



- Go across a char array with pointer shifting :

```c++
char* charrarray = const_cast<char*>("test");
for (uint8_t i = 0; i < sizeof(charrarray); i++) {
    char b = *charrarray++;
    std::cout << b << "\n";
}
```

- Equivalent to moving the pointer manually :

```c++
char* charrarray = const_cast<char*>("test");
for (uint8_t i = 0; i < sizeof(charrarray); i++) {
    char b = *charrarray;
    charrarray = charrarray + 1;
    std::cout << b << "\n";
}
```

- Equivalent if needed in reverse order to move manually pointer to end of variable and go backward : (if addressed data is not splitted in RAM though but i think it if it is, the physical ram address layer refer internally to a virtual ram address layer and we only access this one.)

```c++
char* charrarray = const_cast<char*>("test");
charrarray = charrarray + sizeof(charrarray)-1;
for (uint8_t i = 0; i < sizeof(charrarray); i++) {
    char b = *charrarray--;
    std::cout << b << "\n";
}
```

- <u>Dictionnaries:</u>

https://stackoverflow.com/questions/15151480/simple-dictionary-in-c





- <u>Strings and variable length variables :</u> [ref](https://stackoverflow.com/questions/3770457/what-is-memory-fragmentation)

	:warning: **Heap crash / Heap Fragmentation** :warning:

	Heap is the name of the physical memory here working variables are stored during execution. It can be fragmented if variables keep being created and deleted with variable size and on small RAM devices it can cause crash of **heap** into **stack** which is the static memory where execution constants and function storage is present, leading to unexpected behavior / crash / instability.
	
	<img src="..\..\Images\learn_arduino_Stack_Operation.gif" alt="Heap Crash" style="zoom: 50%;" />

[C-strings](https://www.tutorialspoint.com/cprogramming/c_strings.htm) , null terminated and defined in reverse order, can be a solution to this issue

Arduino Strings are quite shitty regarding this issue - [ref](https://hackingmajenkoblog.wordpress.com/2016/02/04/the-evils-of-arduino-strings/)

Caution with the use of : [ref](https://forum.arduino.cc/index.php?topic=37796.0)

- malloc()
- free()
- realloc()

## Operators : 

All types of operators : [ref](https://www.cplusplus.com/doc/tutorial/operators/) 

- Assignment / compound assignment operators ( = ) : [ref](https://en.cppreference.com/w/cpp/language/operator_assignment)

| operator  | definition                       | description                    |
| --------- | -------------------------------- | ------------------------------ |
| `a = b`   | T& T::operator =(const T2& b);   | simple assignment              |
| `a += b`  | T& T::operator +=(const T2& b);  | addition assignment            |
| `a -= b`  | T& T::operator -=(const T2& b);  | subtraction assignment         |
| `a *= b`  | T& T::operator *=(const T2& b);  | multiplication assignment      |
| `a /= b`  | T& T::operator /=(const T2& b);  | division assignment            |
| `a %= b`  | T& T::operator %=(const T2& b);  | modulo assignment              |
| `a &= b`  | T& T::operator &=(const T2& b);  | bitwise AND assignment         |
| `a |= b`  | T& T::operator \|=(const T2& b); | bitwise OR assignment          |
| `a ^= b`  | T& T::operator ^=(const T2& b);  | bitwise XOR assignment         |
| `a <<= b` | T& T::operator <<=(const T2& b); | bitwise left shift assignment  |
| `a >>= b` | T& T::operator >>=(const T2& b); | bitwise right shift assignment |

- Subscript operator () [ ] ) :
- Member acess ( . , -> )  :
- Pointer-to-member ( .* , ->* ) :
- Scope operator ( :: )  :
- Allocation / Deallocation (new delete)
- Bitewise :

| operator | assembler equivalent | description                      |
| -------- | -------------------- | -------------------------------- |
| `&`      | `AND`                | Bitwise AND                      |
| `|`      | `OR`                 | Bitwise inclusive OR             |
| `^`      | `XOR`                | Bitwise exclusive OR             |
| `~`      | `NOT`                | Unary complement (bit inversion) |
| `<<`     | `SHL`                | Shift bits left                  |
| `>>`     | `SHR`                | Shift bits right                 |

- Logical (!, &&, ||)
- Increment (++, -- )
- Arithmetic (+,-,*,/,%)
- Conditional ternary (?)

```c++
condition ? result1 : result2 
```

 If `condition` is `true`, the entire expression evaluates to `result1`, and otherwise to `result2`.

```c++
// conditional operator
#include <iostream>

int main ()
{
  int a,b,c;

  a=2;
  b=7;
  c = (a>b) ? a : b;

  std::cout << c << '\n';
}
>>> 7
```



## Definitions :

- [Macros :](https://gcc.gnu.org/onlinedocs/cpp/Macros.html) 

> A *macro* is a fragment of code which has been given a name. Whenever the name is used, it is replaced by the contents of the macro.
>
> example 
>
> ```c++
> #ifndef X //macros definitions can be checked with this
> 	#define X() virtual ReturnType Accept(BaseVisitor& guest) { return AcceptImpl(*this, guest); }
> #elseif Y
> #else
> #endif
> ```

- <u>Aggregate Initialization :</u> [ref](https://en.cppreference.com/w/cpp/language/aggregate_initialization)

> Initializes an aggregate from braced-init-list.

```c++
T object = {arg1, arg2, ...};
```

- <u>Null :</u> [ref](https://en.cppreference.com/w/cpp/types/NULL)

Null is represented by a 00 pointer

- <u>Array of Char Arrays :</u>

```c++
char *t[3] = {a,b,c} // where a, b and c are char* arrays.
```



## Bitewise operations :

Usefull bitewise operation tester website : [BitewiseCMD](https://bitwisecmd.com/#0xff%2C%3C%3C%2C8)

> 1. The **& (bitwise AND)** in C or C++ takes two  numbers as operands and does AND on every bit of two numbers.   The  result of AND is 1 only if both bits are 1.
> 2. The **| (bitwise OR)** in C or C++ takes two numbers as operands and does OR on every bit of two numbers.   The result of OR is 1 if any of the two bits is 1.
> 3. The **^ (bitwise XOR)** in C or C++ takes two numbers  as operands and does XOR on every bit of two numbers.   The result of  XOR is 1 if the two bits are different.
> 4. The **<< (left shift)** in C or C++ takes two  numbers, left shifts the bits of the first operand, the second operand  decides the number of places to shift.
> 5. The **>> (right shift)** in C or C++ takes two  numbers, right shifts the bits of the first operand, the second operand  decides the number of places to shift.
> 6. The **~ (bitwise NOT)** in C or C++ takes one number and inverts all bits of it

[source](https://www.geeksforgeeks.org/bitwise-operators-in-c-cpp/)

Size of variable in **bytes** :

```c++
uint32_t test = 5;
sizeof(test)
>>> 4
```

- <u>:warning: The << operator with a negative value is ["undefined behavior"](https://stackoverflow.com/questions/54679593/bitwise-shift-by-a-negative-number-to-reverse-the-bits-in-a-number)  :warning:</u> :

To shift in variable directions : Better to first shift >> the variable amount necessary to go back to the rightmost byte, then shift << a variable amount.

To set a byte content from a variable to another regardless of the type interpretation, use :

```c++
 memcpy(destination, source, bytes_size_to_copy) //bytesize is unsigned integral type. Source & Destination are pointer types
```







- <u>Float representation :</u> [ref](https://softwareengineering.stackexchange.com/questions/215065/can-anyone-explain-representation-of-float-in-memory)

A typical 32-bit float layout looks like the following:

```c
3 32222222 22211111111110000000000
 1 09876543 21098765432109876543210
+-+--------+-----------------------+
| |        |                       |
+-+--------+-----------------------+
 ^    ^                ^
 |    |                |
 |    |                +-- significand 
 |    |
 |    +------------------- exponent 
 |
 +------------------------ sign bit
```

3.14159 can be represented as :
$$
0.7853975 \times 2^2
$$
- 0.7853975 is the ***significand***, a.k.a. the **mantissa** : the part of the number containing the significant digits.

- 2 is the ***exponent***.

- The most significant bit is ised to define the ***sign***.



## Variable types :

### Data type of a variable :

```c++
#include <typeinfo>
typeid(myVar).name()
```

> ***However,\*** that requires a compiler feature  called Runtime Type Information (RTTI). It's disabled in the Arduino  IDE, presumably because it tends to increase the runtime memory  requirements of the program.

[source](https://arduino.stackexchange.com/questions/3079/how-to-retrieve-the-data-type-of-a-variable)

So we can use : 

```c++
// Generic catch-all implementation.
template <typename T_ty> struct TypeInfo { static const char * name; };
template <typename T_ty> const char * TypeInfo<T_ty>::name = "unknown";

// Handy macro to make querying stuff easier.
#define TYPE_NAME(var) TypeInfo< typeof(var) >::name

// Handy macro to make defining stuff easier.
#define MAKE_TYPE_INFO(type)  template <> const char * TypeInfo<type>::name = #type;

// Type-specific implementations.
MAKE_TYPE_INFO( int )
MAKE_TYPE_INFO( float )
MAKE_TYPE_INFO( short )

// Call :
    
int myVar = 17;
Serial.println( TYPE_NAME(myVar) );
>>> int
```

In arduino for code compacity and exec performance

<u>raw type names :</u>

```c++
uint8_t uint8 = 0; 
typeid(uint8).raw_name()
....
    
uint8 : ".E"
uint16_t : ".G"
uint32_t : ".I"
uint64_t : "._K"

int8_t : ".C"
int16_t : ".F"
int32_t : ".H"
int64_t : "._J"

int : ".H"
float  : ".M"
double  : ".N"
```

Another implementation to store types in raw c++ : [ref](https://stackoverflow.com/questions/2562176/storing-a-type-in-c)

Not much more usefull though

### Templates :

> In C++ this can be achieved using *template parameters*. A template parameter is a special kind of parameter that can be used to pass a  type as argument: just like regular function parameters can be used to  pass values to a function, template parameters allow to pass also types  to a function. These function templates can use these parameters as if  they were any other regular type.
>
>  The format for declaring function templates with type parameters is:
>
> ```c++
>  template <class identifier> function_declaration; 
> //or
>  template <typename identifier> function_declaration; 
> ```
>
>
>  The only difference between both prototypes is the use of either the keyword `class` or the keyword `typename`. Its use is indistinct, since both expressions have exactly the same meaning and behave exactly the same way.
>
>  For example, to create a template function that returns the greater one of two objects we could use: 
>
> ```c++
> template <class myType>
> myType GetMax (myType a, myType b) {
> 	return (a>b?a:b); 
> }
> ```
>
>  Here we have created a template function with `myType` as its  template parameter. This template parameter represents a type that has  not yet been specified, but that can be used in the template function as if it were a regular type. As you can see, the function template `GetMax` returns the greater of two parameters of this still-undefined type.
>
>  To use this function template we use the following format for the function call:
>
> ` function_name <type> (parameters); `
>  For example, to call `GetMax` to compare two integer values of type `int` we can write: 
>
> ```c++
> int x,y; GetMax <int> (x,y);
> ```

[source](https://www.cplusplus.com/doc/oldtutorial/templates/)

### Casts :

```c++
const_cast<newtype>(value or variable) // removes const from an object
reinterpret_cast<newtype>(value or variable) //reshapes and casts into variable indepandatly of type byte size
unsigned() or signed() // usefull for avoiding raw c++ to print 8bit values as char (default behavior)
```

> Perhaps a better way of thinking of `reinterpret_cast` is the rouge operator that can "convert" *pointers* to apples as *pointers* to submarines.

### size_t : 

[source](https://en.cppreference.com/w/cpp/types/size_t)



### Boost Variants :

[source](https://www.boost.org/doc/libs/1_48_0/doc/html/variant/tutorial.html)



## Classes and functions :

[Function overloading](http://www.cplusplus.com/doc/tutorial/functions2/#function_overload) (same function name with different types expected as inputs - the proper function is chosen depening on the input parameters at call)

[The use of the arrow operator](https://stackoverflow.com/questions/221346/what-can-i-use-instead-of-the-arrow-operator) : `->` is equivalent to `(*a).b`

> `a->b` is generally a synonym for `(*a).b`. The parenthesises here are necessary because of the binding strength of the operators `*` and `.`:  `*a.b` wouldn't work because `.` binds stronger and is executed first. This is thus equivalent to `*(a.b)`.



- Indexation **operator[]** overload : [ref](https://stackoverflow.com/questions/26670367/c-index-class-members)

```c++
float& operator[] (size_t i)
{
  return (&x)[i];
}
```

[Accessing the [] operator from a pointer](https://stackoverflow.com/questions/8493829/accessing-the-operator-from-a-pointer)

- Constructor : [ref](https://stackoverflow.com/questions/24280521/stdarray-constructor-inheritance)

	Constructor and member initializer : [ref](https://en.cppreference.com/w/cpp/language/constructor) 

	```
	struct S {
	    int n;
	    S() : n(7) {}; // "constructor definition. : n(7)" is the initializer list
	    S(int x) : n{x} {}; // constructor definition. ": n{x}" is the initializer list
	};
	```

	

- Structures : [ref](http://www.cplusplus.com/doc/tutorial/structures/)

```c++
struct foo {
  int bar;
};
```

- Dynamically allocate struct space in a variable size array : [ref1](https://stackoverflow.com/questions/260915/how-can-i-create-a-dynamically-sized-array-of-structs) [ref2](http://www.cplusplus.com/forum/general/86425/)

- Nested classes : [ref](https://riptutorial.com/cplusplus/example/11914/nested-classes-structures)



Pass the class object to a function in c++ : 

```c++
template<class MODULE>
void function_taking_class() {
	// use static functions of AnyClass
	MODULE::count_instances();

	// or create an object of AnyClass and use it
	MODULE object;
	object.member = value;
}
```



## Arduino specifics :

[Question about C++ Javan and C# compilation and execution time](https://stackoverflow.com/questions/145110/c-performance-vs-java-c) - Answer, with JIT (just in time compiler) C#and Java can be even faster than C++ because optimizations can be made depending on the architecture of the machine, optimisations that are less drastic for OS versatility sake when compiling C++ long before execution.

[Color theme "One dark"](https://github.com/konrad91/OneDarkArduino)



<u>Simulate an arduino project :</u> [Tinkercad](https://create.arduino.cc/projecthub/KM_Saifullah/virtual-arduino-simulation-ce1bd2)



[Optiboot repo and explanation](https://github.com/Optiboot/optiboot)

[Stepper motors acceleration advices :](https://forum.arduino.cc/index.php?topic=506797.msg3455713#msg3455713)

[Stepper motor high speed operations](https://forum.arduino.cc/index.php?topic=506797.msg3455713#msg3455713)

[DigitalWriteFast](https://github.com/NicksonYap/digitalWriteFast)

[Arduino FPGA](https://store.arduino.cc/mkr-vidor-4000)

### **CRC :** 

- CRC16 algorithm in various languages :

	[CRC-16/CCITT-FALSE](https://gist.github.com/tijnkooijmans/10981093)  : Java, C, python, Ruby...

- [CRC website with algorithm explanation for 8-16-32 versions](http://www.sunshine2k.de/articles/coding/crc/understanding_crc.html)

### **Millis unsigned long overflow :** 

```C++
if  (millis()-memory > 100) {
}
```

because unsigned long comparisons use modulo uperator if result is overflowing ( negative ).

explanation [here](https://www.best-microcontroller-projects.com/arduino-millis.html)

### Libraries :

[Custom library writing tutorial](https://www.arduino.cc/en/Hacking/libraryTutorial)



## C++ Specifics : 

- **<u>Prints :</u>**

```c++
#include <iostream>
#include <iomanip> 
#include <string>
#include <string.h>
int value = 15;
std::cout << std::setw(3) << std::hex << value; //HEXA fixed width 3
std::cout << std::dec << value; //DECIMAL
```

List of std::io manipulators :

```c++
std::dec
std::hex
std::setprecision (15)
std::setw(3)
```

- <u>**Function overhead :**</u>

	In every language, calling a function generates operations that takes additional time (thread about that [here](https://stackoverflow.com/questions/144993/how-much-overhead-is-there-in-calling-a-function-in-c)). 

	> On most architectures, the cost consists of saving all (or some, or  none) of the registers to the stack, pushing the function arguments to  the stack (or putting them in registers), incrementing the stack pointer and jumping to the beginning of the new code.  Then when the function  is done, you have to restore the registers from the stack. 
	>
	> ref : [Calling conventions on the x86 platform](http://www.angelcode.com/dev/callconv/callconv.html)

	In C++ however, because it is a compiled language, we can specify the compiler to "[inline](https://docs.microsoft.com/fr-fr/cpp/cpp/inline-functions-cpp?view=msvc-160)" a function inside it's calling code to reduce that overhead.

## File architecture :

[Header and implementation files](http://www.math.uaa.alaska.edu/~afkjm/csce211/handouts/SeparateCompilation.pdf)

[Forward declarations](https://www.geeksforgeeks.org/what-are-forward-declarations-in-c/)

[Templates](https://isocpp.org/wiki/faq/templates#templates-defn-vs-decl)



## Compilation details in C : 

- Compilateur fichiers H et CPP

Il faut comprendre comment fonctionne la "compilation", et par  "compilation" j'entends preprocesseur + compilation + le linkage.

Les instructions de préprocesseur sont exécuté AVANT le compilateur.
Toute les instruction de préprocesseur sont évalue et font leurs jobs.
Par exemples, "#include fichier" permet de copier le contenue de "fichier" à la place de #include.

 `<...>` for inclusions only looks in the system and library areas.  `"..."` also looks inside your sketch.

Ca remplace la ligne par le contenue du fichier, carrément.

Ensuite, la compilation (qui ne s'effectue QUE sur les fichiers .c).
À chaque fois que le compilateur commence à un compiler un fichier, il  "oublie" tout : il ne connaît plus les fonctions, les variables, etc  etc.
Il part du haut du fichier, et descend ligne par ligne en faisant ses vérifications (syntaxique, sémantique, etc etc).
Quand il tombe sur le prototype d'une fonction, il "retient" cette dernière  en mémoire (son nom, son type de retour, ses arguments ...).
Quand il tombe sur un appel de fonction, il regarde dans sa mémoire s'il la connaît.
Si oui, pas de soucis (a moins que mauvais nombre d'argument, retour mal  utilisé, mais ça c'est la vérification syntaxique et sémantique).
Si non, il va émettre un avertissement de type "implicite declaration of function 'untel'".

Mais il est possible que cela n'arrête pas la compilation : le compilateur  va considérer que puisqu'il ne la connaît pas, c'est une fonction qui  retourne un int et qui prends aucun arguments, et si d'aventure c'est  correct sémantiquement (par exemple, la variable qui récupère le retour  de la fonction est "compatible" avec un int, c'est ok), alors la  compilation se poursuivra.

Ensuite, une fois qu'il a compilé tout les .c, le travail du vrai compilateur est terminé.
C'est au tour du linker. Le linker va prendre tout les .o (c'est les .c compilés) et les assembler.
C'est a ce moment que le linker va vérifier si chaque fonctions utilisé dans les .c existe.
Typiquement, tu as la fonction "position" défini dans "position.c", et utilisé dans "main.c".
le linker va vérifier que la fonction "position" appelé dans "main.c" existe bien et en un seul exemplaire.
Si ce n'est pas le cas, il émettra un erreur (et la ça arrête tout) de type "undefined reference to 'untel'".

Pour que le compilateur puisse connaitre les prototype de fonction dans  chaque .c, on déclare simplement le prototype dans un .h que l'on inclue au debut du fichier .c.
Ainsi, à l'étape du préprocesseur, le  contenue du .h (et donc le prototype de la fonction) est copié au debut  du .c, à l'étape de compilation, le compilateur va connaitre la fonction (et n'émettra pas de warning), et le linker sera content.

Tout cela pour dire : Non, le "programme" ne vas jamais chercher le  prototype : soit il le connaît, soit il émet un warning, et ensuite un  #include n'est jamais fouillé, il est remplacé au début, avant même la  compilation.

[Source]: https://openclassrooms.com/forum/sujet/fichier-h-et-fichier-c	"Fichier.h et fichier.c"



- How to actually write declarations in H and CPP :

<u>Template Class Header File</u> (.h)

```c++
// TestTemp.h
#ifndef _TESTTEMP_H_
#define _TESTTEMP_H_

// OR 

#pragma once
 
template<class T>
class TestTemp  
{
 
public:
 
    TestTemp();
    template <int size>
    void SetValue( T obj_i[size] );
    T Getalue();
 
private:
 
    T m_Obj;
};
#endif
```

<u>Template Class Source File</u> (.cpp)

```c++

// TestTemp.cpp
#include "TestTemp.h"
 
template <class T>
TestTemp<T>::TestTemp()
{
}
template <class T> template <int size>
void TestTemp<T>::SetValue( T obj_i[size] )
{
 
}
template <class T>
T TestTemp<T>::Getalue()
{
    return m_Obj;
}
```

[ref](https://www.codeproject.com/Articles/48575/How-to-Define-a-Template-Class-in-a-h-File-and-Imp)

- With parent and inherited child classes : 

In Child.h, you would simply declare:

```c++
Child(int Param, int ParamTwo);
```

In Child.cpp, you would then have:

```c++
Child::Child(int Param, int ParamTwo) : Parent(Param) {
    //rest of constructor here
}
```

[ref](https://stackoverflow.com/questions/24047140/c-inheritance-calling-base-class-constructor-in-header)

- <u>to avoid error :</u> error C4996: 'strcmp': This function or variable may be unsafe.

`_CRT_SECURE_NO_WARNINGS` 

[source]: https://stackoverflow.com/questions/22450423/how-to-use-crt-secure-no-warnings	"Disable CRT Secure Warnings"



- _DEBUG

is a reserved name for compiler options : [ref](https://docs.microsoft.com/fr-fr/cpp/c-runtime-library/debug?view=msvc-160)

<u>QT tutorials :</u> 

https://openclassrooms.com/fr/courses/1894236-programmez-avec-le-langage-c/1898935-initiez-vous-a-qt

