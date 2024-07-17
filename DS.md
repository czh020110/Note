# <p align="center">数据结构</p>

# <p align="center">一、代码部分 🎊(●'◡'●)🎉</p>

# 🌑 顺序表

## 顺序表定义和初始化

### 静态分配`InitList`

```c
#define Maxsize 50;
typedef struct
{
    ElemType data[Maxsize];
    int length;
} Sqlist;
```

```c
void InitList(SqList &L)
{
    for (int i = 0; i < Maxsize; i++)
        L.data[i] = 0;
    L.length = 0;
}
```

### 动态分配`InitList`

```c
#define InitSize 100
typedef struct
{
    ElemType *data;
    int length;
    int Maxsize;
} Seqlist;
```

```c
void InitList(Seqlist &L)
{
    L.data = (int *)malloc(InitSize * sizeof(int));
    L.length = 0;
    L.Maxsize = InitSize;
}
```

---

## <p align="center">编写程序需要的函数</p>

### 销毁`Dstroy`

```c
void Dstroy(SqList &L)
{
    if (L.data)
        free(L.data);
}
```

### 清空`ClearList`

```c
void ClearList(SqList &L)
{
    L.length = 0;
}
```

### 求线性表长度：`GetLength`

```c
int GetLength(SqList L)
{
    return (L.length);
}
```

### 判断是否为空：`IsEmpty`

```c
bool IsEmpty(SqList L)
{
    if (L.length == 0)
        return true;
    else
        return false;
}
```

---

## <p align="center">查找</p>

### 按位查值`GetElem`

```c
bool GetElem(Sqlist L, int i, ElemType &e)
{
    if (i < 1 || i > L.length)
        return false;
    e = L.data[i - 1];
    return true;
}
```

### 按值查位`LocateElem`

```c
bool LocateElem(SqList L, ElemType e)
{
    for (i = 0; i < L.length; i++)
        if (L.data[i] == 0)
            return i + 1;
    return false;
}
```

---

## <p align="center">插入与删除</p>

### 顺序表的插入 O(n)`ListInsert`

```c
bool ListInsert(SqList &L, int i, int e)
{
    int j;
    if (i < 1 || i > L.length + 1)
        return false;
    if (L.length >= MaxSize)
        return false;
    for (intj = L.length; j >= i; j--)
        L.datalj]=L.data[j-1];
    L.data[i - 1] = e;
    L.length++;
    return true;
}
```

### 顺序表的删除 O(n)`ListDelete`

```c
bool ListDelete(SqList &L, int i, int &e)
{
    if (i < 1 || i > L.length)
        return false;
    e = L.data[1 - 1];
    for (int j = i; j < L.length; j++)
        L.data[j - 1] = L.data[j];
    L.length--;
}
```

---

# 🌘 单链表

## <p align="center">单链表的定义和初始化</p>

### 不带头结点`LNode`, `*LinkList`

```c
typedef struct LNode
{
    ElemType data;
    struct LNode *next;
} LNode, *LinkList;
```

```c
bool InitList(LinkList &L)
{
    L = NULL;
    return true;
}
```

```c
bool Empty(LinkList L)
{
    return (L == NULL);
}
```

### 带头结点`LNode` `*LinkList`

```c
typedef struct LNode
{
    ElemType data;
    struct LNode *next;
} LNode, *LinkList;
```

```c
bool InitList(LinkList &L)
{
    L = (LNode *)malloc(sizeof(LNode));
    L->next = NULL;
    return true;
}
```

```c
bool Empty(LinkList L)
{
    return (L->next == NULL);
}
```

---

## <p align="center">单链表的插入 O(n)</p>

### 按位序后插(带头结点)`ListInsert`

```c
bool ListInsert(LinkList &L, int i, ElemType e)
{
    if (i < 1)
        return false;
    LNode *p;
    int j = 0;
    p = L;
    while (p != NULL && j < i - 1)
    {
        p = p->next;
        j++;
    }
    if (p == NULL)
        return false;
    LNode *s = (LNode *)malloc(sizeof(LNode));
    s->data = e;
    s->next = p->next;
    p->next = s;
    return true;
}
```

### 按位序后插(不带头结点)`ListInsert`

```c
bool ListInsert(LinkList &L, int i, ElemType e)
{
    if (i < 1)
        return false;
    if (i == 1)
        t
        {
            LNode _s = (LNode _)malloc(sizeof(LNode));
            s->data = e;
            s->next = L;
            L = s;
            return true;
        }
    LNode *p;
    int j = 1;
    p = L； while (p != NULL && j < i - 1)
    {
        p = p->next;
        j++;
    }
    if (p == NULL)
        return false;
    LNode *s = (LNode \*)malloc(sizeof(LNode));
    s->data = e;
    s->next = p->next;
    p->next = s;
    return true;
}
```

### 在指定节点的后插 O(1)`InsertNextNode`

```c
bool InsertNextNode(LNode *p, ElemType e)
{
    if (p == NULL)
        return false;
    LNode *s = (LNode *)malloc(sizeof(LNode));
    s->data = e;
    s->next = p->next;
    p->next = s;
    return true;
}
```

### 在指定节点的前插`InsertPriorNode`

> 此项不传入指针 O(1)，若传入 O(n):

```c
bool InsertPriorNode(LNode *p, ElemType e)
{
    if (p == NULL)
        return false;
    LNode *s = (LNode *)malloc(sizeof(LNode));
    s->next = p->next;
    p->next = s;
    s->data = p->data;
    p->data = e;
    return true;
}
```

---

## <p align="center">单链表的删除</p>

### 按位序删除节点 O(n)`ListDelete`

```c
bool ListDelete(LinkList &L, int i, ElemType e)
{
    if (i < 1)
        return false;
    LNode *p;
    int j = 0;
    p = L;
    while (p != NULL && j < i - 1)
    {
        p = p->next;
        j++;
    }
    if (p == NULL)
        return false;
    if (p->next == NULL)
        return false;
    LNode *q = p->next;
    e = q->data;
    p->next = q->next;
    free(q);
    return true;
}
```

### 指定节点删除 O(1)`DeleteNode`

```c
bool DeleteNode(LNode *p)
{
    if (p == NULL)
        return false;
    LNode *q = p->next;
    p->data = p->next->data;
    p->next = q->next;
    free(q);
    return true;
}
```

---

## <p align="center">单链表求表长`getLength`</p>

```c
int getLength(LinkList L)
{
    int len = 0;
    while (p->next != NULL)
    {
        p = p->next;
        len++;
    }
    return len;
}
```

---

## <p align="center">单链表的查找</p>

### 按位查找 O(n)`GetElem`

```c
LNode *GetElem(LinkList L, int i)
{
    if (i < 0)
        return NULL;
    LNode *p;
    int j = 0;
    p = L;
    while (p != NULL && lj < i)
    {
        p = p->next;
        j++；
    }
    return p;
}
```

### 按值查找 O(n)`LocateElem`

```c
LNode *LocateElem(LinkList L, ElemType e)
{
    LNode *p = L->next;
    while (p != NULL &&p->data = e)
        p = p->next;
    return p;
}
```

---

## <p align="center">单链表的建立</p>

### 尾插法 O(n) `ListTaillnsert`

```c
LinkList ListTaillnsert(LinkList &L)
{
    int_x;
    L = (LinkList)malloc(sizeof(LNode));
    LNode *s, *r = L;
    scanf("%d", &x);
    while (x != 9999)
    {
        s = (LNode *)malloc(sizeof(LNode));
        s->data = x;
        r->next = s;
        r = s;
        scanf("%d", &x);
    }
    r->next = NULL;
    return L;
}
```

### 头插法（单链表的逆置）O(n)`ListHeadInsert`

```c
LinkList ListHeadInsert(LinkList &L)
{
    LNode *s;
    int x;
    L = (LinkList)malloc(sizeof(LNode));
    L->next = NULL;
    scanf("%d", &x);
    while (x != 9999)
    {
        s = (LNode *)malloc(sizeof(LNode));
        s->data = x;
        s->next = L->next;
        L->next = s;
        scanf("%d", &x);
    }
    return L;
}
```

---

# 🌗 循环链表

## <p align="center">循环单链表</p>

### 循环单链表的定义 `LNode` `*LinkList` 和初始化`InitList`

```c
typedef struct LNode
{
    ElemType data;
    struct LNode *next;
} LNode, *LinkList;
```

```c
bool InitList(LinkList &L)
{
    L = (LNode *)malloc(sizeof(LNode));
    L->next = L;
    return true;
}
```

### 判断表空`isEmpty`

```c
bool isEmpty (LinkList L)(
	if (L->next ==L)
		return true;
	else
		return false;
```

### 判断节点 p 是否为循环单链表表尾节点`isTail`

```c
bool isTail (LinkListL, LNode *p){
    if (p->next == L)
        return true;
    else
        return false;
}
```

---

## <p align="center">循环双链表</p>

### 循环双链表的定义`DNode` `*DLinklist`和初始化`InitDLinklist`

```c
typedef struct DNode
{
    ElemType data;
    struct DNode *prior, *next;
} DNode,*DLinklist;
```

```c
bool InitDLinklist(DLinklist &L)
{
    L = (DNode *)malloc(sizeof(DNode));
    L->prior = L;
    L->next = L;
    return true;
}
```

### 判断表空`isEmpty`

```c
bool isEmpty(DLinklist L)
{
    if (L->next == L)
        return true;
    else
        return false;
}
```

### 判断节点 p 是否为循环双链表表尾节点`isTail`

```c
bool isTail(DLinklist L, DNode *p)
{
    if (p->next == L)
        return true;
    else
        return false;
}
```

---

# 🌖 栈

## <p align="center">顺序栈</p>

### 定义`SqStack`和初始化`InitStack`

```c
#define MaxSize 10
typedef struct
{
    ElemType data[MaxSize];
    int top;
} SqStack;
```

```c
void InitStack(SqStack &S)
{
    S.top = -1;
}
```

### 判空`StackEmpty`

```c
bool StackEmpty(SqStack S)
{
    if (S.top == -1)
        return true;
    else
        return false;
}
```

### 入栈`push`

```c
bool Push(SqStack &S, ElemType x)
{
    if (S.top == MaxSize - 1)
        return false;
    S.top = S.top + 1;
    S.data[S.top] = x; // 等价S.data[++S.top]=x
    return true;
}
```

### 出栈`pop`

```c
bool Pop(SqStack &S, ElemType &x)
{
    if (S.top == -1)
        return false;
    x = S.data[S.top];
    S.top = S.top - 1; // 等价x=S.data[S.top--]
    return true;
}
```

### 读栈顶元素

```c
bool GetTop(SqStack S, ElemType &x)
{
    if (S.top == -1)
        return false;
    x = S.data[S.top]; // 审题，若top非指向栈顶
    return true;       // 可先--top
}
```

---

## <p align="center">链栈</p>

### 链栈的定义和初始化`*LiStack`

```c
typedef struct Linknode
{
    ElemType data;
    struct Linknode *next;
} *LiStack;
```

> 初始化，插入，查找... ： 本质是对操作受限链表的操作

---

## <p align="center">栈应用：判断括号是否匹配的算法</p>

```c
void InitStack(SqStack &S);    // 初始化栈
bool StackEmpty(SqStack S);    // 判断栈是否为空
bool Push(SqStack &S, char x); // 新元素入栈
bool Pop(SqStack &S, char &x); // 栈顶元素出栈，用x返回
bool bracketCheck(char str[], int length)
{
    SqStack S;
    InitStack(S);
    for (int i = 0; i < length; i++)
    {
        if (str[i] == '(' || str[i] == '[' || str[i] == '{')
            Push(S, strlil);
        else
        {
            if (StackEmpty(S))
                return false;
            char topElem;
            Pop(S, topElem);
            if (str[i] == ')' && topElem != '(')
                return false : if (str[i] == ']' && topElem != '[') return false;
            if (str[i] == '}' && topElem != '{')
                return false;
        }
    }
    return StackEmpty(S);
} // 数组每扫描一个元素入栈，新元素与栈顶判断匹配
```

---

# 🌒 队列

## <p align="center">顺序队列</p>

### 顺序队列的定义`SqQueue`与初始化`InitQueue`

```c
#define MaxSize 10
    typedef struct
{
    ElemType data[MaxSize];
    int front, rear;
} SqQueue;

void InitQueue(SqQueue &Q)
{
    Q.rear = Q.front = 0; // 队尾指针->下个插入的位置
}
```

### 顺序队列判空`QueueEmpty`

```c
bool QueueEmpty(SqQueue Q)
{
    if (Q.rear == Q.front)
        return true;
    else
        return false;
}
```

---

## <p align="center">循环队列</p>

### 入队

```c
bool EnQueue(SqQueue &Q, ElemType x)
{
    if ((Q.rear + 1) % MaxSize == Q.front)
        return false;
    Q.data[Q.rear] = x;
    Q.rear = (Q.rear + 1) % MaxSize; // 非循环去掉%MaxSize
    return true;
}
```

### 出队

```c
bool DeQueue(SqQueue &Q, ElemType)
{
    if (Q.rear == Q.front)
        return false;
    x = Q.data[Q.front];
    Q.front - (Q.front + 1) % MaxSize;
    return true;
}
```

### 获得队头元素的值

```c
bool GetHead(SqQueue Q, ElemType &x)
{
    if (Q.rear == Q.front)
        return false;
    x = Q.data[Q.front];
    return true;
}
```

### 循环队列的几种判空 / 满：

> 主要看 `rear` 指针指向哪？

- 牺牲一个存储单元

  ```c
  #define MaxSize 10
  typedef struct
  {
      ElemType data[MaxSize];
      int front, rear;
  } SqQueue;
  ```

  > 初始时 Q.rear = Q.front = 0  
  > 队满：(Q.rear + 1) % MaxSize == Q.rear  
  > 队空：Q.rear = Q.front  
  > 牺牲了一个存储单元

* 记录队列长度

  ```c
  #define MaxSize 10
  typedef struct
  {
      ElemType data[MaxSize];
      int front, rear;
      int size; // 记录队列长度
  } SqQueue;
  ```

  > 队满：size == MaxSize  
  > 队空：size == 0 没牺牲存储单元

* 做`tag`标记
  ```c
  #define MaxSize 10
      typedef struct
  {
      ElemType data[MaxSize];
      int front, rear;
      int tag; // 记录上个操作
  } SqQueue;   // 插入 1，删除 0
  ```
  > 队空：front == rear &&tag == 0  
  > 队满：front == rear &&tag == 1  
  > 没牺牲存储单元

---

## <p align="center">链式队列</p>

> 有尾指针

### 链队的定义`LinkNode` ➕ `LinkQueue`

> 两个结构体函数

```c
typedef struct LinkNode
{
    ElemType data;
    struct LinkNode *next;
} LinkNode;
```

```c
typedef struct
{
    LinkNode *front, *rear;
} LinkQueue;
```

### 链队的初始化`InitQueue`

#### 带头结点

```c
void InitQueue(LinkQueue &Q)
{
    0.front = Q.rear = (LinkNode *)malloc(sizeof(LinkNode));
    Q.front->next = NULL:
}
```

#### 不带头结点

```c
void InitQueue(LinkQueue &Q)
{
    Q.front = NULL;
    Q.rear = NULL;
}
```

### 链队判空`IsEmpty`

#### 带头结点

```c
bool IsEmpty(LinkQueue Q)
{
    if (Q.front == Q.rear)
        return true;
    else
        return false;
}
```

#### 不带头结点

```c
bool IsEmpty(LinkQueue Q)
{
    if (Q.front == NULL)
        return true;
    else
        return false;
}
```

### 链队的入队`EnQueue`

> （相当于尾插法）

#### 带头结点

```c
void EnQueue(LinkQueue &Q, ElemType x)
{
    LinkNode *s = (LinkNode *)malloc(sizeof(LinkNode));
    s->data = x;
    s->next = NULL;
    Q.rear->next = s;
    Q.rear = s;
}
```

#### 不带头结点

```c
void EnQueue(LinkQueue &Q, ElemTypex)
{
    LinkNode *s = (LinkNode *)malloc(sizeof(LinkNode));
    s->data = x;
    s->next = NULL;
    if (Q.front == NULL)
    {
        Q.front = s;
        Q.rear = s;
    }
    else
    {
        Q.rear->next = s;
        Q.rear = s;
    }
}
```

### 链队的出队`DeQueue`

> 从第一个元素开始删除

#### 带头结点

```c
bool DeQueue(LinkQueue &Q, ElemType &x)
{
    if (Q.front == Q.rear)
        return false;
    LinkNode \*p = Q.front->next;
    x = p->data;
    Q.front->next = p->next;
    if (Q.rear == p)
        Q.rear = Q.front;
    free(p);
    return true;
}
```

#### 不带头结点

```c
bool DeQueue(LinkQueue &Q, ElemType &x)
{
    if (Q.front == NULL)
        return false;
    LinkNode \*p = Q.front;
    x = p->data;
    Q.front = p->next;
    if (Q.rear == p)
    {
        Q.front = NULL;
        Q.rear = NULL;
    }
    free(p);
    return true;
}
```

---

# 🌓 树

## <p align="center">树的存储结构</p>

### 双亲表示法`PTNode`➕`Ptree`

- **顺序存储**

  ```c
  #define MAX TREE SIZE 100
  typedef struct
  {
      ElemType data;
      int parent;
  } PTNode;

  typedef struct
  {
      PTNode nodes[MAX_TREE_SIZE];
      int n;
  } Ptree;
  ```

> 找双亲方便，找孩子麻烦

### 孩子表示法`CTNode`➕`CTBox`➕`CTree`

- **顺序 + 链式存储**

  ```c
  struct CTNode
  {
      int child;
      struct CTNode *next;
  }

  typedef struct
  {
      ElemType data;
      struct CTNode *firstChild；
  } CTBox;

  typedef struct
  {
      CTBox nodes[MAX_TREE_SIZE];
      int n, r;
  } CTree;
  ```

> 找孩子方便，找双亲麻烦

### 孩子兄弟表示法`CSNode` `*CSTree`

- **链式存储**

  ```c
  typedef struct CSNode
  {
      ElemType data;
      struct CSNode *firstchild, *nextsibling;
  } CSNode, *CSTree;
  ```

> 可转化为熟悉的二叉树形式

---

## <p align="center">树、二叉树、森林 的遍历顺序</p>

<p align="center">

|            树            |   森林   |  二叉树  |
| :----------------------: | :------: | :------: |
| 先根遍历（深度优先遍历） | 先序遍历 | 先序遍历 |
| 后根遍历（深度优先遍历） | 中序遍历 | 中序遍历 |

</p>

---

# 🌔 二叉树

## 顺序存储

### \*定义`TreeNode`

```c
#define Maxsize 100
typedef struct TreeNode
{
    ElemType data;
    bool isEmpty; // 结点是否为空
} TreeNode;
```

### \*初始化`InitNode`

```c
void InitNode(TreeNode t[])
{
    for (int i = 0; i < Masize; i++)
        t[i].isEmpty = true;
}
```

> 只适合存储完全二叉树  
> 主函数定义：`TreeNode t[MaxSize]`

### 判空

- 完全二叉树

  - $i$ 的左孩子－－$2i$
  - $i$ 的右孩子－－$2i+1$
  - i$$ 的父节点－－$⌊\frac{n}{2}⌋$
  - 判断 $i$ 是否有左孩子？ ——$2i≤n$
  - 判断 $i$ 是否有右孩子？ ——$2i + 1≤n$
  - 判断 $i$ 是否是叶子 / 分支结点 —— $i >⌊\frac{n}{2}⌋$

- 非完全二叉树不能判断

---

## <p align="center">链式存储二叉树`BiTNode` `*BiTree`</p>

### \*定义

```c
typedef struct BiTNode
{
    ElemType data;
    struct BiTNode *lchild, *rchild;
} BiTNode, *BiTree;
```

```c
BiTree root = NULL;// 定义一棵空树
```

### \*初始化

```c
root = (BiTree)malloc(sizeof(BiTNode)); // 插入根节点
root->data = 1;
root->lchild = NULL;
root->rchild = NULL;
```

```c
BiTNode *p = (BiTNode *)malloc(sizeof(BiTNode)); // 插入新结点
p->data = 2;
p->lchild = NULL;
p->rchild = NULL;
```

```c
root->lchild = p; // 作为根节点的左孩子
```

---

## <p align="center">二叉树的遍历</p>

### 先序遍历`Pre0rder`

```c
void Pre0rder(BiTree T)
{
    if (T != NULL)
    {
        visit(T);
        Pre0rder(T->lchild);
        Pre0rder(T->rchild);
    }
}
```

### 中序遍历`In0rder`

```c
void In0rder(BiTree T)
{
    if (T != NULL)
    {
        In0rder(T->lchild);
        visit(T);
        In0rder(T->rchild);
    }
}
```

### 后序遍历`Post0rder`

```c
void Post0rder(BiTree T)
{
    if (T != NULL)
    {
        Post0rder(T->lchild);
        Post0rder(T->rchild);
        visit(T);
    }
}
```

### 层序遍历`Level0rder`

> **队列**

> 二叉树结点结构体（链式存储）  
>  链式队列结点结构体  
>  链式队列结构体

```c
void Level0rder(BiTree T)
{
    LinkQueue Q;
    InitQueue(Q);
    BiTree p;
    EnQueue(Q, T);
    while (!IsEmpty(Q))
    {
        DeQueue(Q, p);
        visit(p);
        if (p->lchild != NULL)
            EnQueue(Q, p->lchild);
        if (p->rchild != NULL)
            EnQueue(Q, p->rchild);
    }
}
```

#### 应用：求树的深度

> **递归**  
> **链式**

```c
int treeDepth(BiTree T)
{
    if (T == NULL)
        return 0;
    else
    {
        int l = treeDepth(T->lchild);
        int r = treeDepth(T->rchild);
        return l > r ? l + 1 : r + 1; // 树的深度=Max(左子树深度,右子树深度)+1
    }
}
```
