# Вариант 4

$$
A = \begin{pmatrix}
2 & -1 & 0 & \cdots & 0 & 0 \\
3 & 2 & -1 & \cdots & 0 & 0 \\
0 & 3 & 2 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & 0 & \cdots & 2 & -1 \\
0 & 0 & 0 & \cdots & 3 & 2
\end{pmatrix}
$$
Порядок матрицы n = 7
# Алгоритм вычисления ленточного определителя
## Шаг 1 - Рекуррентное соотношение
### 1. Вычислим определитель матрицы, разложив по первой строке
$$
X_n =
\left|\begin{array}{cccccc}
2 & -1 & 0 & \cdots & 0 & 0 \\
3 & 2 & -1 & \cdots & 0 & 0 \\
0 & 3 & 2 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & 0 & \cdots & 2 & -1 \\
0 & 0 & 0 & \cdots & 3 & 2
\end{array}\right|
=
2\cdot
\left|\begin{array}{ccccc}
2 & -1 & \cdots & 0 & 0 \\
3 & 2 & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 &\cdots & 2 & -1 \\
0 & 0 & \cdots & 3 & 2
\end{array}\right|
-
(-1)\cdot
\left|\begin{array}{ccccc}
3 & -1 & \cdots & 0 & 0 \\
0 & 2 & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 &\cdots & 2 & -1 \\
0 & 0 & \cdots & 3 & 2
\end{array}\right|
$$
### 2. Разложим определитель порядка n-1 (последний определитель в предыдущем выражении) по первому столбцу
$$
X_{n-1} =
\left|\begin{array}{ccccc}
3 & -1 & \cdots & 0 & 0 \\
0 & 2 & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 &\cdots & 2 & -1 \\
0 & 0 & \cdots & 3 & 2
\end{array}\right|
=
3\cdot
\left|\begin{array}{cccc}
2 & \cdots & 0 & 0 \\
\vdots & \ddots & \vdots & \vdots \\
0 & \cdots & 2 & -1 \\
0 & \cdots & 3 & 2
\end{array}\right|
=
3\cdot X_{n-2}
$$
### 3. Таким образом, получаем рекуррентное соотношение
$$
X_n =
\left|\begin{array}{cccccc}
2 & -1 & 0 & \cdots & 0 & 0 \\
3 & 2 & -1 & \cdots & 0 & 0 \\
0 & 3 & 2 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & 0 & \cdots & 2 & -1 \\
0 & 0 & 0 & \cdots & 3 & 2
\end{array}\right|
=
2\cdot
\left|\begin{array}{ccccc}
2 & -1 & \cdots & 0 & 0 \\
3 & 2 & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 &\cdots & 2 & -1 \\
0 & 0 & \cdots & 3 & 2
\end{array}\right|
-(-1)\cdot3\cdot
\left|\begin{array}{cccc}
2 & \cdots & 0 & 0 \\
\vdots & \ddots & \vdots & \vdots \\
0 & \cdots & 2 & -1 \\
0 & \cdots & 3 & 2
\end{array}\right|
$$
### 3. Получаем рекуррентное соотношение
$$ X_n = 2X_{n-1} -(-1)\cdot 3\cdot X_{n-2} $$
## Шаг  2 - Характеристическое уравнение
### 1. Используем метод подстановки:
$$ X_n = λ^n$$  тогда, $$ λ^n = 2λ^{n-1} +3 \cdot λ^{n-2} $$
### 2. Поделим обе части уравнения на $λ^{n-2}$ (при $λ^{n-2}$ $\cancel{=}$ 0)
$$λ^2 = 2λ+3$$

### 3. Перенесём всё в одну часть, получаем характеристическое уравнение  $$λ^2-2λ-3=0 $$
### 4. Решаем квадратное уравнение, применив теорему Виета

$$
\qquad
\begin{cases}
λ_1 + λ_2 = 2,\\[4pt]
λ_1\cdotλ_2 = -3.
\end{cases}
$$
### 5. Получаем корни
$$
\boxed{\;λ_1 = 3,\qquad λ_2 = -1\; }
$$
## Шаг 3 - Формула общего решения
### 1. Проверим равенство корней характеристического уравнения и выберем основанную на этом формулу
$$λ_1\cancel{ = }λ_2$$
Так как корни различны, используем следующую формулу:
$$
\Delta_n = C_1\lambda_1^n + C_2\lambda_2^n
$$
Подставим наши значения
$$
X_n = C_1\cdot 3^n + C_2\cdot(-1)^n
$$
### 2. Найдём константы C₁ и C₂  
Сначала найдём определители порядков 1 и 2, чтобы затем составить систему:
Определитель порядка 1:
$$
\Delta_1 = |2| = 2
$$
Определитель порядка 2:
$$
\Delta_2 =
\left|\begin{array}{cc}
2 & -1 \\
3 & 2
\end{array}\right|
= 4 + 3 = 7
$$
Cоставим систему со значениями определителей порядков 1 и 2:
$$
\begin{cases}
2 = C_1\cdot 3^1 - C_2\cdot(-1)^1\\
7 = C_1\cdot 3^2 + C_2\cdot(-1)^2
\end{cases}
$$
Решим систему, cкладывая два уравнения:
$$
9 = 12C_1 \quad\Rightarrow\quad C_1 = \frac{3}{4}
$$
Подставим в первое уравнение:
$$
2 = \frac{9}{4} - C_2 \quad\Rightarrow\quad C_2 = \frac{1}{4}
$$
Таким образом, формула общего решения имеет вид:
$$
\boxed{\Delta_n = \frac{3}{4}\,3^n + \frac{1}{4}\,(-1)^n }
$$
## Шаг 4 - Расчёт значения определителя матрицы
Подставим в общую формулу порядок 7 вместо n и найдём определитель:
$$
{\Delta_7 = \frac{3}{4}\,3^7 + \frac{1}{4}\,(-1)^7= \frac{3\cdot 2187}{4}+\frac{-1}{4}=\frac{6561-1}{4}=1640}
$$
Значение определителя порядка 7, вычисленное через общую формулу:
$$
\boxed{1640}
$$