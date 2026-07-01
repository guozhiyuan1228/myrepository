续experiment3.md

1.流量图建模（代码提取数据集中前100行的对应字段，可视化或者代码导入TuGraph）

流作为图中的顶点（TCG），TCG 中的点和边分别表示网络流和流间的因果关系。

编写generate_tcg.py提取数据集Dataset-Unicauca-Version2-87Atts.csv中我们需要的字段，并计算因果关系。

<img width="1534" height="763" alt="186e97e63249fed99dd7f91233368c40" src="https://github.com/user-attachments/assets/6a916673-c35e-4915-9e9e-101671d48b6a" />

<img width="760" height="69" alt="9b6050679cc19907405f63b0552d6305" src="https://github.com/user-attachments/assets/8f4a01cb-af64-4a62-b549-96ac03183093" />

新建数据库TCG。

<img width="1920" height="900" alt="e9bdb9152e53ba75004733baaffda992" src="https://github.com/user-attachments/assets/fa9ec25d-5041-4a2c-85c0-f65f765d97ad" />

创建点类型、边类型。

<img width="1920" height="900" alt="f70ec2c85cd02afc52d4365c377c1776" src="https://github.com/user-attachments/assets/49efa0ee-99fc-4999-9eb9-859d3cda21d5" />

<img width="1920" height="900" alt="f811b212f053d7fbed2b46b51071a1c6" src="https://github.com/user-attachments/assets/db0b9fa3-dc72-4c9b-ad4d-d8ef466e5421" />

导入tcg_nodes.csv和tcg_edges.csv数据。

<img width="1920" height="900" alt="452d9181ee7802ea5238ba5c1918f983" src="https://github.com/user-attachments/assets/f2f5c651-088c-49c7-9a51-31c82781d151" />

<img width="1920" height="900" alt="25b9ca6d8ac2338b462b2e7b95011834" src="https://github.com/user-attachments/assets/29499bfb-3414-4987-807e-7badf7c6ae1d" />

<img width="1920" height="900" alt="6fc9ad85ca50dd250728d002c20b9b6b" src="https://github.com/user-attachments/assets/c0c6f898-2757-4d92-8a48-706ec10f4790" />

<img width="1920" height="900" alt="9faabd3536d7ecba0f33732815337f5b" src="https://github.com/user-attachments/assets/fe59dc18-1011-40c3-be91-cd07c44cd625" />

导入完成后在图分析处执行查询验证：MATCH (n) - [r] - () RETURN n, r LIMIT 100

<img width="1920" height="830" alt="b13f9059919fea258ad22749f43f8f68" src="https://github.com/user-attachments/assets/2a7bb428-ad8c-4a9a-83fd-2ee8722ce3ff" />

2.边嵌入、特征融合（通过文字、代码、截图描述步骤）

导入edge2vec算法。

<img width="1920" height="830" alt="5a8942fabdf57cb72f6313aebb8b21a0" src="https://github.com/user-attachments/assets/19a55ce0-beb3-4ddb-94b8-c18191fd4e07" />

获取存储过程的执行结果。

<img width="1920" height="830" alt="1c152a908d8d8156d3353f1f084123fd" src="https://github.com/user-attachments/assets/10bb56fd-2f8c-4d3b-9dfd-90bc25a2565d" />

用GET方法导出执行结果。

<img width="1521" height="770" alt="b8fb293b761423bc8595af658bf4598f" src="https://github.com/user-attachments/assets/a2cedf68-1255-421b-86e7-6ab272f5b7b2" />

<img width="775" height="85" alt="73a7faf3529ff6723a02c41bb47d4c73" src="https://github.com/user-attachments/assets/a2c61e67-00bb-4fc3-b319-8f4b51d584d7" />

<img width="1423" height="739" alt="7587e55cbebf16d5e9be0ec272ffa1df" src="https://github.com/user-attachments/assets/f5cbc884-17f7-4cc8-b646-07acb6a02816" />

3.KNN分类器预测并显示评价指标

<img width="1614" height="810" alt="90d78835844aa19f72e085d120eb7cdc" src="https://github.com/user-attachments/assets/dc0c9f14-0426-4f5e-9c4b-b0e569ec1319" />













