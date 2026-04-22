1.成功启动TuGraph平台

创建TuGraph服务，配置服务实例信息的参数列表。
<img width="1910" height="925" alt="cc6a6f6c6acb64fa6307f70b45592d58" src="https://github.com/user-attachments/assets/1b9cbafa-82dc-4dbb-b6f8-8339346b5ae3" />

勾选“权限确认”和“服务条款”中的复选框。
<img width="1910" height="925" alt="febbb0e41e0d5e6ada63787eecd72d54" src="https://github.com/user-attachments/assets/0a627afc-8ecc-454f-937f-7cf2617fe527" />

部署完成后，页面上可以看到对应的服务实例。
<img width="1910" height="925" alt="20309e99a32eb65b68da6541b9bd2bc2" src="https://github.com/user-attachments/assets/82b8cb36-9dc2-44f7-8f3b-f67d22b4809d" />

点击该服务实例访问TuGraph。进入到对应的服务实例后，可以在页面上获取到web、rpc、ssh、bolt共4种使用方式，并且页面上展示了admin用户的密码，其中bolt字段和密码在登陆时需要用到。
<img width="1910" height="925" alt="2a7988245d34a6f8c00b6b179b201111" src="https://github.com/user-attachments/assets/a6aa9553-69d3-4250-9631-5a69417dea2c" />

点击web的链接，即可跳转访问已经部署好的TuGraph Web。在TuGraph Web的登录页面上，输入bolt字段、默认用户名admin和页面上展示的admin用户的密码进行登录。
<img width="1910" height="925" alt="fd46289a8d9028781cb3d2c75a75a1d3" src="https://github.com/user-attachments/assets/2cec5948-e728-45d6-85b2-99a98aafe97d" />

登录成功。
<img width="1910" height="925" alt="812b0326d738d195cedddff6b3b52df6" src="https://github.com/user-attachments/assets/11b5eeb7-2466-424f-a16c-64b9ea77d4de" />

2.使用Bolt协议导入/导出数据

方法一：直接导入数据文件，但是需要提前描述schema。

新建空模板。
<img width="1910" height="925" alt="dddb206cfeb87f4f1316e485deba8e01" src="https://github.com/user-attachments/assets/64bfbd61-184a-46c4-a23a-49a7ae0fe210" />

<img width="1910" height="925" alt="abd3bc2a2a249147b9579e1537d67620" src="https://github.com/user-attachments/assets/596fcf24-12fd-4e59-955d-db7309c785fe" />

创建成功。
<img width="1910" height="925" alt="6eb22c69d2eafaf464ade98d2d390c99" src="https://github.com/user-attachments/assets/108a4958-4ac9-4843-9d1b-2fc8b49bcc31" />

添加点类型movie，填写属性列表。
<img width="1910" height="925" alt="7ea60fd484cc6d19bfb5c8e7e82b8795" src="https://github.com/user-attachments/assets/7bd06d55-5f23-4d43-a791-105aafa45e5e" />

添加成功。
<img width="1910" height="925" alt="b9df5ce55d46e7b158c2a1b877d5335b" src="https://github.com/user-attachments/assets/fb4c6c6e-fbe3-437c-bb61-ef5524de6a5e" />

添加点类型person，填写属性列表。
<img width="1910" height="925" alt="06762e2a261a7e5037c25493da284a87" src="https://github.com/user-attachments/assets/0dcebe78-34f8-4ce3-bb20-3574bff0ac67" />

添加成功。
<img width="1910" height="925" alt="6eac96574a14a6f226f180a556830e12" src="https://github.com/user-attachments/assets/c1a924ed-908a-42f3-84ad-9d9b299f7efd" />

添加边类型produce，填写映射关系（起点->终点）。
<img width="1910" height="925" alt="03e001cba46cccc07300e6e0def974b9" src="https://github.com/user-attachments/assets/3e38b318-6b72-45e6-a988-50843260832a" />

添加成功。
<img width="1910" height="925" alt="43e247b40434c53c590e1b2c82ca4040" src="https://github.com/user-attachments/assets/46bdd805-6540-4fe1-93be-8c652597d5e2" />

分别导入数据文件。
<img width="1909" height="926" alt="7a897a91eda541ad6b13bbd46f79d1d3" src="https://github.com/user-attachments/assets/af328100-771f-43e2-b080-03bb72e26466" />

选择movie标签及相应字段。
<img width="1910" height="925" alt="5603e69eaa8331d3e3ec95500de80c84" src="https://github.com/user-attachments/assets/ec114204-d14a-4065-8133-5f2ea47770d5" />

导入成功。
<img width="1910" height="925" alt="c0ea43165678179096f022f0d0fbc298" src="https://github.com/user-attachments/assets/25c41819-05ba-467c-8541-9526a15f606f" />

选择person标签及相应字段。
<img width="1910" height="925" alt="4b87612d86917b6d2d85ce1fb835a5ca" src="https://github.com/user-attachments/assets/e4b12ef8-ae32-4481-8107-d35b9f0d38ba" />

导入成功。
<img width="1910" height="925" alt="f5892456d2f085e124aa383920588386" src="https://github.com/user-attachments/assets/bcfd38ef-8b47-4051-a3eb-39cb7478bb9b" />

选择produce标签及映射关系（起点->终点）。
<img width="1910" height="925" alt="408630c2e6f7cb175a3fe17f39d77b9b" src="https://github.com/user-attachments/assets/317722e6-894c-4dd0-8395-bb34a4ae73c1" />

导入成功。
<img width="1910" height="925" alt="4c91d9f6edffc951820db4cec5b1a4b3" src="https://github.com/user-attachments/assets/5a7d60b2-7a50-437d-a87c-68af1557f3c0" />

构建Cypher查询语句并执行（点边视图+表格文本）。
<img width="1910" height="925" alt="09f776850dc973b0aa5330b76e439b44" src="https://github.com/user-attachments/assets/98c7570a-f211-4d60-939d-869cca689df1" />

<img width="1910" height="925" alt="e9d0ad7924dfa1d668d1661e1a394571" src="https://github.com/user-attachments/assets/a82cda42-193d-4664-bc8b-79e9cb3764b6" />

图分析。
<img width="1910" height="925" alt="33d2f70021b8cdfb0b2a4ef029d75d89" src="https://github.com/user-attachments/assets/5d714219-4f84-40af-80e7-55c81b209d66" />

方法二：使用Bolt协议+Python文件导入数据。

新建空模板gzy。
<img width="1910" height="925" alt="6cd687790d518042d7d015e66190001a" src="https://github.com/user-attachments/assets/2d1fb37a-f3eb-4094-bbee-948e0b6251e2" />

安装neo4j库。
<img width="1221" height="639" alt="7a9429aa2443458d0c9ca4cfb636b9de" src="https://github.com/user-attachments/assets/3076e398-19a6-4b27-90ac-218bb358a5de" />

先注释掉删除数据部分，仅执行插入数据。
<img width="1365" height="691" alt="c69fc8f669c6b8ddf47710d69c2a8236" src="https://github.com/user-attachments/assets/16ef89dd-00d8-4fab-8532-f0822053b835" />

插入成功。
<img width="1910" height="925" alt="0e9b88f41425037376f8b398ad14535a" src="https://github.com/user-attachments/assets/19ac927b-4654-4de3-b1f1-ffb0d14415ad" />

<img width="1910" height="925" alt="b5bb7ed4a017bf5f7c521942c0cf89b0" src="https://github.com/user-attachments/assets/b9c9fc91-4b6b-477a-8c25-c0a8994c994e" />

再注释掉插入数据部分，仅执行删除数据。
<img width="1379" height="690" alt="5178cab291ef180f05ca22ca079b28fe" src="https://github.com/user-attachments/assets/4c6a1e19-ab28-420c-a8e1-45c4d092e978" />

删除成功。
<img width="1910" height="925" alt="23bcd750f40cdbb091398a224e53d3cc" src="https://github.com/user-attachments/assets/40007ef2-4822-482f-b021-75e463097b95" />

3.跑通存储过程代码示例

新建存储过程。
<img width="1910" height="925" alt="66393a83f16bc090ac4ed2a10ced406b" src="https://github.com/user-attachments/assets/22e6a5dd-7732-4e4e-9c81-52182b82590f" />

新建失败，根据报错信息解决了以下问题：

（1）缺少参数：打开远程终端，进入容器，添加配置参数"enable_plugin":true，重启tugraph服务。
<img width="1910" height="465" alt="db91cbdc5bb6587c4e43ccdcd5af2e61" src="https://github.com/user-attachments/assets/9df82da5-cefb-48e0-a0d8-a0c3544aa1cf" />

<img width="1910" height="925" alt="65e52f85285a3475b9fd4456cc51c0ce" src="https://github.com/user-attachments/assets/a6efbb17-be2d-40be-8d53-65d6bdfb0f91" />

（2）重启docker后断连：如果browser显示断开连接的话，在宿主机上用sudo docker exec -it tugraph_demo bash进到镜像里面再用lgraph_server -d restart命令重启TuGraph 服务。
<img width="925" height="160" alt="49bc5c80d0f69b5562ebb7fdf7d506b1" src="https://github.com/user-attachments/assets/17983106-89b7-46ad-bb62-6103291ec9fe" />

（3）缺少pip命令行工具：yum install -y python3-pip
<img width="724" height="800" alt="0cd2f9092cd56c229a725c2367377f26" src="https://github.com/user-attachments/assets/318da075-a093-4dfc-b844-3b3c12753fc7" />

（4）缺少cython命令行工具：pip3 install cython
<img width="721" height="790" alt="6c83ff84d7140be0b4699ea503a84810" src="https://github.com/user-attachments/assets/5e484b66-248c-4cef-873e-e990344b8ff9" />

（5）缺少C++编译器：yum install -y gcc-c++ python3-devel
<img width="714" height="686" alt="a3db57400a8804dd9ed441a5bb3d8d5d" src="https://github.com/user-attachments/assets/4bfa3001-f454-4c59-9490-dd0d73a6232c" />

（6）C++编译器版本不适配。

换yum镜像源：

#备份原有源

mv /etc/yum.repos.d /etc/yum.repos.d.bak

mkdir -p /etc/yum.repos.d

#下载阿里云的CentOS 7 vault源配置

curl -o /etc/yum.repos.d/Cent0S-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo

#清理缓存

yum clean all

yum makecache

#检查镜像是否替换成功

yum repolist

<img width="1328" height="265" alt="b4f7588fc1e4f45a0074c432419ae670" src="https://github.com/user-attachments/assets/d48ece18-fc2b-49c9-bc82-e07fc0d18558" />

安装SCL源和gcc9开发套件：

yum install -y centos-release-scl

yum install -y devtoolset-9-gcc-c++ python3-devel

<img width="925" height="190" alt="394f5f2cde3fe7cc1831d735f293911f" src="https://github.com/user-attachments/assets/b33cd605-4998-4ace-904c-331ddae7d0f7" />

如果找不到gcc9开发套件，则需要检查SCL仓库文件。如果这些文件不存在或损坏，使用以下命令重新创建SCL仓库文件：

#重建 /etc/yum.repos.d/CentOS-SCLo-scl.repo

cat <<EOF > /etc/yum.repos.d/CentOS-SCLo-scl.repo

[centos-sclo-sclo]

name=Cent0S-7 - SCLo sclo

baseurl=https://mirrors.aliyun.com/centos/7/sclo/x86_64/sclo/

enabled=1

gpgcheck=0

EOF

#重建 /etc/yum.repos.d/CentOS-SCLo-scl-rh.repo

cat <<EOF > /etc/yum.repos.d/Cent0S-SCLo-scl-rh.repo

[centos-sclo-rh]

name=Cent0S-7 - SCLo rh

baseurl=https://mirrors.aliyun.com/centos/7/sclo/x86_64/rh/

enabled=1

gpgcheck=0

EOF

#清理缓存，重新生成元数据，并确保SCL仓库生效

yum clean all

yum makecache

yum repolist | grep scl

在SCL仓库中看到有效条目，如centos-sclo-sclo和centos-sclo-rh。确保SCL仓库已启用，可以尝试重新安装开发工具集gcc9。
<img width="1336" height="779" alt="880b8d85965be4e52baaae659bb8c211" src="https://github.com/user-attachments/assets/16f2cbbe-e92d-4fae-bf4b-202ef7a763ef" />

将新版gcc软链接到/usr/local/bin，验证版本：

ln - sf /opt/rh/devtoolset-9/root/usr/bin/g++ /usr/local/bin/g++

ln - sf /opt/rh/devtoolset-9/root/usr/bin/gcc /usr/local/bin/gcc

g++ --version

gcc --version

<img width="931" height="280" alt="5d8fac0ee74199c8056e3d8beb49eb39" src="https://github.com/user-attachments/assets/ac9ad40b-6393-402a-bb95-2f69b1cdf245" />

（7）找不到liblgraph.so：查找liblgraph.so路径，添加到编译器的默认搜索路径，创建软链接到标准库目录，验证是否可以被链接器识别。
<img width="1060" height="229" alt="806d3364b9bcd06e9bd0917f6087a43f" src="https://github.com/user-attachments/assets/dbbd584d-be74-4e44-bb03-afe3ae94e25e" />

（8）找不到liblgraph_python_api：查找liblgraph_python_api路径，将路径添加到系统级Python路径。
<img width="790" height="49" alt="95cbfabd0d993388834d3f7f6246b3db" src="https://github.com/user-attachments/assets/db164d21-abfd-46e4-9722-8e8f1a54a772" />

#创建.pth文件(这是系统级配置，所有Python进程都会加载)

echo "/usr/local/lib64/lgraph" > /usr/lib64/python3.6/site-packages/lgraph.pth

#验证

python3 -c "import site; print(site.getsitepackages())"

ls -la /usr/lib64/python3.6/site-packages/lgraph.pth

env -i PATH=$PATH python3 -c "import liblgraph_python_api; print('=')"

<img width="1330" height="160" alt="cedee22a7a1ba00aebc25ab272722d20" src="https://github.com/user-attachments/assets/388c8bae-6233-46d5-9235-91cc0c1234c9" />


报错问题解决完毕，新增成功！
<img width="1910" height="925" alt="7034e3f38be48f8ad1d70b7d7c4eeb18" src="https://github.com/user-attachments/assets/210b141b-7547-48ef-b1dc-81644c875e78" />

查看源代码。
<img width="1910" height="925" alt="4ae5cad9094d882cff7cd93dd4f81486" src="https://github.com/user-attachments/assets/5915da66-ce5c-4bf4-89da-22c5da0872ad" />

执行代码，结果如图。
<img width="1920" height="1030" alt="faaa6a2d4189204f1a454b14eb26f27c" src="https://github.com/user-attachments/assets/fb2c34ea-9e74-47cc-a8f0-6403624a9532" />

<img width="1910" height="925" alt="3de6481b7ed1e83b6b0485e0b243ff6a" src="https://github.com/user-attachments/assets/d437be0c-b75d-4736-a3e4-0fa4db6311a6" />








