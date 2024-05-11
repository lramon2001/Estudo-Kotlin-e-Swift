```python
import numpy as np
```

# Reshape


```python
a = np.arange(30)
a
# Um vetor com 30 elementos que é 2*3*5 pra ter vários divisores e ajudar
# nos exemplos
```




    array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16,
           17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29])




```python
a = np.arange(30)
#             i   j
b = a.reshape(-1, 3)
b
# quando tu usa -1, tu ta basicamente falando "Descobre ae mano"
# Ent nesse caso tu deu reshape de forma que a quantidade de i (linhas) ele descubra
# E que a quantidade de j (colunas) seja 3
# Como o vetor a tinha 30 elementos e a gente pediu pra ter 3 colunas, ele vai gerar
# uma matriz 10x3 (10 linhas e 3 colunas)
```




    array([[ 0,  1,  2],
           [ 3,  4,  5],
           [ 6,  7,  8],
           [ 9, 10, 11],
           [12, 13, 14],
           [15, 16, 17],
           [18, 19, 20],
           [21, 22, 23],
           [24, 25, 26],
           [27, 28, 29]])




```python
a = np.arange(30)
c = a.reshape(2, -1)
c
# Se a gente pedir 2 linhas e -1 colunas, ele vai gerar uma matriz 2x15
```




    array([[ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14],
           [15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29]])




```python
a = np.arange(30)
# Se pedir um valor em que i*j != len(v) ele vai dar erro
# Todos abaixo geram erros
a.reshape(7, -1) # Não é possível dividir por 7 (Não existe nenhum valor que multiplicado por 7 vai dar o len do vetor)
a.reshape(-1, 7) # Idem
a.reshape(2, 1) # 2 * 1 != 30
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[6], line 3
          1 # Se pedir um valor em que i*j != len(v) ele vai dar erro
          2 # Todos abaixo geram erros
    ----> 3 a.reshape(7, -1) # Não é possível dividir por 7 (Não existe nenhum valor que multiplicado por 7 vai dar o len do vetor)
          4 a.reshape(-1, 7) # Idem
          5 a.reshape(2, 1) # 2 * 1 != 30


    ValueError: cannot reshape array of size 30 into shape (7,newaxis)


# Operações ndarray com números literais


```python
a = np.arange(30)
# Ao pegar vetores de 1 dimensão
print("Soma:", a + 3)
# Aplicam a cada elemento
# Lembrando que pode ser usada --> QUALQUER <-- operação do python
# Exemplo:
print("Potenciação:", a ** 2)
print("Divisão Inteira:", a // 2)
```

    Soma: [ 3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26
     27 28 29 30 31 32]
    Potenciação: [  0   1   4   9  16  25  36  49  64  81 100 121 144 169 196 225 256 289
     324 361 400 441 484 529 576 625 676 729 784 841]
    Divisão Inteira: [ 0  0  1  1  2  2  3  3  4  4  5  5  6  6  7  7  8  8  9  9 10 10 11 11
     12 12 13 13 14 14]


# Operações python ndarray com ndarray


```python
# Só é possível se forem de mesma dimensão i1 == i2 && j1 == j2
# --> TODAS <-- as operações python são aceitas
# Será aplica elemento por elemento
v = a.reshape(2, 15)
t = np.ones(30).reshape(2, 15)
v + t

```




    array([[ 1.,  2.,  3.,  4.,  5.,  6.,  7.,  8.,  9., 10., 11., 12., 13.,
            14., 15.],
           [16., 17., 18., 19., 20., 21., 22., 23., 24., 25., 26., 27., 28.,
            29., 30.]])



# Operações do próprio numpy


```python
# Sum -> Pode ter quantas dimensões quiser, sempre retornará a soma de todos os
# elementos
s = np.sum(a.reshape(2, 3, 5))
m = np.mean(a.reshape(2, 3, 5))
print(s, m)
```

    435 14.5


# Funções python nos arrays do numpy


```python
"""
Aqui tem q tomar cuidado hein, pra nn confundir.
A lib python implementa o sum iterando por todos os elementos e somando
em uma variável acumulativa. Portanto, se tiver sum([[1, 2], [3, 4]])
é a mesma coisa de [1, 2] + [3, 4]

E lembre que diferente de um array python comum, os arrays numpy quando feitos
operações eles fazem as operações com cada posição relativa ao outro
então geraria: [1+3, 2+4] = [4, 6]
"""
a = np.array([[1, 2], [3, 4]])
print("sum(a) =", sum(a))

b = np.array([[1], [2], [3], [4]])
print("sum(b) =", sum(b))

c = np.array([1, 2, 3, 4])
print("sum(c) =", sum(c))
"""
Repare a diferença entre sum(b) e sum(c)
Já que o b vai somando vetores [1] + [2] + [3] + [4]
ele retorna um vetor [10]

Já no c, só tem uma dimensão, ent ele vai somando os valores 1 + 2 + 3 + 4
Retornando apenas o número 10
"""
```

    sum(a) = [4 6]
    sum(b) = [10]
    sum(c) = 10



```python
"""
Mas nn vai confundir na prova com os arrays padrões do python hein
[1, 2] + [3, 4] = [1, 2, 3, 4]

Apenas os arrays do numpy que conseguem fazer as operações matemáticas
Os arrays nativos do python é diferente
O + faz extend no vetor
E o * repete os elementos
"""
print([1, 2] + [3, 4])
print([1, 2, 3] * 3)
```

    [1, 2, 3, 4]
    [1, 2, 3, 1, 2, 3, 1, 2, 3]

