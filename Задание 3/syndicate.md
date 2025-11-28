# Вариант 2

Матрица:
$$    
A =     
  \begin{pmatrix}    
  5 & 6 & 0 & \cdots & 0 & 0 \\    
  1 & 5 & 6 & \cdots & 0 & 0 \\    
  0 & 1 & 5 & \cdots & 0 & 0 \\    
  \vdots  & \vdots & \vdots & \ddots & \vdots & \vdots  \\    
  0 & 0 & 0 & \cdots & 5 & 6 \\    
  0 & 0 & 0 & \cdots & 1 & 5     
  \end{pmatrix}   
$$

Порядок матрицы **n** = 10

## Алгоритм вычисления ленточного определителя

### Шаг 1 - Рекуррентное соотношение

1. Вычислим определитель матрицы, разложив его по первой строке

$$  
X_{n} =   
 {\begin{vmatrix}  
  5 & 6 & 0 & \cdots & 0 & 0 \\  
  1 & 5 & 6 & \cdots & 0 & 0 \\  
  0 & 1 & 5 & \cdots & 0 & 0 \\  
  \vdots  & \vdots & \vdots & \ddots & \vdots & \vdots  \\  
  0 & 0 & 0 & \cdots & 5 & 6 \\  
  0 & 0 & 0 & \cdots & 1 & 5   
 \end{vmatrix}} =   
 5 \cdot  {\begin{vmatrix}  
  5 & 6 & \cdots & 0 & 0 \\  
  1 & 5 & \cdots & 0 & 0 \\  
  \vdots & \vdots & \ddots & \vdots & \vdots  \\  
  0 & 0 & \cdots & 5 & 6 \\  
  0 & 0 & \cdots & 1 & 5   
 \end{vmatrix}} -   
 6 \cdot {\begin{vmatrix}  
  1 & 6 & \cdots & 0 & 0 \\  
  0 & 5 & \cdots & 0 & 0 \\  
  \vdots  & \vdots & \ddots & \vdots & \vdots  \\  
  0 & 0 & \cdots & 5 & 6 \\  
  0 & 0 & \cdots & 1 & 5   
 \end{vmatrix}}   
$$ 

2. Разложим определитель порядка **n-1** (последний определитель в предыдущем выражении) по первому столбцу

$$  
X_{n-1} =  
{\begin{vmatrix}    
  1 & 6 & \cdots & 0 & 0 \\    
  0 & 5 & \cdots & 0 & 0 \\    
  \vdots  & \vdots & \ddots & \vdots & \vdots  \\    
  0 & 0 & \cdots & 5 & 6 \\    
  0 & 0 & \cdots & 1 & 5     
 \end{vmatrix}}  =   
 1 \cdot {\begin{vmatrix}    
  5 & \cdots & 0 & 0 \\    
  \vdots & \ddots & \vdots & \vdots  \\    
  0 & \cdots & 5 & 6 \\    
  0 & \cdots & 1 & 5     
 \end{vmatrix}} = 1 \cdot X_{n-2}  
$$  

3. Таким образом, получаем рекуррентное соотношение

$$  
X_{n} =   
 {\begin{vmatrix}  
  5 & 6 & 0 & \cdots & 0 & 0 \\  
  1 & 5 & 6 & \cdots & 0 & 0 \\  
  0 & 1 & 5 & \cdots & 0 & 0 \\  
  \vdots  & \vdots & \vdots & \ddots & \vdots & \vdots  \\  
  0 & 0 & 0 & \cdots & 5 & 6 \\  
  0 & 0 & 0 & \cdots & 1 & 5   
 \end{vmatrix}} =   
 5 \cdot  {\begin{vmatrix}  
  5 & 6 & \cdots & 0 & 0 \\  
  1 & 5 & \cdots & 0 & 0 \\  
  \vdots & \vdots & \ddots & \vdots & \vdots  \\  
  0 & 0 & \cdots & 5 & 6 \\  
  0 & 0 & \cdots & 1 & 5   
 \end{vmatrix}} -   
 6 \cdot 1 \cdot {\begin{vmatrix}    
  5 & \cdots & 0 & 0 \\    
  \vdots & \ddots & \vdots & \vdots  \\    
  0 & \cdots & 5 & 6 \\    
  0 & \cdots & 1 & 5     
 \end{vmatrix}} 
$$ 

$$  
X_{n} =   5 \cdot  X_{n-1} - 6 \cdot  1 \cdot   X_{n-2}
$$


### Шаг 2 - Характеристическое уравнение