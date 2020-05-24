# Pandas Tips

## 1.1 np.argmax()



## 1.2 DataFrame.applymap()

[Pandas数据分析三板斧——map、apply、applymap详解](https://www.jianshu.com/p/e76861ed1815)



## 1.3 pd.read_csv

可以指定usecols参数来选择只读取某些列，nrows=3只读取前3行.

## 1.4 DataFrame.iterrows()

遍历dataframe

for index,row in df.iterrows :

​    print index,row.xx,row.xx

![](https://i.loli.net/2020/05/14/4qijSehptRzsPlL.png)

## 1.5 DataFrame.select_dtypes

pandas中select_dtypes选取特定的列值

[select_dtypes](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.select_dtypes.html)

## 1.6 DataFrame.describe

![image-20200514222733971](https://i.loli.net/2020/05/14/NlaAf92EBg1Mbyq.png)

## 1.7  安装扩展Nbextensions插件

管理员启动Anaconda Prompt

```
conda install -c conda-forge jupyter_contrib_nbextensions
conda install -c conda-forge jupyter_nbextensions_configurator
```

## 1.8 DataFrame.set_index

可以设置某列为index

DataFrame.set_index("colum",inplace=True)

## 1.9 category

![image-20200515205150601](https://i.loli.net/2020/05/15/MNyma9BPthVHGC1.png)

## 1.10 get_dummies

```python
import pandas as pd
xiaoming=pd.DataFrame([1,2,3],index=['yellow','red','blue'],columns=['hat'])
print(xiaoming)
hat_ranks=pd.get_dummies(xiaoming['hat'],prefix='hat')
print(hat_ranks.head())
```

![image-20200515214042989](https://i.loli.net/2020/05/15/gPJkWOdcD2tp5GK.png)

## 1.11 groupby().agg

可以指定自定义函数来进行聚合运算，列名默认是聚合函数的名字，可以传入一个tuble来更改列名

![image-20200516094047405](https://i.loli.net/2020/05/16/9r4Z7tmHSuOvIUc.png)

## 1.12 groupby分组时设置as_index=False

默认分组的key作为index，可以设置as_index=False来取消

## 1.13 groupby分组transform()

[理解Pandas的Transform](https://www.jianshu.com/p/509d7b97088c)

## 1.14 groupby后apply函数

要记住按照指定key groupby(分组)之后，传入给apply函数的是分组后的DataFrame

![image-20200516101854233](https://i.loli.net/2020/05/16/pcGPr1Xq4SjvNJu.png)

## 1.15 pd.read_csv分块读取数据

可以指定chunksize来分块读取数据，然后对每块进行迭代

## 1.16 df.dropna()

可以删除整列，或者整行为NaN的数据

df.dropna(axis=1,how='all')  //删除所有值都为NaN的列

![image-20200522223215062](https://i.loli.net/2020/05/22/OMKyR4GS6nQ3Jp9.png)

## 1.17 df.value_counts()

可以显示数据的个数，加上normalize=True可以转换为百分比

![image-20200522223811204](https://i.loli.net/2020/05/22/vSio3rtD4ubaeHG.png)

## 1.18 ast 模块

可以把string转换成对象

![image-20200523215812656](https://i.loli.net/2020/05/23/cM8v2iL9IdXVBom.png)

```python
ted['rating_list']=ted.ratings.apply(lambda x:ast.literal_eval(x))

ted.assign(ratinglist=lambda x:x.ratings.apply(ast.literal_eval))
```

## 1.19 DataFrame字符串函数

字符串函数中使用正则表达式的方法

![image-20200524111701722](https://i.loli.net/2020/05/24/E7OeyhNw9scFrkR.png)