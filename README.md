[参考地址](https://morvanzhou.github.io/tutorials/data-manipulation/np-pd/)

# 为什么使用 numpy & pandas
* [运算速度快]()：
  numpy 和 pandas 都是采用 C 语言编写, pandas 又是基于 numpy, 是 numpy 的升级版本。
  
* [消耗资源少]()：
  采用的是矩阵运算，会比 python 自带的字典或者列表快好多
  
# Numpy 属性

- [ndim]()：维度
- [shape]()：行数和列数
- [size]()：元素个数

```
print('number of dim:',array.ndim)
```

# Numpy 的创建 array

- [array]() ：创建数组
- [dtype]() : 指定数据类型

```
a = np.array([2,23,4],dtype=np.int)
```

- [zeros]() ：创建数据全为0
- [ones]() ：创建数据全为1
- [empty]() ：创建数据接近0
- [arrange]() ：按指定范围创建数据

```
a = np.arange(10,20,2) # 10-19 的数据，2步长
```

- [linspace]() ：创建线段

```
a = np.linspace(1,10,20)    # 开始端1，结束端10，且分割成20个数据，生成线段
```

# Numpy 基础运算

### 一般运算

```
c=a-b   c=a+b   c=a*b   c=b**2（乘方）
```

# Numpy array 合并

1、vertical stack本身属于一种上下合并

```
print(np.vstack((A,B)))    # vertical stack
"""
[[1,1,1]
 [2,2,2]]
"""
```

2、hstack  左右合并

```
D = np.hstack((A,B))       # horizontal stack
print(D)
# [1,1,1,2,2,2]
```

# Numpy array 分割

1、纵向分割

```
print(np.split(A, 2, axis=1))
"""
[array([[0, 1],
        [4, 5],
        [8, 9]]), array([[ 2,  3],
        [ 6,  7],
        [10, 11]])]
"""
```

2、横向分割

```
print(np.split(A, 3, axis=0))

# [array([[0, 1, 2, 3]]), array([[4, 5, 6, 7]]), array([[ 8,  9, 10, 11]])]
```
3、不等量的分割

```
print(np.array_split(A, 3, axis=1))
"""
[array([[0, 1],
        [4, 5],
        [8, 9]]), array([[ 2],
        [ 6],
        [10]]), array([[ 3],
        [ 7],
        [11]])]
"""
```

# Pandas 基本介绍

如果用 python 的列表和字典来作比较, 那么可以说 Numpy 是列表形式的，没有数值标签，而 Pandas 就是字典形式。Pandas是基于Numpy构建的，让Numpy为中心的应用变得更加简单。

两个数据结构：Series和DataFrame

```
import pandas as pd
import numpy as np
s = pd.Series([1,3,6,np.nan,44,1])

print(s)
"""
0     1.0
1     3.0
2     6.0
3     NaN
4    44.0
5     1.0
dtype: float64
"""

dates = pd.date_range('20160101',periods=6)
df = pd.DataFrame(np.random.randn(6,4),index=dates,columns=['a','b','c','d'])

print(df)
"""
                   a         b         c         d
2016-01-01 -0.253065 -2.071051 -0.640515  0.613663
2016-01-02 -1.147178  1.532470  0.989255 -0.499761
2016-01-03  1.221656 -2.390171  1.862914  0.778070
2016-01-04  1.473877 -0.046419  0.610046  0.204672
2016-01-05 -1.584752 -0.700592  1.487264 -1.778293
2016-01-06  0.633675 -1.414157 -0.277066 -0.442545
"""
```



