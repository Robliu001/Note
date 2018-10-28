---
title: Python小知识 
tags: Python,小知识,编程
grammar_cjkRuby: true
---
### pip查询支持的名称和版本
### AMD64
```
import pip._internal
print(pip._internal.pep425tags.get_supported())
```
### WIN32
``` python
import pip
print(pip.pep425tags.get_supported())
```
## 知识点
联合遍历
for x, y in zip(l1, l2):
...

## numpy
numpy.hsplit(\[(a, b)], 2) 把一个元祖列表水平分割，这个元祖是有两个元素。

### 符号数组
np.sign(数组)->符号数组
np.piecewise(array, \[条件列表], \[标志列表]) -> 标志数组

## matplotpylib.datetime


