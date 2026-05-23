1.数据集的介绍、下载、展示

访问下载链接：https://www.kaggle.com/datasets/jsrojas/ip-network-traffic-flows-labeled-with-87-apps

背景：这里展示的数据采集自哥伦比亚波帕扬市考卡大学的一个网络区域，通过在2017年的六天时间（4月26日、27日、28日，以及5月9日、11日、15日）内，于上午和下午的不同时段进行数据包捕获而获得。共采集了3577296个实例，目前以CSV（逗号分隔值）文件格式存储。

内容：该数据集包含87个特征。每个实例保存了由网络设备生成的IP流信息，包括源IP地址与目标IP地址、端口、到达时间间隔，以及该流所使用的第七层协议（应用层）作为类别等。大多数属性为数值类型，但也存在名义类型，以及因时间戳而产生的一种日期类型。

注册Kaggle账号，填写基本信息，安装Header Editor插件，邮箱获取验证码，注册成功。

登录，下载数据集。
<img width="1920" height="920" alt="b8485c35e33620b43312a4beaefbf902" src="https://github.com/user-attachments/assets/d20d7d4b-352b-42c0-ab68-df69c965676e" />

下载完成。
<img width="1116" height="208" alt="0d5bc5767e111831f6d4fcc34f45e27c" src="https://github.com/user-attachments/assets/e3550a30-8cbe-4f6d-b4eb-a263e90dcf5e" />

<img width="1850" height="724" alt="a38668ac51ec9c8ec9c3c0b63eea721c" src="https://github.com/user-attachments/assets/3f035e63-8551-43d9-b111-4888f56a8b58" />

2.两种流量图建模方法，写代码提取数据集中的对应字段，可视化或者代码导入TuGraph

2.1 {IP,port}对作为图中的顶点（HCG）

HCG表示为G(V,E)，将节点{IP,port}抽象为一个点vi∈V，若vi和vj之间有通信，则在vi和vj之间建立一条边eij∈E。

新建数据库Traffic_HCG。

<img width="506" height="201" alt="2c4447599c2e3ba17b7b8ce5bcae1c2e" src="https://github.com/user-attachments/assets/d24be25d-7243-4ad3-a650-0a6f578e7782" />

创建点类型、边类型。
<img width="1910" height="925" alt="1879b4a29b3b4f7927a500d292281c80" src="https://github.com/user-attachments/assets/5bb26ee3-7585-4843-a87d-58c39b80e666" />

<img width="1910" height="925" alt="2eae8ded8286dd185254af7574b18353" src="https://github.com/user-attachments/assets/fe91e8c9-5ba2-427a-be72-93c92988753a" />

撰写HCG.py采样+提取数据集Dataset-Unicauca-Version2-87Atts.csv中的ip和port字段，并组合形成id(ip:port)字段。
<img width="813" height="800" alt="bc9908095ab9ee244e1077eeb03d1fda" src="https://github.com/user-attachments/assets/c0b27a48-7ba3-4c02-8583-4e2a133dce97" />

<img width="813" height="800" alt="c913503acbd47eacf32cbdac99df9846" src="https://github.com/user-attachments/assets/fa74a3b8-ab03-43c7-89ba-079045bda310" />

运行结果如下。

<img width="706" height="691" alt="56daa10a92a2e950032afb1285d6d9b0" src="https://github.com/user-attachments/assets/a25e5968-043b-4392-acc1-a8f570de34c1" />

<img width="465" height="50" alt="cc642387a08ab056525dcdc7ddef2ff7" src="https://github.com/user-attachments/assets/c5868ac9-61ce-45e9-bbba-b54fc996e0d3" />

导入hcgnodes.csv和hcgedges.csv数据。
<img width="1910" height="925" alt="4b8f21a0c19e60d430ebe285ab90e747" src="https://github.com/user-attachments/assets/0e31dda3-d357-4bfd-b336-ecd9cf3139c3" />

<img width="1910" height="925" alt="6d623906a6bc7dbdb2f49376ecd505e8" src="https://github.com/user-attachments/assets/0f9f6b28-e283-4606-afd7-4c8aafc6a89b" />

<img width="1910" height="925" alt="8a15ee2bbc2b5482d6567504a069d555" src="https://github.com/user-attachments/assets/776dbab0-af07-4fe6-ab9e-572f4cd1c8a0" />

<img width="1910" height="925" alt="4bfd17107dfb1f143b4520f777ab9272" src="https://github.com/user-attachments/assets/7c857597-0bb2-438d-8d67-559180920052" />

导入完成后执行查询验证：MATCH (n:HCGNode)-[r:COMMUNICATES]->(m) RETURN n,r,m LIMIT 200
<img width="1910" height="925" alt="f20a946ed6f9190d0ecedf12425af1e7" src="https://github.com/user-attachments/assets/8dea77c6-1c7f-406f-a9c3-615631111c93" />

2.2 流作为图中的顶点（TCG）

TCG 中的点和边分别表示网络流和流间的因果关系。




3.点嵌入/边嵌入、特征融合，通过文字、代码、截图描述步骤

3.1 点嵌入

导入node2vec算法。
<img width="1910" height="925" alt="282ab36921e2e1ae63fa083dec2d9d3b" src="https://github.com/user-attachments/assets/9e1a7a6e-02e4-4249-9e3b-981e9b15f036" />

获取存储过程执行结果。

















4.测试至少3种不同的分类器，给出评价指标
