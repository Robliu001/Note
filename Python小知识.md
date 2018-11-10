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
	numpy将绝大部分Python运算符都针对ndarray/matrix类进行类重载，借助通用函数支持矢量运算
	
numpy.hsplit(\[(a, b)], 2) 把一个元祖列表水平分割，这个元祖是有两个元素。
numpy.matrixlib 中 numpy.matrix 创建新数组 new = numpy.matrix(old, copy=true/false)true就是完全复制
numpy.mat("1 2; 3 4")生成矩阵，
numpy.bmat("A B; C D")将A B C D四个矩阵拼写
numpy.frompyfunc(标量函数， 参数个数， 返回值个数) ->通用函数对象 类似numpy中的 + 、-、\*、/
### 加法通用函数
numpy.add.reduce - 各元素求和
numpy.add.accumulate - 各元素求和的过程
numpy.add.reduceat - 分组求和
numpy.add.outer - 外和
### 除法通用函数
- 真除：无论元素数值是整型还是浮点数，结果都是浮点数，保留尽可能多的小数位 ( /、true_divide、divide）
- 地板除：如果运算数是整型， 运算结果也是整型， 向下取整。 （//  、floor_divide）
- 天花板处：如果运算数是整型，运算结果也是整型，向上取整 （numpy.ceil(a / b).astype(int)
- 截断除：如果运算数是整型，运算结果也是整型，舍弃小数部分(numpy.trunc(a/b).astype(int)

### 地板余
numpy.remainder、mod、%
### 截断余
numpy. fmod
### 符号数组
np.sign(数组)->符号数组
np.piecewise(array, \[条件列表], \[标志列表]) -> 标志数组
### 矢量化
两个维度的数据实质上就是把一维数组变成二维数组
矢量函数 = np.vectorize(标量函数)
矢量返回值 = 矢量函数(矢量参数)
### 位运算
- ^  / \_\_xor__ / numpy.bitwise_xor
- & 与  numpy.bitwise_and
- | 或 numpy.bitwise_or
- ~ 取反 numpy.bitwise_not
-  << / >> numpy.left_shift  / numpy.right_shift

### 子模块
#### 线性代数（linalg）
##### inv /　Ｉ
如果矩阵A和B的乘积是一个单位阵，那么A和B互称逆矩阵
使用Ｉ属性求的是广义（伪逆矩阵）matrix属性
##### solve 解线性方程组
#### 快速傅里叶变换（fft）
numpy.fft.fftfreq(采样数，采样周期）->频率序列
numpy.fft.fft(源函数值)->目标函数值（复数）
模->能量  幅角->相位
#### 随机数模块（random）
numpy.random.binomial(n, p, size)
产生size个随机数，其中每个随机数来自n次尝试中的成功的次数，每次尝试成功的概率为p。
#### 超几何分布
numpy.random.hypergeometric(ngood, nbad, nsammple, size)
产生size个随机数，其中每个随机数来自随机抽取nsample个样本中好样本的个数，总样本空间由ngood个好样本和nbad个好样本组成
#### 正态分布
numpy.random.normal(size)
产生size个服从标准正态（平均值=0，标准差=1）分布的随机数。
f(x)=e^(-x^2/2) / sqrt(2\*pi)
#### 排序
numpy.lexsort(参考序列，排序序列)，间接排序，返回的是索引
numpy.sort_complex(复数数组),按照实部升序排序，对实部相同的参考虚部排序
numpy.searchsorted(有序序列，待插序列) 将待插序列中的元素插入到有序序列的哪些位置，依然有序
numpy.insert(被插序列，位置序列，待插序列)将待插序列中的元素，按照位置序列中的位置下标，插入被插序列，返回插入以后的结果。
#### 定积分
import scipy.integrate as si
area = si.quad(f, a, b)
#### 插值
linear = si.interpld(dis_x, dis_y) # 线性差值器

## matplotpylib.datetime


