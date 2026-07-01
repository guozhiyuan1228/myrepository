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

2.流量图建模（写代码提取数据集前100行的对应字段，可视化或者代码导入TuGraph）

{IP,port}对作为图中的顶点（HCG）。

HCG表示为G(V,E)，将节点{IP,port}抽象为一个点vi∈V，若vi和vj之间有通信，则在vi和vj之间建立一条边eij∈E。

编写generate_hcg.py提取数据集Dataset-Unicauca-Version2-87Atts.csv中我们需要的字段。

<img width="1514" height="765" alt="932fd974dc7bee6910ec366bb0657a74" src="https://github.com/user-attachments/assets/0a96d750-f1e0-43a6-80e8-1d86c54be444" />

<img width="790" height="60" alt="22e95bb69940a20946a212006080d772" src="https://github.com/user-attachments/assets/8b60a3b8-b6fc-4121-8bed-263657f07b96" />

新建数据库HCG。

<img width="1920" height="900" alt="c820d8752d5ea0776a2eeb6978018986" src="https://github.com/user-attachments/assets/00acb16b-cb62-4f06-9c92-2eaba36b2ae5" />

创建点类型、边类型。

<img width="1920" height="900" alt="6efd801b2c69bfbfa116e46313126cf9" src="https://github.com/user-attachments/assets/7ec343d0-7756-49fa-af08-7b5575cd47ba" />

<img width="1920" height="900" alt="da0104af1f82bc3aed97700baeca0bf9" src="https://github.com/user-attachments/assets/254e5adf-dd40-41c8-ba66-a8f705240bb1" />

导入hcg_nodes.csv和hcg_edges.csv数据。

<img width="1920" height="900" alt="8aab9fd8533d3d3ee120dc2f829d4f88" src="https://github.com/user-attachments/assets/007aa25e-54c0-41a4-a4ea-cf4f06cfdb71" />

<img width="1920" height="900" alt="b9deb8cc707c945bbd36809c27f0eea6" src="https://github.com/user-attachments/assets/a3a44aff-ce37-436d-9584-6b71fa6b510f" />

<img width="1920" height="900" alt="e0064d70fd6cf9fa03c8ed8da0b17223" src="https://github.com/user-attachments/assets/1fff0e63-0f6d-40f1-8d81-d2571bf65a90" />

<img width="1920" height="900" alt="4b2111ef4f0089415ae9f8477496c23a" src="https://github.com/user-attachments/assets/116a3d7d-1e02-4ccc-a0f7-9f2dc0cea978" />

导入完成后在图分析处执行查询验证：MATCH (n) - [r] - () RETURN n, r LIMIT 100

<img width="1920" height="900" alt="978f3d859db303d7dce1fd547671f996" src="https://github.com/user-attachments/assets/0e3e02ab-8132-4c29-a0f8-2da2773f7d7d" />

<img width="1920" height="900" alt="d4aed658ab5b575f292ffa05e3be17cd" src="https://github.com/user-attachments/assets/6840f57d-2da2-4e7f-8b91-5b1c038f85b2" />

3.点嵌入、特征融合（通过文字、代码、截图描述步骤）

导入edge2vec算法。

<img width="1920" height="900" alt="65bd2b86a67dcf5b9f259629d3bd76c8" src="https://github.com/user-attachments/assets/19d46e1c-a670-420b-a0d8-8eabef5bc1a4" />

<img width="1920" height="900" alt="772c6614a89576e0a9bc2dd194b54d7b" src="https://github.com/user-attachments/assets/f47ed04e-98b5-4f26-a27a-8c23d16d5660" />

获取存储过程的执行结果。

<img width="1920" height="900" alt="b10c8c7870c570033b0588b9d34f8e1d" src="https://github.com/user-attachments/assets/b9d7f988-def5-4693-97dc-6b8ad79345bd" />

用GET方法导出执行结果。

<img width="1539" height="766" alt="721417a99e6ec10013042416847c04f5" src="https://github.com/user-attachments/assets/b305ab65-2207-4468-b9eb-d4024b91e77d" />

<img width="790" height="136" alt="b3e79b384806767c5100d68f3afb3866" src="https://github.com/user-attachments/assets/63d29c9d-9337-4eae-93e8-45941171a21f" />

<img width="1423" height="739" alt="c14053fca17540ad2cb8f2899c5ad21b" src="https://github.com/user-attachments/assets/f312e5cd-43f7-4195-8118-a5a3136ba60c" />

4.KNN分类器预测并显示评价指标

<img width="1535" height="769" alt="52eb63713eb767765cf5d8c141ce868d" src="https://github.com/user-attachments/assets/07efb5f8-c9a1-47a1-a380-570767a946dc" />

