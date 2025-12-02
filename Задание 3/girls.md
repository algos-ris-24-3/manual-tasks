# Вариант 3 

$$
A = 
 \begin{pmatrix} 
 -1 & -2 & 0 & \cdots & 0 & 0 \\ 
 3 & -1 & -2 & \cdots & 0 & 0 \\ 
 0 & 3 & -1 & \cdots & 0 & 0 \\ 
 \vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\ 
 0 & 0 & 0 & \cdots & -1 & -2 \\ 
 0 & 0 & 0 & \cdots & 3 & -1 
 \end{pmatrix} 
$$

n = 12  

## 1. Выведем рекуррентное соотношение 
$$
\[\Delta_n = -1 \cdot \Delta_{n-1} + (-2) \cdot (-1)^{1+2} 
 \begin{vmatrix} 
 3 & -2 & 0 & 0 & 0 & \cdots \\ 
 0 & -1 & -2 & 0 & 0 & \cdots \\ 
 0 & 3 & -1 & -2 & 0 & \cdots \\ 
 0 & 0 & 3 & -1 & -2 & \cdots \\ 
 \vdots & \vdots & \vdots & \ddots & \vdots & \vdots 
 \end{vmatrix} = 
-1 \cdot \Delta_{n-1} + (-2) \cdot (-1) \cdot (3 \cdot \Delta_{n-2}) = 
-\Delta_{n-1} + 6\Delta_{n-2}\] 
$$

## 2. Составим характеристическое уравнение
$$
\[\Delta_n = \lambda^n.\] 
\[\lambda^n = -\lambda^{n-1} + 6\lambda^{n-2}\] 
Делим обе части на \[\lambda^{n-2}\] 
\[\lambda^2 = -\lambda + 6\] 
\[\lambda^2 + \lambda - 6 = 0\] 
\[\lambda_1 + \lambda_2 = -1\] 
\[\lambda_1 \lambda_2 = -6\] 
\[\lambda_1 = -3\] 
\[\lambda_2 = 2.\] 
$$

## 3.Проверка кратности корней 
$$
\[\lambda_1 \neq \lambda_2\] так как \[-3 \neq 2\] 
$$

## 4.Заготовка общей формулы: 
$$
\[\Delta_n = C_1 \cdot \lambda_1^n + C_2 \cdot \lambda_2^n\] 
\[\Delta_n = C_1 \cdot (-3)^n + C_2 \cdot 2^n\] 
$$

## 5. Нахождение констант  
$$
\[\Delta_1 = |-1| = -1\] 
\[\Delta_2 = 
 \begin{vmatrix} 
 -1 & -2 \\ 
 3 & -1 
 \end{vmatrix} = (-1)(-1) - (-2)(3) = 1 + 6 = 7\] 
 
\[\Delta_1 = C_1 \cdot (-3)^1 + C_2 \cdot 2^1 = -3C_1 + 2C_2\] 
\[\Delta_2 = C_1 \cdot (-3)^2 + C_2 \cdot 2^2 = 9C_1 + 4C_2\] 
 
\[\begin{cases} 
-3C_1 + 2C_2 = -1 \\ 
9C_1 + 4C_2 = 7 
\end{cases}\] 
 
\[15C_1 = 9\] 
\[C_1 = \frac{9}{15} = \frac{3}{5} = 0.6\] 

\[-3 \cdot 0.6 + 2C_2 = -1\] 
\[-1.8 + 2C_2 = -1\] 
\[2C_2 = -1 + 1.8\] 
\[2C_2 = 0.8\] 
\[C_2 = 0.4\] 
$$
 
### Общая формула: 
$$
\[\Delta_n = 0.6 \cdot (-3)^n + 0.4 \cdot 2^n\] 
$$
 
## 6. Вычисляем по формуле 
$$
\[\Delta_{12} = 0.6 \cdot (-3)^{12} + 0.4 \cdot 2^{12} = 0.6 \cdot 531441 + 0.4 \cdot 4096 = 318864.6 + 1638.4 = 320503\] 
$$
 
## Ответ: 
Общая формула:
$$
\[\Delta_n = 0.6 \cdot (-3)^n + 0.4 \cdot 2^n\] 
\[\Delta_{12} = 320503\]
$$
