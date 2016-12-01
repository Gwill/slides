# 数据科学工具


## 观点

要告诉大家什么是好的，很主观，但是很有效

只说我推荐的，省去理客中

## 观点

远离时间黑洞


## 观点 

有些坑已经绕不过去了

## 电脑

- 大内存
- 固态硬盘
- 不要有奇怪的硬件，方便折腾

至于想玩深度学习的不差钱的同学，还可以准备 NVIDIA 的顶级显卡若干


## 操作系统

想要在数据科学方面好好干他一票的同学

Linux > macOS > Windows

推荐系统：

Ubuntu 

更纠结：

折中方案：


## 语言


## 代码管理

GitHub

---

总结：

不折腾学渣路线： pc + windows + R 

一步到位数据科学职业生涯发展路线： pc + ubuntu + anaconda + jupyter notebook


---

## 如何处理大数据

情况：

- 非常易用

问题：

- 是否合适

琐碎的事情：

- 机子？
- 计算机服务器运维知识？
- 数据流能接上去吗？


hadoop 

- hadoop 的概念
- hdfs
- 不知这一个

spark 计算引擎


步骤：

- 首先有若干台电脑（普通的退役的 pc 机即可）
- 组成一个局域网（交换机要好一点）
- 都装 ubuntu-server 系统（LTS 16.04）
- 做必要的配置
  - 修改软件源的地址，修改到厦大镜像地址
  - 更新系统软件
  - 配置用户 ssh 访问秘钥，可以相互直接访问
- 都装 jdk， OpenJDK 1.8 就好，
  sudo apt update
  sudo apt install openjdk-8-jdk  
- 下载最新的 spark 编译好的包
  - 复制到各个机子
  - 解压缩
  - 简单配置，使用 standalone 集群模式
  - 启动 master
    
    sudo ./sbin/start-master.sh
  
  - 启动各个节点
  
    sudo ./sbin/start-slave.sh <master-spark-URL>
    
        
- 启动一个 spark-shell python 开始工作

    ./bin/pyspark --master <master-spark-URL>

- 可选：搭建 hadoop hdfs ，提供超大文件的读写

其他存储

- 现成的

  问题：费时间、费钱
  
- 不现成的

  问题：太麻烦，不好处理

---

## Spark 

Notice:

- 只把 spark 当做计算工具
- 不要研究 spark 本身，scala 不要碰，时间黑洞
- 各个语言接口
  - 只是提供在这种语言下的操作 spark 的遍历，并不知真的把 spark 和某种语言结合在一起
  - 所以如果混用，效果更差
  - pyspark，sparkr 都是
  

组件：

@图


Spark 提供了对于操作的各种算子

- 通用化的
- 分布式细节被封装隐藏

算子：

```
Transformation

map(func)
filter(func)
flatMap(func)
mapPartitions(func)
mapPartitionsWithIndex(func)
sample(withReplacement,?fraction,?seed)
union(otherDataset)
intersection(otherDataset)
distinct([numTasks]))
groupByKey([numTasks])?
reduceByKey(func, [numTasks])?
aggregateByKey(zeroValue)(seqOp,?combOp, [numTasks])?
sortByKey([ascending], [numTasks])?
join(otherDataset, [numTasks])?
cogroup(otherDataset, [numTasks])?
cartesian(otherDataset)
pipe(command,[envVars])
coalesce(numPartitions)
repartition(numPartitions)
repartitionAndSortWithinPartitions(partitioner)?


Action

reduce(func)
collect()
count()
first()
take(n)
takeSample(withReplacement,?num, [seed])
takeOrdered(n,?[ordering])
saveAsTextFile(path)
countByKey()?
foreach(func)
```

重要的是 SparkSQL，也就是 DataFrame

建立 SparkSQL 环境

```python
from pyspark.sql import SparkSession
spark = SparkSession \
    .builder \
    .appName("Python Spark SQL") \
    .getOrCreate()
```

```python
df = spark.read.csv('python/test_support/sql/ages.csv')
```


机器学习

```python
# Every record of this DataFrame contains the label and
# features represented by a vector.
df = sqlContext.createDataFrame(data, ["label", "features"])

# Set parameters for the algorithm.
# Here, we limit the number of iterations to 10.
lr = LogisticRegression(maxIter=10)

# Fit the model to the data.
model = lr.fit(df)

# Given a dataset, predict each point's label, and show the results.
model.transform(df).show()
```

---

## 环境管理意识

- 有多台电脑的可以分开娱乐/工作电脑
- 
  

---

## 重要的是 DataFrame

---

有价值的东西

## 图

Graph Mining

GraphX

GraphFrame

## 深度学习

tensorflow


## 容器化