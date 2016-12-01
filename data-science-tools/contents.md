# ���ݿ�ѧ����


## �۵�

Ҫ���ߴ��ʲô�Ǻõģ������ۣ����Ǻ���Ч

ֻ˵���Ƽ��ģ�ʡȥ�����

## �۵�

Զ��ʱ��ڶ�


## �۵� 

��Щ���Ѿ��Ʋ���ȥ��

## ����

- ���ڴ�
- ��̬Ӳ��
- ��Ҫ����ֵ�Ӳ������������

�����������ѧϰ�Ĳ���Ǯ��ͬѧ��������׼�� NVIDIA �Ķ����Կ�����


## ����ϵͳ

��Ҫ�����ݿ�ѧ����úø���һƱ��ͬѧ

Linux > macOS > Windows

�Ƽ�ϵͳ��

Ubuntu 

�����᣺

���з�����


## ����


## �������

GitHub

---

�ܽ᣺

������ѧ��·�ߣ� pc + windows + R 

һ����λ���ݿ�ѧְҵ���ķ�չ·�ߣ� pc + ubuntu + anaconda + jupyter notebook


---

## ��δ��������

�����

- �ǳ�����

���⣺

- �Ƿ����

��������飺

- ���ӣ�
- �������������ά֪ʶ��
- �������ܽ���ȥ��


hadoop 

- hadoop �ĸ���
- hdfs
- ��֪��һ��

spark ��������


���裺

- ����������̨���ԣ���ͨ�����۵� pc �����ɣ�
- ���һ����������������Ҫ��һ�㣩
- ��װ ubuntu-server ϵͳ��LTS 16.04��
- ����Ҫ������
  - �޸����Դ�ĵ�ַ���޸ĵ��ô����ַ
  - ����ϵͳ���
  - �����û� ssh ������Կ�������໥ֱ�ӷ���
- ��װ jdk�� OpenJDK 1.8 �ͺã�
  sudo apt update
  sudo apt install openjdk-8-jdk  
- �������µ� spark ����õİ�
  - ���Ƶ���������
  - ��ѹ��
  - �����ã�ʹ�� standalone ��Ⱥģʽ
  - ���� master
    
    sudo ./sbin/start-master.sh
  
  - ���������ڵ�
  
    sudo ./sbin/start-slave.sh <master-spark-URL>
    
        
- ����һ�� spark-shell python ��ʼ����

    ./bin/pyspark --master <master-spark-URL>

- ��ѡ��� hadoop hdfs ���ṩ�����ļ��Ķ�д

�����洢

- �ֳɵ�

  ���⣺��ʱ�䡢��Ǯ
  
- ���ֳɵ�

  ���⣺̫�鷳�����ô���

---

## Spark 

Notice:

- ֻ�� spark �������㹤��
- ��Ҫ�о� spark ����scala ��Ҫ����ʱ��ڶ�
- �������Խӿ�
  - ֻ���ṩ�����������µĲ��� spark �ı���������֪��İ� spark ��ĳ�����Խ����һ��
  - ����������ã�Ч������
  - pyspark��sparkr ����
  

�����

@ͼ


Spark �ṩ�˶��ڲ����ĸ�������

- ͨ�û���
- �ֲ�ʽϸ�ڱ���װ����

���ӣ�

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

��Ҫ���� SparkSQL��Ҳ���� DataFrame

���� SparkSQL ����

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


����ѧϰ

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

## ����������ʶ

- �ж�̨���ԵĿ��Էֿ�����/��������
- 
  

---

## ��Ҫ���� DataFrame

---

�м�ֵ�Ķ���

## ͼ

Graph Mining

GraphX

GraphFrame

## ���ѧϰ

tensorflow


## ������