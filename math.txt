数学，证明

不等式证明专题

1. 恒等变换证明。  

要证明 $ f(x) \leq g(x) $，则  

(1) 只需要证明 $ f(x) - g(x) \leq 0 $；  

(2) 如果 $ f(x) \geq 0 $，则只需要证明 $ \frac {f(x)} {g(x)} \leq 1 $。  

(3) 只需要证明 $ e^{f(x)} \leq e^{g(x)} $；  

(4) 如果 $ f(x) > 0 $，则只需要证明 $ \ln f(x) \leq \ln g(x) $。

例
$$ \frac{1 - \cos x}{\sin x} = \frac{\sin x}{1 + \cos x} $$  

$$ \frac{1 - \cos x}{\sin x} = \frac{2 \sin^2 \frac{x}{2}}{2 \sin \frac{x}{2} \cos \frac{x}{2}} = \frac{\sin \frac{x}{2}}{\cos \frac{x}{2}} = \frac{2 \sin^2 \frac{x}{2} \cos \frac{x}{2}}{2 \cos^2 \frac{x}{2}} = \frac{\sin x}{1 + \cos x} $$  
普通证明  

$$ \frac{1 - \cos x}{\sin x} = \frac{\sin x}{1 + \cos x} \iff (1 - \cos x)(1 + \cos x) = \sin^2 x $$  
恒等变换证明


2. 放缩（绝对值不等式、均值不等式、常见结论不等式、柯西不等式）。

（1）绝对值不等式

① $ -| x | \leq x \leq | x | $， $\forall x \in R$。

当 $ x \leq 0 $ 时， $ -| x | \leq x $ 取等号；当 $ x \geq 0 $ 时， $ x \leq | x | $ 取等号。

② $ | x - y | \leq | x \pm y | \leq | x | + | y | $，$\forall x, y \in R$。

当 $ x y \leq 0 $ 时，$ | x - y | \leq | x + y | $ 取等号，$ | x - y | \leq | x | + | y | $ 取等号；

当 $ x y \geq 0 $ 时，$ | x - y | \leq | x - y | $ 取等号，$ | x + y | \leq | x | + | y | $ 取等号。

(2) 均值不等式（算术平均值≥几何平均值）

① $ a^2 + b^2 \geq 2ab $， $\forall a, b \in \mathbb{R}$。

② $ a + b \geq 2\sqrt{ab} $， $\forall a, b \in \mathbb{R^+}$。

③ $ \frac{a_1 + a_2 + \cdots + a_n}{n} \geq \sqrt[n]{a_1 a_2 \cdots a_n} $。

④ $ \frac{2}{\frac{1}{a} + \frac{1}{b}} \leq \sqrt{ab} \leq \frac{a + b}{2} \leq \sqrt{\frac{a^2 + b^2}{2}} $， $\forall a, b \in \mathbb{R^+}$。

⑤ $ \frac{n}{\sum_{i=1}^{n} \frac{1}{a_i}} \leq \sqrt[n]{\prod_{i=1}^{n} a_i} \leq \frac{1}{n} \sum_{i=1}^{n} a_i \leq \sqrt{\frac{1}{n} \sum_{i=1}^{n} a_i^2} $（调和平均值≤几何平均值≤算术平均值≤平方平均值）

(3) 常用其他不等式。  

① $ x^2 \geq 0， \ \forall x \in \mathbb{R}， \ 当 \ x = 0 \ 时取等号 $;  

② $ |x| \geq 0， \ \forall x \in \mathbb{R}， \ 当 \ x = 0 \ 时取等号 $;  

③ $ | \sin x | \leq 1， \ \forall x \in \mathbb{R}， \ 当 \ x = \frac{\pi}{2} + k\pi \ 时取等号 $;  

④ $ | \sin x | \leq |x|， \ \forall x \in \mathbb{R}， \ 当 \ x = 0 \ 时取等号 $;  

⑤ $ | x | \leq | \tan x |， \ \forall x \in \left( - \frac{\pi}{2}， \frac{\pi}{2} \right)， \ 当 \ x = 0 \ 时取等号 $;  

⑥ $ \frac{x}{1+x} \leq \ln (1+x) \leq x， \ \forall x \geq 0 $;


② $ n $元离散的柯西不等式。  

推广到 $ n $元，有 $ \left( a_1^2 + a_2^2 + \cdots + a_n^2 \right) \left( b_1^2 + b_2^2 + \cdots + b_n^2 \right) \geq \left( a_1 b_1 + a_2 b_2 + \cdots + a_n b_n \right)^2 $ ，  

即 $ \left( \sum_{i=1}^n a_i^2 \right) \left( \sum_{i=1}^n b_i^2 \right) \geq \left( \sum_{i=1}^n a_i b_i \right)^2 $ ， $\forall a_i , b_i \in R $均成立。且仅当 $ a_i = \lambda b_i $ ， $ i = 1 , 2 , \cdots , n $ 时，等号成立。  

③ 连续的二元柯西不等式。  

设 $ f(x) $ ， $ g(x) $ 在 $ [a , b] $ 上均连续，则有 $ \int_a^b f^2(x) \, dx \int_a^b g^2(x) \, dx \geq \left( \int_a^b f(x) g(x) \, dx \right)^2 $ ，当且仅当 $ f(x) = \lambda g(x) $ 时等号成立。


3.利用导数（以及拉格朗日中值定理、极值、最值、单调性等）。  
比如 **要证明 $ f(x) \leq g(x) $**，可以 **构造辅助函数 $ h(x) = f(x) - g(x) $**，则原命题等价于对于定义域中任意一个 $ x $，均有 $ h(x) \leq 0 $，即 $ h_{max} (x) \leq 0 $（要使得得最高的人成为最高的人没有我高了）。  

所以，也可以转换成求函数 $ h(x) $ 的 **最大值（极大值）**，而往往 $ f(x) $ 和 $ g(x) $ 都是可导函数，从而可以利用导数求 $ h(x) $ 的最大值。

注：一阶导证不出来就二阶导，不行就三阶导，  
没有哪个题目是不能用求一次导数来搞定的，  
如果有，就再求一次导数！  
就跟搞定东北人用一顿烧烤+啤酒一样。


4. 利用泰勒公式  

$f(x) = f(x_{0}) + f^{\prime}(x_{0})(x-x_{0}) + \frac{1}{2!} f^{\prime\prime}(x_{0})(x-x_{0})^{2} + \ldots + \frac{1}{n!} f^{(n)}(x_{0})(x-x_{0})^{n} + \frac{1}{(n+1)!} f^{(n+1)}(\xi)(x-x_{0})^{n+1},$  
$\xi$ 在 $x$ 与 $x_{0}$ 之间。

用泰勒公式证明不等式， 最好选用带有 $f^{(n+1)}(\xi)$ 的余项的泰勒公式，尽量不要选择带有佩亚诺  
余项 $o \left[ (x-x_{0})^{n} \right]$ 的泰勒公式，也不要选择展开到无穷远的泰勒级数。


5. 凹凸性.  

设 $ f(x) $ 在区间 $ D $ 上连续，如果对于 $ D $ 上任意两点 $ x_1 $，$ x_2 $ 恒有  
$$
f \left( \frac {x_1 + x_2} {2} \right) \leq \frac {f(x_1) + f(x_2)} {2} ，
$$  
那么称 $ f(x) $ 在 $ D $ 上的图像是凹的；  

如果恒有  
$$
f \left( \frac {x_1 + x_2} {2} \right) \geq \frac {f(x_1) + f(x_2)} {2} ，
$$  
那么称 $ f(x) $ 在 $ D $ 上的图像是凸的.  

上面是函数凹凸性的原式定义，如果已知函数 $ f(x) $ 在区域 $ D $ 内二阶可导，可以得到下面的充要条件:  
$$
f(x) \text { 在区间 } D \text { 上是凹（凸）的 } \iff \forall x \in D ，总有 f''(x) \geq 0 \ (f''(x) \leq 0)，并且在 D \text { 内任意小的区域内 } f''(x) \text { 都不恒为零 }.
$$


一、证明不等式的常见通法：  

1. 恒等变换证明。  

2. 放缩（绝对值不等式、均值不等式、常见结论不等式、柯西不等式）。  

3. 利用导数（以及拉格朗日中值定理、极值、最值、单调性等）。  

4. 利用泰勒公式。  

5. 凹凸性。



内容目录  
一、证明不等式的常见通法（可解决 95%+ 的考研不等式证明题）  
二、恒等变换、放缩证明不等式。  
三、函数不等式  
四、数字不等式  
五、积分不等式


二、恒等变换、放缩证明不等式。  

例1.证明： $ \left ( a_1^2 + a_2^2 \right ) \left ( b_1^2 + b_2^2 \right ) \geq \left ( a_1 b_1 + a_2 b_2 \right )^2 $ ， $\forall a_i, b_i \in R ， i = 1, 2 $ ，  
并且说明等号成立的条件。  

证明: 原式 $\Leftrightarrow a_1^2 b_1^2 + a_1^2 b_2^2 + a_2^2 b_1^2 + a_2^2 b_2^2 \geq a_1^2 b_1^2 + 2 a_1 b_1 a_2 b_2 + a_2^2 b_2^2 $  
$\Leftrightarrow a_1^2 b_2^2 - 2 a_1 b_1 a_2 b_2 + a_2^2 b_1^2 \geq 0 $  
$\Leftrightarrow \left ( a_1 b_2 - a_2 b_1 \right )^2 \geq 0 $ 显然成立。  
当 $ a_1 b_2 = a_2 b_1 $ 时取等号。

例2.证明 $ e^x \geq 1 + x $ ， $\forall x \geq 0 $。

证明： $\frac{x}{x} \leq \ln (1 + x) \leq x $。 $\forall x \geq 0 $  

$ e^{\ln (1 + x)} \leq e^x $
$$
e^{\frac{x}{x}} \leq 1+x \leq e^x
$$

$$
\forall x = \frac{1}{n} . n \in \mathbb{N}_{+} , \frac{1}{n} \leq \ln (1 + \frac{1}{n}) \leq \frac{1}{n}
$$


这个不等式有很多变形，建议同学们多自己动手玩一下，免得以后遇到不认识。  

（1）对原不等式两边取指数则有 $ e^{1+x} \leq 1+x \leq e^x $ ；  

（2）令 $ x = \frac{1}{n} $ ，则原不等式等价于 $ \frac{1}{1+n} \leq \ln \left( 1 + \frac{1}{n} \right) \leq \frac{1}{n} $ ，等号可以去掉，因为 $ \frac{1}{n} $ 取不到0。  

（3）可以继续对（2）变换得到 $ \left[ \ln(n+1) - \ln n \right](n+1) \geq 1 $ 以及 $ \left[ \ln(n+1) - \ln n \right] n \leq 1 $ 。



例 3.判断数列 $ a_n = \left( \frac{e}{n} \right)^n \cdot n! $ 的单调性。

解： $ \frac{a_{n+1}}{a_n} = \left( \frac{ \frac{e}{n+1} }{ \frac{e}{n} } \right)^n \cdot e = e \cdot \left( \frac{n}{n+1} \right)^n $

\[
= \frac{e}{ \left( 1 + \frac{1}{n} \right)^n }
\]

待定。

$ = \frac { e } { ( 1 + \frac { 1 } { n } )^ { n } } \Rightarrow 1 $

$ \Leftrightarrow e \bigcirc ( 1 + \frac { 1 } { n } )^ { n } $

$ \Leftrightarrow 1 \bigcirc n \cdot \ln ( 1 + \frac { 1 } { n } ) $

$ \Rightarrow \frac { 1 } { n } \ln ( 1 + \frac { 1 } { n } ) $

所以 \[  a_{n+1} > a_n  \]


很多同学一遇到放缩，就懵逼了，我们来做做简单的放缩练习：  
例 4. 证明 $\forall x, y \in \mathbb{R} \ (x^2 + y^2 \neq 0)$，均有 $\frac {x^2} {x^2 + y^2} \leq 1$，$\frac {y^2} {x^2 + y^2} \leq 1$。  

$\Leftrightarrow \frac {x^2} {x^2 + y^2} \leq \frac {x^2} {x^2}$ $\Leftrightarrow x^2 \leq x^2 + y^2$

这个不等式简直太简单，学了有用吗？考研会用到吗？  
  
看看这个题：判断二元函数 $ f(x,y) = \begin{cases} 
\frac { x y^4 } { ( x^2 + y^2 )^2 } , x^2 + y^2 \neq 0 \\
0 , x^2 + y^2 = 0 
\end{cases} $ 数在 $( 0,0 ) $ 处是否连续。  
  
$ \lim_{ x \to 0 \atop y \to 0 } \frac { x y^4 } { ( x^2 + y^2 )^2 } = f(0,0) = 0 $  
$ \frac { y^2 } { x^2 + y^2 } \cdot x \to 0 $


例 5. 已知 $ n \in N_{+} $，证明:  
$$\frac{n}{\sqrt{n^{2}+n}} \leq \frac{1}{\sqrt{n^{2}+1}} + \frac{1}{\sqrt{n^{2}+2}} + \cdots + \frac{1}{\sqrt{n^{2}+n}} \leq \frac{n}{\sqrt{n^{2}+1}}$$  

本题的放缩技巧往往用在夹逼准则证明数列极限存在的题目上。

比如计算极限 $ \lim_{n \to \infty} \sum_{k=1}^{n} \frac{1}{\sqrt{n^{2}+k}} $。

例 6. 证明 $\forall x, y \in \mathbb{R} (x^2 + y^2 \neq 0)$，均有 $\left| \frac{\sin (x^3 + y^3)}{x^2 + y^2} \right| \leq \sqrt{x^2 + y^2}$。  

证明：  
$$ \left| \frac{\sin (x^3 + y^3)}{x^2 + y^2} \right| \leq \left| \frac{x^3 + y^3}{x^2 + y^2} \right| \leq \sqrt{x^2 + y^2} $$  
⟺ $\left| x^3 + y^3 \right| \leq (x^2 + y^2)^{\frac{3}{2}}$

$$\Leftrightarrow x^6 + 2x^3y^3 + y^6 \leq x^6 + 3x^4y^2 + 3x^2y^4 + y^6$$  
$$\Leftrightarrow x^2y^2(3x^2 + 3y^2 - 2xy) \geq 0$$  
$$\Leftrightarrow 3x^2 + 3y^2 \geq 2xy \text{ 成立 }.$$  
$$ 2xy \leq x^2 + y^2 \leq 3(x^2 + y^2)$$


本题也可以改造成二元函数连续性判断的问题:  

判断二元函数 $ f(x,y) =  \begin{cases}  
\frac{ \sin (x^3 + y^3)}{ x^2 + y^2} , x^2 + y^2 \neq 0 \\  
0 , x^2 + y^2 = 0  
\end{cases} $ 数在 (0,0) 处是否连续.  

$$ 0 \leq \left| \frac{ \sin (x^3 + y^3)}{ x^2 + y^2} \right| \leq \sqrt{x^2 + y^2} \rightarrow 0$$


例 7. 已知 $ a < c < b $ ，证明：  
$ \text{max} \left\{ \dfrac{1}{{(c - a)}^2} , \dfrac{1}{{(b - c)}^2} \right\} \geq \dfrac{4}{{(b - a)}^2} $  

证明：（分段）左＝ 
$ \begin{cases}  
\dfrac{1}{{(c - a)}^2} ，\dfrac{1}{{(c - a)}^2} \geq \dfrac{1}{{(b - c)}^2} ，只需证 & \dfrac{1}{{(c - a)}^2} \geq \dfrac{4}{{(b - a)}^2} \\ 
\dfrac{1}{{(b - c)}^2} ，\dfrac{1}{{(b - c)}^2} \geq \dfrac{1}{{(c - a)}^2} ，只需证 & \dfrac{1}{{(b - c)}^2} \geq \dfrac{4}{{(b - a)}^2} 
\end{cases}$

$$\frac{1}{(c-a)^2} \geq \frac{1}{(b-c)^2} \iff (b-c)^2 \ge (c-a)^2$$  

$$\iff b-c \ge c-a \quad c \le \frac{a+b}{2}$$

$ \frac{1}{(c-a)^2} < \frac{1}{(b-c)^2} \Leftrightarrow (b-c)^2 < (c-a)^2 $  
$\Leftrightarrow b-c < c-a \Leftrightarrow c > \frac{a+b}{2}$

$ \frac{1}{(c-a)^2} \ge \frac{4}{(b-a)^2} \Leftrightarrow (b-a)^2 \ge 4 (c-a)^2 \Leftrightarrow b-a \ge 2 (c-a) $

$ a + b \geq 2c \iff c \leq \frac {a + b}{2} $

同理可证得 $c > \frac{a+b}{2}$

看下面这个题:

设 $ f(x) $ 在 $ [a,b] $ 上有连续的二阶导数，若 $ f(a)=f(b)=0 $ , 且 $ \left | f''(x) \right |\le M_2 $ , 证明:证明至少存在一点 $ x_0 \in (a,b) $ , 使得:  
$$
\left | f(x_0) \right | \le \dfrac{M_2(b-a)^2}{8}
$$




例 8. 设 $ a_n > 0 $，$ b_n > 0 $，且 $ \frac{a_{n+1}}{a_n} \leq \frac{b_{n+1}}{b_n} $，$ n = 1, 2, \ldots $，证明：$ a_n \leq \frac{a_1}{b_1} b_n $。

证明：  
$$ \frac{a_{n+1}}{b_{n+1}} \leq \frac{a_n}{b_n} $$
令 $ C_n = \frac{a_n}{b_n} $

$ C_{n+1} \leq C_n $. $\{ C_n \}$ 单调  

$ C_{n+1} \leq C_n \leq C_{n-1} \leq \cdots \leq C_2 \leq C_1 $

例9. 设 $ a_1 = 2 $，$ a_{n+1} = \frac{1}{2} \left( a_n + \frac{1}{a_n} \right) (n=1,2, \ldots) $，证明： $\lim_{{n \to \infty}} a_n$ 存在；

证明：$ a_{n+1} = \frac{1}{2} ( a_n + \frac{1}{a_n} ) \geq \frac{1}{2} \cdot 2 \cdot \sqrt{a_n \cdot \frac{1}{a_n}} = 1 \quad n =1,2,\ldots $

$\forall n \in \mathbb{N}^+ , a_n \geq 1 \quad 下\hspace{0.25em}界 $

$ a_{n+1} - a_n = \frac{1}{2} ( a_n + \frac{1}{a_n} ) - a_n = \frac{1}{2} ( - a_n + \frac{1}{a_n} )$

$$ = \frac {1}{2} \frac {1 - a_n^2}{a_n} \leq 0 $$  
  
$\{a_n\}$ 单调。  
  
$$ \lim_{n \to \infty} a_n $$ 存在。

三.函数不等式

此类题往往用方法3 和方法4 处理。  

方法3. 利用导数（以及拉格朗日中值定理、极值、最值、单调性等）。  
比如要证明 $ f(x) \le g(x) $ ，可以构造辅助函数 $ h(x) = f(x) - g(x) $ ，则原命题等价于对定义域中任意一个 $ x $ ，均有 $ h(x) \le 0 $ ，即 $ h_{\text{max}} (x) \le 0 $ 。  

（要使得班里任何一个人都没有我高，当然必须要求最高的人没有我高了）。  

所以，也可以转换成求函数 $ h(x) $ 的最大值（极大值），而往往 $ f(x) $ 和 $ g(x) $ 都是可导函数，从而可以利用导数求 $ h(x) $ 的最大值。  

方法4. 利用泰勒公式。  

$$
f(x) = f(x_{0}) + f'(x_{0})(x - x_{0}) + \frac{1}{2!}f''(x_{0}) (x - x_{0})^2 + \cdots + \frac{1}{n!} f^{(n)} (x_{0}) (x - x_{0})^n + \frac{1}{(n + 1)!}f^{(n + 1)} (\xi) (x - x_{0})^{n + 1} ,
$$  

$\xi$在$x$与$x_{0}$之间。

例1.设$x \geq 0$，证明：$\dfrac{x}{1+x} \leq \ln{(1+x)} \leq x$。

【证明・法一】用方法3证明，我们以右边不等式为例来说明，左边不等式同理便可得。

构造辅助函数$f(x)=\ln{(1+x)}-x，x \geq 0$。

$$
f'(x)=\dfrac{1}{1+x} - 1 = \dfrac{x}{1+x} \geq 0，从而 f(x) 单调递增。再结合 f(0)=0 可得  
$$

$x > 0$时，$f(x) > f(0)=0$。

同理可证另一半。

【证明・法二】本题也可以用拉格朗日中值定理证明，用中值定理把 $ \ln (1+x) $ 处理掉。  

设函数 $ f(t) = \ln (1+t) $ ，$ t \in [0, x] $ ，从而 $ \xi \in (0, x) $ 使得  
$$ f'(\xi) = \frac{f(x) - f(0)}{x - 0} = \frac{\ln (1+x)}{x} = \frac{1}{1+\xi} ，$$  
从而要证明的不等式可化为
$$ \frac{1}{1+x} < \frac{1}{1+\xi} < 1 $$，这个不等式链很容易证明. 我们用之前讲过的恒等变换法来证明.  

$$ \frac{1}{1+x} < \frac{1}{1+\xi} \Leftrightarrow 1 + \xi < 1 + x \Leftrightarrow \xi < x $$，显然成立；  

$$ \frac{1}{1+\xi} < 1 \Leftrightarrow 1 < 1 + \xi \Leftrightarrow 0 < \xi $$也显然成立. 从而命题得证.


例2.若 $ 0 < x < 1 $，证明：$ \frac{1-x}{1+x} < e^{-2x} $.  

【证明】构造辅助函数 $ f(x) = (1-x)e^{2x} - (1+x) $， $ 0 \leq x \leq 1 $.  

$ f'(x) = -e^{2x} + 2(1-x)e^{2x} - 1 = (1-2x)e^{2x} - 1 $ 并不能明显看出来正负，所以继续求导  

$ f''(x) = -2e^{2x} + 2(1-2x)e^{2x} = -4xe^{2x} $，由于 $ 0 \leq x \leq 1 $，所以 $ f''(x) \leq 0 $.  

所以 $ f'(x) $ 在 $ [0,1] $ 上单减，而 $ f'(0) = 0 $，所以 $ f'(x) \leq 0 $，  

从而 $ f(x) $ 在 $ [0,1] $ 上单减，又 $ f(0) = 0 $，所以 $ \forall x \in (0,1) $，均有 $ f(x) < 0 $.

例 3. 设 $ x > 0 $ ，证明： $ ( x^2 - 1 ) \ln x \geq ( x - 1 ) ^2 $ 。
  
【证明·法一】依然用方法 3 处理. 构造辅助函数 $ f \left( x \right) = ( x^2 - 1 ) \ln x - ( x - 1 ) ^2 ，x > 0 $。  

温馨提示：法一并不是最简单的方法，但可以帮助同学们掌握用导数研究函数的方法。  

$ f' \left( x \right) = 2x \ln x - x + 2 - \dfrac{1}{x} $ 。  

（虽然能够看出来一个驻点是 $ x = 1 $，但并不敢确定只有这一个驻点，这是本题的一个细节，如果认为找到一个就只有这一个，考场上必然扣分！所以我们需要继续求导数研究）  

$ f'' \left( x \right) = 2 \ln x + 2 - 1 + \dfrac{1}{x^2} = 2 \ln x + \dfrac{1}{x^2} + 1 $ 。  

（完犊子了，二阶导等于零的点连看都看不出来，而且正负也不能直接看出来. 别担心，我们继续求导）

$$ f''(x) = \frac{2}{x} - \frac{2}{x^3} = \frac{2}{x^3}(x^2 - 1) $$  
令  $ f''(x) = 0 $  有  $\frac{2}{x^3} (x^2 - 1) = 0 $ ， 所以 $ x = 1 $.  

从而当 $ 0 < x < 1 $ 时， $ f''(x) < 0 $ ， 此时 $ f'(x) $ 单调递减；  
当 $ x \geq 1 $ 时， $ f''(x) > 0 $ ， 此时 $ f'(x) $ 单调递增。  

$ f'(x) $ 在经过 $ x = 1 $ 时先减后增， 从而 $ x = 1 $ 是 $ f'(x) $ 的最小值点，  
从而 $ f'(x) \geq f'(1) = 2 \geq 0 $ 从而 $ f'(x) $ 严格单调递增。  

通过观察可得，  $ x = 1 $ 是 $ f'(x) = 0 $ 的一个根 （ 有装 13 嫌疑）， 由于 $ f'(x) $ 单调增,  

所以只有这一个根， 而且 $ 0 < x < 1 $ 时， $ f'(x)< 0 $ ， $ f(x) $ 单调减少； 当 $ x > 1 $ 时，  

$$ f'(x)> 0 $$ ， $ f(x) $ 单调增加。  

从而 $ f(1) $ 为 $ f(x) $ 的最小值点， 即 $ f(x) \geq  f(1) = 0 $ ， 这就是本题要证明的结论。

本方法略有烧脑，我们捋一捋思路：  

根据 $ f'''(x) $ 正负判断出 $ f''(x) $ 的增减，从而判断出 $ f''(x) $ 的最小值大于零，  
从而 $ f'(x) $ 单调增，再结合 $ f'(1) = 0 $ 可知 $ x $ 经过 1 过程中 $ f'(x) $ 由负变正，从而  
$ f(1) $ 是 $ f(x) $ 的最小值点，进而 $ f(x) \geq 0 $ 而得出本题要证明的不等式。

【证明·法二】要证明的不等式左右两边都可以因式分解出来 $(x-1)$，所以可以考虑分类讨论去掉这部分，可以简化证明  
（有的同学不讨论直接两边约掉 $x-1$，必然扣分，鬼知道 $x$ 与 $1$ 的大小？）。  

（1）如果 $x=1$，不等式显然成立。  

（2）若 $x>1$，$(x^2-1) \ln x \geq (x-1)^2 \Leftrightarrow (x+1)\ln x \geq (x-1)$， 构造辅助函数  

$$
f(x)=(x+1)\ln x -x+1，\quad x \geq 1。
$$  

$$
f'(x)=\ln x+\frac{1}{x}，
\quad f''(x)=\frac{1}{x}-\frac{1}{x^2}=\frac{x-1}{x^2}>0，
$$  
从而 $f'(x)$ 单调递增  

从而 $x \geq 1$ 时，$f'(x)>f'(1)>0$，从而 $f(x)$ 单调递增，进一步 $f(x)>f(1)=0$。

（3）若 $ x<1 $， $ ( x^2 - 1 ) \ln x \geq ( x-1 )^2 \Leftrightarrow (x+1) \ln x \leq ( x-1 ) $，  

构造辅助函数 $ f ( x ) = ( x + 1 ) \ln x - x + 1 $， $ x \leq 1 $。  

$$ f' ( x ) = \ln x +\frac{1}{x} $$，  $$ f'' ( x ) = \frac{1}{x} - \frac{1}{x^2} = \frac{1}{x^2} ( x-1 ) < 0 $$，从而 $$ f' ( x ) $$ 单调递减，  

从而 $ x < 1 $ 时，$$ f' ( x ) > f' ( 1 ) > 0 $$，从而 $$ f ( x )$$ 单调递增，进而 $$ f ( x ) > f ( 1 ) = 0 $$。

综上所述，命题成立。  

【总结】两种证法都是用利用导数，结合函数单调或者最值的方法证明不等式的，不同的是，证法二用导数之前先化简处理了一下，所以不需要像证法一那样求到三阶导，过程稍微简单一些。

例4. 设 $ \lim_{{x \to 0}} \frac{f(x)}{x} = 1 $ , 且 $ f''(x) > 0 $ , 证明： $ f(x) \geq x $ .

【证明·法一】用方法3导数搞定.构造辅助函数 $ F(x) = f(x) - x $ , $ x \in \mathbb{R} $ .

要证明的不等式等价于 $ F(x) \geq 0 $ .

由于 $ f(x) $ 二阶导存在, 所以 $ F(x) $ 也存在二阶导数.所以,

$ F'(x) = f'(x) - 1 $ , $ F''(x) = f''(x) > 0 $ , 从而 $ F'(x) $ 单调递增.  

又由于 $ \lim_{{x \to 0}} \frac{f(x)}{x} = 1 $ , 可知 $ f(0) = 0 $ , $ f'(0) = 1 $ , 所以 $ F'(0) = 0 $ .  

且由于 $ F'(x) $ 严格单调递增, 所以 $ x = 0 $ 是 $ F'(x) $ = 0 唯一的根, 所以


|x         | (-∞, 0) | 0        | (0, +∞)|
|----------|---------|----------|--------|
|F'(x)     | －       | 0        | +|
|F(x)      | ↘        | 极小值    | ↗|

由于 x = 0 是 F(x) 唯一的极小值点，所以是最小值点。  
从而 $ F(x) \geq F(0) = 0 $，命题得证。

【证明・法二】本题用方法 4 泰勒公式可以秒杀。  

$$ f(x) = f(0) + f'(0)x + \frac {1}{2!} f''(\xi)x^2 ， \xi 在 0 与 x 之间。$$

根据已知条件 $\lim_{{x \to 0}} \frac {f(x)}{x} = 1$ 可知 $f(0)=0$， $f'(0)=1$， 代入到上述式可得  

$$ f(x) = x + \frac {1}{2} f''(\xi)x^2 \geq x.$$

例 5. 设可导函数 $ f(x) $ 定义在 $ [0,+\infty) $，且恒有 $ f'(x) \ge 2x $，证明  
（1）对于 $\forall x \ge a \ge 0 $，均有 $ f(a)+x^2 \le f(x)+a^2 $；  
（2）对于 $\forall a,b \in [0,+\infty) $，总存在至少一点 $\xi \in [0,+\infty) $，使得 $ f'(\xi) \ge a+b $。  

【证明】（1）要证明的不等式等价于 $ f(a)-a^2 \le f(x)-x^2 $，所以只需要证明  
$ F(x)=f(x)-x^2 $ 单增即可。  

而 $ F'(x)=f'(x)-2x \ge 0 $，所以 $ F(x) $ 单增，  
所以对于 $\forall x \ge a \ge 0 $，均有 $ f(a)+x^2 \le f(x)+a^2 $。

(2) ① 若 $ a=b $，则要证明的结论变为 $ f'(\xi) \geq 2a $，根据恒有 $ f'(x) \geq 2x $，取 $ \xi=a $ 便有 $ f'(\xi)=f'(a) \geq 2a $。  

② 若 $ a \ne b $，不妨设 $ a<b $，则根据第一问可知，总有 $ f(a)-a^2 \leq f(b)-b^2 $，从而    
$$ \frac{f(b)-f(a)}{b-a} \geq a+b $$  
不等号左边再根据拉格朗日中值定理可知存在至少一点 $ \xi \in [0,+\infty) $，使得 $ f'(\xi) \geq a+b $。


例 6. 设 $ f(x) $ 在 $ [0, + \infty ) $ 上可导，且存在 $ k > 0 $，使得 $ f'(x) \leq k f(x) $，  
证明：对任意 $ x \in [0, + \infty) $，均有 $ f(x) \leq e^{kx} f(0) $。  

【分析】我们还是希望能构造一个辅助函数，通过辅助函数的导数来判断辅助函数的增减性，从而得到结论。但由于本题是抽象函数，求导后也必然是抽象函数，要想判断出导数的正负，必须要借助已知条件 $ f'(x) \leq kf(x) $。  

所以我们需要找一个函数，求导之后是 $ f'(x) - kf(x) $，这个思路跟我们之前讲过的中值定理（单中值）可以用微分方程法还原辅助函数极其类似。也可以两边取对数来还原。

我们把 $ f'(x) \leq kf(x) $ 当作等式来解微分方程，同时令 $ y=f(x) $。

$$
\frac{dy}{dx} = ky \Leftrightarrow \frac{dy}{y} = kdx，
$$

$$
\int \frac{dy}{y} = \int kdx，
$$

$$
\ln |y| = kx + C_1，
$$

$$
|y| = e^{C_1} e^{kx}，
$$

$y = \pm e^{c_1}e^{kx}$ ，令 \(\pm e^{c_1}=C\) 可得 \(y = Ce^{kx}\) ，  
从而 \(ye^{-kx}=C\) 。  

所以得到辅助函数 \(F(x) = f(x)e^{-kx}\) 。  

【证明】 构造辅助函数 \(F(x) = f(x)e^{-kx}\) ，\(x \in [0,+\infty)\) 。  

则 \(F'(x) = f'(x)e^{-kx}-kf(x)e^{-kx} = [f'(x)-kf(x)]e^{-kx}\) ,  

由于 \(e^{-kx}>0\) ， 以及 \(f'(x) \leq kf(x)\) ， 可知 \(F'(x) \leq 0\) ，  

从而 \(F(x)\) 单减 ，从而 \(F(x) \leq F(0)\) 。  

即 \(f(x) \leq e^{kx} f(0)\) 。

四.数字不等式
此类型题指的是要证明的式子是由 $ a $ 、 $ b $ 或其他常数组成，往往先构造辅助函数（左右减右， $ b $ 替换成 $ x $ ），然后利用方法 3 处理即可。

例1.设 $ 0<a<b $，证明 $\dfrac {b-a}{b}<\ln \dfrac {b}{a}<\dfrac {b-a}{a}$。

【证明·法一】先证明 $\dfrac {b-a}{b}<\ln \dfrac {b}{a}$，即 $ b-a<b\ln b-b\ln a $，

构造辅助函数 $ f(x)=x\ln x-x\ln a-x+a $，$ x\in [a,b] $。

现在要证明的命题可转化为 $ f(b)>0 $。

$ f'(x)=\ln x-\ln a\ge 0 $，所以 $ f(x) $ 单调递增，再结合 $ f(a)=0 $可得

$ f(b)>f(a)=0 $。

同理可证 $\ln \dfrac {b}{a}<\dfrac {b-a}{a}$。

【证明・法二】要证明的不等式中间是 $\ln b - \ln a$，左边和右边都有 $b-a$，所以可以  

考虑用 **拉格朗日中值定理** 证明。  

要证明的不等式等价于 $ \displaystyle \frac{1}{b}<\frac{\ln b - \ln a}{b-a}<\frac{1}{a} $ 。  

根据拉格朗日中值定理可得 $\exists \xi \in (a,b)$，使得 

$$ (\ln x)' \bigg|_{x=\xi} = \frac{\ln b - \ln a}{b-a} $$  ，即 $$ \frac{1}{\xi} = \frac{\ln b - \ln a}{b-a} $$ 。

从而要证明的不等式等价于 $ \frac{1}{b} < \frac{1}{\xi} < \frac{1}{a} $，再由于 $ 0 < a < \xi < b $ 可知该式显然成立。

【证明·法三】通过观察可以发现,本题可以把 $\frac{b}{a}$ 看做一个整体,设为 $x$ ,从而要证明的不等式等价于 $ 1-\frac{1}{x}<\ln x < x-1,x \geq 1$ 然后再用方法3即可。  

要证明 $1-\frac{1}{x}<\ln x$ 等价于证明 $x-1<x \ln x$ ,设 $f (x) = x \ln x - x + 1, x \geq 1$ 。  

$f'(x) = \ln x \geq 0$, 从而 $f(x)$ 单调递增。由于 $f(1) = 0$, 有 $f(x) > f(1) = 0 $ 。  

类似地可以证明 $\ln x < x - 1$ 。

【证明·法四】把 $ \dfrac{b}{a} $ 看做一个整体 $ x $，要证明的不等式等价于 $ 1-\dfrac{1}{x}<\ln x<x-1 $，  

$x>1$，可以令 $ x-1=t>0 $，进一步可以把要证明的不等式转化成 $ \dfrac{t}{t+1}<\ln (1+t)<t $，  

$t>0$。  

这就是我们前面已经证明过的例1，也是需要记住的常见不等式。  
也就是说，本题就是常见不等式的一种变形而已。

例 2. 设函数 $ f(x) $ 是定义在 $ [0,+\infty) $ 上的可导函数，且 $ f''(x) $ 单调递增. 证明：  

$$ f(a+b)-f(a)< \frac{b}{2} [f'(a)+f'(a+b)] .$$  

【证明】构造辅助函数 $ F(x) = f(x+a) - f(a) - \frac{x}{2} [f'(a) + f'(a+x)] $, $ x \geq 0 $ .  

$$ F'(x) = f'(x+a) - \frac{1}{2} [f'(a)+f'(a+x)]  $$  

$$ = \frac{1}{2}  [f'(a+x)-f'(a)] - \frac{x}{2} f''(a+x) $$  

题目并没有说 $ f(x) $ 三阶可导, 所以不能再继续求导, 所以考虑用拉格朗日中值定理.  

$$ F'(x) = \frac{x}{2} \left[ f''(\xi)-f''(a+x) \right] , \  a < \xi < a+x. $$

由于 $ f''(x) $ 单调递增，所以，$ f''(\xi)<f''(a+x) $，从而 $ F'(x)<0 $。  
从而 $ F(x) $ 单调递减，再结合 $ F(0)=0 $ 可知 $ F(b)<0 $。  

结论得证。


例4.设 $f(x)$ 在 $[a,b]$ 上有连续的二阶导数,若 $f(\frac{a+b}{2})=f'(\frac{a+b}{2})=0$ ,  
$|f''(x)|\leq M_2$ , 证明: $|f(a)|+|f(b)|\leq \frac{M_2(b-a)^2}{4}$ ;  

【分析】有些含有 $a$ 、 $b$ 的不等式证明题,则需要用泰勒公式处理,尤其是涉及到多  
阶导数的题目.  

【证明】先默写出来泰勒公式  

$f(x)=f(x_0)+f'(x_0)(x-x_0)+\frac{1}{2}f''(\xi)(x-x_0)^2$ , $\xi$ 在 $x$ 和 $x_0$ 之间.  

由于已知条件出现了 $f'(\frac{a+b}{2})$ ,所以考虑在 $x_0 = \frac{a+b}{2}$ 处展开.

令 $ x_0 = \frac{a+b}{2} $ 可得  

$ f(x) = f\left(\frac{a+b}{2}\right) + f'\left(\frac{a+b}{2}\right)\left(x-\frac{a+b}{2}\right) + \frac{1}{2}f''(\xi)\left(x-\frac{a+b}{2}\right)^2 $ ·········①  

$ \xi $ 在 $ x $ 和 $ \frac{a+b}{2} $ 之间.  

被展开点选择区间端点，令 $ x = a $ 可得


$ f(a) = f\left(\frac{a+b}{2}\right) - \frac{b-a}{2} f'\left(\frac{a+b}{2}\right) + \frac{(b-a)^2}{8} f''(\xi_1) $ ······················②  

其中 $ a < \xi_1 < \frac{a+b}{2} $ 。  

同理，(1)式中令 $ x = b $ 可得  

$ f(b) = f\left(\frac{a+b}{2}\right) + \frac{b-a}{2} f'\left(\frac{a+b}{2}\right) + \frac{(b-a)^2}{8} f''(\xi_2) $ ······················③
$ f(a) = \frac{(b-a)^2}{8} f''(\xi_1) $ ······································(4)  

$ f(b) = \frac{(b-a)^2}{8} f''(\xi_2) $ ······································(5)  

其中, $ a < \xi_1 < \frac{a+b}{2} < \xi_2 < b $. 从而

$ |f(a)| + |f(b)| = \left|\frac{(b-a)^2}{8} f''(\xi_1)\right| + \left|\frac{(b-a)^2}{8} f''(\xi_2)\right| $

$ = \frac{(b-a)^2}{8} (|f''(\xi_1)| + |f''(\xi_2)|) \leq \frac{M_2(b-a)^2}{4} $

五、积分不等式。  

本质来看，积分不等式也可以归为函数不等式或者数字不等式类型。

例1.设 $ f(x) $ 在 $ [a,b] $ 上连续且严格单调增加，证明：  

$$
(a+b) \int_a^b f(x) dx \leq 2 \int_a^b x f(x) dx .
$$  

【分析】要证明的积分不等式中有字母 $ a $ 和 $ b $，所以我们可以把它当做数字型不等式处理， $ b $ 换成 $ x $，左减右，构造辅助函数。  

【证明】令 $ F(x) = \int_a^x t f(t) dt - \frac{a+x}{2}  \int_a^x f(t) dt $，则有 $ F(a) = 0 $ 。  

$$
F'(x) = \frac{1}{2} \left[ (x-a) f(x) - \int_a^x f(t) dt \right], F'(a) = 0 .
$$

由于没说 $f(x)$ 可导，所以不能再求导数，应该用积分中值定理化掉积分。  

由积分中值定理可得 $\int_a^x f(t)dt = (x-a)f(\xi)$， $a \leq \xi \leq x$， 且 $f(x)$ 单增，  

则 $F'(x) = \frac{1}{2}(x-a)[f(x)-f(\xi)] \geq 0, F'(a) = 0$。  

从而 $F(x)$ 在 $[a,b]$ 上单增，再根据 $F(a) = 0$，  

则 $F(x) \geq 0$，令 $x = b$，则 $F(b) \geq 0$，即 $\int_a^b xf(x)dx \geq \frac{a+b}{2} \int_a^b f(x)dx$。


例2.设 $ f(x) $ 在 $ [0,1] $ 上连续且单调减少，证明：当 $ 0<a<1 $ 时，  

$ \int_0^a f(x)dx \geq a\int_0^1 f(x)dx $ .  

【分析】要证明的式子中有字母 $ a $ ，并且 $ a $ 是可以任意变化的，那么可以把它换成  
$ x $ ，左减右，构造辅助函数，再用导数研究.  

【证明·法一】设 $ F(x)=\int_0^x f(t)dt - x\int_0^1 f(t)dt ,x \in [0,1] $  

显然 $ F(0)=0 $ ， $ F(1)=0 $ .要证明的不等式变为 $ F(a)>0 ,a \in (0,1) $ .  

$ F'(x)=f(x)-\int_0^1 f(t)dt = f(x)-f(\xi),\xi \in (0,1) $  

(没说 $ f(x) $ 可导，所以不能对 $ F'(x) $ 继续求导，只能用积分中值定理处理.)

| $ x $ | $ [0, \xi) $ | $ \xi $ | $ (\xi, 1) $ |  
|---|---|---|---|  
| $ g'(x) $ | $ + $ | $ 0 $ | $ - $ |  
| $ g(x) $ | $ \nearrow $ | 极大 | $ \searrow $ |  

所以 $ F(x) \geq 0 $ 即证得

【证明 · 法二】本题还可以用恒等变换证明:

$ \int_{0}^{a} f(x)dx > a\int_{0}^{1} f(x)dx \Leftrightarrow \int_{0}^{a} f(x)dx > a\int_{0}^{a} f(x)dx + a\int_{a}^{1} f(x)dx $

$ \Leftrightarrow (1-a)\int_{0}^{a} f(x)dx > a\int_{a}^{1} f(x)dx $

$ \Leftrightarrow (1-a) \cdot a \cdot f(\xi_1) > a(1-a)f(\xi_2) $

$ \Leftrightarrow 0 < \xi_1 < a < \xi_2 < 1 $

$ \Leftrightarrow f(\xi_1) > f(\xi_2)，这显然成立。 $


例3.设 $ f(x) $ ， $ g(x) $ 在 $ [a,b] $ 上连续，且满足 $ \int_{a}^{x} f(t)dt \geq \int_{a}^{x} g(t)dt $ ， $ x \in [a,b) $ ，以及 $ \int_{a}^{b} f(t)dt = \int_{a}^{b} g(t)dt $ ，证明： $ \int_{a}^{b} xf(x)dx \leq \int_{a}^{b} xg(x)dx $ 。

【分析】本题已知条件和要证明的结论都有很多积分，看着让人眼花缭乱，所以我们  
把变限积分设成新的函数，方便理解。

【证明】令 $ F(x) = \int_{a}^{x} f(t)dt $ ， $ G(x) = \int_{a}^{x} g(t)dt $ ， $ x \in [a,b] $ 。

则 $ F(a) = G(a) = 0 $ ， $ F(b) = G(b) $ ， $ F'(x) = f(x) $ ， $ G'(x) = g(x) $ ，且 $ F'(x) $   
与 $ G'(x) $ 在 $ [a,b] $ 上连续。

已知条件 $ \int_{a}^{x} f(t)dt \geq \int_{a}^{x} g(t)dt $ 则转化为 $ \int_{a}^{x} F'(t)dt \geq \int_{a}^{x} G'(t)dt $ 。

要证明的结论转化为 $\int_a^b xF'(x)dx \leq \int_a^b xG'(x)dx$.  

接下来我们把已知条件恒等变化一下，看看能得到什么.  

$\int_a^x F'(t)dt \geq \int_a^x G'(t)dt \Leftrightarrow F(t)|_a^x \geq G(t)|_a^x$.  

$\Leftrightarrow F(x)-F(a) \geq G(x)-G(a)$.  

$\Leftrightarrow F(x) \geq G(x)$.

再把要证明的式子恒等变换一下：

$ \int_{a}^{b} xF'(x)dx \leq \int_{a}^{b} xG'(x)dx \Leftrightarrow \int_{a}^{b} xdF(x) \leq \int_{a}^{b} xdG(x) $  

$ \Leftrightarrow xF(x)|_{a}^{b} - \int_{a}^{b} F(x)dx \leq xG(x)|_{a}^{b} - \int_{a}^{b} G(x)dx $  

$ \Leftrightarrow bF(b) - aF(a) - \int_{a}^{b} F(x)dx \leq bG(b) - aG(a) - \int_{a}^{b} G(x)dx $  

$ \Leftrightarrow b[F(b) - G(b)] - \int_{a}^{b} F(x)dx \leq - \int_{a}^{b} G(x)dx \Leftrightarrow \int_{a}^{b} G(x)dx \leq \int_{a}^{b} F(x)dx $

而我们前面刚把已知条件恒等变换成 $F(x) \geq G(x)$，对这个不等式在 $a$ 到 $b$ 上定积分  

即可得到 $\int_a^b G(x)dx \leq \int_a^b F(x)dx$. （连续，积分后相对大小不变，p62比较定理）



例4.设 $f(x)$、$g(x)$ 均为 $[a,b]$ 上的连续函数，证明:  

$ \int_a^b f^2(x)dx \int_a^b g^2(x)dx \geq \left(\int_a^b f(x)g(x)dx\right)^2 $.  

【证明】构造辅助函数 $F(x)=\int_a^x f^2(t)dt \int_a^x g^2(t)dt - \left(\int_a^x f(t)g(t)dt\right)^2$.  

$F'(x)=f^2(x)\int_a^x g^2(t)dt + g^2(x)\int_a^x f^2(t)dt - 2f(x)g(x)\int_a^x f(t)g(t)dt$  

$=\int_a^x [f(x)g(t)-g(x)f(t)]^2 dt \geq 0$，将外面的凑到里面变成完全平方  

由于 $F(a)=0$，从而 $F(b) \geq 0$,  

命题得证.

例5.设 $f(x)$、$g(x)$ 均为 $[a,b]$ 上的连续、单调增加函数 $(0<a<b)$，证明：  

$\int_a^b f(x)dx\int_a^b g(x)dx\leq(b-a)\int_a^b f(x)g(x)dx$.  

【证明】构造辅助函数 $F(x)=\int_a^x f(t)dt\int_a^x g(t)dt-(x-a)\int_a^x f(t)g(t)dt$.  

$F'(x)=f(x)\int_a^x g(t)dt+g(x)\int_a^x f(t)dt-\int_a^x f(t)g(t)dt-(x-a)f(x)g(x)$  

$=\int_a^x[f(x)g(t)+g(x)f(t)-f(t)g(t)-f(x)g(x)]dt$  

$=\int_a^x[f(x)-f(t)][g(t)-g(x)]dt$，因式分解，(x-a)也可以写成积分a～x

$\leq0$，(不管 $x$ 与 $t$ 的大小如何，都小于0)  

由于 $F(a)=0$，从而 $F(b)\leq0$，命题得证.

【总结】例5和例6都是b换成x，左减右构造辅助函数，用导数来证明，同时也都是把积分外面的式子化到积分里面，这个方法与使用积分中值定理化掉积分刚好相反.积分中值定理虽然可以化掉积分，但接下来不好处理，所以为了让两个式子趋同，我们把没有积分的式子放到了积分里面，这是一种处理式子的技巧，同学们要掌握.



例6.设 $ f(x) $ 在 $ [0,1] $ 上有连续的一阶导数, 且 $ f(0)=f(1)=0 $ , $ |f'(x)| \leq M $ , 证明 $ |\int_0^1 f(x)dx| \leq \frac{M}{4} $ .  

【分析】有些积分不等式可以转化成泰勒公式处理, 只需要把变限积分设成一个新的函数.这样就可以把积分化掉, 转化成没有积分的证明题.  

【证明】设 $ F(x)=\int_0^x f(t)dt $ , $ x \in [0,1] $ .  

则已知条件可化为 $ F(x) $ 在 $ [0,1] $ 上有连续的二阶导数, 且 $ F'(0)=F'(1)=0 $ ,  $ |F''(x)| \leq M $ .要证明的式子也可转化为 $ |F(1)| \leq \frac{M}{4} $ .

$ F(x) = F(x_0) + F'(x_0)(x-x_0) + \frac{1}{2}F''(\xi)(x-x_0)^2 $, $ \xi $ 在 $ x $ 与 $ x_0 $ 之间，而 $ x $ 是  $ (0,1) $ 中任意一点。  

因为已知条件中有 $ F'(0) = F'(1) = 0 $，所以可以考虑在 $ x_0 = 0 $ 和 $ x_0 = 1 $ 处展开。  

令 $ x_0 $ 分别为0和1可得  

$ F(x) = F(0) + F'(0)x + \frac{1}{2}F''(\xi_1)x^2 $, $ 0 < \xi_1 < x $.

$ F(x) = F(1) + F'(1)(x-1) + \frac{1}{2}F''(\xi_2)(x-1)^2, \quad x < \xi_2 < 1. $  

根据 $ F(0) = 0 $，以及 $ F'(0) = F'(1) = 0 $，可得  

$ F(x) = \frac{1}{2}F''(\xi_1)x^2, \quad F(x) = F(1) + \frac{1}{2}F''(\xi_2)(x-1)^2, $ 两式相减可得  

$ 0 = F(1) + \frac{1}{2}[F''(\xi_2)(x-1)^2 - F''(\xi_1)x^2], $ 从而

$|F(1)| = \frac{1}{2}|F''(\xi_2)(x-1)^2 - F''(\xi_1)x^2| \leq \frac{1}{2}(x-1)^2|F''(\xi_2)| + \frac{1}{2}x^2|F''(\xi_1)|$  

$\leq \frac{M}{2}[(x-1)^2 + x^2]$  

$= \frac{M}{2}[2(x-\frac{1}{2})^2 + \frac{1}{2}]$  

这时，如果取 $x = \frac{1}{2}$，便有 $|F(1)| \leq \frac{M}{4}$。
（或求出二项式最小值为1/2）


泰勒公式证明题

泰勒公式

$ f(x)=f(x_0)+f'(x_0)(x-x_0)+\frac{1}{2!}f''(x_0)(x-x_0)^2+\cdots+\frac{1}{n!}f^{(n)}(x_0)(x-x_0)^n+\frac{1}{(n+1)!}f^{(n+1)}(\xi)(x-x_0)^{n+1} $

$\xi$ 在 $x$ 与 $x_0$ 之间.
（x是被展开点，$ x_0 $是展开点）

按照展开点的不同可以分为四类：  

一、在题目中已给特殊点展开；  

二、在区间中点展开；  

三、在开区间内任一点展开；  

四、在开区间内的极值（最值）处展开。

（被展开点选择区间的两段点）

一。

例：设 $f(x)$ 在 $[-1,1]$ 上具有三阶连续导数，且 $f(-1)=0$， $f(1)=1$， $f'(0)=0$.证明：在 $(-1,1)$ 上至少存在一点 $\xi$，使得 $f'''(\xi)=3$.  

证明：题目涉及到 $f(x)$， $f'(x)$ 和 $f'''(x)$，沟通他们最好的便是泰勒公式.  

由于有 $f(-1)=0$、 $f(1)=1$ 和 $f'(0)=0$，而且0刚好是 $[-1,1]$ 的中点，  

所以可以尝试在 $x_0 = 0$ 处展开.区间端点定为被展开点.  

$f(x)= f(0)+f'(0)x+\frac{x^2}{2}f''(0)+\frac{x^3}{6}f'''(\eta)$， $\eta$ 在0与x之间.  

令 $x=-1$ 可得， $f(-1)= f(0)-f'(0)+\frac{1}{2}f''(0)-\frac{1}{6}f'''(\xi_1)$， $\xi_1 \in (-1,0)$.  

令 $x=1$ 可得， $f(1)= f(0)+f'(0)+\frac{1}{2}f''(0)+\frac{1}{6}f'''(\xi_2)$， $\xi_2 \in (0,1)$.  

代入时 $\eta$ 要变 $ \xi $

将已知条件 $ f(-1) = 0 $, $ f(1) = 1 $, $ f'(0) = 0 $ 代入上面两个式子，可得  

$ 0 = f(0) + \frac{1}{2}f''(0) - \frac{1}{6}f'''(\xi_1) $, $ 1 = f(0) + \frac{1}{2}f''(0) + \frac{1}{6}f'''(\xi_2) $.  

两式相减可得，$ f'''(\xi_1) + f'''(\xi_2) = 6 $.  

再根据 $ f'''(x) $ 在 $ [-1,1] $ 上连续，根据介值定理可得（平均值必在两者之间）  

$ \exists \xi \in (\xi_1, \xi_2) $，使得 $ f'''(\xi) = \frac{f'''(\xi_1) + f'''(\xi_2)}{2} = 3 $.



二：
例：设 $f(x)$ 在 $[a,b]$ 上有三阶连续导数，证明必定存在 $\xi \in (a,b)$，使得  
$f(b)=f(a)+(b-a)f'(\frac{a+b}{2})+\frac{1}{24}(b-a)^3 f'''(\xi)$.

证明：本题已知条件没给任何特殊点，  
但要证明的式子中有 $f'(\frac{a+b}{2})$，所以考虑在区间中点处展开泰勒公式.

$f(x)=f(\frac{a+b}{2})+f'(\frac{a+b}{2})(x-\frac{a+b}{2})+\frac{1}{2}f''(\frac{a+b}{2})(x-\frac{a+b}{2})^2+\frac{1}{6}f'''(\eta)(x-\frac{a+b}{2})^3$. $\eta$ 在 $x$ 与 $\frac{a+b}{2}$ 之间.

$f(a)=f(\frac{a+b}{2})-f'(\frac{a+b}{2})(\frac{b-a}{2})+\frac{1}{2}f''(\frac{a+b}{2})(\frac{b-a}{2})^2-\frac{1}{6}f'''(\xi_1)(\frac{b-a}{2})^3$. $\xi_1 \in (a,\frac{a+b}{2})$.

$f(b)=f(\frac{a+b}{2})+f'(\frac{a+b}{2})(\frac{b-a}{2})+\frac{1}{2}f''(\frac{a+b}{2})(\frac{b-a}{2})^2+\frac{1}{6}f'''(\xi_2)(\frac{b-a}{2})^3$. $\xi_2 \in (\frac{a+b}{2},b)$.

要证明的式子中 $ f(a) $ 与 $ f(b) $ 在等号两边，所以上面两个泰勒公式需要做减法.  

两式相减，可得 $ f(b) - f(a) = (b-a)f'\left(\frac{a+b}{2}\right) + \frac{(b-a)^3}{48} [f'''(\xi_1) + f'''(\xi_2)] $.  

再根据 $ f'''(x) $ 闭区间内连续，根据介值定理可得  

$ \exists \xi \in (\xi_1, \xi_2) $，使得 $ f'''(\xi) = \frac{f'''(\xi_1) + f'''(\xi_2)}{2} $，从而上式可化为:  

$ f(b) - f(a) = (b-a)f'\left(\frac{a+b}{2}\right) + \frac{(b-a)^3}{24} f'''(\xi) $. 证毕.



三：

例：设 $f(x)$ 在 $[0,1]$ 上具有二阶导数，且满足条件 $|f(x)| \leq a$，$|f''(x)| \leq b$，其中 $a$，$b$ 均为非负实数，$c$ 是 $(0,1)$ 内任意一点，证明：$|f'(c)| \leq 2a + \frac{b}{2}$。

证明：本题没有特殊点的函数值，也没有出现中点，但要证明的 $c$ 在 $(0,1)$ 内，所以可以将 $c$ 作为展开点，区间端点定为被展开点。

$f(x) = f(c) + f'(c)(x-c) + \frac{1}{2!}f''(\eta)(x-c)^2$，$\eta$ 在 $x$ 与 $c$ 之间。

分别令 $x = 0$、$x = 1$ 可得：

$f(0) = f(c) - cf'(c) + \frac{1}{2!}f''(\xi_1)c^2$，$\xi_1 \in (0,c)$。

$f(1) = f(c) + f'(c)(1-c) + \frac{1}{2!}f''(\xi_2)(1-c)^2$，$\xi_2 \in (c,1)$。

两个式子里面c比较多，不方便估算 $f'(c)$ 的范围，  
所可以考虑在保留 $f'(c)$ 的条件下，尽可能消掉多余的c。  

两式相减可得： $f(1) - f(0) = f'(c) + \frac{1}{2}[f''(\xi_2)(1-c)^2 - f''(\xi_1)c^2]$ ，解出 $f'(c)$ ，  

$f'(c) = f(1) - f(0) - \frac{1}{2}[f''(\xi_2)(1-c)^2 - f''(\xi_1)c^2]$ ，从而  

$|f'(c)| = |f(1) - f(0) - \frac{1}{2}[f''(\xi_2)(1-c)^2 - f''(\xi_1)c^2]|$  

$\leqslant |f(1)| + |f(0)| + \frac{1}{2}|f''(\xi_2)|(1-c)^2 + \frac{1}{2}|f''(\xi_1)|c^2$  

$\leqslant 2a + \frac{b}{2}[(1-c)^2 + c^2]$
（用绝对值不等式将绝对值里的➖号变➕号）

如果我们能证明出来 $ (1-c)^2 + c^2 \leq 1 $，那就完美了。

设 $ g(x) = (1-x)^2 + x^2 $， $ x \in [0,1] $。

$ g(x) = 2x^2 - 2x + 1 = 2\left(x - \frac{1}{2}\right)^2 + \frac{1}{2} \leq 2\frac{1}{4} + \frac{1}{2} = 1 $。

所以， $ |f'(c)| \leq 2a + \frac{b}{2}[(1-c)^2 + c^2] \leq 2a + \frac{b}{2} $。

证毕.


四：

例：设函数 $f(x)$ 在 $[0,1]$ 上具有二阶导数，且 $f(0)=f(1)=0$，$\min_{x\in[0,1]} f(x)=-1$. 证明：  
$\max_{x\in[0,1]} f''(x) \geq 8$.

证明：本题给了 $f(0)=f(1)=0$，可以将 $x=0$、$x=1$ 作为被展开点.  
由于 $\min_{x\in[0,1]} f(x)=-1$，并且函数 $f(x)$ 在 $[0,1]$ 上有二阶导数，  
所以一定在开区间 $(0,1)$ 内取到最小值，并且一定是极值，  
从而这点一阶导数为零.这个极值点可以当做展开点.  

设 $x=\eta$ 时， $f(x)$ 取到最小值，易知，该最小值也是极值，  
从而 $f'(\eta)=0$， $f(\eta)=-1$.  

$f(x)=f(\eta)+f'(\eta)(x-\eta)+\frac{1}{2}f''(\xi)(x-\eta)^2$， $\xi$ 在 $x$ 与 $\eta$ 之间.

分别令 $x = 0$、$x = 1$ 可得

$f(0) = f(\eta) - f'(\eta)\eta + \frac{1}{2}f''(\xi_1)\eta^2$, $0 < \xi_1 < \eta$.  

$f(1) = f(\eta) + f'(\eta)(1-\eta) + \frac{1}{2}f''(\xi_2)(1-\eta)^2$, $\eta < \xi_2 < 1$.  

将 $f(0) = f(1) = 0$、$f'(\eta) = 0$ 以及 $f(\eta) = -1$ 代入上面两式，并化简可得

$f''(\xi_1) = \frac{2}{\eta^2}$, $f''(\xi_2) = \frac{2}{(1-\eta)^2}$.
（不用非要相减，有已知可以将不需要的去除就行）

（接下来只要证有一个值大于等于8就行了）




现在需要证明的是，两个式子至少一个大于等于8即可.  
如果不知道如何讨论，可以用恒等变换法处理下一下：

$ \frac{2}{\eta^2} \geq 8 \Leftrightarrow \eta^2 \leq \frac{1}{4} \Leftrightarrow 0 \leq \eta \leq \frac{1}{2} $,

$ \frac{2}{(1-\eta)^2} \geq 8 \Leftrightarrow (1-\eta)^2 \leq \frac{1}{4} \Leftrightarrow 0 \leq 1-\eta \leq \frac{1}{2} \Leftrightarrow \frac{1}{2} \leq \eta \leq 1 $

所以对 $\eta$ 按照 $\frac{1}{2}$ 分类即可.


显然，当 $\eta \in \left[0, \frac{1}{2}\right]$ 时，$\frac{2}{\eta^2} \geq 8$，即 $f''(\xi_1) \geq 8$；  

当 $\eta \in \left(\frac{1}{2}, 1\right]$ 时，$\frac{2}{(1-\eta)^2} \geq 8$，即 $f''(\xi_2) \geq 8$。  

所以原命题成立。  

证毕。


四
例：设 $f(x)$ 函数在 $[a,b]$ 上二阶可导，且 $|f''(x)| \leq M$，$f(a)=f(b)=0$。证明：当 $a \leq x \leq b$  
时，$|f(x)| \leq \frac{M(b-a)^2}{8}$。  

证明：本题给了端点处的函数值 $f(a)=f(b)=0$，可以考虑在被展开点为端点。  
展开点不太好找，选中点不好，因为选中点即便证明出结论，也只能说中点处满足条件，  
不能说对于区间内任何 $x$ 均成立。  
要使得区间内任何一个点都有结论的不等式，我们可以在使得 $|f(x)|$ 取到最大的点展开。  
最大的点都满足结论，那么区间内任何一个点自然也都满足结论了。  
设 $x=x_0$ 时，$|f(x)|$ 取到最大值。  
如果 $x_0$ 在开区间内部，根据费马引理可知，$f'(x_0)=0$，这点是展开点的不二选择。  
但如果 $x_0$ 在区间端点，就不能用费马引理了，所以需要讨论一下 $x_0$ 是否是区间端点。
(1) 若 $x_0 = a$ 或者 $x_0 = b$，那么 $|f(x)|_{\max} = |f(x_0)| = |f(a)| = 0$。  
又由于 $|f(x)| \geq 0$，从而在区间 $[a,b]$ 上， $f(x) \equiv 0$，要证明的结论自然成立。  

(2) 如果 $x_0$ 不在区间端点，那么由于 $f(x)$ 在区间内二阶可导，  
所以根据费马引理可知， $f'(x_0) = 0$。  
在 $x_0$ 处展开泰勒公式，可得  
$f(x) = f(x_0) + f'(x_0)(x-x_0) + \frac{1}{2}f''(\xi)(x-x_0)^2$， $\xi$ 在 $x$ 与 $x_0$ 之间。

$ f(x_0) = -\frac{1}{2}f''(\xi_1)(a-x_0)^2, \quad f(x_0) = -\frac{1}{2}f''(\xi_2)(b-x_0)^2. $  

$ |f(x_0)| = \frac{1}{2}|f''(\xi_1)|(a-x_0)^2 \leq \frac{M}{2}(a-x_0)^2, $  

$ |f(x_0)| = \frac{1}{2}|f''(\xi_2)|(b-x_0)^2 \leq \frac{M}{2}(b-x_0)^2. $  

所以只需要 $ \frac{M}{2}(a-x_0)^2 $ 或者 $ \frac{M}{2}(b-x_0)^2 $ 小于等于 $ \frac{M(b-a)^2}{8} $ 即可.

当 $x_0 \in \left[a, \frac{a+b}{2}\right]$ 时， $(a-x_0)^2 \leq \left(\frac{b-a}{2}\right)^2$ ，从而 $\frac{M}{2}(a-x_0)^2 \leq \frac{M(b-a)^2}{8}$ 。  

同理，当 $x_0 \in \left(\frac{a+b}{2}, b\right]$ 时， $\frac{M}{2}(b-x_0)^2 \leq \frac{M(b-a)^2}{8}$ 。  

所以原命题成立。  

证毕.



总结：泰勒公式证明题，主要是研究展开点与被展开点。  

1.被展开点往往是区间端点；  

2.展开点细节较多，分为下面几种情况：  
（1）已知条件给了区间内部的特殊点，很可能这个特殊点即为展开点；  
（2）要证明的式子中有区间中点，很可能在区间中点展开；  
（3）在函数 $ f(x) $ 的极值点，或者是 $ |f(x)| $ 的极值点很可能是展开点。  
（4）要证明区间内任一点 $ x $ 都满足某式子，可以在开区间内任一点展开。  

3.展开成多个泰勒公式后，相加还是相减，需要观察要证明的式子的特点。  

4.涉及到 $ f(x) $ 、 $ f'(x) $ 和 $ f''(x) $ 的证明题，往往要运用绝对值不等式放缩。  

5.绝对值里有减号的式子用绝对值不等式化为加号

6.已经无其他无关项的不用继续相减，单独与目标形成不等式讨论



有界最值零点定理中值定理

已知$f(x)$闭区间连续，则满足介值定理（最大值最小值）（闭区间）
$m \leq f(x) \leq M$两边同乘同除来凑题目条件

罗尔，拉朗，柯西中值定理 是开区间

证明连续的定义有两个：  
$ \lim_{\Delta x \to 0} [f(x+\Delta x) - f(x)] = 0 $  
$ \lim_{x \to x_0} [f(x) - f(x_0)] = 0 $

例 1.设 $ f(x) $ 在 $ (-\infty,+\infty) $ 内有定义， $ f(x) $ 在点 $ x=0 $ 连续，且对于任意 $ x,y \in R $ ，有 $ f(x+y)=f(x)+f(y) $ ，证明 $ f(x) $ 在 $ (-\infty,+\infty) $ 内处处连续。

证明：$ \lim_{\Delta x \to 0} [f(x+\Delta x)-f(x)] $

$ = \lim_{\Delta x \to 0} [f(x)+f(\Delta x)-f(x)] $

$ = \lim_{\Delta x \to 0} f(\Delta x) = f(0) $

由于$ f(x+y) = f(x) + f(y)$, 令 $x=y=0$, 有  

$ f(0) = 2f(0) \Rightarrow f(0) = 0 $  

$\therefore \lim_{\Delta x \to 0} [f(x+\Delta x) - f(x)] = 0$  

即 $ \forall x \in (-\infty, +\infty), f(x) $ 为连续

或用公式 $ \lim_{x \to x_0} [f(x) - f(x_0)] = 0 $  

即 $ \lim_{x \to x_0} [f(x+x_0-x_0) - f(x_0)] $  

$ = \lim_{x \to x_0} [f(x-x_0) + f(x_0) - f(x_0)] $  

$ = \lim_{x \to x_0} [f(x-x_0)] = f(0) $

...






例2. 设 $f(x)$ 在 $[a,b]$ 连续，且对任何 $x \in [a,b]$，存在 $y \in [a,b]$，使得  
$|f(y)| \leq \frac{1}{2}|f(x)|$。证明：存在 $\xi \in [a,b]$，使得 $f(\xi) = 0$。

证明：反证法。假设不存在，使得 $f(\xi) = 0$。  

则 $f(x)$ 在 $[a,b]$ 恒大于 $ 0 $ 或恒小于 $ 0 $。  

不妨设 $f(x) > 0$，$\forall x \in [a,b]$。  

易知 $f(x)$ 一定有最大值最小值。

设 $ f(x_1) = M $ 为最大值。  

$ f(x_2) = m $ 为最小值。则对于 $ x_2 $,  

一定存在 $ x_3 $, 使得  

$ |f(x_3)| \leq \frac{1}{2}|f(x_2)|, $ 即  

$ f(x_3) \leq \frac{1}{2}f(x_2) $


$ f(x_3) \leq \frac{1}{2} f(x_2) < f(x_2) $  

$\therefore$ 矛盾。

例3.设 $a_1$, $a_2$, $a_3$ 为正数, $\lambda_1$, $\lambda_2$, $\lambda_3$ 互不相等, 证明方程 $\frac{a_1}{x-\lambda_1} + \frac{a_2}{x-\lambda_2} + \frac{a_3}{x-\lambda_3} = 0$  
有且仅有两个根. 

证明: 设 $f(x) = \frac{a_1}{x-\lambda_1} + \left(\frac{a_2}{x-\lambda_2} + \frac{a_3}{x-\lambda_3}\right)$, 不妨设 $\lambda_1 < \lambda_2 < \lambda_3$.  

$x \to \lambda_1^-$ 时, $\frac{a_1}{x-\lambda_1} \to -\infty$, $f(x) \to -\infty$  

$x \to \lambda_1^+$ 时 $\frac{a_1}{x-\lambda_1} \to +\infty$, $f(x) \to +\infty$

$ x \to \lambda_2^- $ 时, $ \frac{a_2}{x-\lambda_2} \to -\infty, f(x) \to -\infty $  

$ x \to \lambda_2^+ $ 时, $ \frac{a_2}{x-\lambda_2} \to +\infty, f(x) \to +\infty $  

$ x \to \lambda_3^- $ 时, $ \frac{a_3}{x-\lambda_3} \to -\infty, f(x) \to -\infty $  

$ x \to \lambda_3^+ $ 时, $ \frac{a_3}{x-\lambda_3} \to +\infty, f(x) \to +\infty $

从 $ \lambda_1^+ $ 到 $ \lambda_2^- $ 有一根，从 $ \lambda_2^+ $ 到 $ \lambda_3^- $ 有一根

$ f(x) = 0 $ 有两根，分别在 $ (\lambda_1, \lambda_2) $ 与 $ (\lambda_2, \lambda_3) $ 之间。

易证: 原方程等价于

$ a_1(x-\lambda_2)(x-\lambda_3) + a_2(x-\lambda_1)(x-\lambda_3) + a_3(x-\lambda_1)(x-\lambda_2) = 0 $

令 $ f(x) = a_1(x-\lambda_2)(x-\lambda_3) + a_2(x-\lambda_1)(x-\lambda_3) + a_3(x-\lambda_1)(x-\lambda_2) $

$ f(\lambda_1) = a_1(\lambda_1-\lambda_2)(\lambda_1-\lambda_3) $  
$ f(\lambda_2) = a_2(\lambda_2-\lambda_1)(\lambda_2-\lambda_3) $  
$ f(\lambda_3) = a_3(\lambda_3-\lambda_1)(\lambda_3-\lambda_2) $

$ \lambda_1 < \lambda_2 < \lambda_3 $  

$ f(\lambda_1) < 0 , f(\lambda_2) > 0 , f(\lambda_3) < 0 $  

有两根

1. $ f(x) = 0 $ 在 $ (x_1, x_2) $ 与 $ (x_2, x_3) $ 之间各有一根。  

2. $ f(x) = 0 $ 是一元二次方程, 最多 2 个根  

3. $ f(x) = 0 $ 有且仅有 2 个根  

证毕

例4.设 $ f(x) $ 在 $ [a,b] $ 上连续， $ x_1, x_2, ..., x_n \in [a,b] $ ，另有一组正数 $ \lambda_1, \lambda_2, ..., $  
$ \lambda_n $ 满足 $ \lambda_1 + \lambda_2 + ... + \lambda_n = 1 $ .证明：存在一点 $ \xi \in [a,b] $ ，使得  
$ f(\xi) = \lambda_1 f(x_1) + \lambda_2 f(x_2) + ... + \lambda_n f(x_n) $ . 右侧定理.  

证明：由于 $ f(x) $ 在 $ [a,b] $ 上连续，则 $ f(x) $ 在 $ [a,b] $ 一定有最大值和最小值，  
设 M, m 分别为 $ f(x) $ 的最大值与最小值，即 $ m \leq f(x) \leq M. \forall x \in [a,b] $ .  

$ m \leq f(x_1) \leq M $  
$ m \leq f(x_2) \leq M $
...
$ m \leq f(x_n) \leq M $
两边同乘$\lambda_1$ ~ $\lambda_n$

$ \lambda_2 m \leq \lambda_2 f(x_2) \leq \lambda_2 M $  

$ \lambda_n m \leq \lambda_n f(x_n) \leq \lambda_n M $  

上述n个式相加可得  

$ m(\lambda_1 + \lambda_2 + \cdots \lambda_n) \leq \sum_{k=1}^n \lambda_k f(x_k) \leq M(\lambda_1 + \lambda_2 + \cdots \lambda_n) $  

$ m \leq \sum_{k=1}^n \lambda_k f(x_k) \leq M $

**加权平均的特性**：
   $\lambda_1 f(x_1) + \lambda_2 f(x_2) + ... + \lambda_n f(x_n)$ 是一个加权平均。加权平均的一个重要性质是，它总是位于其所有项的最小值和最大值之间。

例5.设 $ f(x) $ 在 $ [0,1] $ 上连续，且 $ f(0) = f(1) $ ，证明:  

1.存在 $ \xi \in [0,1] $ ，使得 $ f(\xi) = f(\xi + \frac{1}{2}) $ ; 

2.存在 $ \xi \in (0,1) $ ，使得 $ f(\xi) = f(\xi + \frac{1}{4}) $ ;  

3.若 $ f(x) $ 在 $ [0,1] $ 上非负，对任意 $ a \in (0,1) $ ，总存在 $ \xi \in [0,1] $ ，使得 $ f(\xi) = f(\xi + a) $ .  

证明：1. 设 $ F(x) = f(x) - f(x+\frac{1}{2}) $ ， $ x \in [0,\frac{1}{2}] $ (目标：找 $ \xi \in [0,1], F(\xi)=0 $ )  
     $ F(0) = f(0) - f(\frac{1}{2}) $ .  $ F(\frac{1}{2}) = f(\frac{1}{2}) - f(1) = f(\frac{1}{2}) - f(0) $

(1) $ F(0) \cdot F(\frac{1}{2}) = 0 $  

① $ F(0) = 0 $, 则取 $ \xi = 0 $, 则有 $ F(\xi) = F(0) = 0 $  
② $ F(\frac{1}{2}) = 0 $, 则取 $ \xi = \frac{1}{2} $, 则有 $ F(\xi) = F(\frac{1}{2}) = 0 $  

(2) $ F(0) \cdot F(\frac{1}{2}) < 0 $, 根据零点定理, 可直接得结果.  

综上, 存在 $ \xi \in [0, \frac{1}{2}] \subseteq [0, 1] $, 使得 $ F(\xi) = 0 $.  

证毕.

1.问另证: $ F(0) + F(1) = 0 $, 则根据第4题, $ \forall \xi \in [0,1] $, 使得  

$ F(\xi) = \frac{1}{2}[F(0) + F(1)] = 0 $.

**零点定理是开区间**（正数x负数＜0）

2. 设 $ G(x) = f(x) - f(x+\frac{1}{4}) $, $ x \in [0, \frac{3}{4}] $  

$ G(0) = f(0) - f(\frac{1}{4}) $  
$ G(\frac{1}{4}) = f(\frac{1}{4}) - f(\frac{2}{4}) $  
$ G(\frac{2}{4}) = f(\frac{2}{4}) - f(\frac{3}{4}) $  
$ G(\frac{3}{4}) = f(\frac{3}{4}) - f(0) $  

相加得到 $ G(0) + G(\frac{1}{4}) + G(\frac{2}{4}) + G(\frac{3}{4}) = 0 $

单独讨论$ x=0 $处  

(就怕 $\xi=0 $使得$ G(\xi)=0 $成立, 但 $ \forall x \in (0,\frac{\pi}{4}), G(\xi) \neq 0 $)  
若$ \xi=0$, 则$ G(\xi) = G(0) = 0$ , 则 $ G(\frac{\pi}{4}) + G(\frac{\pi}{4}) + G(\frac{\pi}{4}) = 0 $

设函数 $ G(x) \neq 0 $, 则 $ G(\frac{1}{4}) \neq 0 $, $ G(\frac{2}{4}) \neq 0 $, $ G(\frac{3}{4}) \neq 0 $  

∴ $ G(\frac{1}{4}) $, $ G(\frac{2}{4}) $, $ G(\frac{3}{4}) $ 至少一个为正，至少一个为负。  

不妨设 $ G(\frac{1}{4}) < 0 $, $ G(\frac{3}{4}) > 0 $, 则根据零点定理，  

于 $ \in (\frac{1}{4}, \frac{3}{4}) $, 使得 $ G(ξ) = 0 $  

∴ 于 $ \in (0, \frac{3}{4}) $, 使得 $ G(ξ) = 0 $, 即

$\exists \xi  \in (0,1)$, 使得$ f(\xi) = f(\xi + \frac{1}{4}) $

3.太难别学了

例 6.设函数 $f(x)$ 在 $[a,b]$ 上连续， $g(x)$ 在 $[a,b]$ 上可积且不变号，证明至少存在  
一点 $\xi \in [a,b]$ ，使得 $\int_a^b f(x)g(x)dx = f(\xi)\int_a^b g(x)dx$ .  

证明：设 $f(x)$ 最大值为 $M$ ，最小值为 $m$ . 则 $m \leq f(x) \leq M$ 恒成立.  

$m \cdot g(x) \leq f(x) \cdot g(x) \leq M g(x)$  

$m\int_a^b g(x) dx \leq \int_a^b f(x)g(x)dx \leq M \int_a^b g(x)dx$

$ m \leq \frac{\int_{a}^{b} f(x) \cdot g(x)dx}{\int_{a}^{b} g(x)dx} \leq M $,  

则$  ∃ \xi ∈ [a,b]$, 使得  

$ f(\xi) = \frac{\int_{a}^{b} f(x) \cdot g(x)dx}{\int_{a}^{b} g(x)dx} $.


若题目改成$\xi \in (a,b)$开区间，得换方法

考虑证明ξ在(a,b).  

设 $ F(x) = \int_a^x f(t)g(t)dt. x\in[a,b] $  

则 $ \int_a^b f(t)g(t)dt = F(b)-F(a) $  

$ G(x) = \int_a^x g(t)dt. x\in[a,b] $  

则 $ \int_a^b g(x)dx = G(b)-G(a) $  

$ \int_a^b f(x)g(x)dx = f(ξ).\int_a^b g(x)dx $  

$ \frac{\int_a^b f(x)g(x)dx}{\int_a^b g(x)dx} = f(ξ) $  

$ \frac{F(b)-F(a)}{G(b)-G(a)} = \frac{F'(ξ)}{G'(ξ)} $

根据柯西中值定理， 存在  

$ \frac{F(b) - F(a)}{G(b) - G(a)} = \frac{F'(\xi)}{G'(\xi)} $ 即 $ \frac{\int_a^b f(x)g(x)dx}{\int_a^b g(x)dx} = \frac{f(\xi) \cdot g(\xi)}{g(\xi)} = f(\xi) $  

证毕


例 7.设 $ f(x) $ 在 $ (-\infty,+\infty) $ 上连续，且 $ \lim_{x \to \infty} \frac{f(x)}{x} = 0 $，证明存在 $ \xi \in (-\infty,+\infty) $，使得$ f(\xi) + \xi = 0 $.  
（构造函数某一点为0，连续，零点出正负）
证明：设 $ F(x) = f(x) + x, x \in (-\infty, +\infty) $  

$ \lim_{x \to \infty} F(x) = \lim_{x \to \infty} x \cdot [\frac{f(x)}{x} + 1] = \lim_{x \to \infty} x = \infty $  

$ \lim_{x \to +\infty} F(x) = +\infty, \lim_{x \to -\infty} F(x) = -\infty $

且 $ f(x) $ 在 $ (-\infty, +\infty) $ 上连续，则 $ F(x) $ 连续  

则 $ \exists x_1, x_2 \in (-\infty, +\infty) $ ，使得 $ f(x_1) < 0 $ ， $ f(x_2) > 0 $  

不妨设 $ x_1 < x_2 $ ，则 $ \exists \xi \in (x_1, x_2) \subset (-\infty,+\infty) $ ，  

使得 $ f(\xi) = 0 $ 。

例 8. 证明方程 $ x^n + x^{n-1} + ... + x = 1 (n \geq 2) $ 在区间 $ (0,1) $ 内有且仅有一个实根，并记 该方程的实根为 $ x_n $，证明 $ \lim_{n \to \infty} x_n $ 存在并求该极限。  
（证有且仅有：单调加有根）
证明：设 $ f(x) = x^n + x^{n-1} + ... + x - 1 $. $ x \in [0,1] $ 显然 $ f(x) $ 在 $ [0,1] $ 上  
连续。且 $ f(0) = -1 < 0 $, $ f(1) = n - 1 \geq 1 > 0 $. 根据零点定理,有  
$ \exists \xi \in (0,1) $, 使得 $ f(\xi) = 0 $  

$ f'(x) = n x^{n-1} + (n-1) x^{n-2} + ... + 1 > 0 $, $ \therefore f(x) = 0 $ 只有唯一根 $ x = \xi $
由已知可得 $ x_n^n + x_n^{n-1} + \cdots + x_n = 1, \quad 0 < x_n < 1, \quad \{x_n\} 有界. $  

$ x_{n+1}^{n+1} + x_{n+1}^n + x_{n+1}^{n-1} + \cdots + x_{n+1} = 1 $  

$ (x_n^n - x_{n+1}^n) + (x_n^{n-1} - x_{n+1}^{n-1}) + \cdots + (x_n - x_{n+1}) = x_{n+1}^{n+1} $  

$ (x_n - x_{n+1})[(x_n^{n-1} + x_n^{n-2}x_{n+1} + x_n^{n-3}x_{n+1}^2 + \cdots + x_{n+1}^{n-1}) + (x_n^{n-2} + x_n^{n-3}x_{n+1} + \cdots x_{n+1}^{n-2})  + \cdots + 1] = x_{n+1}^{n+1} $

$ x_n - x_{n+1} > 0 $. 即 $ x_{n+1} < x_n $. 即 $ \{x_n\} $ 单减。又 $ \{x_n\} $ 有界，  

$ \therefore \lim_{n \to \infty} x_n $ 存在。

由于 $ x_n^n + x_n^{n-1} + x_n^{n-2} + ... + x_n = 1 $ , 即  

$ \frac{x_n(1-x_n^n)}{1-x_n} = 1 $. 取 $ n \to \infty $ 时 $ \lim_{n \to \infty} S_n = a \in (0,1) $  

$ \frac{a}{1-a} = 1 \Rightarrow a = \lim_{n \to \infty} x_n = \frac{1}{2} $




例9. 设 $ f(x) $ 在 $ (-\infty,+\infty) $ 连续，且 $ \lim_{x \to -\infty} f(x)=A $，$ \lim_{x \to +\infty} f(x)=B $ 证明：  

(1) 设 $ A<B $，则对 $ \forall C \in (A,B) $，$ \exists \xi \in (-\infty,+\infty) $，使得 $ f(\xi)=C $；  
(2) $ f(x) $ 在 $ (-\infty,+\infty) $ 有界.  

(广义介值定理)  

证明：(1). 因为 $ \lim_{x \to -\infty} f(x)=A<C $. 则 $ \exists x_1 $, 使得 $ f(x_1)<C $  

又 $ \lim_{x \to +\infty} f(x)=B>C $, 则 $ \exists x_2 $, 使得 $ f(x_2)>C $. 则  

在 $ x_1 $ 与 $ x_2 $ 之间, 存在一个 $ \xi $, 使得 $ f(\xi)=C $.

(2) 由于 $\lim_{x \to -\infty} f(x) = A$, 则 $\exists t_1$, 使得 $x \in (-\infty, t_1)$ 时,  
$f(x)$ 有界, 又 $\lim_{x \to +\infty} f(x) = B$, 则 $\exists t_2$, 使得 $x \in (t_2, +\infty)$ 时,  
$f(x)$ 有界,  
（取一个足够小的t1和足够大的t2，那在两边时接近极限值。剩下的用闭区间讨论）
若 $t_1 < t_2$, 则在区间 $[t_1, t_2]$, $f(x)$ 也连续. 从而有界  

综上, $x \in (-\infty, +\infty)$ 时, $f(x)$ 有界.

例 10. 设函数 $f(x)$ 在 $[0,+\infty)$ 上可导， $f(0)=0$ ，且 $\lim_{x \to +\infty} f(x)=2$ ，证明：  

(1) $\exists a>0$ ，使得 $f(a)=1$ ；  

(2) 对于 (1) 中的 $a$ ， $\exists \xi \in (0,a)$ ，使得 $f'(\xi)=\frac{1}{a}$ 。  

证明：(1) 根据 $f(x)$ 在 $[0,+\infty)$ 上可导，则 $f(x)$ 在 $[0,+\infty)$ 上连续，  
由介值定理可知： $\exists a \in (0,+\infty)$ ，使得 $f(a)=1$  

(2) $F(x)=f(x)-\frac{x}{a}$ ， $x \in [0,a]$ ，显然 $F(x)$ 在 $[0,a]$ 上连续，  
在 $(0,a)$ 上可导，且 $F(0)=0$ ， $F(a)=f(a)-1=0$ 。

根据罗尔定理可得 $ \exists c(0,a) $，使得 $ F'(c) = 0 $，即$ f'(c) = \frac{1}{a} $。  

证毕




单调有界数列收敛证明

有界：数学归纳法（第一项已知）

例：设数列 ${u_n}$ 满足 $u_1 = 1$，$u_{n+1} = \sqrt{2u_n}$ $(n=1,2,\cdots)$，证明数列 ${u_n}$ 极限存在  
并求出该极限。  

解：先证明 $u_n < 2$。用数学归纳法。  

当 $n = 1$ 时，$u_1 = 1 < 2$ 成立。  

设当 $n = k$ 时成立，即 $u_k < 2$。  

则当 $n = k+1$ 时，$u_{k+1} = \sqrt{2u_k} < \sqrt{2 \cdot 2} = 2$  

∴ 对 $n \in N_+$，均有 $u_n < 2$。[有上界，只需证明单调]

$ u_{n+1} - u_n = \sqrt{2u_n} - u_n = \sqrt{u_n}(\sqrt{2} - \sqrt{u_n}) > 0 $  

$ \therefore u_{n+1} > u_n. $ 则 $ \{u_n\} $ 单增  

$ \therefore \{u_n\} $ 收敛。设 $ \lim_{n \to \infty} u_n = a, $ 则  

$ \lim_{n \to \infty} u_{n+1} = \lim_{n \to \infty} \sqrt{2u_n} $ 即 $ a = \sqrt{2a} \quad a^2 = 2a $  

$ a(a-2) = 0. \quad \therefore a = 2. $

例：设数列 $u_n$ 且满足 $u_1 = 10$, $u_{n+1} = \sqrt{6+u_n} (n=1,2,\cdots)$, 证明数列 ${u_n}$  
极限存在并求出该极限.  

解: 零易用数学归纳法证明 $u_n > 3$. (证明单减)  

$u_{n+1} - u_n = \sqrt{6+u_n} - u_n = \frac{6+u_n - u_n^2}{\sqrt{6+u_n} + u_n} = \frac{(3-u_n)(u_n+2)}{\sqrt{6+u_n} + u_n} < 0$  

$\therefore {u_n}$单减. $\therefore \lim_{n\to\infty} u_n$存在. $\lim_{n\to\infty} u_n = a$  

$\lim_{n\to\infty} u_{n+1} = \lim_{n\to\infty}\sqrt{6+u_n}$

例：设数列 ${u_n}$，且满足 $u_1 > -6$，$u_{n+1} = \sqrt{6+u_n} (n=1,2,\cdots)$，证明数列 ${u_n}$  
极限存在并求出该极限。 $u_n > 0$  
（改题有界暂无法用数学归纳法判断）
（判断单调的另一种方法）
$u_{n+1} - u_n = \sqrt{6+u_n} - u_n = \frac{(3-u_n)(u_n+2)}{\sqrt{6+u_n} + u_n}$ 正负号待判断。  

$u_{n+1} - u_n = \sqrt{6+u_n} - \sqrt{6+u_{n-1}} = \frac{u_n - u_{n-1}}{\sqrt{6+u_n} + \sqrt{6+u_{n-1}}}$  
$u_{n+1} - u_n$ 的符号由 $u_n - u_{n-1}$ 确定。
$u_2 - u_1$ 确定

$ u_2 - u_1 = \sqrt{6+u_1} - u_1 = \frac{(3-u_1)(u_1+2)}{\sqrt{6+u_1} + u_1} $  

$ u_2 - u_1 $ 的符号由 $ 3-u_1 $ 确定  

(1)当 $ 3-u_1 > 0 $，即 $ u_1 < 3 $ 时，$ u_2 > u_1 \Rightarrow u_{n+1} > u_n $ 即 $ \{u_n\} $ 单增  

(2)当 $ 3-u_1 < 0 $，即 $ u_1 > 3 $ 时，$ u_2 < u_1 \Rightarrow u_{n+1} < u_n $ 即 $ \{u_n\} $ 单减。

例：设数列 ${u_n}$ 满足: $u_1 > 0$，$u_n e^{u_{n-1}} = e^{u_n} - 1$，$(n = 1,2,\cdots)$，证明 ${u_n}$ 收敛，并求 $\lim_{n \to \infty} u_n$。  
（将n放在一边）
证明：$e^{u_{n+1}} = \frac{e^{u_n} - 1}{u_n} > 1$  

用数学归纳法证含 $e^x - 1 > x$ 便可证明 $u_n > 0$  

当 $n = 1$ 时，$u_1 > 0$ 满足条件。  

设当 $n = k$ 时，$u_k > 0$，则当 $n = k+1$ 时，  

$e^{u_{k+1}} = \frac{e^{u_k} - 1}{u_k} > 1$ 即 $u_{k+1} > 0$。

∴ $U_n > 0$. $\forall n \in N_+$. (目标: 证明单调)  

$e^{U_{n+1}} = \frac{e^{U_n}-1}{U_n} = \frac{e^{U_n}-e^0}{U_n-0}$    设 $f(x) = e^x$, $x \in [0, U_n]$  

$= e^{\xi} < e^{U_n}$  

$\frac{f(U_n)-f(0)}{U_n - 0} = f'(\xi)$, $ 0<\xi<U_n$  

$= e^{\xi}$  

∴ $U_{n+1} < U_n$ 即 ${U_n}$ 单调减.

法二单调：
$ e^{U_n+1} - e^{U_n} = \frac{e^{U_n} - 1}{U_n} - e^{U_n} = \frac{e^{Un} - 1 - U_ne^{U_n}}{U_n} $ 与 0 比较  

设 $ f(x) = e^x - 1 - xe^x (x > 0) f(0) = 0. $  

$ f'(x) = e^x - e^x - xe^x = -xe^x < 0 $  

∴ $ f(x) < f(0) = 0 $ ∴ $ f(Un) < 0 $

设 $f(x)$ 是区间 $[0,+\infty)$ 上单调减少且非负的连续函数，  
$u_n = \sum_{k=1}^n f(k) - \int_1^n f(x)dx$, $(n=1,2,\cdots)$, 证明数列 $\{u_n\}$ 极限存在。(单调有界)  

证明：$u_n - u_{n-1} = \sum_{k=1}^n f(k) - \int_1^n f(x)dx - \sum_{k=1}^{n-1} f(k) + \int_1^{n-1} f(x)dx$  

$= f(n) - (\int_1^n f(x)dx + \int_{n-1}^1 f(x)dx)$  （或者中值定理）

$= f(n) - \int_{n-1}^n f(x)dx$

$ = \int_{n-1}^n [f(n) - f(x)] dx $  

$ \leq 0 $

证有下界
$ U_n = \sum_{k=1}^n f(k) - \int_1^n f(x) dx ≥ ??? $  

$ = f(1) + f(2) + ... + f(n) - (\int_1^2 f(x) dx + \int_2^3 f(x) dx + ... + \int_{n-1}^n f(x) dx) $ 

$ = [f(1) - \int_1^2 f(x) dx] + [f(2) - \int_2^3 f(x) dx] + ... + [f(n-1) - \int_{n-1}^n f(x) dx] + f(n) $
（用中值定理可以判断出每项≥0）
∴$ {u_n}$ 有界且单调。  
∴$ {u_n} $ 收敛。

设数列 ${u_n}$ 满足 $u_1 = 1$, $u_{n+1} = 1 + \frac{1}{u_n}$, $n = 1, 2, \cdots$,  

1. 令 $a_n = u_{2n-1}$, 判断数列 ${a_n}$ 的单调性和有界性, 并判断极限是否  
存在, 如果存在, 求出极限;  

2. 令 $b_n = u_{2n}$, 用同样的方法判断 ${b_n}$ 极限是否存在, 如果存在求出  
极限;  

3. 判断 ${u_n}$ 极限是否存在, 并说明理由.

证：由于 $ u_1 = 1 > 0 $, 則 $ u_{n+1} = 1 + \frac{1}{u_n} > 0 $ 即 $ u_n > 0 $  

$ \therefore u_{n+1} \geq 1 $. 而 $ u_1 = 1 $, 則 $ u_n \geq 1 $. 則 $ u_{n+1} = 1 + \frac{1}{u_n} \leq 1 + 1 = 2 $.  

$ \therefore 1 \leq u_n \leq 2 $. 即 $ \{u_n\} $ 有界.

1. $a_n = U_{2n-1}$   ，$ 1 \leq a_n \leq 2$.  

$a_{n+1} - a_n = U_{2n+1} - U_{2n-1} =1+ \frac{1}{U_{2n}} - (1+ \frac{1}{U_{2n-2}})$  

$= \frac{1}{U_{2n}} - \frac{1}{U_{2n-2}} = \frac{1}{1+ \frac{1}{U_{2n-1}}} - \frac{1}{1+ \frac{1}{U_{2n-3}}}$  

$= \frac{U_{2n-1}}{1+U_{2n-1}} - \frac{U_{2n-3}}{1+U_{2n-3}} = \frac{U_{2n-1} + U_{2n-1} \cdot U_{2n-3} - U_{2n-3} - U_{2n-3} \cdot U_{2n-1}}{(1+U_{2n-1})(1+U_{2n-3})}$

$ = \frac{u_{2n-1} - u_{2n-3}}{(1+ \cdot)(1+ \cdot)} = \frac{a_n - a_{n-1}}{(1+ \cdot)(1+ \cdot)} + $  

∴ $ a_{n+1} - a_n $ 两边取极限 $ a_n - a_{n-1} $  

$ a_3 - a_2 - - - - - - - a_2 - a_1 $  

$ a_{n+1} - a_n $取决于$a_2 - a_1 $

$ a_2 - a_1 = u_3 - u_1 = \frac{3}{2} - 1 > 0 $  

∴  $ a_{n+1} - a_n > 0 $, 即 $ \{a_n\} $ 单增。




中值定理
一阶导数中值定理问题

可以直接看出来辅助函数的类型：

1. $ f(\xi)g'(\xi)+f'(\xi)g(\xi)=0, [f(x)g(x)]'=0 $.  

设 $ f(x) $ 与 $ g(x) $ 在 $ [a,b] $ 上连续，在 $ (a,b) $ 内可导， $ f(a)=g(b) $， $ g(x)\neq0 $ 证明：$ \exists\xi\in(a,b) $，使 $ f(\xi)g'(\xi)+f'(\xi)g(\xi)=0 $.

$ 2. f'(\xi)g(\xi) - f(\xi)g'(\xi) = 0 (g(\xi) \neq 0), \left[\frac{f(x)}{g(x)}\right]' = 0. $  

设 $ f(x) $ 与 $ g(x) $ 在 $ [a,b] $ 上连续，在 $ (a,b) $ 内可导， $ f(a) = f(b) = 0 $， $ g(x) \neq 0 $ 证明：$ \exists \xi \in (a,b) $，使 $ f'(\xi)g(\xi) = f(\xi)g'(\xi) $。  

$ 3. f'(\xi)f(\xi) = 0, \left[f^2(x)\right]' = 0. $  

$ 4. f(\xi) + \xi f'(\xi) = 0, \left[xf(x)\right]' = 0. $

设函数 $f(x)$ 在 $[a,b]$ 上连续，在 $(a,b)$ 内可导，且 $f(1)=0$，证明在 $(a,b)$ 内至少存在一点  $\xi$，使得 $f(\xi)+\xi f'(\xi)=0$.  

证明：设 $F(x)=x\cdot f(x)$，$F(0)=F(1)=0$  

由 $\xi \in (0,1)$，得理 $F'(1)=0$...

设函数在[0,1]内连续，(0,1)内可导，且 $ f(1) = 0 $.证明存在至少一点 $ \xi \in (0,1) $，使得  

$ 3f(\xi) + \xi f'(\xi) = 0 $.  

证明：设 $ F(x) = x^3 \cdot f(x) $  

$ F(0) = F(1) = 0 $  

∴  ------

1.$\xi$→ x.  

$ 3f(x) + x \cdot f'(x) = 0 $  

$ [x^3 \cdot f(x)]' $  
$ (x^3)' = 3x^2 $  

$ 3x^2f(x) + x^3 \cdot f'(x) = 0 $  
$ (x^3)'f(x) + x^3 \cdot f'(x) = 0 $

设函数在 $[-a,a]$ 上连续，在 $(-a,a)$ 内可导，且 $f(-a)=f(a)$，$a>0$，证明 $\exists \xi \in (-a,a)$，使得 $f'(\xi)=2\xi f(\xi)$。  

证明：$F(x)=e^{-x^2} \cdot f(x)$  
$F(-a)=F(a)$  ......后续用罗尔定理

1. $\xi \to x$  
2. 左-右=0  
$f'(x)-2xf(x)=0$  
$f'(x) \cdot e^{-x^2}-2x \cdot e^{-x^2}f(x)=0$  
$e^{-x^2} \cdot f(x)$

不容易看出来的一阶类型

一、$ f'(\xi) + g(\xi)f(\xi) = 0 $ 类型.  

$ f'(x)e^{\int g(x)dx} + g(x)e^{\int g(x)dx} f(x) = 0 $,  

$ \left[f(x)e^{\int g(x)dx}\right]' = 0 $,  

$ f(x)e^{\int g(x)dx} = C $.  

设 $ F(x) = f(x)e^{\int g(x)dx} $ 即可.

微分方程法:  

1. $\xi \to x$, 2.左→右, 3.解.  

$f'(x) + g(x) \cdot f(x) = 0$  

$\frac{df(x)}{dx} = - g(x) \cdot f(x)$  

$\frac{df(x)}{f(x)} = - g(x) dx$

$ \ln f(x) = - \int g(x)dx + C_1 $  

$ \ln f(x) + \int g(x)dx = C_1 $  

$ \ln f(x) + \ln e^{\int g(x)dx} = C_1 $  

$ \ln f(x) \cdot e^{\int g(x)dx} = C_1 $

$ f(x) \cdot e^{\int g(x) dx} = C $  

$ F(x) = f(x) \cdot e^{\int g(x) dx} $

这样，两边求导可以得到原式




例：设 $ f(x) $ 在 $ [0,1] $ 上连续，在 $ (0,1) $ 内可导，且满足 $ f(1) = k\int_0^{\frac{1}{k}} xe^{1-x}f(x)dx (k>1) $ 证明至少存在一点 $ \xi \in (0,1) $ ，使得 $ f'(\xi) = (1-\xi^{-1})f(\xi) $ .  

证明：设 $ F(x) = x \cdot f(x)e^{-x} $  

（目标：找 $ \xi \in (0,1) $ ，使得 $ F'(\xi) = 0 $ ）  

$ F(1) = f(1) \cdot e^{-1} = F(?) $  

$ f(1) = k \cdot \int_0^{\frac{1}{k}} xe^{1-x}f(x)dx $

$ = k \cdot (\frac{1}{k} - 0) \cdot \eta \cdot e^{1-\eta} \cdot f(\eta) $  

$ = \eta \cdot e^{1-\eta} \cdot f(\eta) $  

$ F(1) = \eta \cdot e^{1-\eta} \cdot f(\eta) \cdot e^{-1} $

$ = \eta \cdot f(\eta) \cdot e^{-\eta} = F(\eta) $  

$ \therefore \exists \xi \in (0,1), 使得 F'(\xi) = 0 $

设函数 $ f(x) $, $ g(x) $ 在 $ [a,b] $ 上连续，证明存在 $ \xi \in (a,b) $，使得$ f(\xi)\int_{\xi}^b g(x)dx = g(\xi)\int_a^{\xi} f(x)dx $.  

$ f(x) \cdot \int_x^b g(t)dt = g(x) \cdot \int_a^x f(t)dt $  
$ f(x) \cdot G(x) - g(x) \cdot F(x) = 0 $  
$ F'(x) \cdot G(x) + G'(x) \cdot F(x) = 0 $
（注意$G(x)$下限是$x$求导是$-g(x)$）
设 $ H(x) = \int_a^x f(t)dt \cdot \int_x^b g(t)dt $.  

$ H(a) = H(b) = 0 $

设函数 $ f(x) $ 在 $ [a,b] $ 上连续，在 $ (a,b) $ 内可导，证明在 $ (a,b) $ 内至点 $ \xi $，使得$ \frac{f^2(b) - f^2(a)}{b-a} = 2f(\xi)f'(\xi) $.  

证明：(拉) 设 $ F(x) = f^2(x) $.  
对 $ F(x) $ 应用拉格朗日中值定理.  
$ \exists \xi \in (a,b) $, 使得  

$ \frac{F(b) - F(a)}{b-a} = F'(\xi) = 2f(\xi)f'(\xi) $

还原方法：令k等于左式  

$ k = 2f(x) \cdot f'(x) $  

↓积分  

$ C + kx = f^2(x) $  

$ F(x) = f^2(x) - kx $   罗尔定理...

总结(单中值):  
能用拉格朗日中值定理一定搞定的证明题,一定能用罗尔定理搞定。（柯西也能用罗尔做）

例：设 $ f(x) $ 在 $ [0,a] $ 上连续，在 $ (0,a) $ 内可导，且 $ f(0)=0 $ .证明 $ \exists \xi \in (0,a) $ ，使得$ f(a)=(1+\xi)f'(\xi)\ln(1+a) $ .  

证明：(柯) $\xi$都放一边，再变成分数形式  

$ \frac{f(a)}{\ln(1+a)} = \frac{f'(\xi)}{1+\xi} $  

设 $ G(x)= \ln(1+x) $  

$ \exists \xi \in (0,a) $ 使得

$ \frac{f(a) - f(0)}{G(a) - G(0)} = \frac{f'(\xi)}{G'(\xi)} $

证毕

(微分方程还原) 
$ k = \frac{f(a)}{f'(1+a)} = (1+x) \frac{dy}{dx} $  

$ k \int \frac{dx}{1+x} = \int dy $  

$ k \ln(1+x) = y + C $  

$ y - k \ln(1+x) = -C $

$ F(x) = f(x) - \frac{f(a)}{\ln(1+a)} \cdot \ln(1+x), x \in [0,a] $  

$ F(a) = 0 $  

$ F(0) = f(0) = 0 $  

$ \therefore \exists \xi \in (0, a),  $...（罗尔定理）



二、$ f'(\xi) + g(\xi)f(\xi) = h(\xi) $ 类型.  （非齐次）

对应的微分方程的通解为 $ f(x) = e^{-\int g(x)dx} \left[\int h(x)e^{\int g(x)dx} dx + C\right] $,  

所以构造辅助函数 $ F(x) = e^{\int g(x)dx} f(x) - \int h(x)e^{\int g(x)dx} dx $.  

然后验证罗尔定理的三个条件.

例：设 $f(x)$ 在 $[a,b]$ 上连续，在 $(a,b)$ 内可导，证明存在一点 $\xi \in (a,b)$，使得$\frac{f(\xi)-f(a)}{b-\xi} = f'(\xi)$.    

$\frac{y-f(a)}{b-x} = y'$  

$y' - \frac{1}{b-x} \cdot y = - \frac{f(a)}{b-x}$  

$y = e^{\int \frac{dx}{b-x}dx} \cdot [\int - \frac{f(a)}{b-x} \cdot e^{-\int \frac{dx}{b-x}} dx + C]$

$ = \frac{1}{b-x} \left[ \int 1 - \frac{f(a)}{b-x} \cdot (b-x) dx + C \right] $  

$ = \frac{1}{b-x} \left[ - f(a) \cdot \int dx + C \right] $  

$ = \frac{1}{b-x} \left[ - x \cdot f(a) + C \right] $

$ (b-x)f(x) + f(a) \cdot x = F(x) = C $

证明：设 $F(x) = (b-x)f(x) + f(a) \cdot x$  

$F(a) = (b-a)f(a) + a f(a)$  
$= b f(a)$  

$F(b) = b f(a) = F(a)$  

∴ 由罗尔定理得存在 $F'(\xi) = 0$

例设函数 $f(x)$ 在 $[0,1]$ 上连续，在 $(0,1)$ 内可导，且 $f(0)= f(1)= 0$， $f(\frac{1}{2}) =1$ 证明：对于任意实数 $\lambda$，必存在 $\xi \in (0,1)$，使得 $f'(\xi)-\lambda[f(\xi)-\xi]=1$.  

$ y' - \lambda y = 1 - \lambda x $  

$ y = e^{\lambda \int dx} \cdot \left[\int(1-\lambda x) e^{-\int \lambda dx} dx + C\right] $  

$ = e^{\lambda x} \cdot (x \cdot e^{-\lambda x} + C) $  

$ f(x) = x + C \cdot e^{\lambda x} $  

$ [f(x) - x] e^{-\lambda x} = C $

证明：设 $ F(x) = [f(x) - x] \cdot e^{-x} $.  

$ F(0) = [f(0) - 0] = 0 $.  

$ F(1) = -e^{-\lambda} $  

$ F(\frac{1}{2}) = \frac{1}{2}e^{-\frac{1}{2}\lambda} $

再根据零点定理可发现1/2到1之间有一个零点，即可用罗马定理证得

也可以：
$ [f'(x) - 1] - \lambda [f(x) - x] = 0 $  

$ [f(x) - x]' - \lambda [f(x) - x] = 0 $  

$ F(x) = e^{-\lambda x} \cdot [f(x) - x] $



二阶导数中值定理问题

一、多次使用罗尔定理类型  

设函数 $ f(x) $ 在 $ [0,1] $ 内具有三且 $ f(x_1) = f(x_2) = f(x_3) = f(x_4) $ ，  
其中 $ 0 < x_1 < x_2 < x_3 < x_4 < 1 $ ，证明在 $ (0,1) $ 内至点 $ \xi $ ，使得 $ f'''(\xi) = 0 $ .

例：已知函数 $ f(x) $ 在 $ [0,1] $ 连续，在 $ (0,1) $ 内二阶可导，且 $ f(1)=0 $ ，设函数 $ g(x)=x^2f(x) $ ，证明存在一点 $ \xi \in (0,1) $ ，使得 $ g''(\xi)=0 $ .  

证明：$ g(1)= f(1) = 0 $ , $ g(0) = 0 $ .  

$ \therefore \exists \eta \in (0,1) $ ，使得 $ g'(\eta) = 0 $ ，即 $ 2\eta \cdot f(\eta) + \eta^2 \cdot f'(\eta) = 0 $ .  

$ g'(x) = 2x \cdot f(x) + x^2 \cdot f'(x) $ ， $ g'(0) = 0 $  

$ \therefore \exists \xi \in (0,\eta) $ ，使得 $ g''(\xi) = 0 $

二、直接积分得出辅助函数。

设奇函数 $f(x)$ 在 $[-1,1]$ 上具有 2 阶导数，且 $f(1)=1$. 证明：

(1) 存在 $\xi \in (0,1)$，使得 $f'(\xi)=1$；  

(2) 存在 $\eta \in (-1,1)$，使得 $f''(\eta)+f'(\eta)=1$.

证明：(1) 设 $F(x)=f(x)-x$, 则  
$F(0)=F(1)=0$  
$\therefore$ 存在 $\xi \in (0,1)$, 使得 $F'(\xi)=0$,  
即 $f'(\xi)=1$

（$f(x)=x+C$ $\Rightarrow C=f(x)-x$）

(2) 设 $ G(x) = f'(x) + f(x) - x $.  

易知: $ G(-1) = f'(-1) + f(-1) + 1 = f'(1) $  
$ G(1) = f'(1) + f(1) - 1 = f'(1) = G(-1) $  

∴ $ \exists \eta \in (-1,1) $, 使得 $ G'(\eta) = 0 $.

另解：设 $ H(x) = e^x \cdot [f'(x) - 1] $  

又 $ H(\xi) = 0 $ (由$(1)$问)  

$ H(-\xi) = e^{-\xi} \cdot [f'(-\xi) - 1] = 0 $

两辅助函数的关系：
求次通解：$ y = C_1 + C_2 e^{-x} + x $

法1.先消 $ C_1 $

$ f(x) - C_2 e^{-x} - x = C_1 $. 关于 x 求导

$ f'(x) + C_2 e^{-x} - 1 = 0 $. 解出 $ C_2 $

$ f'(x) - 1 = C_2 \cdot e^{-x} $

$ [f'(x) - 1] \cdot e^x = C_2 $

法2. 先消 $C_2$  

$[f(x)-x-C_1] e^x = C_2$, 关于 $x$ 求导  

$[f'(x)-1] e^x + [f(x)-x-C_1] e^x = 0$  

$f'(x) + f(x) - x = C_1 + 1 = C$

总结：将C移到一边，先消一个C再解另一个C

三、应该积累的常见导数类型:  

1. $ [f(x)g(x)]'' = f''(x)g(x) + 2f'(x)g'(x) + f(x)g''(x) $ 型.  

设函数 $ f(x) $ 在 $ [0,1] $ 上二阶可导, 且 $ f(0) = f(1) = 0 $, 证明必存在 $ \xi \in (0,1) $, 使得  $ \xi^2 f''(\xi) + 4\xi f'(\xi) + 2f(\xi) = 0 $. 构造 $ x^2 f(x) = g(x) $

2. $[f(x)g'(x) - f'(x)g(x)]' = f(x)g''(x) - f''(x)g(x) $ 型.  

设函数 $ f(x) $ 和 $ g(x) $ 在 $ [a,b] $ 上存在二阶导数, 有 $ f(a) = f(b) = g(a) = g(b) = 0 $, 并且  
$ g''(x) \neq 0 $. 证明:  

(1) 在开区间 $ (a,b) $ 内 $ g(x) \neq 0 $ ;（反证法）

(2) 在开区间 $ (a,b) $ 内至少存在一点 $ \xi $, 使得 $ \frac{f(\xi)}{g(\xi)} = \frac{f''(\xi)}{g''(\xi)} $.



3. $ [f(x)f'(x)]' = [f'(x)]^2 + f(x)f''(x) $ 型.  

设函数 $ f(x) $ 在区间 $ [0,1] $ 上具有2阶导数，且 $ f(1) > 0 $ ， $ \lim_{x \to 0^+} \frac{f(x)}{x} < 0 $ .证明:  

(1) 方程 $ f(x) = 0 $ 在区间 $ (0,1) $ 内至少存在一个实根；(2017.一.二.三)  

(2) 方程 $ f(x)f''(x) + [f'(x)]^2 = 0 $ 在区间 $ (0,1) $ 内至少存在两个不同实根.

证明:(1) $\lim_{x \to 0^+} \frac{f(x)}{x}<0$. 由保号性可知 $\exists \delta>0$, 使得当 $x \in (0,\delta)$ 时  

$\frac{f(x)}{x}<0$, 此时 $f(x)<0$. 又 $f(1)>0$. 由零点定理可知$\exists \xi \in (0,1). f(\xi)=0$

(2) $ F(x) = f(x) \cdot f'(x) \quad F(n) = 0 $  
  
又 $ f(0) = f(n) = 0, \quad F(0) = 0 $  
  
则 $ \exists n_1 \in (0,n), 使得 f'(n_1) = 0 \Rightarrow F'(n_1) = 0 $  
  
∴ $ \exists \xi \in (n_1,n) \subseteq (0,1), 使得 F(\xi) = 0 $  
  
∴ $ \exists \xi_2 \in (0,n_1) \subseteq (0,1), 使得 F(\xi_2) = 0 $  
  
证毕



4. $ \left[\frac{f'(x)}{f'(x)}\right]' = \frac{[f'(x)]^2 - f(x)f''(x)}{[f'(x)]^2} $ 型.  

已知函数 $ f(x) $ 在 $ [a,b] $ 上连续，在 $ (a,b) $ 内二阶可导，且 $ f(a)f'(b)=f(b)f'(a) $ ，且$ f'(x) \neq 0 $ .证明 $ \exists \xi \in (a,b) $ ，使得 $ [f'(\xi)]^2 = f(\xi)f''(\xi) $ ;  

证明：设 $ F(x) = \frac{f(x)}{f'(x)} $ ，(证明子为0)  
$ F(a) = \frac{f(a)}{f'(a)} = \frac{f(b)}{f'(b)} = F(b) $  

又 $ F(a) = F(b) $  

$ \therefore \exists \xi \in (a,b) $ ，使得......



四、不容易看出来辅助函数的二阶类型  

设函数 $f(x)$, $g(x)$ 在 $[a,b]$ 上连续，在 $(a,b)$ 内二阶可导且存在相等的最大值，又  
$f(a)=g(a)$, $f(b)=g(b)$。证明：存在 $\xi \in (a,b)$，使得 $f''(\xi)=g''(\xi)$。  

证明：设 $F(x)=f(x)-g(x)$。（目标：$F''(\xi)=0$）  
$F(a)=F(b)=0$  
下面证明 $\exists \xi \in (a,b)$，使得 $F''(\xi)=0$

用反证法，假设不存在这样的点。  

则由于 $F(x)$ 连续，可知 $F(x)$ 在 $(a,b)$ 上恒正或恒负。  

不妨设 $F(x)$ 恒正。则 $\forall x \in (a,b)$, 使得 $F(x) > 0$

设 $ f(x) $ 在 $ \eta_1 $ 处取到最大值：  
（即 $ f(x) \leq f(\eta_1) $ , 则）  

$ F(\eta_1) = f(\eta_1) - g(\eta_1) > 0 $  

设 $ g(x) $ 在 $ \eta_2 $ 处取到最大值：  
（即 $ g(x) \leq g(\eta_2) $ ）

$F(\eta_2) = f(\eta_2) - g(\eta_2) > 0$  

$\Leftrightarrow f(\eta_2) > g(\eta_2)$  

由已知可得 $f(x) \leq g(\eta_2)$ 矛盾。
......



中值定理（双中值）

一、两个中值可相等。

二、两个中值不想等

例：设函数 $ f(x) $、$ g(x) $ 在 $ [a,b] $ 内连续，在 $ (a,b) $ 内可导，且 $ f'(x) \neq 0 $， $ g'(x) \neq 0 $。证明$ \exists \xi_1,\xi_2 \in (a,b) $，使得 $ [f(b)-f(a)]g'(\xi_1)=[g(b)-g(a)]f'(\xi_2) $。  

证明：要证明的式子等价于 $ \frac{f(b)-f(a)}{g(b)-g(a)} = \frac{f'(\xi_2)}{g'(\xi_1)} $。  

可以用两次使用拉格朗日中值定理后相除得到。  

对 $ f(x) $ 在 $ [a,b] $ 上用拉格朗日中值定理，可得：  
$ \exists \xi_2 \in (a,b) $，使得 $ f(b)-f(a)=f'(\xi_2)(b-a) $。  
同理可得，$ \exists \xi_1 \in (a,b) $ 使得 $ g(b)-g(a)=g'(\xi_1)(b-a) $，从而  
$ [f(b)-f(a)]g'(\xi_1)=[g(b)-g(a)]f'(\xi_2) $。  
证毕。

例：设函数 $ f(x) $ 在 $ [a,b] $ 内连续，在 $ (a,b) $ 内可导，且 $ f'(x) \neq 0 $ ， $ a>0 $ .证明:存在 $ \xi_1 $ 、 $ \xi_2 \in (a,b) $ 使得 $ f'(\xi_1)\xi_1\ln\left(\frac{b}{a}\right) = (b-a)f'(\xi_2) $ .  

证明：要证明的式子等价于 $ f'(\xi_1)\xi_1\frac{\ln b - \ln a}{b-a} = f'(\xi_2) $ .  

可以考虑拉格朗日中值定理和柯西中值定理结合.  

对 $ \ln x $ 和 $ f(x) $ 用柯西中值定理，可得  

$ \frac{\ln b - \ln a}{f(b) - f(a)} = \frac{1}{\xi_1f'(\xi_1)} $ ， $ \xi_1 \in (a,b) $ ，即 $ \frac{\ln b - \ln a}{f(b) - f(a)} = \frac{1}{\xi f'(\xi)} $ .  

对 $ f(x) $ 用拉格朗日中值定理，可得

$ f(b) - f(a) = (b-a)f'(\xi_2) $, 代入到上式，可得  

$ f'(\xi_1)\xi_1 \frac{\ln b - \ln a}{b-a} = f'(\xi_2) $.

（柯西，同一个$\xi$ ，再用拉郎多一个$\xi$ 即双中值）

小总结:

1.双中值题目中要证明的结论中如果没有 $ b-a $ ，那么很可能是两次拉格朗日（因为两次拉格朗日可以约掉 $ b-a $ ），也可能是两次柯西中值定理（柯西中值定理没有 $ b-a $ ）;  

2.双中值题目中要证明的结论中有 $ b-a $ ，很可能是一次拉格朗日一次柯西，因为一次拉格朗日一次柯西会约掉 $ f(b)-f(a) $ ，但保留 $ b-a $ 。

例：设 $f(x)$ 在 $\left[0,\frac{\pi}{2}\right]$ 上有连续的二阶导数，且 $f'(0)=0$ .证明：$\exists \xi_1,\xi_2 \in \left(0,\frac{\pi}{2}\right)$，使得$f'(\xi_1)=\frac{\pi^2}{8}f''(\xi_2)\sin 2\xi_1$.  

证明：把要子整理一下，$\xi_1$ 放到一起，得到 $\frac{f'(\xi_1)}{\sin 2\xi_1}=\frac{\pi^2}{8}f''(\xi_2)$.  

等号左边很可能是柯西中到的，而且出现了二阶导数，所以考虑拉格朗日中  
泰勒公式结合.  

对 $f(x)$ 和 $\cos 2x$ 在 $\left[0,\frac{\pi}{2}\right]$ 上用定理，可得 $\frac{f\left(\frac{\pi}{2}\right)-f(0)}{\cos \pi - \cos 0}=\frac{f'(\xi_1)}{-2\sin 2\xi_1}$.

化简得 $ f\left(\frac{\pi}{2}\right) - f(0) = \frac{f'(\xi_1)}{\sin 2\xi_1} $ .再对 $ f\left(\frac{\pi}{2}\right) - f(0) $ 用泰勒公式可得  

$ f\left(\frac{\pi}{2}\right) = f(0) + f'(0)\left(\frac{\pi}{2} - 0\right) + \frac{1}{2}\left(\frac{\pi}{2} - 0\right)^2 f''(\xi_2), \xi_2 \in \left(0, \frac{\pi}{2}\right), $ 即  

$ f\left(\frac{\pi}{2}\right) - f(0) = \frac{\pi^2}{8}f''(\xi_2), $ 结合 $ f\left(\frac{\pi}{2}\right) - f(0) = \frac{f'(\xi_1)}{\sin 2\xi_1} $ 可得  

$ \frac{f'(\xi_1)}{\sin 2\xi_1} = \frac{\pi^2}{8}f''(\xi_2)\sin 2\xi_1. $

设 $f(x)$ 在 $[a,b]$ 上连续，$(a,b)$ 内可导，$ 0 \leq a \leq b \leq \frac{\pi}{2}$，证明 $\exists \xi_1,\xi_2 \in (a,b)$，使得$f'(\xi_2)\tan \frac{a+b}{2} = f'(\xi_1)\frac{\sin \xi_2}{\cos \xi_1}$。  
证明：先把要证明的式子中，两个中值中值分别凑在一起，可得 $\frac{f'(\xi_2)}{\sin \xi_2}\tan \frac{a+b}{2} = \frac{f'(\xi_1)}{\cos \xi_1}$。  

所以我们可以大胆猜测一下：  

1.要证明的式子里面没有 $b-a$，很可能是由两个柯西中值定理组成；  

2.要证明的式子中有 $\frac{f'(\xi_2)}{\sin \xi_2}$ 和 $\frac{f'(\xi_1)}{\cos \xi_1}$，  

并且 sin 和 cos 也会组成要证明的式子中剩余部分 tan，  

所以我们可以考虑对 $f(x)$ 和 $\sin x$ 用一次柯西中值定理，再对 $f(x)$ 和 $\cos$ 用一次  

柯西中值定理.出现的公共部分 $f(b)-f(a)$ 约掉后整理一下，看看会得到什么式子.

显然对于任何 $ x \in \left(0, \frac{\pi}{2}\right) $ ，$ \sin x \neq 0 $ ，$ \cos x \neq 0 $ 。(保证柯西中值定理分母不为零)  

对 $ f(x) $ 和 $ \sin x $ 在 $ [a,b] $ 上用定理可得：$ \frac{f(b)-f(a)}{\sin b - \sin a} = \frac{f'(\xi_1)}{\cos \xi_1} $ ，$ \xi_1 \in (a,b) $ 。  

对 $ f(x) $ 和 $ \cos x $ 在 $ [a,b] $ 上用柯西中得：$ \frac{f(b)-f(a)}{\cos b - \cos a} = \frac{f'(\xi_2)}{-\sin \xi_2} $ ，$ \xi_2 \in (a,b) $ 。

两个式子约掉 $f(b)-f(a)$ 后，并整理，可得  

$\frac{f'(\xi_1)}{\cos \xi_1} = \frac{f'(\xi_2)}{-\sin \xi_2} \cdot \frac{\cos b - \cos a}{\sin b - \sin a} = \frac{f'(\xi_2)}{-\sin \xi_2} \cdot \frac{-2\sin \frac{a+b}{2} \sin \frac{b-a}{2}}{2\cos \frac{a+b}{2} \sin \frac{b-a}{2}} = \frac{f'(\xi_2)}{\sin \xi_2} \tan \frac{a+b}{2}.$  

证毕.


总结:  

双中值可相等类型，其实就是多次在同一个区间（或者不同但交集不为空的区间）  
内使用中值定理.拉格朗日中值定理和柯西中值定理的组合最为常见，偶尔也会  
结合泰勒中值定理，如上面例 3.  

而且，一般来说，几个中值，就会运用几次中值定理.所以，可以根据题目给出的  
已知条件，以及要证明的结论，来寻找蛛丝马迹，证明的突破口.

常见突破口：  

1.两个中值分别凑在一起，即 $\xi_1$ 的放在一起，$\xi_2$ 的放在一起，观察拉格朗日或者  
柯西中值定理所需的辅助函数；  

2.出现 $f(b)-f(a)$ 类型，要能想到拉格朗日或与柯西中值定理；  

3.要证明的结论中有 $b-a$，很可能是一次拉格朗日一次柯西，因为一次拉格朗日  
一次柯西会约掉 $f(b)-f(a)$，但保留 $b-a$；  

4.要证明的结论中如果没有 $b-a$，那么很可能是两次拉格朗日（因为两次拉格朗  
日可以约掉 $b-a$），也可能是两次柯西中值定理（柯西中值定理没有 $b-a$）；  

5.出现高阶导数，应该想到泰勒中值定理。

设函数 $f(x)$ 在 $[0,1]$ 上连续，$(0,1)$ 内可导，且 $f(0)=0$， $f(1)=1$，证明存在不相等的两个 $\xi_1$、$\xi_2 \in (0,1)$，使得 $\frac{1}{f'(\xi_1)}+\frac{1}{f'(\xi_2)}=2$.  

【白话】两个不相等的 $\xi_1$、$\xi_2$，往往会在不同的区间，而不同区间的分类临界点，如果题目没有蛛丝马迹，可以通过待定的方法（有时候也直接暴力设成中点，但未必能100%成功）.  

即，本题可以考虑把区间 $[0,1]$ 从 $\xi \in (0,1)$ 处拆成两个区间，在这两个区间分别对 $f(x)$ 使用一次拉格朗日中值定理.  

在 $[0,\xi]$ 对 $f(x)$ 使用拉格朗日中值定理可得 $f(\xi)-f(0)=\xi f'(\xi_1)$， $\xi_1 \in (0,\xi)$.  

同理，在 $[\xi,1]$ 使用拉格朗日中值定理可得 $f(1)-f(\xi)=(1-\xi)f'(\xi_2)$， $\xi_2 \in (\xi,1)$.  

显然两个 $\xi_1$、$\xi_2$ 是不相等的.  

接下来我们要让 $\frac{1}{f'(\xi_1)}+\frac{1}{f'(\xi_2)}=2$，看看 $\xi$ 会满足什么条件:

$ \frac{1}{f'(\xi_1)} + \frac{1}{f'(\xi_2)} = \frac{\xi}{f(\xi)-f(0)} + \frac{1-\xi}{f(1)-f(\xi)} = \frac{\xi[f(1)-f(\xi)]+(1-\xi)[f(\xi)-f(0)]}{[f(\xi)-f(0)][f(1)-f(\xi)]} $  

$ = \frac{\xi[1-f(\xi)]+(1-\xi)f(\xi)}{f(\xi)[1-f(\xi)]} = \frac{\xi-2\xi f(\xi)+f(\xi)}{f(\xi)[1-f(\xi)]} $  

今这个复杂的式子等于2，即 $ \frac{\xi-2\xi f(\xi)+f(\xi)}{f(\xi)[1-f(\xi)]} = 2 $. 继续恒等变换可得  

$ \xi-2\xi f(\xi) = f(\xi)-2f^2(\xi) $, 提公因式继续化简可得

$ \xi[1-2f(\xi)] = f(\xi)[1-2f(\xi)] ⇔[1-2f(\xi)][f(\xi)-\xi] = 0. $  

从而，只要满足 $ 1-2f(\xi) = 0 $ 或者 $ f(\xi)-\xi = 0 $，即可满足 $ \frac{1}{f'(\xi_1)} + \frac{1}{f'(\xi_2)} = 2 $.  

那么 $ 1-2f(\xi) = 0 $ 或者 $ f(\xi)-\xi = 0 $ 能成立吗？  

(1) 证明 $ 1-2f(\xi) = 0 $，即证明 $ \exists \xi \in (0,1) $，使得 $ f(\xi) = \frac{1}{2} $.  

这是比，我们在第一期就讲过方法，左减右构造：(或中值定理证明)  

$ F(x) = f(x) - \frac{1}{2}, x \in [0,1] $. 显然 $ F(x) $ 在 $ [0,1] $ 上连续，且 $ F(0)F(1) < 0 $.

根据零点定理可得 $ \exists \xi \in (0,1) $，使得 $ F(\xi) = 0 $，即 $ f(\xi) = \frac{1}{2} $.  

(2) 证明 $ f(\xi) - \xi = 0 $，即证明 $ \exists \xi \in (0,1) $，使得 $ f(\xi) = \xi $.  

这个不一定成立，比如 $ f(x) = x^2 $.  

但这并不影响原题可以证明出来，因为只要满足 $ 1 - 2f(\xi) = 0 $ 或者 $ f(\xi) - \xi = 0 $ 即可，不需要二者同时成立.

【黑话】证明：先证明 $ \exists \xi \in (0,1) $ ，使得 $ f(\xi) = \frac{1}{2} $ 。设 $ F(x) = f(x) - \frac{1}{2} $ ， $ x \in [0,1] $ 。  

显然 $ F(x) $ 在 $ [0,1] $ 上连续，且 $ F(0)F(1)<0 $ 。  

根据零点定理可得 $ \exists \xi \in (0,1) $ ，使得 $ F(\xi) = 0 $ ，即 $ f(\xi) = \frac{1}{2} $ 。  

在区间 $ (0,\xi) $ 和 $ (\xi,1) $ 上分别对 $ f(x) $ 用拉格朗日中值定理可得  

$ \frac{f(\xi)-f(0)}{\xi-0} = f'(\xi_1) $ ， $ \xi_1 \in (0,\xi) $ ，即 $ \frac{1}{2\xi} = f'(\xi_1) $ ；

$ \frac{f(1)-f(\xi)}{1-\xi} = f'(\xi_2), \xi_2 \in (\xi,1), \text{即} \frac{1}{2(1-\xi)} = f'(\xi_2). $  

从而$ \frac{1}{f'(\xi_1)} + \frac{1}{f'(\xi_2)} = 2. $  

证毕.

设函数 $f(x)$ 在 $[0,1]$ 上连续，$(0,1)$ 内可导，且 $f(0)=0$，$f(1)=1$，证明：  

(1) $\exists \xi \in (0,1)$，使得 $f(\xi)=1-\xi$；  

(2) 存在两个不相等的 $\xi_1$，$\xi_2$，使得 $f'(\xi_1)f'(\xi_2)=1$。  (1) 这一问很简单,用我们第一期讲过的方法即可.  

设 $F(x)= f(x)+x-1$，$x \in [0,1]$,显然 $F(x)$ 在 $[0,1]$ 上连续.  

又 $F(0)=-1<0$，$F(1)=1>0$，$F(0)F(1)<0$.根据零点定理可得  

$\exists \xi \in (0,1)$，使得 $f(\xi)=1-\xi$。  

(2) 第一问已经做了铺垫.考场上有两问的证明题，往往第用的结论.第一问  

已经有一个 $\xi$ 把区部分了：$[0,\xi]$ 和 $[\xi,1]$，所以直接使用拉格朗日中可.  

分别在区间 $[0,\xi]$ 和 $[\xi,1]$ 上，对函数 $f(x)$ 运用拉格朗日中有

$ \frac{f(\xi) - f(0)}{\xi - 0} = f'(\xi_1), \xi_1 \in (0, \xi), \text{即} f'(\xi_1) = \frac{1-\xi}{\xi} ; $  

$ \frac{f(1) - f(\xi)}{1 - \xi} = f'(\xi_2), \xi_2 \in (\xi, 1), \text{即} f'(\xi_2) = \frac{\xi}{1-\xi}. $  

从而存在两个不相等的 $ \xi_1, \xi_2, $ 使得 $ f'(\xi_1) f'(\xi_2) = 1. $  

证毕.（或同待定系数法，最后代入第一问的式子）

当然，上述过程可以答在考场上，但同学们需要知道这是黑话，得知道对应的白话才合格.  

【白话思维】本题第一问如果没有的话，我们也可以自己通过待定的方法找到:  

假设 $\xi$ 把区间分成了两部分，分别在区间 $[0,\xi]$ 和 $[\xi,1]$ 上对函数 $f(x)$ 用拉格朗日中  

可得: $\frac{f(\xi)-f(0)}{\xi-0} = f'(\xi_1)$, $\xi_1 \in (0,\xi)$, 即 $\frac{f(\xi)}{\xi} = f'(\xi_1)$;  

$\frac{f(1)-f(\xi)}{1-\xi} = f'(\xi_2)$, $\xi_2 \in (\xi,1)$, 即 $\frac{1-f(\xi)}{1-\xi} = f'(\xi_2)$.

要使得 $ f'(\xi_1)f'(\xi_2)=1 $ ，只需 $ \frac{f(\xi)}{\xi}\frac{1-f(\xi)}{1-\xi}=1 $ ，即  

$$ f(\xi)-f^2(\xi)=\xi-\xi^2 \Leftrightarrow f(\xi)-\xi=f^2(\xi)-\xi^2 \Leftrightarrow [f(\xi)-\xi][f(\xi)+\xi]. $$  

$[ [f(\xi) - \xi][f(\xi) + \xi - 1] = 0.$

即 $ f(\xi)=\xi $ 或 $ f(\xi)=1-\xi $ 成立即可达到目标 $ f'(\xi_1)f'(\xi_2)=1 $ 。  

而 $ f(\xi)=1-\xi $ 便是第一问。


例：设函数 $ f(x) $ 在 $ [a,b] $ 上连续，在 $ (a,b) $ 内可导，且 $ f'(x) > 0 $ 。如果极限 $ \lim_{x \to a^+} \frac{f(2x-a)}{x-a} $ 存在，证明：  
(1) 在 $ (a,b) $ 内 $ f(x) > 0 $ ;  
(2) $\exists \xi_1 \in (a,b) $ ，使得 $ \frac{b^2 - a^2}{\int_a^b f(x) dx} = \frac{2 \xi_1}{f(\xi_1)} $ ;  
(3) 在 $ (a,b) $ 内存在两个不相等的 $ \xi_1 $ ， $ \xi_2 $ ，使得 $ f'(\xi_2)(b^2 - a^2) = \frac{2 \xi_1}{\xi_1 - a} \int_a^b f(x) dx $ .  

【证明】(1) 导函数大于零，如果要能证明出来 $ f(a) \geq 0 $ ，便可以说明在 $ (a,b) $ 内 $ f(x) > 0 $ .  
根据 $ \lim_{x \to a^+} \frac{f(2x-a)}{x-a} $ 存在，设 $ \lim_{x \to a^+} \frac{f(2x-a)}{x-a} = A $ ，则有
$f(a) = \lim_{x \to a^+} f(x) = \lim_{x \to a^+} f(2x - a) = \lim_{x \to a^+} \frac{f(2x - a)}{x - a} = \lim_{x \to a^+} (x - a)A = 0.$  

又在 $(a, b)$ 内 $f'(x) > 0$，可得 $f(x) > 0.$

(2)（第二问利用上一期课程的方法即可）。

设函数 $ F(x) = \int_{a}^{x} f(t) dt $，显然 $ F(x) $ 在 $ [a,b] $ 上连续，在 $ (a,b) $ 内可导。  

又由于 $ f(x) > 0 $，从而 $ F(x) > 0 $。（为了保证柯西中值定理分母不为零）  

对函数 $ G(x) = x^2 $ 和 $ F(x) $ 在区间运用柯西中值定理，可得

$ \frac{G(b) - G(a)}{F(b) - F(a)} = \frac{G'(\xi_1)}{F'(\xi_1)} $, $ \xi_1 \in (a,b) $, 即 $ \frac{b^2 - a^2}{\int_a^b f(x) dx} = \frac{2\xi_1}{f(\xi_1)} $.

(3) 证明题有两问，后面一问用前面的结论.而且第三问要证明的式子跟第二问有些相似.  

把要子恒等变换一下，可得 $ \frac{b^2-a^2}{\int_a^b f(x)dx} = \frac{2\xi_1}{f'(\xi_2)(\xi_1-a)} $.  

结论对照一下发现，要能证明出来 $ f(\xi_1) = f'(\xi_2)(\xi_1-a) $，就可以达到目的了.  

在 $ [a,\xi_1] $ 上对函数 $ f(x) $ 用拉格朗日中得，  

$ f(\xi_1)-f(a) = f'(\xi_2)(\xi_1-a), \xi_2 \in (a,\xi_1) $.再结合 $ f(a) = 0 $，便有  

$ f'(\xi_2)(b^2-a^2) = \frac{2\xi_1}{\xi_1-a}\int_a^b f(x)dx, \xi_{1,2} \in (a,b), 且\xi_1 \neq \xi_2 $.

总结:  
两个中值不相等的类型的特点是:  
1.两次使用中值定理;  
2.在不同的区间使用中值定理，使得两个中值不可能相等.  

常见套路总结:  
1.如果题目有两问，往往第二问两个中值所在的不同区间的临界点就是第一问的中值，即把积分区间从第一问的中值处拆成两个，分别在这两个区间运用中值定理;  
2.如果题目只有一问，要么区间中点展开，要么用待定法解出来.






数列极限

