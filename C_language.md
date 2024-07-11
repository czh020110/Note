# <center>C 语言

# 初识 C 语言

## 细碎

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

## <center>switch 语句（可嵌套）

在 C 语言中，`switch`语句允许根据变量的值执行不同的代码块。嵌套的`switch`语句就是在一个`switch`语句的某个`case`块中再包含另一个`switch`语句。下面是一个嵌套`switch`语句的示例：

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

### 在这个示例中：

1. 外层`switch`语句根据变量`outerVar`的值来选择执行哪个`case`块。
2. 当`outerVar`的值为`1`时，程序会执行外层`switch`语句的`case 1`块中的代码。
3. 在`case 1`块中，有一个嵌套的`switch`语句，它根据变量`innerVar`的值来选择执行哪个`case`块。
4. 当`innerVar`的值为`2`时，程序会执行内层`switch`语句的`case 2`块中的代码。

### 注意事项：

- 每个`case`块末尾通常需要有一个`break`语句，以防止执行到下一个`case`块中的代码。
- `default`块是可选的，但建议在`switch`语句中包含一个`default`块来处理所有未被明确处理的情况。

通过这种方式，可以在`switch`语句中嵌套另一个`switch`语句，以处理更复杂的多级条件判断。

---

## <center>getchar()语句

`getchar()` 是 C 语言标准输入库函数之一，用于从标准输入（通常是键盘）读取一个字符。它的作用是等待用户输入，并返回输入的字符。

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

1. **缓冲区**：`getchar()` 读取的是标准输入缓冲区中的字符，直到用户按下回车键，整个输入行才会进入缓冲区。
2. **返回类型**：`getchar()` 返回一个 `int` 类型的值。这是因为在处理字符的同时，还需要处理输入结束（EOF）的情况。EOF 通常定义为 -1。
3. **多次调用**：每次调用 `getchar()` 会读取下一个字符。如果在读取一个字符后希望继续读取，可以使用循环。

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

- **过滤换行符**：如果只需要读取字符而忽略换行符，可以使用循环或条件判断来跳过换行符。
- **输入缓冲清空**：有时候需要清空输入缓冲区，以确保后续输入不受之前输入的影响。可以使用 `fflush(stdin)`，但这在不同平台上的行为可能有所不同。（`scanf`语句输入后，输入不正确字符被截断，可以用来清除缓冲区字符）

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

这段代码将会忽略所有的换行符，直到读取到一个非换行符的字符。

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

在 C 语言中，链接（linking）分为内部链接（internal linkage）和外部链接（external linkage）。这两种链接方式决定了标识符（如变量和函数）的可见性和作用域。`static`和`extern`是用于控制这些链接的两个关键字。

## <center>内部链接（Internal Linkage）

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

## <center>外部链接（External Linkage）

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

## <center>`static` 关键字

`static` 关键字在 C 语言中有多种用途，它的作用取决于它所在的上下文。主要有以下几种使用场景：

1. **静态局部变量**
2. **静态全局变量**
3. **静态函数**

### 1. 静态局部变量

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

输出：

```
countCalls has been called 1 times
countCalls has been called 2 times
countCalls has been called 3 times
```

### 2. 静态全局变量

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

### 3. 静态函数

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

## <center>`extern` 关键字

`extern` 关键字用于声明一个在其他文件中定义的变量或函数。它的作用是告诉编译器这个变量或函数的定义在其他地方，并且在链接阶段会找到它的定义。

### 1. 声明全局变量

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

### 2. 声明函数

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

通过理解 `static` 和 `extern` 关键字的不同用途和使用场景，可以更好地控制变量和函数的可见性和作用域，从而编写出更加模块化和维护性更好的代码。

`const` 关键字在 C 语言中用于定义常量。常量是指在程序执行过程中其值不会发生变化的变量。使用 `const` 关键字可以提高代码的可读性和安全性，防止意外修改。下面是 `const` 关键字的一些常见用法和详细介绍：

## <center>const 常量

### 基本用法

1. **常量变量**

   ```c
   const int a = 10;
   ```

   上面的代码定义了一个常量整型变量 `a`，并将其初始化为 10。之后，`a` 的值不能再被修改。

2. **指针常量**
   指针常量表示指针指向的地址是固定的，但指针指向的内容可以修改。

   ```c
   int x = 5;
   int y = 10;
   int *const p = &x;
   *p = 20;  // 合法，修改指针指向的内容
   p = &y;   // 非法，试图修改指针本身
   ```

3. **常量指针**
   常量指针表示指针指向的内容是固定的，但指针本身可以指向不同的地址。

   ```c
   int x = 5;
   int y = 10;
   const int *p = &x;
   p = &y;   // 合法，修改指针本身
   *p = 20;  // 非法，试图修改指针指向的内容
   ```

4. **常量指针常量**
   既表示指针本身不能修改，指针指向的内容也不能修改。
   ```c
   int x = 5;
   const int *const p = &x;
   *p = 20;  // 非法，试图修改指针指向的内容
   p = &y;   // 非法，试图修改指针本身
   ```

### `const` 在函数中的使用

1. **传递常量参数**

   ```c
   void printValue(const int value) {
       printf("%d\n", value);
   }
   ```

   传递常量参数可以确保函数内部不会修改传入的参数。

2. **常量指针参数**
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

## <center>strcmp 函数：比较字符串

`strcmp`是一个 C 语言库函数，用于比较两个字符串。它的声明可以在`<string.h>`头文件中找到。`strcmp`函数的原型为：

```c
int strcmp(const char *s1, const char *s2);
```

`strcmp` 的工作原理是通过比较两个字符串 `s1` 和 `s2` 的每个字符，按字典序进行大小比较。如果字符串相等，返回 0；如果`s1`在字典序中比`s2`小，则返回负值；反之，返回正值。

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

注意，当比较字符串的时候，不要直接使用 `==` 运算符，因为 `==` 是比较两个指针是否指向相同的内存地址。在这种情况下，请使用 `strcmp` 函数来正确处理两个字符串之间的比较。

### `my_strcmp`

你可以编写自己的`my_strcmp`函数来模仿标准库中的`strcmp`函数。这个函数将逐个比较两个字符串的字符，直到它们的字符不同或到达字符串的结尾。下面是一个示例实现：`my_strcmp`

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

#### 解释

1. **参数**：`const char *s1, const char *s2` 是指向要比较的两个字符串的指针。
2. **循环**：`while (*s1 && (*s1 == *s2))`：
   - 只要两个字符串的当前字符相等且不为 `\0`（字符串结束符），循环将继续。
   - 如果当前字符相等，指针将前进到下一个字符。
3. **返回差值**：如果两个字符串在某一位置不同，返回它们的字符差值。这将决定哪个字符串在字典序中更小或更大。如果两个字符串完全相等，返回 0。

这个 `my_strcmp` 函数在功能上与标准库中的 `strcmp` 函数相同。
