# np.pad
1. 参数解释
ndarray = numpy.pad(array, pad_width, mode, **kwargs)
+ array 为要pad的数组
+ pad_width 是在各个维度各个方向上想要填补的长度，如：((1, 2), (2, 2))表示在第一个维度上水平方向上padding=1，垂直方向上padding=2；在第二个维度上水平方向上padding=2，垂直方向padding=2。如果直接输入一个整数，则说明各个维度和各个方向所填补的长度都一样。
+ mode 为填补类型，有“constant”, “edge”，如果为constant模式，就得指定填补的值，如果不指定，则默认填充0。


# 例子
### 一维数组　
```python3
>>> import numpy as np
>>> array = np.array([1, 1, 1])
"""
(1, 2)表示在一维数组前面填充1位，最后面填充2位
costant_values=(0,2)，表示前面填充0，后面填充2
"""
>>> ndarray = np.pad(array, (1, 2), mode='constant', constant_values=(0, 2))
>>> print(str(array))
[1 1 1]
>>> print(str(ndarray))
[0 1 1 1 2 2]
```

### 二维数组
```python3
>>> array = np.array([[1, 1],[2,2]])
"""
((1,1),(2,2))表示在二维数组array第一维（此处便是行）前面填充1行，最后面填充1行；
                 在二维数组array第二维（此处便是列）前面填充2列，最后面填充2列
constant_values=(0,3) 表示第一维填充0，第二维填充3
"""
>>> ndarray=np.pad(array,((1,1),(2,2)),'constant', constant_values=(0,3))
>>> print(str(array))
[[1 1]
 [2 2]]
>>> print(str(ndarray))
[[0 0 0 0 3 3]
 [0 0 1 1 3 3]
 [0 0 2 2 3 3]
 [0 0 3 3 3 3]]
>>>

```
