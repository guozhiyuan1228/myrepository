一、图查询：执行1例复杂查询，展示执行结果截图，并解释Cypher语句含义。

1.路径匹配

MATCH p=(n)-[*..2]-(m) WHERE n.born > 1960 RETURN p

含义：匹配所有长度不超过2的路径，其中起始节点n的属性born大于1960，然后返回完整路径p。
<img width="1910" height="925" alt="0fa2fd4bbc83934d964869cf839cd472" src="https://github.com/user-attachments/assets/7927ef10-89e6-42e6-acc2-30a524627783" />

2.聚合与排序

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

二、图算法

1.路径查找

新建数据库Station_GZY，添加点、边。
<img width="1910" height="925" alt="d8796b9898c2c9a978e68b8e59850d40" src="https://github.com/user-attachments/assets/74076dd7-619f-4278-8669-386a7df28e6b" />

<img width="1910" height="925" alt="29f04ae1472221237f460420ad4e6929" src="https://github.com/user-attachments/assets/13589fa8-8b64-4c0d-b042-86d6f353e96e" />

MATCH (x:station {name: 'Kings Cross'}), (y:station {name: 'Kentish Town'}) 

WITH x, y CALL algo.allShortestPaths(x, y) YIELD nodeIds,relationshipIds,cost RETURN nodeIds,relationshipIds,cost

含义：使用图算法库中的最短路径算法，查找Kings Cross和Kentish Town两个车站之间的最短路径，返回路径上的节点数量、总成本和完整路径。
<img width="1910" height="925" alt="f2cfd571decfbd6627c5fcb3d190b7d4" src="https://github.com/user-attachments/assets/3102c193-ee0a-481b-a7a3-73b89c325c09" />

MATCH (x:station {name: 'Kings Cross'}), (y:station {name: 'Kentish Town'}) 

WITH x, y CALL algo.shortestPath(x, y) YIELD nodeCount,totalCost,path RETURN nodeCount,totalCost,path

含义：使用图算法库中的全部最短路径算法，查找Kings Cross和Kentish Town两个车站之间的所有最短路径，返回每条路径的节点ID列表、关系ID列表和路径成本。
<img width="1910" height="925" alt="5d6346962ee0b9edace9e96983c36086" src="https://github.com/user-attachments/assets/00f3d805-af39-48bb-900d-4abe56566312" />

2.图遍历

在Station_GZY中导入存储过程BFS并执行。
<img width="1910" height="925" alt="992354d6ea76b8fbbc06d9795dc03162" src="https://github.com/user-attachments/assets/0df7e2ab-ef51-4971-97a4-809bfc801698" />

3.图的中心性

新建数据库Page_GZY，添加点、边。
<img width="1910" height="925" alt="84403af75a8fdf811f37eabffd753c82" src="https://github.com/user-attachments/assets/6d2f5b4d-dfd6-4a78-b074-73e1c2a3efbb" />

<img width="1910" height="925" alt="a943169f02375edca2e2fe532d231c6d" src="https://github.com/user-attachments/assets/b326113d-fd3d-4d81-8fc7-5ceeb5a8839e" />

导入存储过程PageRank并执行。
<img width="1910" height="925" alt="6161eac03b99ddc7a8d2c4f0b1fa874b" src="https://github.com/user-attachments/assets/db262ad5-0013-4c54-9e00-1d737bba5158" />

<img width="1910" height="925" alt="2dbd506912983e1eb560f655f70bff2f" src="https://github.com/user-attachments/assets/355c935f-1df0-4e2f-8857-d7b29c26ab10" />

4.社区检测

新建数据库Follow_GZY，添加点、边。
<img width="1910" height="925" alt="3e8a8d34b73c8c080e8e1bc16ed3e5fc" src="https://github.com/user-attachments/assets/f88007e6-e1ab-4cc6-a505-be4fc9d733c9" />

<img width="1910" height="925" alt="4c9fd13ab0f9b3976b6bdb582e0627e9" src="https://github.com/user-attachments/assets/278728e5-d4db-4a1b-b983-a4bda3d1e72c" />

导入存储过程LPA并执行。
<img width="1910" height="925" alt="11cfbf8b59283fe83dd0c362707ee5d3" src="https://github.com/user-attachments/assets/3f410531-641a-427d-80da-0dba11093597" />

<img width="1910" height="925" alt="3808573041a60ad3b5ea4e6dd535b410" src="https://github.com/user-attachments/assets/4f662ef2-6b66-4d4e-9746-9bfd512470a1" />

5.节点嵌入
将Node2Vec示例数据集导入TuGraph，运行采样步骤成功，通过文字、代码、截图描述步骤
<img width="1910" height="925" alt="bd110a6063a9368914730b64e78b2eae" src="https://github.com/user-attachments/assets/0a58c6ca-8dab-4889-8f56-9a6e4c53f035" />

完整实现Node2Vec算法，得到嵌入向量，描述配置过程中解决了哪些问题、用的什么方法（文字、代码、截图）


6.链接预测


