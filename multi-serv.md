# 多服务规划

## 旧--单体服务：
1、以KUSER为中心，如果有配合的服务。在KUSER中，配置服务地址。
    比如文件服务、文件搜索、消息、SAP等。

## 新--多独立服务：
![](./media/multi-serv.png)

1、把前端、后端分来看，会比较清晰。虚线把Nginx、壳系统、仓储系统拆分为虚拟的前后端。
2、多个服务：会产生多种互相依赖，不能在每个服务中，配置依赖的服务。
3、在Nginx中：统一反代各个服务的API接口。这样每个服务不需要配置依赖的服务，可以直接调用接口。
4、接口路径唯一：各个独立服务，有自己独立的路径前缀，全局不冲突。

## 要求
后面新加独立服务，统一按新方式增加。