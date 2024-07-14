# <p align="center">🌚C 语言</p>

# 🌑 初识 C 语言

## 细碎小知识点

- `define`

~~不是关键字，是预处理指令（也不能用来做变量名）~~

- 判断语句不能写成 18<=age<28：

  ```c
  int age = 10;
  if(18<=age<28) //相当于0<28
      printf("青年\n");
  return 0;
  ```

- 定义指针

  ```c
  int *p1, *p2, *p3;//多个指针定义都要加*
  ```

- printf()打印字符串
  ```c
  printf("%s",arr);
  ```
- 函数的定义
  函数定义要写在 main 函数之前，或者在 main 函数前先声明函数

---

## <center>`switch` 语句（可嵌套）

> 在 C 语言中，`switch`语句允许根据变量的值执行不同的代码块。嵌套的`switch`语句就是在一个`switch`语句的某个`case`块中再包含另一个`switch`语句。下面是一个嵌套`switch`语句的示例：

### 示例

```c
#include <stdio.h>

int main() {
    int outerVar = 1;
    int innerVar = 2;

    // 外层 switch 语句
    switch (outerVar) {
        case 1:
            printf("Outer switch: Case 1\n");

            // 内层 switch 语句
            switch (innerVar) {
                case 1:
                    printf("Inner switch: Case 1\n");
                    break;
                case 2:
                    printf("Inner switch: Case 2\n");
                    break;
                default:
                    printf("Inner switch: Default case\n");
                    break;
            }
            break;

        case 2:
            printf("Outer switch: Case 2\n");
            break;

        default:
            printf("Outer switch: Default case\n");
            break;
    }

    return 0;
}
```

> - 外层`switch`语句根据变量`outerVar`的值来选择执行哪个`case`块。
> - 当`outerVar`的值为`1`时，程序会执行外层`switch`语句的`case 1`块中的代码。
> - 在`case 1`块中，有一个嵌套的`switch`语句，它根据变量`innerVar`的值来选择执行哪个`case`块。
> - 当`innerVar`的值为`2`时，程序会执行内层`switch`语句的`case 2`块中的代码。

### 注意事项：

> - 每个`case`块末尾通常需要有一个`break`语句，以防止执行到下一个`case`块中的代码。
> - `default`块是可选的，但建议在`switch`语句中包含一个`default`块来处理所有未被明确处理的情况。

通过这种方式，可以在`switch`语句中嵌套另一个`switch`语句，以处理更复杂的多级条件判断。

---

## <p align="center">`getchar()`语句</p>

> `getchar()` 是 C 语言标准输入库函数之一，用于从标准输入（通常是键盘）读取一个字符。它的作用是等待用户输入，并返回输入的字符。

### `getchar()` 的作用

- **读取单个字符**：`getchar()` 函数每次调用只读取一个字符。
- **阻塞式输入**：调用 `getchar()` 后程序会暂停执行，直到用户输入一个字符并按下回车键。

### `getchar()` 的用法

### 基本用法

```c
#include <stdio.h>

int main() {
    char c;
    printf("请输入一个字符：");
    c = getchar();  // 读取一个字符并赋值给变量 c
    printf("你输入的字符是：%c\n", c);
    return 0;
}
```

在这段代码中，程序会等待用户输入一个字符，然后将该字符存储在变量 `c` 中，并输出这个字符。

### 注意事项

> - **缓冲区**：`getchar()` 读取的是标准输入缓冲区中的字符，直到用户按下回车键，整个输入行才会进入缓冲区。
>
> * **返回类型**：`getchar()` 返回一个 `int` 类型的值。这是因为在处理字符的同时，还需要处理输入结束（EOF）的情况。EOF 通常定义为 -1。
> * **多次调用**：每次调用 `getchar()` 会读取下一个字符。如果在读取一个字符后希望继续读取，可以使用循环。

### 示例：读取多个字符

```c
#include <stdio.h>

int main() {
    char c;
    printf("请输入字符（按 Ctrl+D 结束）：\n");
    while ((c = getchar()) ! = EOF) {  // Ctrl+D（Linux/Mac）或 Ctrl+Z（Windows）表示输入结束
        printf("你输入的字符是：%c\n", c);
    }
    return 0;
}
```

在这个示例中，程序会持续读取用户输入的字符，直到用户输入 EOF 为止。

### 进阶用法

> - **过滤换行符**：如果只需要读取字符而忽略换行符，可以使用循环或条件判断来跳过换行符。
> - **输入缓冲清空**：有时候需要清空输入缓冲区，以确保后续输入不受之前输入的影响。可以使用 `fflush(stdin)`，但这在不同平台上的行为可能有所不同。（`scanf`语句输入后，输入不正确字符被截断，可以用来清除缓冲区字符）

### 示例：过滤换行符

```c
#include <stdio.h>

int main() {
    char c;
    printf("请输入一个字符（忽略换行）：");
    while ((c = getchar()) = = '\n');  // 跳过所有换行符
    printf("你输入的字符是：%c\n", c);
    return 0;
}
```

_这段代码将会忽略所有的换行符，直到读取到一个非换行符的字符。_

### getchar()打印数字部分的输入

```c
#include <stdio.h>

int main() {
    char c;
    printf("请输入字符（输入 Ctrl+D 结束）：\n");
    while ((c = getchar()) != EOF) {
        if (c >= '0' && c <= '9') {  // 只打印数字字符
            printf("你输入的数字字符是：%c\n", c);
        }
    }
    return 0;
}
```

在这个程序中，`getchar()` 函数会从标准输入中读取一个字符，然后检查该字符是否为数字字符（'0' 到 '9'）。如果是数字字符，程序会打印该字符；否则，程序会忽略该字符。程序会一直运行，直到检测到 **_EOF_** （通常是通过 Ctrl+D 结束输入）。

---

## <p align="center">`sizeof`函数</p>

> 在 C 语言中，使用`sizeof`运算符可以帮我们计算出数组的总大小（以字节为单位）。这是常用来确定数组中有多少个元素的一种方法，特别是当我们不直接知道数组的长度时。

### 基本用法

如果你有一个数组，比如：

```c
int arr[10];
```

使用`sizeof`计算这个数组的大小会得到整个数组占用的字节数。由于`int`通常是 4 字节（这取决于编译器和平台），所以这个数组的大小将是：

```c
sizeof(arr); // 结果为 40 字节 (10 * 4)
```

这里，`sizeof(arr[0])`计算的是数组中单个元素的大小，即一个`int`的大小。

---

## <p align="center">内部链接（Internal Linkage）</p>

> 在 C 语言中，链接（linking）分为内部链接（internal linkage）和外部链接（external linkage）。这两种链接方式决定了标识符（如变量和函数）的可见性和作用域。`static`和`extern`是用于控制这些链接的两个关键字。

- **内部链接**意味着标识符在其定义所在的翻译单元（translation unit）内是可见的，但在其他翻译单元中不可见。
- 使用`static`关键字可以实现内部链接。

### 例子：

```c
// file1.c
static int count = 0; // 只能在 file1.c 中访问

static void increment() { // 只能在 file1.c 中调用
    count++;
}

void doSomething() {
    increment();
}
```

在这个例子中，`count`变量和`increment`函数都具有内部链接，它们仅在`file1.c`中可见，其他文件不能直接访问它们。

---

## <p align="center">外部链接（External Linkage）</p>

- **外部链接**意味着标识符在所有翻译单元中都是可见的。
- 默认情况下，不带`static`的全局变量和函数具有外部链接。
- 使用`extern`关键字可以引用其他翻译单元中定义的标识符。

### 例子：

```c
// file1.c
int count = 0; // 在所有翻译单元中可见

void increment() { // 在所有翻译单元中可见
    count++;
}
```

```c
// file2.c
extern int count; // 引用 file1.c 中的 count 变量

void doSomething() {
    count++;
}
```

在这个例子中，`count`变量和`increment`函数具有外部链接，可以在`file2.c`中引用并使用它们。

---

## <p align="center">`static` 关键字</p>

> `static` 关键字在 C 语言中有多种用途，它的作用取决于它所在的上下文。主要有以下几种使用场景：

- **静态局部变量**
- **静态全局变量**
- **静态函数**

### 静态局部变量

- **定义**：在函数内部定义的 `static` 变量。
- **作用域**：仅在函数内部可见。
- **生命周期**：贯穿整个程序的运行时间（即使函数已经返回，静态局部变量的值也会被保留）。

```c
#include <stdio.h>

void countCalls() {
    static int count = 0; // 静态局部变量
    count++;
    printf("countCalls has been called %d times\n", count);
}

int main() {
    countCalls();
    countCalls();
    countCalls();
    return 0;
}
```

**输出：**

```
countCalls has been called 1 times
countCalls has been called 2 times
countCalls has been called 3 times
```

### 静态全局变量

- **定义**：在文件的顶层（函数外部）定义的 `static` 变量。
- **作用域**：仅在定义它的文件内可见。
- **生命周期**：贯穿整个程序的运行时间。

```c
// file1.c
#include <stdio.h>

static int count = 0; // 静态全局变量

void increment() {
    count++;
    printf("Count in file1.c: %d\n", count);
}

// file2.c
#include <stdio.h>

// extern int count; // 错误：无法访问 file1.c 中的静态全局变量

void callIncrement() {
    increment();
}
```

在这个例子中，`count` 变量仅在 `file1.c` 文件内可见，不能在 `file2.c` 中访问。

### 静态函数

- **定义**：在文件的顶层使用 `static` 定义的函数。
- **作用域**：仅在定义它的文件内可见。

```c
// file1.c
#include <stdio.h>

static void helper() { // 静态函数
    printf("This is a static function\n");
}

void publicFunction() {
    helper();
}

// file2.c
#include <stdio.h>

// void helper(); // 错误：无法访问 file1.c 中的静态函数

void callPublicFunction() {
    publicFunction();
}
```

在这个例子中，`helper` 函数仅在 `file1.c` 文件内可见，不能在 `file2.c` 中访问。

---

## <p align="center">`extern` 关键字</p>

> `extern` 关键字用于声明一个在其他文件中定义的变量或函数。它的作用是告诉编译器这个变量或函数的定义在其他地方，并且在链接阶段会找到它的定义。

### 声明全局变量

- **定义**：在一个文件中定义的全局变量。
- **声明**：在另一个文件中使用 `extern` 关键字来声明。

```c
// file1.c
#include <stdio.h>

int count = 0; // 定义全局变量

void increment() {
    count++;
    printf("Count in file1.c: %d\n", count);
}

// file2.c
#include <stdio.h>

extern int count; // 声明全局变量

void display() {
    printf("Count in file2.c: %d\n", count);
}
```

在这个例子中，`count` 变量在 `file1.c` 中定义，在 `file2.c` 中使用 `extern` 关键字声明。

### 声明函数

- **定义**：在一个文件中定义的函数。
- **声明**：在另一个文件中使用 `extern` 关键字来声明（虽然函数声明通常不需要 `extern` 关键字，因为默认情况下函数具有外部链接）。

```c
// file1.c
#include <stdio.h>

void increment() { // 定义函数
    printf("Increment function called\n");
}

// file2.c
#include <stdio.h>

extern void increment(); // 声明函数

void callIncrement() {
    increment();
}
```

在这个例子中，`increment` 函数在 `file1.c` 中定义，在 `file2.c` 中声明并调用。

### 注意

> 通过理解 `static` 和 `extern` 关键字的不同用途和使用场景，可以更好地控制变量和函数的可见性和作用域，从而编写出更加模块化和维护性更好的代码。

> `const` 关键字在 C 语言中用于定义常量。常量是指在程序执行过程中其值不会发生变化的变量。使用 `const` 关键字可以提高代码的可读性和安全性，防止意外修改。下面是 `const` 关键字的一些常见用法和详细介绍：

---

## <p align="center">`const` 常量</p>

### 基本用法

- **常量变量**

  ```c
  const int a = 10;
  ```

  上面的代码定义了一个常量整型变量 `a`，并将其初始化为 10。之后，`a` 的值不能再被修改。

- **指针常量**
  指针常量表示指针指向的地址是固定的，但指针指向的内容可以修改。

  ```c
  int x = 5;
  int y = 10;
  int *const p = &x;
  *p = 20;  // 合法，修改指针指向的内容
  p = &y;   // 非法，试图修改指针本身
  ```

- **常量指针**
  常量指针表示指针指向的内容是固定的，但指针本身可以指向不同的地址。

  ```c
  int x = 5;
  int y = 10;
  const int *p = &x;
  p = &y;   // 合法，修改指针本身
  *p = 20;  // 非法，试图修改指针指向的内容
  ```

- **常量指针常量**
  既表示指针本身不能修改，指针指向的内容也不能修改。
  ```c
  int x = 5;
  const int *const p = &x;
  *p = 20;  // 非法，试图修改指针指向的内容
  p = &y;   // 非法，试图修改指针本身
  ```

### `const` 在函数中的使用

- **传递常量参数**

  ```c
  void printValue(const int value) {
      printf("%d\n", value);
  }
  ```

  传递常量参数可以确保函数内部不会修改传入的参数。

- **常量指针参数**
  ```c
  void printArray(const int *array, int size) {
      for (int i = 0; i < size; i++) {
          printf("%d ", array[i]);
      }
      printf("\n");
  }
  ```
  常量指针参数确保函数内部不会修改数组内容。

### 使用场景

- **保护数据**：当你有一些不希望被修改的数据时，可以使用 `const` 来保护这些数据。
- **代码可读性**：通过 `const` 关键字，其他开发者可以清楚地知道哪些变量不应该被修改。
- **编译器优化**：有时编译器可以利用 `const` 关键字进行优化。

### 示例

```c
#include <stdio.h>

void printMessage(const char *message) {
    printf("%s\n", message);
}

int main() {
    const int a = 100;
    // a = 200;  // 错误，a 是常量

    int x = 10;
    int y = 20;
    int *const p1 = &x;  // p1 是指针常量
    const int *p2 = &x;  // p2 是常量指针
    const int *const p3 = &x;  // p3 是常量指针常量

    printMessage("Hello, World!");

    return 0;
}
```

在上面的示例中，`a` 是一个常量整型变量，`p1` 是指针常量，`p2` 是常量指针，`p3` 是常量指针常量。通过这些例子，可以更好地理解 `const` 关键字的 使用。

---

## <p align="center">`goto`语句</p>

> 在 C 语言中，`goto` 语句用于在同一函数内无条件地跳转到程序中预定义的标签。虽然 `goto` 可以使某些类型的逻辑更容易实现，例如跳出多层嵌套的循环，但一般建议尽量避免使用它，因为它会让程序的流程变得难以追踪，从而增加代码的复杂性和出错的可能。

### `goto` 的基本语法如下：

```c
goto label;
...
label:
statement;
```

这里，`label` 是一个用户定义的标识符，用于标记程序中的一个位置，`goto` 语句则会使程序跳转到标记的位置继续执行。

### 示例：

```c
#include <stdio.h>

int main() {
    int num = 0;

    start:
        num++;
        if (num < 10) {
            printf("%d\n", num);
            goto start;
        }

    return 0;
}
```

> 在这个例子中，代码从标签 `start` 开始执行，然后增加变量 `num` 的值，打印它，然后通过 `goto start;` 又跳回到 `start` 标签处。这里 `goto` 实现了一个循环，每次循环都会检查 `num` 的值，直到其达到 10 结束循环。

### 使用建议：

> 尽管 `goto` 可以处理一些复杂的流程控制问题，比如从嵌套深的循环或条件判断中跳出，但过度使用可能导致所谓的“意大利面条代码”（Spaghetti Code），即逻辑复杂、难以维护的代码。一般推荐使用其他结构化的程序控制语句如循环（`for`，`while`）和条件（`if`，`switch`）来替代 `goto`，使得代码逻辑更加清晰和可维护。

---

## `rand`和`srand`函数

> 在 C 语言中，`rand()`和`srand()`函数用于生成伪随机数。

### `rand()` 函数

> `rand()` 函数用于生成一个伪随机整数。它的原型在 `stdlib.h` 头文件中定义：

```c
#include <stdlib.h>

int rand(void);
```

`rand()` 函数返回一个在 `0` 到 `RAND_MAX` 之间的整数，其中 `RAND_MAX` 是一个宏，通常定义为 `32767`。注意，这个范围可以因实现而异。

#### 示例代码

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    printf("随机数：%d\n", rand());
    return 0;
}
```

### `srand()` 函数

> `rand()` 生成的随机数是伪随机的，这意味着它们是通过一个确定的算法生成的。因此，如果你每次运行程序时都调用 `rand()`，生成的随机数序列将是相同的。为了解决这个问题，可以使用 `srand()` 函数来设定一个种子值，从而影响 `rand()` 的生成序列。

`srand()` 函数的原型如下：

```c
#include <stdlib.h>

void srand(unsigned int seed);
```

`seed` 参数用于初始化随机数生成器。通常，使用当前时间作为种子值可以确保每次运行程序时生成的随机数序列不同。

#### 示例代码

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    // 用当前时间作为种子
    srand((unsigned int)time(NULL));

    // 生成并打印随机数
    printf("随机数：%d\n", rand());
    return 0;
}
```

在这个例子中，`time(NULL)` 返回当前时间，以秒为单位。将它转换为 `unsigned int` 类型后传给 `srand()`，这样每次运行程序时，`rand()` 生成的序列都将不同。

### 总结

- `rand()` 用于生成伪随机数。
- `srand()` 用于设置随机数生成器的种子，以便生成不同的随机数序列。
- 通常将 `srand()` 与 `time(NULL)` 一起使用，以确保每次运行程序时生成的随机数序列不同。

---

## <p align="center">`assert` 断言</p>

> `assert` 是 C 语言中用于进行断言检查的宏，主要用于调试程序。它可以在程序运行时验证某个条件是否为真。如果条件为假，`assert` 宏会使程序终止，并输出错误信息。

以下是 `assert` 宏的一些主要特点和用法：

### 引入头文件

使用 `assert` 宏需要引入头文件 `assert.h`：

```c
#include <assert.h>
```

### 使用 `assert` 宏

`assert` 宏的语法如下：

```c
assert(expression);
```

其中 `expression` 是一个可以计算为布尔值的表达式。如果 `expression` 为假，`assert` 会触发一个错误并终止程序。

### 示例代码

以下是一个使用 `assert` 的简单示例：

```c
#include <stdio.h>
#include <assert.h>

int main() {
    int a = 5;
    int b = 0;

    assert(b != 0); // 如果 b 为 0，程序将终止，并输出错误信息

    int c = a / b;  // 这行代码不会被执行，因为上面的断言会失败
    printf("c = %d\n", c);

    return 0;
}
```

运行上面的代码会输出类似如下的错误信息，并终止程序：

```
Assertion failed: (b != 0), file main.c, line 8
```

### 断言在调试和发布版本中的差异

`assert` 宏在调试过程中非常有用，但在发布版本中通常会被禁用。可以通过定义 `NDEBUG` 宏来禁用所有 `assert` 语句：

```c
#define NDEBUG
#include <assert.h>
```

一旦定义了 `NDEBUG`，所有的 `assert` 语句将不再进行检查。这对于发布版本可以提高程序的性能。

### 总结

> `assert` 宏是一个非常有用的工具，可以帮助开发者在调试过程中验证程序的假设和不变量。虽然它在发布版本中通常会被禁用，但在开发阶段它可以有效地捕获并报告许多潜在的错误。

---

## 链式访问`printf`函数

```c
#include <stdio.h>

int main() {
    printf("The message 'Hello, world!' has %d characters.\n", printf("Hello, world!\n"));
    return 0;
}
```

打印结果:

```
Hello, world!
The message 'Hello, world!' has 14 characters.
```

---

## <p align="center">变量类型的输入和输出</p>

> 在 C 语言中，`scanf()` 和 `printf()` 函数是非常基础且广泛使用的输入和输出函数。它们都使用格式化字符串来指定或解析数据的类型。下面是一些最常用的格式说明符和它们的用途：

### 对于 `printf()`

- `%d` 或 `%i`: 用于打印一个带符号的整数（`int`类型）。
- `%u`: 用于打印一个无符号整数（`unsigned int`类型）。
- `%f`: 用于打印一个浮点数（`float`或`double`），默认情况下会包含 6 位小数。
- `%lf`: 用于打印`double`类型的浮点数，`float`在使用`printf`时也可以用`%f`。
- `%e` 或 `%E`: 用于以科学计数法打印浮点数。
- `%g` 或 `%G`: 自动选择`%f`或`%e`（`%E`），取决于数值（更自然的表示方式）。
- `%c`: 用于打印一个单个字符（`char`类型）。
- `%s`: 用于打印一个字符串（以空字符`'\0'`结尾的字符数组）。
- `%p`: 用于打印一个指针的值（通常是内存地址，以十六进制表示）。
- `%x` 或 `%X`: 用于以十六进制数格式打印无符号整数。
- `%%`: 用于打印`%`字符本身。

### 对于 `scanf()`

- `%d`: 读取一个带符号的整数（`int`）。
- `%u`: 读取一个无符号整数（`unsigned int`）。
- `%f`: 读取一个浮点数（`float`）。对于`double`类型应使用`%lf`。
- `%lf`: 读取`double`类型的浮点数。
- `%c`: 读取一个字符。
- `%s`: 读取一个字符串，直到碰到空白字符（空格、制表符、换行等）为止。
- `%x` 或 `%X`: 读取一个十六进制数存为无符号整数。
- `%p`: 读取一个指针（地址）。

### 注意

> - 在使用`scanf()`时，对于大部分数据类型，需要在变量名前加上`&`字符（取地址操作符），来获取该变量的内存地址，使`scanf()`能正确写入值。例如: `scanf("%d", &myInt);`。但对于字符串（`%s`）不需要使用`&`，因为字符串名本身就表示地址。

> - `scanf("%[^\n]", str);`可以用来读取一行文本，直到按下 Enter 键为止（不包括`\n`），这里的`str`是一个字符数组。

---

## <p align="center">隐式类型转换和整型提升</p>

### 隐式类型转换

> 隐式类型转换（implicit type conversion），也称为自动类型转换（automatic type conversion），是指在不同类型的数据进行运算或赋值时，编译器自动将一种类型转换为另一种类型，以确保操作的合法性和正确性。

#### 规则

1. **从小范围类型到大范围类型**：
   小范围类型可以自动转换为大范围类型。例如，`int` 可以隐式转换为 `float`，`float` 可以隐式转换为 `double`。

   ```c
   int i = 10;
   float f = i; // int 自动转换为 float
   ```

2. **算术运算符**：
   当不同类型的数据进行算术运算时，编译器会将它们转换为同一种类型。例如，`int` 和 `float` 相加时，`int` 会被转换为 `float`。

   ```c
   int i = 5;
   float f = 3.5;
   float result = i + f; // int 自动转换为 float
   ```

3. **赋值运算**：
   赋值运算符会尝试将右侧的值转换为左侧变量的类型。例如，`float` 赋值给 `int` 时，编译器会进行类型转换，但这种转换可能会导致精度丢失。

   ```c
   float f = 3.9;
   int i = f; // float 转换为 int，精度丢失，i 的值为 3
   ```

### 整型提升（Integer Promotion）

整型提升是指将小于 `int` 大小的整型数据（如 `char` 和 `short`）提升为 `int` 或 `unsigned int` 类型，以便进行运算。这是为了保证运算的结果在当前平台上至少具有 `int` 类型的精度。

#### 规则

1. **提升规则**：

   - 如果所有的值能用 `int` 表示（即没有溢出），则转换为 `int`。
   - 否则，转换为 `unsigned int`。

2. **运算中的提升**：
   在表达式中，如果存在 `char` 或 `short` 类型的数据，它们会先被提升为 `int` 再进行运算。

   ```c
   char c = 1;
   short s = 2;
   int result = c + s; // char 和 short 被提升为 int 再进行加法运算
   ```

#### 示例

以下是一个整型提升的示例：

```c
#include <stdio.h>

int main() {
    char a = 10;
    char b = 20;
    int result = a + b; // a 和 b 被提升为 int
    printf("Result: %d\n", result);
    return 0;
}
```

在这个示例中，`a` 和 `b` 都是 `char` 类型，但在进行加法运算时，它们会先被提升为 `int`，所以 `result` 的值是 `30`。

### 总结

> 隐式类型转换和整型提升是 C 语言中重要的特性，理解它们的规则对于避免潜在的错误和编写高效的代码非常重要。在实际编程中，尽量明确地进行类型转换（使用强制类型转换）可以提高代码的可读性和可维护性。

---

## <p align="center">无符号整型</p>

> 无符号整数用于表示非负整数。在 C 语言中，无符号整数的类型有：

1. `unsigned char`：通常占用 1 个字节。
2. `unsigned short`：通常占用 2 个字节。
3. `unsigned int`：通常占用 4 个字节。
4. `unsigned long`：通常占用 4 个或 8 个字节。
5. `unsigned long long`：通常占用 8 个字节。

### 定义与初始化

```c
unsigned int u1 = 10;
unsigned long u2 = 1000UL;
```

### 使用

无符号整数可以进行普通的算术和位运算，和有符号整数一样。

```c
unsigned int x = 5, y = 3;
unsigned int result = x + y; // result 为 8
```

### 注意事项

1. **溢出问题**：无符号整数在进行算术运算时，如果结果超出了该类型的表示范围，不会报错，而是回绕到零继续。

```c
unsigned int u = UINT_MAX;
u = u + 1; // u 变成 0
```

2. **避免负数**：无符号整数不能表示负数，任何负数赋值给无符号整数都会导致不可预料的结果。

```c
unsigned int u = -1; // u 会得到 UINT_MAX
```

- **无符号整数**用于非负整数，具有溢出和避免负数的问题。

---

## <p align="center">大端和小端存储</p>

> 大端存储（Big-endian）和小端存储（Little-endian）是计算机系统中数据存储的一种约定，主要用于描述多字节数据在内存中的存储方式。

### 大端存储（Big-endian）

> 在大端存储方式中，高位字节存储在低地址处，低位字节存储在高地址处。

比如，对于一个 32 位的整数 0x12345678，其在内存中的存储方式如下（假设从地址 0x00 开始存储）：

```
地址   值
0x00   0x12
0x01   0x34
0x02   0x56
0x03   0x78
```

### 小端存储（Little-endian）

> 在小端存储方式中，低位字节存储在低地址处，高位字节存储在高地址处。

同样，对于一个 32 位的整数 0x12345678，其在内存中的存储方式如下：

```
地址   值
0x00   0x78
0x01   0x56
0x02   0x34
0x03   0x12
```

### 示例代码

下面是一个简单的 C 语言示例代码，演示如何检查当前系统是大端还是小端存储：

```c
#include <stdio.h>

int main() {
    int a = 1;    //00000001大端，01000000小端
    char *p = (char *)&a;

    if (*p == 1) {
        printf("Little-endian\n");
    } else {
        printf("Big-endian\n");
    }

    return 0;
}
```

---

## <p align="center">操作符</p>

### 算术操作符

- **`+`**：加法。
- **`-`**：减法。
- **`*`**：乘法。
- **`/`**：除法。
- **`%`**：取模操作符。注意，`%` 两边必须是整数，否则会导致编译错误。

```c
int a = 10;
int b = 3;
int result = a % b; // result = 1
```

### 位移操作符

- **`<<`**：左移操作符。将左操作数的二进制位向左移动指定的位数，右边用 0 填充。
- **`>>`**：右移操作符。将左操作数的二进制位向右移动指定的位数。

```c
int a = 5;  // 二进制 00000101
int b = a << 1;  // b = 10, 二进制 00001010
int c = a >> 1;  // c = 2,  二进制 00000010
```

### 位操作符

- **`&`**：按位与。
- **`|`**：按位或。
- **`^`**：按位异或。
- **`~`**：按位取反。

```c
int a = 5;   // 二进制 00000101
int b = 3;   // 二进制 00000011
int c = a & b;  // c = 1, 二进制 00000001
int d = a | b;  // d = 7, 二进制 00000111
int e = a ^ b;  // e = 6, 二进制 00000110
int f = ~a;     // f = -6, 二进制 11111010 (假设是8位整数)
```

### 三目操作符

- 语法：`condition ? expr1 : expr2;`
- 如果 `condition` 为真，返回 `expr1`，否则返回 `expr2`。

```c
int a = 10;
int b = 20;
int max = (a > b) ? a : b; // max = 20
```

### 逻辑操作符

- **`&&`**：逻辑与。若两个操作数均为真，则结果为真。
- **`||`**：逻辑或。若任一操作数为真，则结果为真。
- **`!`**：逻辑非。取反。

```c
int a = 1;
int b = 0;
int result1 = a && b; // result1 = 0 (假)
int result2 = a || b; // result2 = 1 (真)
int result3 = !a;     // result3 = 0 (假)
```

### 逗号表达式

- 逗号表达式会依次计算所有操作数，并返回最后一个操作数的值。

```c
int a, b;
a = (b = 3, b + 2); // b = 3, a = 5
```

### 下标操作符 `[]`

- 用于数组元素的访问。  
  下标操作符 [] 在 C 语言中用于访问数组元素。实际上，a[i] 是通过指针算术来实现的。它的等价形式是 \*(a + i)

```c
int arr[5] = {1, 2, 3, 4, 5};
int x = arr[2]; // x = 3
```

### 结构体操作符

- **`.`**：用于访问结构体成员。
- **`->`**：用于通过指向结构体的指针访问结构体成员。

```c
struct Point {
    int x;
    int y;
};

struct Point p;
p.x = 10;
p.y = 20;

struct Point *ptr = &p;
int x = ptr->x; // x = 10
int y = ptr->y; // y = 20
```

---

## <p align="center">问题表达式</p>

> 在 C 语言中，某些表达式可能会产生不唯一的运算结果，这通常是因为表达式中包含了副作用（side effects）或者运算顺序未定义的情况。常见的有以下几种情况：

1. **未定义行为（Undefined Behavior）**：

   - 当代码执行结果未被 C 标准定义时，结果可能是不确定的。例如：
     ```c
     int i = 0;
     i = i++;
     ```
     上面的代码中，`i = i++` 表达式的结果是未定义的，因为 `i++` 和 `i` 的赋值操作顺序未定义，不同编译器可能会产生不同的结果。

2. **顺序点问题（Sequence Points）**：

   - C 语言中有些操作的顺序点是未定义的。例如：
     ```c
     int a = 10;
     int b = a++ + a++;
     ```
     在上面的代码中，`a++` 的副作用顺序未定义，不同编译器在不同环境下可能会产生不同的结果。

3. **短路求值（Short-circuit Evaluation）**：

   - 在逻辑运算中，短路求值会导致部分表达式未被执行，从而使结果不唯一。例如：
     ```c
     int a = 1;
     int b = (a == 1) || (a = 2);
     ```
     在这个例子中，如果 `a == 1` 为真，整个表达式将短路，`a = 2` 将不会执行。但如果 `a == 1` 为假，`a = 2` 将会执行，从而改变 `a` 的值。

4. **宏定义中的副作用（Side Effects in Macros）**：
   - 宏定义中，如果包含副作用，会导致运算结果不唯一。例如：
     ```c
     #define SQUARE(x) (x * x)
     int a = 5;
     int b = SQUARE(a++);
     ```
     在这个例子中，宏 `SQUARE(a++)` 会扩展为 `(a++ * a++)`，其行为未定义，因为 `a++` 的副作用顺序未定义。

**避免不唯一结果的建议：**

> - **避免在同一个表达式中多次修改同一个变量**。
> - **在复杂表达式中使用临时变量**。
> - **理解并遵守 C 语言的顺序点规则**。
> - **小心使用宏定义，尽量使用函数来替代复杂的宏**。

## <p align="center">短路求值（与和或的运算）</p>

> 短路求值（short-circuit evaluation）是指在布尔表达式中，当整个表达式的值已经可以确定时，程序不会继续计算剩余部分的技术。C 语言中的逻辑运算符 `&&` 和 `||` 都使用了短路求值。

### 逻辑与运算符 `&&`

逻辑与运算符 `&&` 在求值时，如果左操作数为 `false`，则整个表达式结果必为 `false`，因此不会计算右操作数。例如：

```c
int a = 0;
int b = 1;
if (a && b) {
    // 此处的代码不会执行，因为 a 为 0 (false)
}
```

在上面的例子中，`a` 为 `0`（即 `false`），所以 `a && b` 的结果为 `false`，程序不会计算 `b` 的值，也不会执行 `if` 语句内部的代码。

### 逻辑或运算符 `||`

逻辑或运算符 `||` 在求值时，如果左操作数为 `true`，则整个表达式结果必为 `true`，因此不会计算右操作数。例如：

```c
int a = 1;
int b = 0;
if (a || b) {
    // 此处的代码会执行，因为 a 为 1 (true)
}
```

在上面的例子中，`a` 为 `1`（即 `true`），所以 `a || b` 的结果为 `true`，程序不会计算 `b` 的值，而是直接执行 `if` 语句内部的代码。

### 短路求值的副作用

由于短路求值的特性，右操作数的副作用（如函数调用、变量赋值等）可能不会执行。这一点在编写代码时需要特别注意。例如：

```c
int a = 1;
int b = 0;
if (a || (b = 2)) {
    // b 的值不会被修改，因为 a 为 true，短路求值生效
}
```

在这个例子中，`(b = 2)` 这个赋值操作不会执行，因为 `a` 为 `true`，整个表达式已经可以确定为 `true`，所以不会再计算右操作数。

### 实例：逻辑与运算中的短路求值

```c
#include <stdio.h>

int main() {
    int a = 0;
    int b = 1;
    if (a && (b = 2)) {
        // 这段代码不会执行
    }
    printf("a = %d, b = %d\n", a, b); // 输出: a = 0, b = 1
    return 0;
}
```

在这个例子中，由于 `a` 为 `0`（即 `false`），`a && (b = 2)` 短路求值，`(b = 2)` 不会执行，所以 `b` 的值保持不变。

### 实例：逻辑或运算中的短路求值

```c
#include <stdio.h>

int main() {
    int a = 1;
    int b = 0;
    if (a || (b = 2)) {
        // 这段代码会执行
    }
    printf("a = %d, b = %d\n", a, b); // 输出: a = 1, b = 0
    return 0;
}
```

在这个例子中，由于 `a` 为 `1`（即 `true`），`a || (b = 2)` 短路求值，`(b = 2)` 不会执行，所以 `b` 的值保持不变。

---

# 🌘 循环

## <p align="center">`for` 循环</p>

> 在 C 语言中，`for` 循环是一种控制流语句，它允许代码多次执行，直到指定条件为假。`for` 循环非常灵活，常用于循环遍历数组、执行固定次数操作等场景。

`for` 循环的基本语法如下：

```c
for (初始化语句; 循环条件; 更新语句)
{
    // 循环体
}
```

- **初始化语句**：在循环开始前执行一次。通常用于初始化一个或多个循环控制变量。

- **循环条件**：在每次循环开始前评估。如果条件为真（非零），则执行循环体。如果条件为假（0），则循环结束。

- **更新语句**：在每次循环体执行后执行。通常用于更新循环控制变量。

- **循环体**：如果循环条件为真，这部分代码会被执行。

### 执行顺序

考虑如下的`for`循环例子：

```c
for (int i = 0; i < 5; i++) {
    printf("%d\n", i);
}
```

执行顺序如下：

1. **初始化语句**：首先执行一次初始化语句，这里是`int i = 0;`。

2. **循环条件检查**：然后检查循环条件，这里是`i < 5;`。这是一个布尔表达式，如果表达式的结果为真（即非零），循环继续；如果为假（即 0），循环结束。

3. **循环体执行**：如果循环条件为真，则执行循环体内的语句，这里是`printf("%d\n", i);`。

4. **更新语句执行**：接下来执行更新语句，这里是`i++`。更新语句执行后，会再次回到步骤 2，检查循环条件。

> 这个过程会重复，直到循环条件变为假。在上述例子中，循环会打印数字 0 到 4，每次循环`i`都会增加 1，当`i`增加到 5 时，循环条件`i < 5`变为假，因此循环结束。

### 注意

> - 在`for`循环的三个部分（初始化语句、循环条件、更新语句），任何一个都可以省略，但是两个分号是必需的。如果省略循环条件，则默认为“真”，这样的循环将无限循环，直到被`break`语句显式退出。
> - 循环体可以包含多条语句，但如果只有一条语句，大括号可以省略。然而，推荐始终使用大括号以提高代码的清晰度和易维护性。

---

## <p align="center">`while`和`do while`循环</p>

> 在 C 语言中，`while` 循环和 `do-while` 循环是用来在满足指定的条件时重复执行一段代码的控制结构。

### 1. `while` 循环

> `while` 循环首先评估条件表达式，如果条件为真（非零），则执行循环体。每执行一次循环体后，再次检查条件表达式。如果条件仍为真，循环继续执行。这个过程重复进行，直到条件表达式为假（零）。

**语法：**

```c
while (condition) {
    // 循环体
}
```

**示例：**

```c
#include <stdio.h>

int main() {
    int i = 0;
    while (i < 5) {
        printf("%d\n", i);
        i++;
    }
    return 0;
}
```

在这个例子中，只要 `i` 小于 5，`while` 循环就会继续执行。循环每次执行都会输出 `i` 的值然后增加 `i`。

### 2. `do-while` 循环

> 与 `while` 循环不同，`do-while` 循环首先执行一次循环体，然后检查条件。如果条件为真，则继续执行循环体。这意味着 `do-while` 循环至少会执行一次循环体，无论条件初次是否为真。

**语法：**

```c
do {
    // 循环体
} while (condition);
```

**示例：**

```c
#include <stdio.h>

int main() {
    int i = 0;
    do {
        printf("%d\n", i);
        i++;
    } while (i < 5);
    return 0;
}
```

在这个例子中，即使 `i` 初始值不满足循环条件，`do-while` 循环体中的代码也至少执行一次。这里的初次执行仍然会发生，因为循环体的执行优先于条件判断。

### 总结

> 选择 `while` 循环还是 `do-while` 循环主要取决于你是否至少需要执行一次循环体（即使用 `do-while`）。如果条件从一开始就是假，则 `while` 循环不会执行任何循环迭代，而 `do-while` 循环会执行至少一次。

---

# 🌗 字符串

## <p align="center">strcmp 函数：比较字符串</p>

> `strcmp`是一个 C 语言库函数，用于比较两个字符串。它的声明可以在`<string.h>`头文件中找到。

`strcmp`函数的原型为：

```c
int strcmp(const char *s1, const char *s2);
```

> `strcmp` 的工作原理是通过比较两个字符串 `s1` 和 `s2` 的每个字符，按字典序进行大小比较。如果字符串相等，返回 0；如果`s1`在字典序中比`s2`小，则返回负值；反之，返回正值。

这里是一个简单的示例：

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "hello";
    char str2[] = "world";
    char str3[] = "hello";

    int result1 = strcmp(str1, str2);  // 返回负值，因为 "hello" < "world"
    int result2 = strcmp(str1, str3);  // 返回0，因为 "hello" == "hello"

    printf("Result of strcmp(str1, str2): %d\n", result1);
    printf("Result of strcmp(str1, str3): %d\n", result2);

    return 0;
}
```

> **注意**：当比较字符串的时候，不要直接使用 `= =` 运算符，因为 `= =` 是比较两个指针是否指向相同的内存地址。在这种情况下，请使用 `strcmp` 函数来正确处理两个字符串之间的比较。

### 模拟实现`strcmp`函数

> 我们可以编写自己的`my_strcmp`函数来模仿标准库中的`strcmp`函数。这个函数将逐个比较两个字符串的字符，直到它们的字符不同或到达字符串的结尾。

下面是一个示例实现：

```c
#include <stdio.h>

int my_strcmp(const char *s1, const char *s2) {
    // 比较字符串的每个字符
    while (*s1 && (*s1 == *s2)) {
        s1++;
        s2++;
    }
    // 返回差值
    return *(unsigned char *)s1 - *(unsigned char *)s2;
}

int main() {
    char str1[] = "hello";
    char str2[] = "world";
    char str3[] = "hello";

    int result1 = my_strcmp(str1, str2);  // 返回负值，因为 "hello" < "world"
    int result2 = my_strcmp(str1, str3);  // 返回0，因为 "hello" == "hello"

    printf("Result of my_strcmp(str1, str2): %d\n", result1);
    printf("Result of my_strcmp(str1, str3): %d\n", result2);

    return 0;
}
```

**解释:**

- **参数**：`const char *s1, const char *s2` 是指向要比较的两个字符串的指针。
- **循环**：`while (*s1 && (*s1 == *s2))`：
  - 只要两个字符串的当前字符相等且不为 `\0`（字符串结束符），循环将继续。
  - 如果当前字符相等，指针将前进到下一个字符。
- **返回差值**：如果两个字符串在某一位置不同，返回它们的字符差值。这将决定哪个字符串在字典序中更小或更大。如果两个字符串完全相等，返回 0。

这个 `my_strcmp` 函数在功能上与标准库中的 `strcmp` 函数相同。

---

## <p align="center">`strlen`函数</p>

> `strlen` 函数是 C 标准库中的一个函数，用于计算字符串的长度。它的原型定义在 `<string.h>` 头文件中。`strlen` 函数返回字符串的长度，不包括字符串结尾的空字符 `\0`。

### 函数原型

```c
size_t strlen(const char *str);
```

### 参数

- `str`: 指向要计算长度的字符串的指针。

### 返回值

- 返回字符串 `str` 的长度（不包括结尾的空字符 `\0`）。

### 示例代码

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hello, world!";
    size_t length = strlen(str);
    printf("The length of the string is: %zu\n", length);
    return 0;
}
```

**解释:**

- 在上面的代码中，我们首先包含了 `stdio.h` 和 `string.h` 头文件。
- 然后，我们定义了一个字符串 `str`，其内容为 `"Hello, world!"`。
- 使用 `strlen` 函数计算字符串的长度，并将结果存储在 `length` 变量中。
- 最后，使用 `printf` 函数输出字符串的长度。

### 注意事项

> - `strlen` 函数只适用于以空字符结尾的 C 字符串。如果字符串没有以空字符结尾，函数会一直读取内存，直到遇到一个空字符，可能导致未定义行为。
> - 确保传递给 `strlen` 的指针不是 `NULL`，否则会导致段错误（segmentation fault）。

### `strlan`函数的返回值(unsigned int)

```c
int main()
{
    if (strlen("abc") - strlen("abcdef") > 0)
    {
        printf(">\n");
    }
    else
    {
        printf("<=\n");
    }
    return 0;
}
```

- **`strlen` 返回值的类型**：

  > `strlen` 函数返回一个 `size_t` 类型的值，这是一个无符号整数。在代码中，`strlen("abc") - strlen("abcdef")` 可能会导致未定义行为，因为在计算两个无符号整数的差值，而结果可能是一个负数，负数在无符号整数中表示一个非常大的数。

- **逻辑错误**：
  > `strlen("abc")` 的结果是 3，而 `strlen("abcdef")` 的结果是 6。由于 `size_t` 类型是无符号的，所以 `strlen("abc") - strlen("abcdef")` 实际上会是一个非常大的无符号数（在大多数系统上，这个值大约是 `-3` 的补码表示）。因此，条件 `strlen("abc") - strlen("abcdef") > 0` 将始终为真，`printf(">")` 将总是执行。

### 模拟实现 `strlen` 函数

> 要在 C 语言中实现 `strlen` 函数，我们需要遍历字符串，直到遇到空字符 `'\0'`，并计算字符的数量。以下是 `strlen` 函数的模拟实现：

```c
#include <stdio.h>

size_t my_strlen(const char *str) {
    size_t length = 0;
    while (str[length] ! = '\0') {
        length++;
    }
    return length;
}

int main() {
    const char *testStr = "Hello, World!";
    printf("Length of the string \"%s\" is %zu.\n", testStr, my_strlen(testStr));
    return 0;
}
```

#### 代码解释

1. **函数声明**:

   ```c
   size_t my_strlen(const char *str);
   ```

   - `const char *str`: 函数参数是一个指向字符数组（字符串）的指针，`const` 表示我们不会修改字符串内容。
   - `size_t`: 返回值类型，通常用于表示对象的大小。

2. **函数实现**:

   ```c
   size_t my_strlen(const char *str) {
       size_t length = 0;
       while (str[length] ! = '\0') {
           length++;
       }
       return length;
   }
   ```

   - `size_t length = 0;`: 初始化一个变量 `length` 用于计数。
   - `while (str[length] != '\0') { length++; }`: 循环遍历字符串，直到遇到空字符 `'\0'`。
   - `return length;`: 返回字符串的长度。

3. **测试函数**:
   ```c
   int main() {
       const char *testStr = "Hello, World!";
       printf("Length of the string \"%s\" is %zu.\n", testStr, my_strlen(testStr));
       return 0;
   }
   ```
   - `const char *testStr = "Hello, World!";`: 定义一个测试字符串。
   - `printf(...)`: 打印测试字符串及其长度。

#### 运行结果

程序运行后会输出：

```txt
Length of the string "Hello, World!" is 13.
```

---

## <p align="center">`strcpy`函数</p>

> `strcpy` 是 C 语言中的一个标准库函数，用于将一个字符串复制到另一个字符串中。它定义在 `<string.h>` 头文件中。

`strcpy` 的原型如下：

```c
char *strcpy(char *dest, const char *src);
```

### 参数

- `dest`：目标字符串的指针。复制的内容将放置在这里。
- `src`：源字符串的指针，即要复制的字符串。

### 返回值

`strcpy` 函数返回目标字符串 `dest` 的指针。

### 功能

`strcpy` 会将 `src` 指向的字符串复制到 `dest` 指向的数组中，包括终止 null 字符（`\0`）。

### 使用注意

> 使用 `strcpy` 时需要确保目标数组 `dest` 足够大，能够容纳源字符串 `src` 的所有字符，包括终止字符。如果 `dest` 的空间不足，可能会导致缓冲区溢出，这是常见的安全隐患。

### 示例

下面的示例展示了如何使用 `strcpy` 函数：

```c
#include <stdio.h>
#include <string.h>

int main() {
    char src[40] = "Hello, World!";
    char dest[40];

    strcpy(dest, src);

    printf("Copied string: %s\n", dest);

    return 0;
}
```

这个程序定义了两个字符数组 `src` 和 `dest`，使用 `strcpy` 将 `src` 的内容复制到 `dest`，然后打印 `dest` 的内容。

### 安全替代

> 由于 `strcpy` 无法检查目标缓冲区的大小，建议使用更安全的函数，如 `strncpy` 或 C11 引入的 `strcpy_s`，它们可以帮助预防缓冲区溢出。使用这些函数需要更多关注他们的参数和返回值，以确保用法正确。

### 模拟实现`strcpy`函数

```c
char *my_strcpy(char *dest, const char *src)
{
    assert(dest);
    assert(src);
    char *ret = dest;
    while (*dest++ = *src++)
        continue; //'\0'也能复制进去
    return ret;
}
```

---

## <p align="center">`strcat`函数</p>

> `strcat`函数是 C 标准库中的一个字符串操作函数，用于将一个字符串追加到另一个字符串的末尾。`strcat`函数将源字符串`src`的内容追加到目标字符串`dest`的末尾，覆盖目标字符串末尾的空字符（`'\0'`），并在追加后的结果字符串末尾添加一个空字符（`'\0'`）。

### 函数原型

```c
char *strcat(char *dest, const char *src);
```

### 参数

- `dest`：目标字符串，即要在其末尾追加内容的字符串。
- `src`：源字符串，即要追加到目标字符串末尾的字符串。

### 返回值

> 返回指向目标字符串`dest`的指针。

### 示例代码

```c
#include <stdio.h>
#include <string.h>

int main() {
    char dest[50] = "Hello, ";
    char src[] = "World!";

    strcat(dest, src);

    printf("%s\n", dest); // 输出 "Hello, World!"

    return 0;
}
```

### 注意事项

> - **内存安全**：`dest`数组必须足够大，能够容纳追加后的字符串。否则，会导致缓冲区溢出，可能引发未定义行为或程序崩溃。
> - **源字符串不可修改**：`src`字符串通常是`const`修饰的，意味着它的内容不会被`strcat`函数修改。
> - **字符串末尾的空字符**：确保`dest`和`src`字符串都正确地以空字符`'\0'`结尾，否则会导致未定义行为。

### 实现原理

`strcat`函数的实现原理可以概述如下：

- 找到`dest`字符串的末尾，即第一个空字符的位置。
- 从`src`字符串的开头开始，将每个字符复制到`dest`字符串的末尾位置。
- 复制完成后，在追加的内容末尾添加一个空字符`'\0'`。

### 模拟实现`strcat`函数

```c
char *my_strcat(char *dest, const char *src)
{
    char *d = dest;
    // 找到dest的末尾
    while (*dest++)
        continue;
    d--;
    // 复制src到dest的末尾
    while (*dest++ = *str++)
        continue;
    return d;
}
```

优化：可以自己加自己

```c
char *my_strcat(char *dest, const char *src)
{
    char *d = dest;
    // 找到dest的末尾
    while (*dest++)
        continue;
    char *p = --d;
    // 复制src到dest的末尾
    while (*dest++ = *str++)
        if (str == p)
        {
            rest++ = '\0';
            break;
        }
    return d;
}
```

---

## <p align="center">字符串面值</p>

> 在 C 语言中，指针之间的相等性取决于它们所指向的内存地址。对于字符串和数组的处理，情况会稍有不同。

### 字符串字面值

当你在 C 语言中创建两个指向同一个字符串字面值的指针，例如：

```c
const char *s1 = "abcd";
const char *s2 = "abcd";
```

> 在大多数情况下（尤其是大多数现代编译器优化的情况下），`s1` 和 `s2` 可能会指向相同的内存地址，因为编译器会优化存储，使得相同的字符串字面值只存储一份，从而减少程序的内存占用。但这种行为并非 C 语言标准所规定，而是编译器选择实施的一种优化。

### 数组存储

对于数组而言，情况则完全不同。考虑以下代码：

```c
char a1[] = "abcd";
char a2[] = "abcd";
```

> 这里，`a1` 和 `a2` 都是数组，它们各自在内存中独立存储了一份字符串的副本。即使这两个数组的内容完全相同，它们也位于内存的不同位置，因此他们的地址是不一样的。你可以通过比较他们的首地址来看到这一点：

```c
printf("%p\n", (void*)a1);
printf("%p\n", (void*)a2);
```

这会打印出两个不同的地址。

### 总结

> - **字符串字面值**：多个指向相同字符串字面值的指针可能指向相同的内存地址（取决于编译器的优化）。
> - **数组**：即使两个数组包含相同的数据，它们也会被存储在不同的内存地址中。

---

# 🌓 数组

## <p align="center">一维数组（int）</p>

> 在 C 语言中，一继维数组是同类型元素的集合，这些元素在内存中连续存储。

### 数组的声明

数组声明的一般形式如下：

```c
type arrayName[arraySize];
```

其中：

- `type` 是数组元素的数据类型。
- `arrayName` 是数组的名称。
- `arraySize` 是数组可以存储的元素数量，必须是一个大于 0 的整数常量表达式。

例如，声明一个可以存储 10 个整数的数组：

```c
int numbers[10];
```

### 数组的初始化

数组可以在声明时进行初始化。有几种不同的方式来初始化数组：

1. **明确初始化所有元素**：

   ```c
   int numbers[5] = {1, 2, 3, 4, 5};
   ```

2. **部分初始化**：

   如果初始化时未提供足够的元素，未初始化的元素将被自动设置为 0。

   ```c
   int numbers[5] = {1, 2}; // 后面的元素自动初始化为0
   ```

3. **无需指定数组大小**：

   如果在初始化数组时省略了大小，编译器会自动计算所需的大小。

   ```c
   int numbers[] = {1, 2, 3, 4, 5}; // 数组大小自动为5
   ```

### 注意事项

> - 数组的大小必须是编译时已知的常量表达式。
> - 数组下标是从 0 开始的，即第一个元素位于`arrayName[0]`，最后一个元素位于`arrayName[arraySize - 1]`。
> - 访问数组时，必须确保索引值不超出数组的界限，否则会产生未定义行为。

### 数组名和内存地址

数组名`arrayName`代表数组首元素的地址。例如，`numbers`代表上述数组的第一个元素`numbers[0]`的地址。

### 数组元素的访问

访问数组元素的一种常见方式是使用下标（或索引）。但是，也可以通过指针运算来访问。例如，考虑以下数组：

```c
int arr[10];
```

- 使用下标访问：`arr[9]`访问的是数组的第十个元素。

- 使用指针表达式：`*(arr + 9)`也访问的是数组的第十个元素。这里，`arr`是数组的首地址，`9`是要访问的元素相对于数组首地址的偏移量。因此，`arr+9`是第十个元素的地址，前面加上解引用操作符`*`后可以访问该位置的值。

### 其他细节

- **动态大小数组**（C99 及以后）：可以在运行时确定数组的大小，但这种数组的作用范围限定于定义它们的块。

  ```c
  int n = 10;
  int arr[n]; // C99及以后支持
  ```

- 在函数间传递数组时，实际上传递的是数组的首地址，因此在函数中对数组元素所做的更改将影响原数组。

- 数组作为数据结构非常简单，不支持插入、删除等操作。如果需要这些操作，应该考虑使用其他数据结构，如链表等。

---

## <p align="center">一维数组(char)</p>

> 在 C 语言中，`char` 类型数组通常用于处理字符串。字符串是一系列以 `null` 终止的字符。了解如何声明、初始化和操作 `char` 类型数组对于字符串处理非常重要。

### 声明 `char` 类型数组

声明 `char` 类型数组的语法与其他类型的数组相同：

```c
char arrayName[arraySize];
```

例如，声明一个可以存储 10 个字符的数组：

```c
char letters[10];
```

### 字符数组的初始化

- **使用字符常量初始化**：

  ```c
  char letters[5] = {'a', 'b', 'c', 'd', 'e'};
  ```

- **字符串初始化**：

  使用字符串常量来初始化字符数组：

  ```c
  char str[6] = "hello";
  ```

  需要注意的是，字符串常量自动包含一个 `null` 终止符 `\0`，所以这里数组大小必须是 6（包含终止符）。

- **省略数组大小**：

  让编译器自动确定数组大小：

  ```c
  char str[] = "hello"; // 自动大小为6
  ```

### 字符串操作函数

> C 标准库提供了一些用于处理字符串的函数。这些函数声明在 `<string.h>` 头文件中。

- **`strcpy`**: 复制字符串

  ```c
  char src[] = "hello";
  char dest[6];
  strcpy(dest, src);
  ```

- **`strcat`**: 连接字符串

  ```c
  char str1[11] = "hello";
  char str2[] = "world";
  strcat(str1, str2); // str1 现在是 "helloworld"
  ```

- **`strlen`**: 计算字符串长度

  ```c
  char str[] = "hello";
  int len = strlen(str); // len 是 5
  ```

- **`strcmp`**: 比较字符串

  ```c
  char str1[] = "hello";
  char str2[] = "world";
  int cmp = strcmp(str1, str2); // 返回负数，因为 "hello" 小于 "world"
  ```

### 注意事项

- **字符数组与字符串常量**：

  字符数组和字符串常量是不同的。字符串常量是只读的，而字符数组可以修改。

  ```c
  char str[] = "hello";  // 可修改
  char *str = "hello";   // 字符串常量，不可修改
  ```

- **数组越界**：

  访问或修改数组的边界之外的元素会导致未定义行为。

  ```c
  char str[5] = "hello"; // 错误，数组大小不足以容纳字符串和终止符
  ```

- **使用 `sizeof` 运算符**：

  使用 `sizeof` 运算符可以得到数组的大小（字节数），这与 `strlen` 不同。

  ```c
  char str[] = "hello";
  int size = sizeof(str); // size 是 6，包括终止符
  int len = strlen(str);  // len 是 5，不包括终止符
  ```

### 通过指针访问字符数组

与其他数组类型一样，可以通过指针访问字符数组。

```c
char str[] = "hello";
char *p = str;
char c = *(p + 1); // c 是 'e'
```

### `sizeof`计算一维数组大小

> 在 C 语言中，使用`sizeof`运算符可以帮我们计算出数组的总大小（以字节为单位）。这是常用来确定数组中有多少个元素的一种方法，特别是当我们不直接知道数组的长度时。

#### 基本用法

如果你有一个数组和一个二维数组，比如：

```c
int arr1[10];
int arr2[10][10];

```

使用`sizeof`计算这个数组的大小会得到整个数组占用的字节数。由于`int`通常是 4 字节（这取决于编译器和平台），所以这个数组的大小将是：

```c
sizeof(arr1); // 结果为 40 字节 (10 * 4)
sizeof(arr2); // 结果为 400 字节 (100 * 4)

```

#### 计算数组中元素的数量

如果你想计算数组中有多少个元素，你可以将数组的总大小除以单个元素的大小。例如：

```c
int totalElements = sizeof(arr1) / sizeof(arr[0]);
int totalElements = sizeof(arr2) / sizeof(arr[0][0]);

```

这里，`sizeof(arr1[0])`和`sizeof(arr[0][0])`计算的是数组中单个元素的大小，即一个`int`的大小。

#### 注意事项

> **指针和数组：**  
>  如果你传递 _一维数组_ 到一个函数，它实际上是传递了一个指向数组首元素的指针，而不是整个数组。因此，在函数内部使用`sizeof`在指针上并不会返回数组的总大小，而是返回指针的大小。  
>  同样，_二维数组_ 传入的是第一行数组的地址，而不是整个数组地址

例如：

```c
void func(int arr[]) {
    // 这里的 sizeof(arr) 将不会返回原数组的大小，而是返回指针的大小。
    int sizeOfPointer = sizeof(arr); // 通常是 4 或 8 字节，依据系统架构
}
```

- **动态分配的数组**: 对于动态分配的数组（例如，使用`malloc`），`sizeof`同样只会返回指针的大小，而不是动态分配的内存块的大小：

```c
int *arr = malloc(10 * sizeof(int));
int size = sizeof(arr); // 返回指针的大小，而不是40字节
```

在实际编程中，合理使用`sizeof`可以帮助我们更好地管理内存，尤其是处理数组和数据结构时。

### `arr`和`&arr`的区别

> 在 C 语言中，`&arr`和`arr`虽然都涉及数组，但它们的意义不同。

#### `arr` 和 `&arr` 的区别

1. **`arr`**:

   - 数组名`arr`本身在许多上下文中会被解释为指向数组第一个元素的指针。例如，如果你有一个数组`int arr[10]`，那么`arr`就相当于`&arr[0]`，是一个指向第一个元素的指针。
   - 当你对`arr`使用`sizeof`时，它会给你整个数组的大小（单位是字节）。

2. **`&arr`**:
   - `&arr`是数组的地址，但它的类型与`arr`不同。`&arr`是一个指向整个数组的指针，而不是指向数组第一个元素的指针。对于一个`int arr[10]`数组来说，`&arr`的类型是`int (*)[10]`。
   - 当你对`&arr`使用`sizeof`时，它会给你整个数组的大小（单位是字节），与`sizeof(arr)`相同。

#### 示例代码

让我们通过代码来展示它们之间的区别：

```c
#include <stdio.h>

int main() {
    int arr[10];

    // 数组的大小
    printf("sizeof(arr) = %zu\n", sizeof(arr));           // 输出40，数组的总大小

    // 数组第一个元素的大小
    printf("sizeof(arr[0]) = %zu\n", sizeof(arr[0]));     // 输出4，一个int的大小

    // 数组中元素的数量
    printf("Number of elements = %zu\n", sizeof(arr) / sizeof(arr[0])); // 输出10

    // &arr的大小
    printf("sizeof(&arr) = %zu\n", sizeof(&arr));         // 输出40，数组的总大小

    // &arr[0]的大小
    printf("sizeof(&arr[0]) = %zu\n", sizeof(&arr[0]));   // 输出8或4，指针的大小，依赖于系统架构

    return 0;
}
```

#### 解释

- `sizeof(arr)` 和 `sizeof(&arr)` 都返回整个数组的大小，单位是字节。
- `sizeof(arr[0])` 返回数组中第一个元素的大小，即一个`int`的大小。
- `sizeof(&arr[0])` 返回指向数组第一个元素的指针的大小，通常是 4 或 8 字节，取决于系统架构。

---

## <p align="center">二维数组</p>

### 二维数组的定义

> 二维数组是一种多维数组，它可以看作是数组的数组。在 C 语言中，二维数组可以用于存储矩阵或表格形式的数据。

```c
type arrayName[rows][cols];
```

- `type` 是数组元素的类型（如 `int`, `float`）。
- `arrayName` 是数组的名称。
- `rows` 是数组的行数。
- `cols` 是数组的列数。

例如，定义一个 `3x4` 的整数数组：

```c
int array[3][4];
```

### 二维数组的初始化

二维数组可以在声明时进行初始化，有几种不同的方式：

- **逐元素初始化**：

  ```c
  int array[3][4] = {
      {1, 2, 3, 4},
      {5, 6, 7, 8},
      {9, 10, 11, 12}
  };
  ```

- **部分元素初始化**：

  ```c
  int array[3][4] = {
      {1, 2},
      {5},
      {9, 10, 11}
  };
  ```

  未指定的元素将被初始化为 `0`。

- **自动计算行数**：
  ```c
  int array[][4] = {
      {1, 2, 3, 4},
      {5, 6, 7, 8}
  };
  ```
  行数可以省略，编译器将根据初始化列表的数量自动确定。

### 二维数组名

> 在 C 语言中，数组名本质上是一个指向数组第一个元素的指针。对于二维数组，数组名 `array` 是指向包含 `cols` 个元素的一维数组的指针。

因此：

- `array` 的类型是 `int (*)[4]`，表示指向包含 4 个整数的一维数组的指针。
- `array[0]` 是一个指向第一个元素（即一维数组 `array[0]`）的指针。
- `array[0][0]` 是数组中的第一个元素。

### 访问二维数组元素

通过指定行和列的索引来访问元素：

```c
int value = array[1][2]; // 访问第二行第三列的元素
array[2][3] = 15; // 修改第三行第四列的元素为15
```

### 注意事项

> - **内存布局**：二维数组在内存中是以行优先（Row-major order）方式存储的，这意味着数组的各行是连续存储的。
> - **边界检查**：C 语言不进行数组边界检查，访问越界的元素会导致未定义行为。
> - **指针与数组**：二维数组可以与指针结合使用，但需要注意指针的类型和内存的连续性。

### 其他细节

- **传递二维数组给函数**：

  ```c
  void printArray(int array[3][4], int rows, int cols) {
      for(int i = 0; i < rows; i++) {
          for(int j = 0; j < cols; j++) {
              printf("%d ", array[i][j]);
          }
          printf("\n");
      }
  }
  ```

- **动态分配二维数组**：

  ```c
  int** create2DArray(int rows, int cols) {
      int** array = (int**)malloc(rows * sizeof(int*));
      for(int i = 0; i < rows; i++) {
          array[i] = (int*)malloc(cols * sizeof(int));
      }
      return array;
  }

  void free2DArray(int** array, int rows) {
      for(int i = 0; i < rows; i++) {
          free(array[i]);
      }
      free(array);
  }
  ```

### 示例代码

```c
#include <stdio.h>
#include <stdlib.h>

void printArray(int array[3][4], int rows, int cols) {
    for(int i = 0; i < rows; i++) {
        for(int j = 0; j < cols; j++) {
            printf("%d ", array[i][j]);
        }
        printf("\n");
    }
}

int main() {
    int array[3][4] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };
    printArray(array, 3, 4);

    int** dynamicArray = create2DArray(3, 4);
    for(int i = 0; i < 3; i++) {
        for(int j = 0; j < 4; j++) {
            dynamicArray[i][j] = i * 4 + j + 1;
        }
    }
    free2DArray(dynamicArray, 3);

    return 0;
}
```

这个示例展示了如何定义、初始化、打印和动态分配二维数组。理解这些概念将帮助你更好地使用二维数组进行编程。

### 函数传递数组名来打印二维数组

```c
#include <stdio.h>

void print2(int (*p)[5], int r, int c)
{
    int i, j;
    for (i = 0; i < r; i++)
    {
        for (j = 0; j < c; j++)
        {
            printf("%d ", p[i][j]); // *(*(p+i)+j)也可以
        }
        printf("\n"); // 将 "\n" 移到了内循环后，以在打印每一行后换行
    }
}

int main()
{
    // 定义了一个数组 arr，并初始化了值
    int arr[3][5] = {{1, 2, 3, 4, 5},
                     {6, 7, 8, 9, 10},
                     {11, 12, 13, 14, 15}};
    print2(arr, 3, 5); // 修正了函数名称以匹配定义
    return 0;
}
```

### 用一维数组模拟二维数组

> 在 C 语言中，我们可以使用多个一维数组来模拟一个二维数组。比如，我们要模拟一个 3x3 的二维数组，我们可以使用 3 个一维数组，每个数组包含 3 个元素。

下面是一个简单的示例，展示如何使用多个一维数组来模拟一个 3x3 的二维数组，并打印出它的所有元素：

```c
#include <stdio.h>

int main() {
    // 定义三个一维数组，每个数组有 3 个元素
    int row0[3] = {1, 2, 3};
    int row1[3] = {4, 5, 6};
    int row2[3] = {7, 8, 9};

    // 使用一个指针数组来存储这三个一维数组的地址
    int *matrix[3] = {row0, row1, row2};

    // 打印二维数组的元素
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```

#### 代码说明：

> - **定义一维数组：**
>   我们定义了三个一维数组 `row0`, `row1`, `row2`，每个数组包含 3 个整数，分别代表二维数组的每一行。

> - **定义指针数组：**
>   我们定义了一个指针数组 `matrix`，该数组包含 3 个元素，每个元素都是指向一个一维数组的指针。这样，我们就可以使用 `matrix` 来访问模拟的二维数组的元素。

> - **打印二维数组元素：**
>   使用两个嵌套的 `for` 循环来遍历并打印二维数组的所有元素。外层循环遍历行，内层循环遍历列。

**输出结果：**

运行上述代码后，输出如下：

```
1 2 3
4 5 6
7 8 9
```

这样，我们就使用多个一维数组成功地模拟了一个二维数组，并打印了其中的所有元素。如果有更多行和列，可以按照相同的方法进行扩展。

---

# 🌖 指针

## <p align="center">地址运算符 `&`</p>

`&`是一个取址运算符，可以获取一个变量的内存地址。例如：

```c
int x = 10;
int *p = &x;
```

在这个例子中，`&x`取得了`x`的内存地址，然后将该地址赋值给指针`p`。这样，`p`就指向了`x`。

---

## <p align="center">解引用运算符 `*`</p>

`*`运算符还有另一个用途，称为解引用运算符。解引用一个指针就是获取该指针所指向的值。例如：

```c
int x = 10;
int *p = &x;
int y = *p;  // y的值现在是10
```

在这个例子中，`*p`返回了`p`所指向的值，也就是`x`的值。

这是指针和`*` `&`运算的基本概念，但实际在编程中会有更多细节需要注意，例如空指针、动态内存分配等等。

---

## <p align="center">针的详细讲解</p>指

### 指针的声明与定义

在 C 语言中，指针变量的声明语法如下：

```c
type *pointer_name;
```

其中，`type` 是指针所指向的变量的数据类型，`pointer_name` 是指针变量的名字。例如，声明一个指向整数的指针可以这样写：

```c
int *p;
```

### 指针的初始化

> 指针可以在声明的同时进行初始化，也可以在声明后再进行初始化。

```c
int a = 10;
int *p = &a;  // p 指向变量 a 的地址
```

在这个例子中，`&a` 返回变量 `a` 的地址，将其赋值给指针 `p`。

### 访问指针所指向的值

> 通过指针可以访问它所指向的变量的值，使用解引用操作符 `*`，

```c
int a = 10;
int *p = &a;

printf("%d\n", *p);  // 输出 10
```

在这个例子中，`*p` 获取 `p` 所指向的变量的值，即 `a` 的值。

### 指针的运算

> 指针可以进行一些运算，如加法和减法。指针加上一个整数，表示在内存地址上向后移动相应的字节数。

```c
int arr[5] = {1, 2, 3, 4, 5};
int *p = arr;

printf("%d\n", *(p + 2));  // 输出 3
```

在这个例子中，`p` 指向数组的第一个元素，通过 `p + 2` 可以访问数组的第三个元素。

### 常见的指针类型

- **空指针**：即 `NULL` 指针，它指向内存地址 0，一般用于初始化指针，表示指针目前不指向任何有效的内存地址。

  ```c
  int *p = NULL;
  ```

- **野指针**：未初始化的指针或已经释放了指向的内存的指针，被称为野指针。使用野指针会导致不可预知的行为。

  ```c
  int *p;  // 未初始化，可能指向未知地址
  ```

- **指向指针的指针**：即多级指针，可以指向另一个指针。例如：

  ```c
  int a = 10;
  int *p = &a;
  int **pp = &p;
  ```

### 指针与数组

> 数组名实际上是一个指向数组首元素的指针。

```c
int arr[5] = {1, 2, 3, 4, 5};
int *p = arr;

for (int i = 0; i < 5; i++) {
    printf("%d ", *(p + i));
}
// 输出：1 2 3 4 5
```

### 函数中的指针

> 指针在函数参数传递中非常有用，可以实现引用传递。

```c
void swap(int *x, int *y) {
    int temp = *x;
    *x = *y;
    *y = temp;
}

int a = 5, b = 10;
swap(&a, &b);
// 现在 a 的值是 10，b 的值是 5
```

在这个例子中，通过传递 `a` 和 `b` 的地址，实现了在函数内部交换 `a` 和 `b` 的值。

### 指针与动态内存分配

> 指针可以用来动态分配和释放内存。

```c
int *p = (int *)malloc(5 * sizeof(int));
if (p == NULL) {
    printf("Memory allocation failed\n");
    return 1;
}

// 使用 p 指向的动态内存

free(p);  // 释放动态内存
```

在这个例子中，`malloc` 分配了一块内存，`free` 用于释放分配的内存。

---

## <p align="center">指针的运算关系</p>

> 指针运算在 C 语言中是一个重要的概念。理解指针和运算符的结合使用非常重要，尤其是在操作指针时。我们将详细解释一下`*vp++`、`*--vp`、`(*vp)++`等操作。

### `*vp++`

这段代码首先会执行`vp++`操作，然后解引用该指针。具体步骤如下：

1. `vp++`：`vp`指针先指向原来的地址，然后指针增加。
2. `*`：解引用增加前的指针，获取该地址存储的值。

例如：

```c
int arr[] = {10, 20, 30};
int *vp = arr;
int value = *vp++;
```

- 初始时，`vp`指向`arr[0]`。
- 经过`vp++`后，`vp`指向`arr[1]`。
- `*vp++`取`vp`指向增加前的地址上的值，即`arr[0]`的值`10`。

### `*--vp`

这段代码首先会执行`--vp`操作，然后解引用该指针。具体步骤如下：

1. `--vp`：`vp`指针先减一。
2. `*`：解引用减一后的指针，获取该地址存储的值。

例如：

```c
int arr[] = {10, 20, 30};
int *vp = arr + 2;
int value = *--vp;
```

- 初始时，`vp`指向`arr[2]`。
- 经过`--vp`后，`vp`指向`arr[1]`。
- `*--vp`取`vp`指向减一后的地址上的值，即`arr[1]`的值`20`。

### `(*vp)++`

这段代码会首先解引用指针，获取指针所指向的值，然后对该值进行递增操作。具体步骤如下：

1. `*vp`：解引用指针，获取该地址存储的值。
2. `++`：对获取的值进行递增操作。

例如：

```c
int arr[] = {10, 20, 30};
int *vp = arr;
int value = (*vp)++;
```

- 初始时，`vp`指向`arr[0]`。
- `(*vp)++`先获取`arr[0]`的值，即`10`，然后对`arr[0]`的值递增，`arr[0]`变为`11`。
- `value`保存了`arr[0]`递增前的值，即`10`。

### 总结

- `*vp++`：先使用当前指向的值，然后指针移动到下一个地址。
- `*--vp`：先将指针移动到前一个地址，然后使用该地址的值。
- `(*vp)++`：先使用指针指向的值，然后对该值进行递增。

---

## <p align="center">指针 ➖ 指针</p>

> 在 C 语言中，指针减指针主要用于计算两个指针之间的元素个数。这个操作通常用于数组和指针的运算。具体来说，如果你有两个指向同一数组的指针，减去一个指针得到的是这两个指针之间的元素数量差值。

以下是详细的解释和示例：

### 语法

```c
ptrdiff_t diff = ptr1 - ptr2;
```

### 示例代码

```c
#include <stdio.h>

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int *ptr1 = &arr[3]; // 指向数组中第 4 个元素
    int *ptr2 = &arr[1]; // 指向数组中第 2 个元素

    // 计算指针差值
    ptrdiff_t diff = ptr1 - ptr2;

    // 输出结果
    printf("ptr1 - ptr2 = %td\n", diff); // 结果应该是 2

    return 0;
}
```

### 注意事项

> - **指针必须指向同一个数组**：只有当指针指向同一个数组时，减法操作才有意义。否则结果是未定义的。
> - **返回类型**：指针减指针的结果类型是 `ptrdiff_t`，这是一个有符号整数类型，定义在 `<stddef.h>` 中。
> - **单位是元素**：结果表示两个指针之间的元素数量，而不是字节数。

### 背后的原理

> 当你对两个指针进行减法操作时，编译器会根据指针所指向的数据类型来计算它们之间的差值。假设指针 `ptr1` 和 `ptr2` 都指向类型为 `int` 的数组中的元素，那么 `ptr1 - ptr2` 的结果就是它们之间的 `int` 元素的个数。

---

## <p align="center">指针的加减操作</p>

> 在 C 语言中，指针的运算包括加法和减法，这些运算在操作数组和动态内存分配时非常有用。下面我们来详细讲解一下指针的加法和减法。

### 指针的加法

> 指针的加法通常用于遍历数组。当我们对一个指针进行加法操作时，其实是对它所指向的内存地址进行偏移。

```c
int arr[5] = {1, 2, 3, 4, 5};
int *p = arr;

p = p + 1;
```

在这个例子中，`p`最初指向`arr[0]`，当`p = p + 1`之后，`p`指向`arr[1]`。这里需要注意的是，指针加法操作所增加的值是根据指针类型来决定的。例如，`int *p`指针加 1 实际上是增加了`sizeof(int)`个字节（通常是 4 个字节）。

### 指针的减法

> 指针的减法操作与加法类似，用于从一个地址向前移动。

```c
int arr[5] = {1, 2, 3, 4, 5};
int *p = arr + 3; // p指向arr[3]

p = p - 2;
```

在这个例子中，`p`最初指向`arr[3]`，当`p = p - 2`之后，`p`指向`arr[1]`。同样地，指针减法操作所减少的值也是根据指针类型来决定的。

### 指针与指针之间的减法

> 两个指针之间可以进行减法运算，这样的运算会返回两个指针之间的元素个数。

```c
int arr[5] = {1, 2, 3, 4, 5};
int *p1 = &arr[2];
int *p2 = &arr[4];

int diff = p2 - p1;
```

在这个例子中，`diff`的值为 2，因为`p2`和`p1`之间有两个`int`类型的元素。

### 示例代码

以下是一个完整的示例代码，演示了指针的加法和减法：

```c
#include <stdio.h>

int main() {
    int arr[5] = {1, 2, 3, 4, 5};
    int *p = arr; // p指向arr[0]

    printf("Initial address: %p, value: %d\n", (void*)p, *p);

    p = p + 2; // p指向arr[2]
    printf("After adding 2: %p, value: %d\n", (void*)p, *p);

    p = p - 1; // p指向arr[1]
    printf("After subtracting 1: %p, value: %d\n", (void*)p, *p);

    int *p1 = &arr[1];
    int *p2 = &arr[4];
    printf("Difference between p2 and p1: %ld\n", p2 - p1);

    return 0;
}
```

运行该代码将输出：

```
Initial address: 0x7ffee8a1c890, value: 1
After adding 2: 0x7ffee8a1c898, value: 3
After subtracting 1: 0x7ffee8a1c894, value: 2
Difference between p2 and p1: 3
```

---

## <p align="center">函数指针</p>

> 函数指针是 C 语言中的一种非常强大的工具，它允许你存储和调用函数，就像你可以用指针存储和访问变量一样。下面我们来详细了解函数指针的定义、使用和示例。

### 函数指针的定义

函数指针是指向函数的指针，其声明方式如下：

```c
return_type (*pointer_name)(parameter_list);
```

- `return_type` 是函数返回的类型。
- `pointer_name` 是指针的名字。
- `parameter_list` 是函数参数列表。

#### 示例

假设我们有一个简单的函数，它接受两个整数并返回它们的和：

```c
int add(int a, int b) {
    return a + b;
}
```

我们可以定义一个指向该函数的指针并使用它：

```c
#include <stdio.h>

// 定义一个函数指针类型
typedef int (*func_ptr)(int, int);

int add(int a, int b) {
    return a + b;
}

int main() {
    // 声明一个函数指针并初始化为函数 add
    func_ptr ptr = &add;

    // 使用函数指针调用函数
    int result = ptr(2, 3);
    printf("Result: %d\n", result);

    return 0;
}
```

在这个示例中，我们定义了一个类型 `func_ptr`，它是一个指向接受两个 `int` 参数并返回 `int` 的函数的指针。然后我们声明了一个 `func_ptr` 类型的变量 `ptr`，并将它初始化为函数 `add` 的地址。最后，我们使用 `ptr` 调用了 `add` 函数。

### 函数指针数组

函数指针数组可以用来存储多个函数指针。假设我们有几个数学运算函数：

```c
int add(int a, int b) { return a + b; }
int subtract(int a, int b) { return a - b; }
int multiply(int a, int b) { return a * b; }
int divide(int a, int b) { return a / b; }
```

我们可以声明一个函数指针数组并初始化它们：

```c
#include <stdio.h>

typedef int (*func_ptr)(int, int);

int add(int a, int b) { return a + b; }
int subtract(int a, int b) { return a - b; }
int multiply(int a, int b) { return a * b; }
int divide(int a, int b) { return a / b; }

int main() {
    // 声明并初始化函数指针数组
    func_ptr operations[4] = { add, subtract, multiply, divide };

    // 使用函数指针数组调用函数
    int a = 6, b = 3;
    for (int i = 0; i < 4; i++) {
        printf("Result: %d\n", operations[i](a, b));
    }

    return 0;
}
```

在这个示例中，我们创建了一个函数指针数组 `operations`，它包含了 `add`、`subtract`、`multiply` 和 `divide` 函数的指针。然后，我们遍历数组并调用每个函数指针。

### 函数指针用途：回调函数

> 函数指针在 C 语言中有多种用途，其中之一就是实现回调函数。回调函数是一种通过函数指针调用的函数，常用于设计灵活的 API 和库，使得代码可以在某些操作完成时调用用户自定义的函数。

#### 回调函数的用途

- **事件驱动编程**：在事件驱动编程中，回调函数通常用于处理事件，例如按钮点击、鼠标移动等。
- **信号处理**：在操作系统编程中，信号处理函数经常通过回调机制注册和调用。
- **排序和搜索**：例如，标准库中的 `qsort` 函数允许用户通过回调函数自定义排序的比较方式。
- **异步操作**：在网络编程或 I/O 操作中，回调函数可以用来处理异步操作完成后的任务。

#### 示例：使用回调函数的 `qsort`

以下是一个简单的例子，演示如何在 `qsort` 中使用回调函数自定义排序方式。

```c
#include <stdio.h>
#include <stdlib.h>

// 比较函数，用于按升序排序
int compare(const void *a, const void *b) {
    return (*(int*)a - *(int*)b);
}

int main() {
    int arr[] = {5, 2, 9, 1, 5, 6};
    int n = sizeof(arr) / sizeof(arr[0]);

    // 使用qsort进行排序，并传入比较函数compare作为回调函数
    qsort(arr, n, sizeof(int), compare);

    for(int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
    return 0;
}
```

在这个例子中，`compare` 函数作为回调函数被传递给 `qsort`，用于比较数组中的元素。`qsort` 根据 `compare` 函数的结果对数组进行排序。

#### 如何定义和使用回调函数

> 定义和使用回调函数的关键在于：
>
> 1. **定义函数指针类型**：指定函数指针的签名。
> 2. **声明和定义回调函数**：确保回调函数与函数指针类型匹配。
> 3. **传递回调函数**：将回调函数的指针作为参数传递给需要调用它的函数。

以下是一个更一般的例子，展示如何定义和使用回调函数：

```c
#include <stdio.h>

// 定义一个函数指针类型，指向返回类型为void，参数为int的函数
typedef void (*Callback)(int);

// 一个接受回调函数的函数
void performAction(int x, Callback callback) {
    printf("Performing action with %d\n", x);
    // 调用回调函数
    callback(x);
}

// 一个简单的回调函数
void myCallback(int y) {
    printf("Callback called with %d\n", y);
}

int main() {
    // 将回调函数传递给performAction函数
    performAction(5, myCallback);
    return 0;
}
```

在这个例子中，我们定义了一个 `Callback` 类型的函数指针，然后在 `performAction` 函数中接受并调用回调函数 `myCallback`。

### 函数指针数组

> 函数指针数组是一个数组，每个元素都是一个函数指针。

我们可以这样声明一个函数指针数组：

```c
return_type (*array_name[array_size])(parameter_list);
```

例如，一个包含 3 个函数指针的数组，每个指向返回 `int` 并接受两个 `int` 参数的函数，可以这样声明：

```c
int (*func_ptr_array[3])(int, int);
```

#### 示例代码

下面是一个完整的示例，展示了如何声明、初始化和使用函数指针数组：

```c
#include <stdio.h>

// 函数声明
int add(int a, int b) {
    return a + b;
}

int subtract(int a, int b) {
    return a - b;
}

int multiply(int a, int b) {
    return a * b;
}

int main() {
    // 声明一个函数指针数组
    int (*func_ptr_array[3])(int, int) = { add, subtract, multiply };

    // 调用函数指针数组中的函数
    int a = 5, b = 3;
    for (int i = 0; i < 3; i++) {
        printf("Result: %d\n", func_ptr_array[i](a, b));
    }

    return 0;
}
```

**输出**

```
Result: 8
Result: 2
Result: 15
```

> 在这个示例中，我们首先声明了三个函数 `add`、`subtract` 和 `multiply`，然后我们创建了一个函数指针数组 `func_ptr_array`，并将这些函数的地址赋给了数组元素。最后，通过循环，我们依次调用数组中的函数指针。

### 函数指针与指针数组与函数指针数组比较

#### 基本原理

- `int arr[]`数组
- `int (*arr)[]`数组指针

* `int *arr`指针
* `int (*arr)(int,int)`函数指针

- `int *arr[]`指针数组
- `int (*arr[])(int,int)`函数指针数组

* `int *(*arr)[]`指向指针数组的指针
* `int (*(*arr)[10])(int,int)`指向函数指针数组的指针

### 基于 sqsort 思想实现的冒泡排序算法

#### 排数

```c
void bubble_sort(void*base, int sz, int width, int(*cmp)(const void*e1, const void*e2))
{
    int i = 0;
    //趟数
    for (i = 0; i < sz - 1; i++)
    {
        int flag = 1;//假设数组已排好序
        //一趟冒泡排序的过程
        int j = 0;
        for (j = 0; j < sz - 1 - i; j++)
        {
            if (cmp((char*)base+j*width, (char*)base+(j+1)*width)>0)
            {
                //交换
                Swap((char*)base + j * width, (char*)base + (j + 1) * width, width);
            }
        }
        if (flag == 1)
        {
            break;
        }
    }
}



int cmp_int(const void* e1, const void* e2)
{
    return (*(int*)e1 - *(int*)e2);
}



void test3()
{
    //int arr[] = { 9,8,7,6,5,4,3,2,1,0 };
    int arr[] = { 0,1,2,3,4,5,6,7,8,9 };
    //0 1 2 3 4 5 6 7 8 9
    //把数组排成升序
    int sz = sizeof(arr) / sizeof(arr[0]);
    //bubble_sort(arr, sz);

    bubble_sort(arr, sz, sizeof(arr[0]), cmp_int);

    int i = 0;
    for (i = 0; i < sz; i++)
    {
        printf("%d ", arr[i]);
    }
}

int main()
{
    //test1();
    //test2();
    test3();
    return 0;
}
```

#### 排结构体

```c
void test4()
{
    //测试使用qsort来排序结构数据
    struct Stu s[] = { {"zhangsan", 15}, {"lisi", 30}, {"wangwu", 25} };
    int sz = sizeof(s) / sizeof(s[0]);
    //qsort(s, sz, sizeof(s[0]), cmp_stu_by_name);
    bubble_sort(s, sz, sizeof(s[0]), cmp_stu_by_age);
}

void swap(char *buf1, char *buf2, int width)
{ // 交换一个元素，一个字节一个字节地交换，width
    // 是数据类型长度，如int四字节
    for (int i = 0; i < width; i++)
    {
        char temp = *buf1;
        buf1 = *buf2;
        buf2 = temp;
        buf1++;
        buf2++;
    }
}

int main()
{
    //test1();
    //test2();
    //test3();
    test4();
    return 0;
}
```

---

## <p align="center">数组传参和指针传参对比</p>

### 一维

```c
int main()
{
    int arr[10] = {0};
    int *arr2[20] = {0};
    test(arr);
    test(arr2);
}
```

**数组：**

- [x] `void test(int arr[])  `
- [x] `void test(int arr[10])`
- [x] `void test(int *arr)   `

**指针：**

- [x] `void test2(int *arr[])  `
- [x] `void test2(int *arr[20])`
- [x] `void test2(int **arr)   `

### 二维

```c
int main()
{ int arr[3][5] = {0};
test(arr);
}
```

**数组：**

- [x] `void test(int arr[3][5])`
- [x] `void test (int arr[][5])`
- [ ] `void test (int arr[][]) `

**指针：**

- [ ] `void test (int \*arr)     `  
       一维级组地址不能按进一维指针
- [ ] `void test (int \*arr[5])  `  
       指针数组
- [x] `void test (int (\*arr)[5])`
- [ ] `void test (int \*\*arr)   `

* 二维数组成错指针形式只能用数组指针(指向第一行数组地址).

---

## <p align="center">`(*star)++`与`*star++`和`*(star++)`比较

</p>

**分析`(*star)++`**

- `*star` 是解引用操作，它获取指针`star`所指向的值。
- `(*star)++` 是对这个解引用值进行后缀自增操作。

所以，`(*star)++`的含义是：

- 先取出`star`指向的值，并对这个值进行自增。

### 举例说明

假设有如下代码：

```c
int array[5] = {10, 20, 30, 40, 50};
int *star = array;

printf("%d\n", (*star)++); // 输出 10
printf("%d\n", *star);     // 输出 11
```

在这段代码中：

1. `(*star)++` 先取出`star`指向的值（10），然后将这个值自增，结果是数组中的第一个元素变成了 11。
2. `*star` 此时指针`star`还是指向同一个位置，所以解引用后得到的值是 11。

### 总结

- `*star++` 或 `*(star++)`：先解引用，后指针自增。等效于：
  ```c
  *star;
  star = star + 1;
  ```
- `(*star)++`：先解引用，后对解引用的值自增，指针不变。等效于：
  ```c
  int temp = *star;
  *star = temp + 1;
  ```

---

## <p align="center">野指针</p>

> 野指针（wild pointer）是指向未知位置的指针。在 C 语言中，野指针通常是因为以下几种情况造成的：

- **未初始化的指针**：声明指针后没有立即给它赋予一个明确的地址。

```c
int *ptr;  // 声明了一个名为ptr的指针，但没有初始化
```

这时，`ptr`指向的地址是不确定的，它可能指向任意的、随机的内存地址。

- **已释放的内存**：指针指向的内存已被释放（例如通过`free`函数），但是指针没有被赋予`NULL`。

```c
int *ptr = malloc(sizeof(int)); // 分配了内存
free(ptr);  // 释放内存
// ptr 现在成为了野指针
```

- **越界的指针**：数组越界后的指针也可以成为野指针。

```c
int arr[10];
int *ptr = &arr[10]; // 指向arr数组之外的内存，造成野指针
```

- **指针操作错误**：通过不正确的算术操作修改指针的值。

```c
char *ptr = ...;
ptr += 1000;  // 不当地移动了指针
```

> 使用野指针的危险之处在于，当你通过野指针去访问或修改数据时，由于它指向不确定的内存区域，可能会导致程序崩溃、数据损坏或不可预见的行为。

为了避免野指针，可以采取以下措施：

1. **初始化指针**：声明指针时立即初始化为`NULL`或一个有效的地址。

```c
int *ptr = NULL; // 初始化为 NULL，避免成为野指针
```

2. **使用后清零**：当指针释放内存后，立即将指针设为`NULL`。

```c
free(ptr);
ptr = NULL; // 防止成为野指针
```

3. **小心操作指针**：在进行指针运算时，确保运算结果是有效且意图明确的。

务必谨慎处理指针，以免引发安全问题或程序错误。

---

# 🌕 结构体

> 结构体（structure）是 C 语言中的一种用户定义的数据类型，它允许你将不同类型的数据组合在一起。结构体可以帮助你创建更复杂的数据结构，如链表、树和图等。下面是关于结构体的一些基础知识和示例。

## 定义结构体

结构体使用 `struct` 关键字来定义。下面是一个简单的例子，定义了一个名为 `Person` 的结构体：

```c
#include <stdio.h>

struct Person {
    char name[50];
    int age;
    float height;
};
```

在这个例子中，`Person` 结构体包含三个成员：`name`、`age` 和 `height`。这些成员可以是不同类型的数据。

## 声明结构体变量

你可以使用 `struct` 关键字来声明一个结构体变量：

```c
struct Person person1;
```

也可以在定义结构体时同时声明变量：

```c
struct Person {
    char name[50];
    int age;
    float height;
} person1, person2;
```

## 访问结构体成员

使用点运算符 `.` 来访问结构体成员。例如：

```c
#include <stdio.h>

struct Person {
    char name[50];
    int age;
    float height;
};

int main() {
    struct Person person1;

    // 给结构体成员赋值
    strcpy(person1.name, "John Doe");  // 使用 strcpy 复制字符串
    person1.age = 30;
    person1.height = 5.9;

    // 打印结构体成员
    printf("Name: %s\n", person1.name);
    printf("Age: %d\n", person1.age);
    printf("Height: %.1f\n", person1.height);

    return 0;
}
```

## 结构体数组

你可以创建结构体数组来存储多个结构体变量。例如：

```c
#include <stdio.h>

struct Person {
    char name[50];
    int age;
    float height;
};

int main() {
    struct Person people[3];

    // 给结构体数组成员赋值
    strcpy(people[0].name, "John Doe");
    people[0].age = 30;
    people[0].height = 5.9;

    strcpy(people[1].name, "Jane Smith");
    people[1].age = 28;
    people[1].height = 5.7;

    strcpy(people[2].name, "Bob Johnson");
    people[2].age = 35;
    people[2].height = 6.0;

    // 打印结构体数组成员
    for (int i = 0; i < 3; i++) {
        printf("Person %d:\n", i+1);
        printf("  Name: %s\n", people[i].name);
        printf("  Age: %d\n", people[i].age);
        printf("  Height: %.1f\n", people[i].height);
    }

    return 0;
}
```

## 结构体指针

你可以使用指针来访问结构体成员。使用箭头运算符 `->` 来访问指针所指向的结构体成员。例如：

```c
#include <stdio.h>

struct Person {
    char name[50];
    int age;
    float height;
};

int main() {
    struct Person person1;
    struct Person *ptr;

    ptr = &person1;

    // 给结构体成员赋值
    strcpy(ptr->name, "John Doe");  // 使用指针访问成员
    ptr->age = 30;
    ptr->height = 5.9;

    // 打印结构体成员
    printf("Name: %s\n", ptr->name);
    printf("Age: %d\n", ptr->age);
    printf("Height: %.1f\n", ptr->height);

    return 0;
```

---

## <p align="center">结构体嵌套</p>

> 在 C 语言中，我们可以在结构体中嵌套另一个结构体。这在你需要创建更复杂的数据模型时非常有用。以下是一些关于如何在结构体中嵌套结构体的基本信息。

### 定义嵌套结构体

一个结构体可以包含同类型的结构体或其他类型的结构体的变量。下面是一个简单的例子：

```c
struct Date {
    int day;
    int month;
    int year;
};

struct Person {
    char name[50];
    int age;
    struct Date birthday;  // 嵌套结构体
};
```

在这个例子中, `Person` 结构体包含了一个 `Date` 类型的成员 `birthday`。

### 访问嵌套结构体成员

你可以使用双点运算符 `.` 来访问嵌套的结构体成员。例如，要设置 `Person` 结构体的 `birthday` 成员的 `day` 成员，你可以做如下操作：

```c
struct Person person1;

person1.birthday.day = 22;  // 设置 birthday 的 day 成员
```

也可以一次设置整个 `birthday` 成员：

```c
person1.birthday = (struct Date){22, 7, 1990};  // 使用复合字面量设置 birthday
```

### 结构体可以嵌套其自身

> 结构体可以包含指向其自身类型的指针，从而创建更复杂的数据结构，如链表和树。

```c
struct Node {
    int data;
    struct Node* next;  // 指向同类型的指针
};
```

在这个例子中，`Node` 结构体有一个 `Node` 类型的指针 `next`。这在创建链表结构等数据结构中非常常用。

---

## <p align="center">赋值</p>

```c
struct Person person1 = {"John Doe", 30, {15, 7, 1990}};
struct Person person2;

// 将 person1 的数据复制给 person2
person2 = person1;
```

你可以使用复合字面量给整个结构体赋值，如下：

```c
struct Person person1 = {
.name = "John Doe",
.age = 30,
.birthday = (struct Date){15, 7, 1990} // 使用复合字面量给嵌套的结构体赋值
};
```

---

## <p align="center">取值</p>

```c
#include <stdio.h>

struct Address {
    char city[50];
    char street[50];
    int number;
};

struct Person {
    char name[50];
    int age;
    struct Address address;
};

int main() {
    struct Person person1 = {"Alice", 30, {"New York", "5th Avenue", 101}};

    // 使用点操作符访问和打印嵌套结构体成员
    printf("Name: %s\n", person1.name);
    printf("Age: %d\n", person1.age);
    printf("City: %s\n", person1.address.city);
    printf("Street: %s\n", person1.address.street);
    printf("Number: %d\n", person1.address.number);

    // 使用指针访问和打印嵌套结构体成员
    struct Person *ptr = &person1;
    printf("Using pointer:\n");
    printf("City: %s\n", ptr->address.city);
    printf("Street: %s\n", ptr->address.street);
    printf("Number: %d\n", ptr->address.number);

    return 0;
}
```

---

## <p align="center">结构体传参</p>

在 C 语言中，可以通过以下两种方式将结构体作为参数传递给函数：

1. **按值传递（Pass by Value）**
2. **按引用传递（Pass by Reference）**

### 按值传递

> 按值传递时，将结构体的一个副本传递给函数。对该副本的修改不会影响原始结构体。这种方法的缺点是如果结构体较大，复制过程会比较耗时。

#### 示例代码

```c
#include <stdio.h>

typedef struct {
    int x;
    int y;
} Point;

void printPoint(Point p) {
    printf("Point: (%d, %d)\n", p.x, p.y);
}

int main() {
    Point p1 = {10, 20};
    printPoint(p1); // 传递结构体的副本
    return 0;
}
```

### 按引用传递

> 按引用传递时，传递的是结构体的指针。这样可以避免复制结构体，且函数内对结构体的修改会影响原始结构体。

#### 示例代码

```c
#include <stdio.h>

typedef struct {
    int x;
    int y;
} Point;

void movePoint(Point *p, int dx, int dy) {
    p->x += dx;
    p->y += dy;
}

int main() {
    Point p1 = {10, 20};
    movePoint(&p1, 5, -3); // 传递结构体的指针
    printf("Moved Point: (%d, %d)\n", p1.x, p1.y);
    return 0;
}
```

### 按值传递 vs 按引用传递

- **按值传递**适用于结构体较小且不希望函数修改原结构体的情况。
- **按引用传递**适用于结构体较大或希望函数能够修改原结构体的情况。

### 选择哪种方式

- 如果结构体较大，优先考虑按引用传递以避免不必要的复制开销。
- 如果不希望函数修改结构体内容，可以使用 `const` 修饰符来传递结构体指针，如 `const Point *p`。
