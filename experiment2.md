1.执行1例复杂查询，展示执行结果截图，并解释Cypher语句含义

1.1 路径匹配

MATCH p=(n)-[*..2]-(m) WHERE n.born > 1960 RETURN p

含义：匹配所有长度不超过2的路径，其中起始节点n的属性born大于1960，然后返回完整路径p。
<img width="1910" height="925" alt="0fa2fd4bbc83934d964869cf839cd472" src="https://github.com/user-attachments/assets/7927ef10-89e6-42e6-acc2-30a524627783" />

1.2 聚合与排序

MATCH (n) RETURN count(n) AS total

含义：计算并返回数据库中节点的总数量。
<img width="1910" height="925" alt="c4ed837e277552676c51e74a2a3e34ab" src="https://github.com/user-attachments/assets/c45a4f48-7170-4242-b461-8b99f9318fd5" />

MATCH (n:person) RETURN n ORDER BY n.born DESC LIMIT 10

含义：查询所有标签为person的节点，按born属性降序排序，返回出生年份最晚（即年龄最小）的前10个人。
<img width="1910" height="925" alt="a52790d434687100f214dd14245e6912" src="https://github.com/user-attachments/assets/8829860c-5722-41d9-8e7a-d23a3d2761c9" />

MATCH (p:person)-[r]->(m)

WITH p, COUNT(m) AS movieCount

WHERE movieCount > 2

RETURN p.name, movieCount ORDER BY movieCount DESC LIMIT 10

含义：查询制作电影数量超过2部的人，按制作数量降序排列，返回前10人的姓名和制作电影数。
<img width="1910" height="925" alt="4a5b3d26aa7122d04f4b82b4274000a7" src="https://github.com/user-attachments/assets/fcaa015e-67ec-451d-a290-399432cc9366" />

2.将Node2Vec示例数据集导入TuGraph，运行采样步骤成功，通过文字、代码、截图描述步骤


3.完整实现Node2Vec算法，得到嵌入向量，描述配置过程中解决了哪些问题、用的什么方法（文字、代码、截图）
