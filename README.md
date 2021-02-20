# 尝试使用数据流体系结构；  
## 具体实现如下：
+ 基本思路：  
&emsp;&emsp;使用一个结构体数组存放站点信息，包括站点编号，站点名称，相邻的站点，包含于的线路。下标控制站点编号
使用一个结构体数组存放线路信息，包括线路编号，包含站点信息。下标控制线路编号。
这两个结构体全部直接初始化数据。
使用一个结构体存放站点之间的连接关系，包含站点数量，一个关系二维数组，其初始化用到站点信息结构体中
的相邻站点编号。具体做法为：开一个二维数组【i】【j】，i变量循环所有节点，j遍历所有节点，再遍历相邻站
点数组，如果存在j，赋值1，否则赋值INT_MAX。
---
+ 拥有条件：  
&emsp;&emsp;![公交][公交地图]  
&emsp;&emsp;![线路][线路地图]  
---
+ 需求实现：      
&emsp;&emsp;寻找最短路径：最短路径：用Dijkstra算法实现（1）  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;最短路径中找到最少换乘（2）

&emsp;&emsp;显示不止一条最短路径需要对Dijkstra算法进行改进。  

&emsp;&emsp;1. 如何存储多条路径？？？  
&emsp;&emsp;升级了path数组为二维数组，存储每个站点的前缀站点。定义一个num一维数组，存储每个站的前缀
站点数量。
	每遇到一个分支，ansnu++，now随补全新的分支前缀数组进入完整的站点加入。使用bufnow继承
now，随原ansnum进入站点加入。    

&emsp;&emsp;2. 找出经历的线路数量：初始点a，下一站b，经历的站点ans=1。找到共同的路线rodeone。a=b;b=b->next;遍历b站点包含线路，查看是否存在rodeone,存在则ans不变。否则ans++；
		选取ans最少的那一条最短路径作为答案。



用户输入起点站、目标站。系统显示最短路径。
1
[公交地图]:公交地图.png "公交地图"
[线路地图]:线路地图.png "线路地图"


