# NEZHA接口文档 v1.0.0

## 目录

- [1 规范说明](#1-规范说明)
- &emsp;[1.1 通信协议](#11-通信协议)
- &emsp;[1.2 请求方法](#12-请求方法)
- &emsp;[1.3 字符编码](#13-字符编码)
- &emsp;[1.4 格式说明](#14-格式说明)
- &emsp;[1.5 响应报文结构](#15-响应报文结构)
- &emsp;&emsp;[1.5.1 结构说明](#151-结构说明)
- &emsp;&emsp;[1.5.2 响应报文示例](#152-响应报文示例)
- [2. 接口定义](#2-接口定义)
- &emsp;[2.1 设备管理](#21-设备管理)
- &emsp;&emsp;[2.1.1 节点管理](#211-节点管理)
- &emsp;&emsp;&emsp;[2.1.1.1 节点列表查询](#2111-节点列表查询)
- &emsp;&emsp;&emsp;[2.1.1.2 节点详情查询](#2112-节点详情查询)
- &emsp;&emsp;&emsp;[2.1.1.3 节点新增](#2113-节点新增)
- &emsp;&emsp;&emsp;[2.1.1.4 节点修改](#2114-节点修改)
- &emsp;&emsp;&emsp;[2.1.1.5 节点状态变更](#2115-节点状态变更)
- &emsp;&emsp;&emsp;[2.1.1.6 查询可用机柜](#2116-查询可用机柜)
- &emsp;&emsp;&emsp;[2.1.1.7 IP校验](#2117-ip校验)
- &emsp;&emsp;&emsp;[2.1.1.8 节点名称校验](#2118-节点名称校验)
- &emsp;&emsp;[2.1.2 节点组管理](#212-节点组管理)
- &emsp;&emsp;&emsp;[2.1.2.1 节点组列表查询](#2121-节点组列表查询)
- &emsp;&emsp;&emsp;[2.1.2.2 节点组详情查询](#2122-节点组详情查询)
- &emsp;&emsp;&emsp;[2.1.2.3 节点组下的节点列表查询](#2123-节点组下的节点列表查询)
- &emsp;&emsp;&emsp;[2.1.2.4 节点组新增](#2124-节点组新增)
- &emsp;&emsp;&emsp;[2.1.2.5 节点组修改](#2125-节点组修改)
- &emsp;&emsp;&emsp;[2.1.2.6 节点组删除](#2126-节点组删除)
- &emsp;&emsp;&emsp;[2.1.2.7 可分配节点查询](#2127-可分配节点查询)
- &emsp;&emsp;&emsp;[2.1.2.8 节点组分配节点](#2128-节点组分配节点)
- &emsp;&emsp;&emsp;[2.1.2.9 节点组移除节点](#2129-节点组移除节点)
- &emsp;&emsp;&emsp;[2.1.2.10 节点组名称校验](#21210-节点组名称校验)
- &emsp;&emsp;[2.1.3 机房管理](#213-机房管理)
- &emsp;&emsp;&emsp;[2.1.3.1 机房列表查询](#2131-机房列表查询)
- &emsp;&emsp;&emsp;[2.1.3.2 机房详情查询](#2132-机房详情查询)
- &emsp;&emsp;&emsp;[2.1.3.3 机房新增](#2133-机房新增)
- &emsp;&emsp;&emsp;[2.1.3.4 机房修改](#2134-机房修改)
- &emsp;&emsp;&emsp;[2.1.3.5 机房删除](#2135-机房删除)
- &emsp;&emsp;&emsp;[2.1.3.6 机房名称校验](#2136-机房名称校验)
- &emsp;&emsp;&emsp;[2.1.3.7 机房修改时行列校验](#2137-机房修改时行列校验)
- &emsp;&emsp;&emsp;[2.1.3.8 机房内机柜列表查询](#2138-机房内机柜列表查询)
- &emsp;&emsp;[2.1.4 机柜管理](#214-机柜管理)
- &emsp;&emsp;&emsp;[2.1.4.1 机柜列表查询](#2141-机柜列表查询)
- &emsp;&emsp;&emsp;[2.1.4.2 机柜详情查询](#2142-机柜详情查询)
- &emsp;&emsp;&emsp;[2.1.4.3 机柜新增](#2143-机柜新增)
- &emsp;&emsp;&emsp;[2.1.4.4 机柜修改](#2144-机柜修改)
- &emsp;&emsp;&emsp;[2.1.4.5 机柜删除](#2145-机柜删除)
- &emsp;&emsp;&emsp;[2.1.4.6 机柜名称校验](#2146-机柜名称校验)
- &emsp;&emsp;&emsp;[2.1.4.7 校验U位数量是否可用](#2147-校验u位数量是否可用)
- &emsp;&emsp;&emsp;[2.1.4.8 查询机柜可选的机房及行号列号](#2148-查询机柜可选的机房及行号列号)
- &emsp;[2.2 权限](#22-权限)
- &emsp;&emsp;[2.2.1 业务系统](#221-业务系统)
- &emsp;&emsp;&emsp;[2.2.1.1 业务系统列表查询](#2211-业务系统列表查询)
- &emsp;&emsp;&emsp;[2.2.1.2 业务系统详情查询](#2212-业务系统详情查询)
- &emsp;&emsp;&emsp;[2.2.1.3 业务系统新增](#2213-业务系统新增)
- &emsp;&emsp;&emsp;[2.2.1.4 业务系统修改](#2214-业务系统修改)
- &emsp;&emsp;&emsp;[2.2.1.5 业务系统删除](#2215-业务系统删除)
- &emsp;&emsp;&emsp;[2.2.1.6 查询业务系统下的节点](#2216-查询业务系统下的节点)
- &emsp;&emsp;&emsp;[2.2.1.7 业务系统分配节点](#2217-业务系统分配节点)
- &emsp;&emsp;&emsp;[2.2.1.8 业务系统移除节点](#2218-业务系统移除节点)
- &emsp;&emsp;&emsp;[2.2.1.9 业务系统名称校验](#2219-业务系统名称校验)
- &emsp;&emsp;&emsp;[2.2.1.10 查询用户所属的业务系统列表](#22110-查询用户所属的业务系统列表)
- &emsp;&emsp;&emsp;[2.2.1.11 切换业务系统](#22111-切换业务系统)
- &emsp;&emsp;&emsp;[2.2.1.12 用户组列表](#22112-用户组列表)
- &emsp;&emsp;[2.2.2 用户组](#222-用户组)
- &emsp;&emsp;&emsp;[2.2.2.1 用户组列表查询](#2221-用户组列表查询)
- &emsp;&emsp;&emsp;[2.2.2.2 用户组详情查询](#2222-用户组详情查询)
- &emsp;&emsp;&emsp;[2.2.2.3 用户组新增](#2223-用户组新增)
- &emsp;&emsp;&emsp;[2.2.2.4 用户组修改](#2224-用户组修改)
- &emsp;&emsp;&emsp;[2.2.2.5 用户组删除](#2225-用户组删除)
- &emsp;&emsp;&emsp;[2.2.2.6 业务系统列表](#2226-业务系统列表)
- &emsp;&emsp;&emsp;[2.2.2.7 用户组名称校验](#2227-用户组名称校验)
- &emsp;[2.3 监测配置](#23-监测配置)
- &emsp;&emsp;[2.3.1 监测类别](#231-监测类别)
- &emsp;&emsp;&emsp;[2.3.1.1 监测类别列表查询](#2311-监测类别列表查询)
- &emsp;&emsp;&emsp;[2.3.1.2 监测类别详情查询](#2312-监测类别详情查询)
- &emsp;&emsp;&emsp;[2.3.1.3 监测类别新增](#2313-监测类别新增)
- &emsp;&emsp;&emsp;[2.3.1.4 监测类别修改](#2314-监测类别修改)
- &emsp;&emsp;&emsp;[2.3.1.5 监测类别删除](#2315-监测类别删除)
- &emsp;&emsp;&emsp;[2.3.1.6 元数据字典查询](#2316-元数据字典查询)
- &emsp;&emsp;&emsp;[2.3.1.7 元数据字典新增](#2317-元数据字典新增询)
- &emsp;&emsp;&emsp;[2.3.1.8 元数据字典修改](#2318-元数据字典修改)
- &emsp;&emsp;&emsp;[2.3.1.9 元数据字典删除](#2319-元数据字典删除)
- &emsp;&emsp;&emsp;[2.3.1.10 监测类别名称校验](#23110-监测类别名称校验)
- &emsp;&emsp;&emsp;[2.3.1.11 元数据字典type校验](#23111-元数据字典type校验)
- &emsp;&emsp;[2.3.2 监测设置](#232-监测设置)
- &emsp;&emsp;&emsp;[2.3.2.1 监测设置列表查询](#2321-监测设置列表查询)
- &emsp;&emsp;&emsp;[2.3.2.2 监测设置详情查询](#2322-监测设置详情查询)
- &emsp;&emsp;&emsp;[2.3.2.3 监测设置新增](#2323-监测设置新增)
- &emsp;&emsp;&emsp;[2.3.2.4 监测设置修改](#2324-监测设置修改)
- &emsp;&emsp;&emsp;[2.3.2.5 监测设置删除](#2325-监测设置删除)
- &emsp;&emsp;&emsp;[2.3.2.6 监测设置名称校验](#2326-监测设置名称校验)
- &emsp;&emsp;[2.3.3 告警设置](#233-告警设置)
- &emsp;&emsp;&emsp;[2.3.3.1 告警设置列表查询](#2331-告警设置列表查询)
- &emsp;&emsp;&emsp;[2.3.3.2 告警设置详情查询](#2332-告警设置详情查询)
- &emsp;&emsp;&emsp;[2.3.3.3 告警设置新增](#2333-告警设置新增)
- &emsp;&emsp;&emsp;[2.3.3.4 告警设置修改](#2334-告警设置修改)
- &emsp;&emsp;&emsp;[2.3.3.5 告警设置删除](#2335-告警设置删除)
- &emsp;&emsp;&emsp;[2.3.3.6 告警名称校验](#2336-告警名称校验)
- &emsp;[2.4 任务](#24-任务)
- &emsp;&emsp;[2.4.1 任务](#241-任务)
- &emsp;&emsp;&emsp;[2.4.1.1 任务列表查询](#2411-任务列表查询)
- &emsp;&emsp;&emsp;[2.4.1.2 任务详情查询](#2412-任务详情查询)
- &emsp;&emsp;&emsp;[2.4.1.3 任务新增](#2413-任务新增)
- &emsp;&emsp;&emsp;[2.4.1.4 任务修改](#2414-任务修改)
- &emsp;&emsp;&emsp;[2.4.1.5 周期任务停用/启用](#2415-周期任务停用启用)
- &emsp;&emsp;&emsp;[2.4.1.6 新增逆向任务](#2416-新增逆向任务)
- &emsp;&emsp;&emsp;[2.4.1.7 结果查看](#2417-结果查看)
- &emsp;[2.5 拓扑图](#25-拓扑图)
- &emsp;&emsp;[2.5.1 拓扑图配置](#251-拓扑图配置)
- &emsp;&emsp;&emsp;[2.5.1.1 拓扑图列表查询](#2511-拓扑图列表查询)
- &emsp;&emsp;&emsp;[2.5.1.2 拓扑图详情查询](#2512-拓扑图详情查询)
- &emsp;&emsp;&emsp;[2.5.1.3 拓扑图节点新增](#2513-拓扑图节点新增)
- &emsp;&emsp;&emsp;[2.5.1.4 拓扑图节点修改](#2513-拓扑图节点修改)
- &emsp;&emsp;&emsp;[2.5.1.5 拓扑图节点删除](#2514-拓扑图节点删除)
- &emsp;&emsp;&emsp;[2.5.1.6 拓扑图连线新增](#2515-拓扑图连线新增)
- &emsp;&emsp;&emsp;[2.5.1.7 拓扑图连线修改](#2516-拓扑图连线修改)
- &emsp;&emsp;&emsp;[2.5.1.8 拓扑图连线删除](#2517-拓扑图连线删除)
- &emsp;&emsp;&emsp;[2.5.1.9 拓扑节点静态图片列表查询](#2518-拓扑节点静态图片列表查询)
- &emsp;[2.6 仪表盘](#26-仪表盘)
- &emsp;&emsp;[2.6.1 仪表盘管理](#261-仪表盘管理)
- &emsp;&emsp;&emsp;[2.6.1.1 仪表盘列表查询](#2611-仪表盘列表查询)
- &emsp;&emsp;&emsp;[2.6.1.2 仪表盘新增](#2612-仪表盘新增)
- &emsp;&emsp;&emsp;[2.6.1.3 仪表盘修改](#2613-仪表盘修改)
- &emsp;&emsp;&emsp;[2.6.1.4 仪表盘删除](#2614-仪表盘删除)
- &emsp;&emsp;&emsp;[2.6.1.5 仪表盘位置及宽高修改](#2615-仪表盘位置及宽高修改)
- [3 附录](#3-附录)
- &emsp;[A 响应码说明](#a-响应码说明)
- &emsp;[B 仪表盘data格式说明](#b-仪表盘data格式说明)
- &emsp;[C 任务param格式说明](#c-任务param格式说明)



## 1 规范说明

### 1.1 通信协议

HTTP协议

### 1.2 请求方法

HttpRequest Method	|SQL	|实现方式	|说明
---- | ---- | -----|----
GET					|SELECT	            |GET请求	|服务器获取资源(一项或多项)
POST				|INSERT	            |POST请求	|服务器新建一个资源，返回操作结果
PUT					|UPDATE         	|PUT 请求   |服务器更新资源（向客户端提供改变后的完整资源）
PATCH				|UPDATE	            |PATCH请求  |服务器更新资源（向客户端提供改变的属性）
DELETE				|UPDATE/DELETE	    |DELETE请求 |从服务器删除资源，返回空文档

### 1.3 字符编码
HTTP通讯均采用UTF-8字符集编码格式。

### 1.4 格式说明
元素出现要求说明：

符号				|说明
:----:			|:---
R				|报文中该元素必须出现（Required）
O				|报文中该元素可选出现（Optional）
C				|报文中该元素在一定条件下出现（Conditional）

### 1.5 响应报文结构

#### 1.5.1 结构说明
所有接口响应均采用JSON格式，如无特殊说明，每次请求的返回值中，都包含下列字段：

参数名称						|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，代码定义请见“附录A 响应吗说明”
msg							|string		|R			|响应描述
data						|object		|R			|每个接口特有的参数，详见每个接口定义
&emsp;totalCount			|int		|C			|总结果数，批量分页查询时需要
&emsp;list					|Object[]	|C			|当前页查询结果，批量查询时需要


#### 1.5.2 响应报文示例

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "Channel": "A10086",
            "Type": 7004
        }]
    }
}
```


## 2. 接口定义

### 2.1 设备管理

#### 2.1.1 节点管理

##### 2.1.1.1 节点列表查询

- **接口说明：** 节点列表查询
- **接口地址：** /node/list
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
ip       			|String 		|O			|查询ip
state 		    	|String			|O			|设备状态，1：在线，2：下线
type      			|String 		|O			|设备类型 数字1|2, 1：server,2：net
tag      			|Integer 		|O			|设备标签
cabinetId      		|Integer 		|O			|机柜
roomId				|Integer		|O			|机房
groupId				|Integer		|C			|节点组ID
name				|String			|O			|名称

示例：

```
GET /node/list?limit=20&page=1&ip=192.168.1.1&state=1&tag=1&type=1&cabinetId=12&sidx=id&order=asc

```


###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;name			|String		|R			|&nbsp;
&emsp;&emsp;hostName		|String		|R			|主机名
&emsp;&emsp;ip				|String		|R			|ip
&emsp;&emsp;uuid			|Integer	|R			|全局唯一
&emsp;&emsp;type			|String		|R			|设备类型，返回国际化翻译后的“服务器”、“网元”
&emsp;&emsp;tag				|Integer 	|R			|设备标签id，与sys_dict的type:node-type关联
&emsp;&emsp;tagName			|String 	|R			|设备标签名称（翻译后）
&emsp;&emsp;userName		|String		|R			|snmpv3 用户名
&emsp;&emsp;password		|String		|R			|snmpv3 密码
&emsp;&emsp;state			|String		|R			|设备状态，1：在线，2：下线
&emsp;&emsp;roomName		|String 	|R			|机房名称
&emsp;&emsp;cabinetInfo		|Object 	|R			|机柜
&emsp;&emsp;&emsp;id		|Integer 	|R			|机柜ID
&emsp;&emsp;&emsp;name		|String 	|R			|机柜名称
&emsp;&emsp;uSize			|Integer	|R			|u位大小
&emsp;&emsp;cabinetStart	|Integer	|R			|机柜起始位置
&emsp;&emsp;snmpPort		|Integer	|R			|snmp默认端口号
&emsp;&emsp;snmpCommunity	|String		|R			|snmp团体字
&emsp;&emsp;remark			|String		|R			|备注

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "name": "node1",
            "hostName": "ysp-01",
            "ip": "192.168.10.1",
            "uuid": 1,
            "type": "服务器",
            "tag": 9,
            "tagName": "server9",
            "userName": "",
            "password": "",
            "state": "1",
            "roomName": "机房1",
            "cabinetInfo": {
                "id": 3,
                "name": "cab1"
            },
            "uSize": 1,
            "cabinetStart": 1,
            "snmpPort": 1,
            "snmpCommunity": "",
            "remark": ""
        }]
    }
}
```

##### 2.1.1.2 节点详情查询

- **接口说明：** 节点详情查询
- **接口地址：** /node/detail
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
uuid 				|Integer		|R			|唯一标识

示例：

```
GET /node/detail?uuid=5
```


###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|object		|R			|&nbsp;
&emsp;name					|String		|R			|
&emsp;hostName				|String		|R			|主机名
&emsp;ip					|String		|R			|ip
&emsp;uuid					|Integer	|R			|全局唯一
&emsp;type					|String		|R			|设备类型，返回国际化翻译后的“服务器”、“网元”
&emsp;tag					|Integer 	|R			|设备标签id，与sys_dict的type:node-type关联
&emsp;tagName				|String 	|R			|设备标签名称（翻译后）
&emsp;userName				|String		|R			|snmpv3 用户名
&emsp;password				|String		|R			|snmpv3 密码
&emsp;state					|String		|R			|设备状态，1：在线，2：下线
&emsp;roomName				|String 	|R			|机房名称
&emsp;cabinetInfo			|Object 	|R			|机柜
&emsp;&emsp;id				|Integer 	|R			|机柜ID
&emsp;&emsp;name			|String 	|R			|机柜名称
&emsp;uSize					|Integer	|R			|u位大小
&emsp;cabinetStart			|Integer	|R			|机柜起始位置
&emsp;snmpPort				|Integer	|R			|snmp默认端口号
&emsp;snmpCommunity			|String		|R			|snmp团体字
&emsp;remark				|String		|R			|备注
&emsp;systemInfo			|Object[]	|R			|所在业务系统
&emsp;&emsp;id      		|Integer 	|R			|业务系统id
&emsp;&emsp;name    		|String 	|R			|业务系统名称

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "name": "node1",
        "hostName": "ysp-01",
        "ip": "192.168.10.1",
        "uuid": 1,
        "type": "服务器",
        "tag": 9,
        "tagName": "server9",
        "userName": "",
        "password": "",
        "state": "1",
        "roomName": "机房1",
        "cabinetInfo": {
            "id": 3,
            "name": "cab1"
        },
        "uSize": 1,
        "cabinetStart": 1,
        "snmpPort": 1,
        "snmpCommunity": "",
        "remark": "",
        "systemInfo": [{
            "id": 1,
            "name": "业务系统1"
        }]
    }
}
```

##### 2.1.1.3 节点新增

- **接口说明：** 节点新增
- **接口地址：** /node/save
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
ip       			|String 		|R			|ip
type      			|String 		|R			|设备类型  1：server，2：net（传数字1或2）
tag      			|Integer 		|O			|设备标签id
cabinetId      		|Integer 		|O			|机柜
cabinetStart      	|Integer 		|O			|机柜起始位置
name				|String			|R			|名称
userName			|String			|O			|snmpv3 用户名
password			|String			|O			|snmpv3 密码
snmpPort			|Integer		|O			|snmp端口号
snmpCommunity		|String			|O			|snmp团体字
uSize				|Integer		|O			|U位大小
remark				|String			|O			|备注


示例：

```
{
    "name": "",
    "ip": "",
    "type": "2",
    "tag": 1,
    "userName": "snnnn",
    "password": "mpppp",
    "cabinetId": 1,
    "uSize": 1,
    "cabinetStart": 1,
    "snmpPort": 161,
    "snmpCommunity": "public",
    "remark": "en"
}
```


###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
成功
{
    "code": 200,
    "msg": "success"
}
失败
{
    "code": xxx,
    "msg": "机柜该位置无法使用"
}
```

##### 2.1.1.4 节点修改

- **接口说明：** 节点修改
- **接口地址：** /node/update
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
uuid       			|Integer 		|R			|唯一标识
ip       			|String 		|R			|查询ip
type      			|String 		|R			|设备类型  1：server，2：net（传数字1或2）
tag      			|Integer 		|O			|设备标签
cabinetId      		|Integer 		|O			|机柜
cabinetStart      	|Integer 		|O			|机柜起始位置
name				|String			|R			|名称
userName			|String			|O			|snmpv3 用户名
password			|String			|O			|snmpv3 密码
snmpPort			|Integer		|O			|snmp端口号
snmpCommunity		|String			|O			|snmp团体字
uSize				|Integer		|O			|U位大小
remark				|String			|O			|备注

示例：

```
{
    "uuid": 121,
    "name": "",
    "ip": "",
    "type": "1",
    "tag": 1,
    "userName": "snnnn",
    "password": "mpppp",
    "cabinetId": 1,
    "uSize": 1,
    "cabinetStart": 1,
    "snmpPort": 161,
    "snmpCommunity": "public",
    "remark": "enac"
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
成功
{
    "code": 200,
    "msg": "success"
}
失败
{
    "code": xxx,
    "msg": "机柜该位置无法使用"
}
```

##### 2.1.1.5 节点状态变更

- **接口说明：** 节点状态变更(上线/下线/删除)
- **接口地址：** /node/changeState
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
uuids       		|Integer[] 		|R			|唯一标识
state				|String			|R			|变更的状态，1：在线，2：下线，3：删除

示例：

```
{
    "uuids": [2,6],
    "state": "1"
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|String		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.1.1.6 查询可用机柜

- **接口说明：** 节点修改
- **接口地址：** /node/selectCab
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
uuid       			|Integer 		|O			|唯一标识，为空表示正在新增节点
uSize				|Integer		|R			|u位大小

示例：

```
GET /node/selectCab?uuid=5&uSize=2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;list					|Object		|R			|&nbsp;
&emsp;&emsp;roomId			|Integer	|R			|机房id
&emsp;&emsp;roomName		|String		|R			|机房名称
&emsp;&emsp;cabinets		|Object[]	|R			|机柜
&emsp;&emsp;&emsp;id		|Integer	|R			|机柜id
&emsp;&emsp;&emsp;name		|String		|R			|机柜名称
&emsp;&emsp;&emsp;starts	|Integer[]	|R			|机柜起始位置

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "list": [{
            "roomId": 2,
            "roomName": "room1",
            "cabinets": [{
                "id": 1,
                "name": "机柜1",
                "starts": [1,2,8,9,10]
            }]
        }]
    }
}
```

##### 2.1.1.7 IP校验

- **接口说明：** IP校验，分三种情况：1.校验不通过；2.校验通过；3.ip已在其他业务系统里存在，此时返回node实体，询问用户是否关联；
- **接口地址：** /node/ipCheck
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
uuid       			|Integer 		|O			|唯一标识，为空表示正在新增节点
ip					|String			|R			|IP

示例：

```
GET /node/ipCheck?uuid=5&ip=192.11.14.20
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|String		|R			|&nbsp;
data                        |Object     |O          |同2.1.1.2，nodeInfo详情

示例：

```
成功
{
	"code": 200,
    "msg": "success"
    "data": 节点详情
}
失败
{
	"code": xxx,
    "msg": "IP已被占用"
}
```

##### 2.1.1.8 节点名称校验

- **接口说明：** 节点名称校验
- **接口地址：** /node/nodeNameCheck
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
uuid       			|Integer 		|O			|唯一标识，为空表示正在新增节点
name				|String			|R			|节点名称

示例：

```
GET /node/nodeNameCheck?uuid=5&name=atc2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|String		|R			|&nbsp;

示例：

```
成功
{
	"code": 200,
    "msg": "success"
}
失败
{
	"code": xxx,
    "msg": "名称已被占用"
}
```


#### 2.1.2 节点组管理

##### 2.1.2.1 节点组列表查询

- **接口说明：** 节点组列表查询
- **接口地址：** /nodegroup/list
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	

示例：

```
GET /nodegroup/list
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;systemId		|Integer	|R			|业务系统id
&emsp;&emsp;systemName		|String		|R			|业务系统名称
&emsp;&emsp;nodegroups		|Object[]	|R			|接电阻
&emsp;&emsp;&emsp;id		|Integer	|R			|节点组id
&emsp;&emsp;&emsp;name		|String		|R			|节点组名称
&emsp;&emsp;&emsp;allowAss	|String		|R			|能否分配节点 0不能，1可以
&emsp;&emsp;&emsp;allowSub	|String		|R			|能否增加子节点组 0不能，1可以
&emsp;&emsp;&emsp;pid		|Integer	|R			|父ID，默认0

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "list": [{
            "systemId": 1,
            "systemName": "system1",
            "nodegroups": [
                {"id": 8, "name": "group1", "pid": 0, "allowAss": "0", "allowSub": "1"},
                {"id": 9, "name": "group1-1", "pid": 8, "allowAss": "0", "allowSub": "1"},
                {"id": 28, "name": "group1-1-9", "pid": 9, "allowAss": "1", "allowSub": "0"}
            ]
        }]
    }
}
```

##### 2.1.2.2 节点组详情查询

- **接口说明：** 节点组详情查询
- **接口地址：** /nodegroup/detail
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|节点组ID

示例：

```
GET /nodegroup/detail?id=3
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;id					|Integer	|R			|&nbsp;
&emsp;name					|String		|R			|节点组名称
&emsp;pid					|Integer	|R			|父ID，默认0
&emsp;pname					|String		|R			|父名称
&emsp;remark				|String		|R			|备注

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "id": 8,
        "name": "group1",
        "pid": 2,
        "pname": "group0",
        "remark": "呵呵"
    }
}
```

##### 2.1.2.3 节点组下的节点列表查询

- **接口说明：** 节点组下属节点列表查询，同 "2.1.1.1 节点列表查询"，请求参数"groupId"为必须参数

##### 2.1.2.4 节点组新增

- **接口说明：** 节点组新增
- **接口地址：** /nodegroup/save
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
name				|String			|R			|名称
systemId			|Integer		|O			|业务系统ID
pid					|Integer		|R			|父ID
remark				|String			|O			|备注

示例：

```
{
    "name": "节点组4",
    "systemId": 1,
    "pid": 1,
    "remark": "en"
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
失败
{
    "code": xxx,
    "msg": "原因"
}
```

##### 2.1.2.5 节点组修改

- **接口说明：** 节点组修改
- **接口地址：** /nodegroup/update
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id
name				|String			|R			|名称
remark				|String			|O			|备注

示例：

```
{
    "id": 35,
    "name": "节点组4",
    "remark": "enaccc"
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
失败
{
    "code": xxx,
    "msg": "原因"
}
```

##### 2.1.2.6 节点组删除

- **接口说明：** 节点组删除
- **接口地址：** /nodegroup/delete
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id

示例：

```
{
	"id": 35
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.1.2.7 可分配节点查询

- **接口说明：** 查询可以分配给指定节点组的节点
- **接口地址：** /nodegroup/assList
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
groupId				|Integer		|R			|节点组id
systemId			|Integer		|R			|业务系统id
ip					|String			|O			|ip查询条件,支持模糊查询

示例：

```
GET /nodegroup/assList?groupId=3&systemId=1&ip=192
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;name			|String		|R			|名称
&emsp;&emsp;hostName		|String		|R			|主机名
&emsp;&emsp;ip				|String		|R			|ip
&emsp;&emsp;uuid			|Integer	|R			|全局唯一
&emsp;&emsp;type			|String		|R			|设备类型，返回国际化翻译后的“服务器”、“网元”
&emsp;&emsp;tagName			|String 	|R			|设备标签名称，与sys_dict code关联，type:node-type

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "name": "node1",
            "hostName": "ysp-01",
            "ip": "192.168.10.1",
            "uuid": 1,
            "type": "服务器",
            "tagName": "server9"
        }]
    }
}
```

##### 2.1.2.8 节点组分配节点

- **接口说明：** 建立节点组--节点关系
- **接口地址：** /nodegroup/saveNodeRel
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|节点组id
uuids				|Integer[]		|R			|节点id

示例：

```
{
    "id": 2,
    "uuids": [3, 43]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.1.2.9 节点组移除节点

- **接口说明：** 解除节点组--节点关系
- **接口地址：** /nodegroup/deleteNodeRel
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|节点组id
uuids				|Integer[]		|R			|节点id

示例：

```
{
    "id": 2,
    "uuids": [3, 11]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.1.2.10 节点组名称校验

- **接口说明：** 节点组名称校验，同父节点下名称不能重复
- **接口地址：** /nodegroup/groupNameCheck
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id       			|Integer 		|O			|节点组ID，为空表示正在新增节点组
name				|String			|R			|名称
pid					|Integer		|R			|父节点组id

示例：

```
GET /nodegroup/groupNameCheck?pid=5&id=15&name=group2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
失败
{
    "code": xxx,
    "msg": "原因"
}
```


#### 2.1.3 机房管理

##### 2.1.3.1 机房列表查询

- **接口说明：** 机房列表查询
- **接口地址：** /room/list
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
name				|String			|O			|机房名称
area				|Integer		|O			|所属区域

示例：

```
GET /room/list?limit=10&page=2&name=room2&area=43
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;id				|Integer	|R			|主键
&emsp;&emsp;name			|String		|R			|机房名称
&emsp;&emsp;roomRows		|Integer	|R			|行数
&emsp;&emsp;roomCols		|Integer	|R			|列数
&emsp;&emsp;addr			|Integer	|R			|地区
&emsp;&emsp;remarks			|String		|R			|备注

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "id": 1,
            "name": "room2",
            "roomRows": 4,
            "roomCols": 6,
            "addr": 1,
            "remarks": ""
        }]
    }
}
```

##### 2.1.3.2 机房详情查询

- **接口说明：** 机房列表查询
- **接口地址：** /room/detail
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---
id					|Integer		|R			|机房id

示例：

```
GET /room/detail?id=4
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;id					|Integer	|R			|主键
&emsp;name					|String		|R			|机房名称
&emsp;roomRows				|Integer	|R			|行数
&emsp;roomCols				|Integer	|R			|列数
&emsp;addr					|Integer	|R			|地区
&emsp;remarks				|String		|R			|备注

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "id": 1,
        "name": "room2",
        "roomRows": 4,
        "roomCols": 6,
        "addr": 1,
        "remarks": ""
    }
}
```

##### 2.1.3.3 机房新增

- **接口说明：** 机房新增
- **接口地址：** /room/save
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
name				|String			|R			|名称
roomRows			|Integer		|R			|行数
roomCols			|Integer		|R			|列数
addr				|Integer		|R			|地区
remark				|String			|O			|备注

示例：

```
{
    "name": "room9",
    "roomRows": 2,
    "roomCols": 4,
    "addr": 54,
    "remark": "en"
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
失败
{
    "code": xxx,
    "msg": "原因"
}
```

##### 2.1.3.4 机房修改

- **接口说明：** 机房修改
- **接口地址：** /room/update
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id
name				|String			|R			|名称
roomRows			|Integer		|R			|行数
roomCols			|Integer		|R			|列数
addr				|Integer		|R			|地区
remark				|String			|O			|备注


示例：

```
{
    "id": 9,
    "name": "room9",
    "roomRows": 2,
    "roomCols": 4,
    "addr": 54,
    "remark": "en"
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
失败
{
    "code": xxx,
    "msg": "原因"
}
```

##### 2.1.3.5 机房删除

- **接口说明：** 机房删除
- **接口地址：** /room/delete
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
ids					|Integer[]		|R			|id

示例：

```
{
    "ids": [35,24,1]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
失败
{
    "code": xxx,
    "msg": "存在关联的机柜"
}
```

##### 2.1.3.6 机房名称校验

- **接口说明：** 机房名称校验，不能重复
- **接口地址：** /room/roomNameCheck
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id       			|String 		|O			|唯一标识，为空表示正在新增节点组
name				|String			|R			|父id

示例：

```
GET /room/roomNameCheck?pid=5&id=15
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
失败
{
    "code": xxx,
    "msg": "原因"
}
```

##### 2.1.3.7 机房修改时行列校验

- **接口说明：** 机房修改时行列校验，行、列数不能小于已被机柜占用的数
- **接口地址：** /room/roomSizeCheck
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id       			|String 		|R			|唯一标识
roomCols			|Integer		|R			|列数
roomRows			|Integer		|R			|行数

示例：

```
GET /room/roomSizeCheck?id=15&roomCols=5&roomRows=3
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
失败
{
    "code": xxx,
    "msg": "原因"
}
```

##### 2.1.3.8 机房内机柜列表查询

- **接口说明：** 查询机房内的机柜列表，同"2.1.4.1 机柜列表查询"，"roomId"为必须参数

#### 2.1.4 机柜管理

##### 2.1.4.1 机柜列表查询

- **接口说明：** 机柜列表查询
- **接口地址：** /cab/list
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
name				|String			|O			|机柜名称
roomId				|Integer		|O			|所属机房id

示例：

```
GET /cab/list?limit=10&page=2&name=cab3&roomId=2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;id				|Integer	|R			|主键
&emsp;&emsp;name			|String		|R			|机柜名称
&emsp;&emsp;roomName		|String		|R			|机房名称
&emsp;&emsp;roomRow				|Integer	|R			|行号
&emsp;&emsp;roomCol				|Integer	|R			|列号
&emsp;&emsp;ubit			|Integer	|R			|u位数量
&emsp;&emsp;remarks			|String		|R			|备注

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": [{
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "id": 1,
            "name": "cab2",
            "roomName": "room2",
            "roomRows": 4,
            "roomCols": 6,
            "ubit": 1,
            "remarks": ""
        }]
    }]
}
```

##### 2.1.4.2 机柜详情查询

- **接口说明：** 机柜列表查询
- **接口地址：** /cab/detail
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|O			|机柜id

示例：

```
GET /cab/detail?id=2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;id					|Integer	|R			|主键
&emsp;name					|String		|R			|机柜名称
&emsp;roomName				|String		|R			|机房名称
&emsp;roomRow				|Integer	|R			|行号
&emsp;roomCol				|Integer	|R			|列号
&emsp;ubit					|Integer	|R			|u位数量
&emsp;nodes					|Object[]	|R			|包含的节点
&emsp;&emsp;uuid			|Integer	|R			|uuid
&emsp;&emsp;ip				|String		|R			|ip
&emsp;&emsp;name			|String		|R			|节点名称
&emsp;&emsp;uSize			|Integer	|R			|u位大小
&emsp;&emsp;uStart			|Integer	|R			|起始U位
&emsp;remarks				|String		|R			|备注

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "id": 1,
        "name": "cab2",
        "roomName": "room2",
        "rooRrows": 4,
        "roomCols": 6,
        "nodes": [{
            "uuid": 5,
            "ip": "1.2.3.4",
            "name": "node2",
            "uSize": 3,
            "uStart": 1
        }],
        "ubit": 1,
        "remarks": ""
    }
}
```

##### 2.1.4.3 机柜新增

- **接口说明：** 机柜新增
- **接口地址：** /cab/save
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
name				|String			|R			|名称
roomId				|Integer		|R			|机房id
roomRow				|Integer		|R			|行号
rooCcol				|Integer		|R			|列号
ubit				|Integer		|R			|U位数量
remark				|String			|O			|备注

示例：

```
{
    "name": "cab9",
	"roomId": 1,
    "rooRrow": 2,
    "roomCol": 4,
    "ubit": 12,
	"remark": "en"
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "xxx"
}
```

##### 2.1.4.4 机柜修改

- **接口说明：** 机柜修改
- **接口地址：** /cab/update
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id
name				|String			|R			|名称
rooRrow				|Integer		|R			|行号
roomRol				|Integer		|R			|列号
ubit				|Integer		|R			|U位数量
remark				|String			|O			|备注

示例：

```
{
    "id": 9,
    "name": "cab9",
    "roomRow": 2,
    "roomCol": 4,
    "ubit": 12,
    "remark": "en"
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "xxx"
}
```

##### 2.1.4.5 机柜删除

- **接口说明：** 机柜删除
- **接口地址：** /cab/delete
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
ids					|Integer[]		|R			|id

示例：

```
{
    "ids": [35,24,1]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success/存在关联的节点"
}
```

##### 2.1.4.6 机柜名称校验

- **接口说明：** 机柜名称校验，同机房下名称不能重复
- **接口地址：** /cab/cabNameCheck
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id       			|String 		|O			|唯一标识，为空表示正在新增
name				|String			|R			|名称
roomId				|Integer		|R			|机房id

示例：

```
GET /cab/cabNameCheck?id=5&roomId=15&name=cab54
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "xxx"
}
```

##### 2.1.4.7 校验U位数量是否可用

- **接口说明：** 修改机柜时校验U位数量是否可用，如果U位数小于已被节点占用的U位则校验不通过
- **接口地址：** /cab/cabUbitCheck
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id       			|String 		|O			|唯一标识
ubit				|Integer		|R			|U位数量

示例：

```
GET /cab/cabUbitCheck?id=5&ubit=15
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "xxx"
}
```

##### 2.1.4.8 查询机柜可选的机房及行号列号

- **接口说明：** 查询机柜下可选的机房及行号列号
- **接口地址：** /cab/optionalRoom
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id       			|String 		|O			|唯一标识，为空表示正在新增

示例：

```
GET /cab/cabUbitCheck?id=5
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|String		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;roomId			|Integer	|R			|房间id
&emsp;&emsp;roomName		|String		|R			|房间名称
&emsp;&emsp;roomRows		|Object[]	|R			|可用行
&emsp;&emsp;&emsp;roomRow	|Integer	|R			|可用行号
&emsp;&emsp;&emsp;roomCols	|Integer[]	|R			|可用列号

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "list": [{
            "roomId": 1,
            "roomName": "room88",
            "roomRows": [{
                "roomRow": 1,
                "roomCols": [1,3,4]
            },
            {
                "roomRow": 2,
                "roomCols": [1,2,3,4,7,8,9]
            }]
        }]
    }
}
```


### 2.2 权限

#### 2.2.1 业务系统

##### 2.2.1.1 业务系统列表查询

- **接口说明：** 业务系统列表查询
- **接口地址：** /system/list
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
usergroupId			|Integer		|C			|用户组id

示例：

```
GET /system/list?limit=10&page=2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;id				|Integer	|R			|编号
&emsp;&emsp;name			|String		|R			|系统名称
&emsp;&emsp;builtIn			|Integer	|R			|是否内置，内置不可删除，1：内置，0：非内置
&emsp;&emsp;remarks			|String		|R			|备注信息
&emsp;&emsp;createDate		|Date		|R			|创建时间
&emsp;&emsp;updateDate		|Date		|R			|更新时间
&emsp;&emsp;delFlag			|Integer	|R			|删除标记 1：删除，0：未删除，默认：0

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "id": 1,
            "name": "system1",
            "builtIn": 1,
            "remarks": "",
            "delFlag": 0,
            "createDate": "2019-07-10 10:10:10",
            "updateDate": "2019-07-10 10:10:10"
        }]
    }
}
```

##### 2.2.1.2 业务系统详情查询

- **接口说明：** 业务系统详情查询
- **接口地址：** /system/detail
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|O			|业务系统id，为空时表示查询当前业务系统

示例：

```
GET /system/detail?id=2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;id					|Integer	|R			|编号
&emsp;name					|String		|R			|系统名称
&emsp;builtIn				|Integer	|R			|是否内置，内置不可删除，1：内置，0：非内置
&emsp;createDate			|Date		|R			|创建时间
&emsp;updateDate			|Date		|R			|更新时间
&emsp;remarks				|String		|R			|备注信息
&emsp;delFlag				|Integer	|R			|删除标记 1：删除，0：未删除，默认：0
&emsp;usergroups			|Object[]	|R			|用户组列表
&emsp;&emsp;id				|Integer	|R			|用户组ID
&emsp;&emsp;name			|Integer	|R			|用户组名称

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "id": 1,
        "name": "system2",
        "builtIn": 1,
        "createDate": "2019-07-10 10:10:10",
        "updateDate": "2019-07-10 10:10:10",
        "remarks": "",
        "delFlag": 1,
        "usergroups": [{
            "id": 2,
            "name": "group1"
        },
        {
            "id": 3,
            "name": "group2"
        }]
    }
}
```

##### 2.2.1.3 业务系统新增

- **接口说明：** 业务系统新增
- **接口地址：** /system/save
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
name				|String			|R			|名称
remark				|String			|O			|备注
usergroupIds		|Integer[]		|O			|用户组id,分配现有用户组


示例：

```
{
    "name": "system22",
    "remark": "en",
    "usergroupIds": [1,2,3,4]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "xxx"
}
```

##### 2.2.1.4 业务系统修改

- **接口说明：** 业务系统修改
- **接口地址：** /system/update
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id
name				|String			|R			|名称
remark				|String			|O			|备注
usergroupIds		|Integer[]		|O			|用户组id

示例：

```
{
    "id": 9,
    "name": "cab9",
    "remark": "en",
    "usergroupIds": [1,2,3,4]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "xxx"
}
```

##### 2.2.1.5 业务系统删除

- **接口说明：** 业务系统删除
- **接口地址：** /system/delete
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
ids					|Integer[]		|R			|id

示例：

```
[35,24,1]
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200
    "msg": "xxx"
}
```


##### 2.2.1.6 查询业务系统下的节点

- **接口说明：** 查询业务系统下的节点
- **接口地址：** /system/nodes
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
id					|Integer		|O			|业务系统id，global时可指定这个参数

示例：

```
GET /system/nodes?id=5&limit=50&page=3
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|String		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;name			|String		|R			|名称
&emsp;&emsp;hostName		|String		|R			|主机名
&emsp;&emsp;ip				|String		|R			|ip
&emsp;&emsp;uuid			|Integer	|R			|全局唯一
&emsp;&emsp;type			|Integer	|R			|设备类型，1、server,2、net
&emsp;&emsp;tagName			|String 	|R			|设备标签名称
&emsp;&emsp;tag				|Integer	|R			|设备标签，与sys_dict关联
&emsp;&emsp;state			|String		|R			|设备状态，1：在线，2：下线，3：删除
&emsp;&emsp;remark			|String		|R			|备注

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "id": 1,
            "name": "a",
            "hostName": "b",
            "ip": "112.21.122.212",
            "uuid": 1,
            "tagName": "atc",
            "type": 1,
            "tag": 1,
            "state": 1,
            "remark": ""
        }]
    }
}
```

##### 2.2.1.7 业务系统分配节点

- **接口说明：** 建立业务系统--节点关系
- **接口地址：** /system/saveNodeRel
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|O			|业务系统id，global时可指定这个参数
uuids				|Integer[]		|R			|节点id

示例：

```
{
    "id": 2,
    "uuids": [1,2,3]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.2.1.8 业务系统移除节点

- **接口说明：** 解除业务系统--节点关系
- **接口地址：** /system/deleteNodeRel
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|O			|业务系统id，global时可指定这个参数
uuids				|Integer[]		|R			|节点id

示例：

```
{
    "id": 2,
    "uuids": [1,2,3]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.2.1.9 业务系统名称校验

- **接口说明：** 业务系统名称校验，同父节点下名称不能重复
- **接口地址：** /system/nameCheck
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id       			|String 		|O			|唯一标识，为空表示正在新增业务系统
name				|String			|R			|名称

示例：

```
GET /system/nameCheck?id=5&name=system2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.2.1.10 查询用户所属的业务系统列表

- **接口说明：** 查询用户所属的业务系统列表，用于切换业务系统
- **接口地址：** /system/listByUser
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---

示例：

```
GET /system/listByUser
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;id				|Integer	|R			|id
&emsp;&emsp;name			|String		|R			|系统名称

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "list":[{
            "id": 2,
            "name": "system1"
        }]
    }
}
```

##### 2.2.1.11 切换业务系统

- **接口说明：** 切换业务系统
- **接口地址：** /system/changeSystem
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---
id                  |Integer        |R          |业务系统id

示例：

```
GET /system/changeSystem?id=54
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.2.1.12 用户组列表

- **接口说明：** 用于新增/修改业务系统时展示用户组，同 "2.2.2.1 用户组列表查询"，请求参数"systemId"为必须参数，"limit"参数值为999（避免被分页）


#### 2.2.2 用户组

##### 2.2.2.1 用户组列表查询

- **接口说明：** 用户组列表查询
- **接口地址：** /sys/usergroup/list
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
systemId			|Integer		|C			|业务系统id

示例：

```
GET /sys/usergroup/list?limit=10&page=2&systemId=4
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;id				|Integer	|R			|主键
&emsp;&emsp;name			|String		|R			|用户组名称
&emsp;&emsp;remark			|String		|R			|备注信息
&emsp;&emsp;systems	    	|Object[]	|R			|业务系统
&emsp;&emsp;&emsp;id		|Integer	|R			|业务系统id
&emsp;&emsp;&emsp;name		|String		|R			|业务系统名称
&emsp;&emsp;users			|Object[]	|R			|用户组内的用户
&emsp;&emsp;&emsp;id		|Integer	|R			|用户id
&emsp;&emsp;&emsp;username	|String		|R			|用户登录名

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "id": 1,
            "name": "usergroup1",
            "remarks": "",
            “systems": [{
                "id": 1,
                "name": "system1"
            }],
            "users": [{
                "id": 1,
                "username": "admin"
            }]
        }]
    }
}
```

##### 2.2.2.2 用户组详情查询

- **接口说明：** 用户组详情查询
- **接口地址：** /sys/usergroup/detail
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|O			|用户组id

示例：

```
GET /sys/usergroup/detail?id=2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;id					|Integer	|R			|主键
&emsp;name					|String		|R			|用户组名称
&emsp;remark				|String		|R			|备注信息
&emsp;systemInfos			|Object[]	|R			|业务系统
&emsp;&emsp;id				|Integer	|R			|业务系统id
&emsp;&emsp;name			|String		|R			|业务系统名称
&emsp;users					|Object[]	|R			|用户组内的用户
&emsp;&emsp;id				|Integer	|R			|用户id
&emsp;&emsp;username		|String		|R			|用户登录名

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "id": 1,
        "name": "usergroup1",
        "remarks": "",
        “systemInfos": [{
            "id": 1,
            "name": "system1"
        }],
        "users": [{
            "id": 1,
            "username": "admin"
        }]
    }
}
```

##### 2.2.2.3 用户组新增

- **接口说明：** 用户组新增
- **接口地址：** /sys/usergroup/save
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
name				|String			|R			|名称
remark				|String			|O			|备注
systemIds			|Integer[]		|O			|业务系统id
userIds				|Integer[]		|O			|用户id

示例：

```
{
    "name": "usergroup22",
    "remark": "en",
    "systemIds": [1,2,3,4],
    "userIds": [1,3]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```

##### 2.2.2.4 用户组修改

- **接口说明：** 用户组修改
- **接口地址：** /sys/usergroup/update
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id
name				|String			|R			|名称
remark				|String			|O			|备注
systemIds			|Integer[]		|O			|业务系统id
userIds				|Integer[]		|O			|用户id

示例：

```
{
    "id": 9,
    "name": "cab9",
    "remark": "en",
    "systemIds": [1,2,3,4],
    "userIds": [1,3]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```

##### 2.2.2.5 用户组删除

- **接口说明：** 用户组删除
- **接口地址：** /sys/usergroup/delete
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
ids					|Integer[]		|R			|id

示例：

```
[35,24,1]
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.2.2.6 业务系统列表

- **接口说明：** 用于新增/修改用户组时展示业务系统，同 "2.2.1.1 业务系统列表查询"，请求参数"usergroupId"为必须参数

##### 2.2.2.7 用户组名称校验

- **接口说明：** 用户组名称校验，不能重复
- **接口地址：** /sys/usergroup/nameCheck
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id       			|String 		|O			|唯一标识，为空表示正在新增
name				|String			|R			|名称

示例：

```
GET /sys/usergroup/nameCheck?id=5&name=ug2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```


### 2.3 监测配置

#### 2.3.1 监测类别

##### 2.3.1.1 监测类别列表查询

- **接口说明：** 监测类别列表查询
- **接口地址：** /deteType/list
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
name				|String			|O			|监测类别

示例：

```
GET /deteType/list?limit=10&page=2&name=cpu
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;id				|Integer	|R			|&nbsp;
&emsp;&emsp;name			|String		|R			|名称，唯一索引
&emsp;&emsp;method			|String		|R			|1、脚本，2、snmp，3、内置，默认：1，页面显示翻译后内容
&emsp;&emsp;dete_interval	|Integer	|R			|监控间隔，单位：s，默认：60
&emsp;&emsp;content			|String		|R			|1、脚本储存路径，2、oid，可以为空，3、类全路径
&emsp;&emsp;buildIn			|String		|R			|1、隐藏界面不显示，2、内置，不允许修改，3、用户自定义，默认3
&emsp;&emsp;version			|Integer	|R			|更新version加1，默认：1
&emsp;&emsp;i18nCode		|String		|R			|name 的国际化 code，不为空时页面显示翻译后的内容，为空直接显示name
&emsp;&emsp;remark			|String		|R			|备注

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
           "id": 1,
           "name": "",
           "viewLevel": "",
           "method": "",
           "dete_interval": 1,
           "content": "",
           "buildIn": "",
           "tableName": "",
           "version": 1,
           "i18nCode": "",
           "remark": ""
        }]
    }
}
```

##### 2.3.1.2 监测类别详情查询

- **接口说明：** 监测类别详情查询，返回监测类别、元数据和参数
- **接口地址：** /deteType/detail
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|类别id

示例：

```
GET /deteType/detail?id=2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;id					|Integer	|R			|&nbsp;
&emsp;name					|String		|R			|名称，唯一索引
&emsp;method				|String		|R			|1、脚本，2、snmp，3、内置，默认：1，显示翻译后的内容
&emsp;deteInterval			|Integer	|R			|监控间隔，单位：s，默认：60
&emsp;content				|String		|R			|1、脚本储存路径，2、oid，可以为空，3、类全路径
&emsp;i18nCode				|String		|R			|name 的国际化 code，不为空时name显示翻译后的内容，为空直接显示
&emsp;remark				|String		|R			|备注
&emsp;opTime				|String		|R			|操作时间
&emsp;deteTypeMetas			|Object[]	|R			|元数据列表
&emsp;&emsp;id				|Integer	|R			|&nbsp;
&emsp;&emsp;name			|String		|R			|显示名称，唯一索引
&emsp;&emsp;fieldName		|String		|R			|字段名
&emsp;&emsp;typeId			|Integer	|R			|类别id
&emsp;&emsp;fieldType		|String		|R			|字段分类，1:Tag 数据库添加索引 ,2:field 普通字段, 3:temp 临时字段，数据传输不入库, 4:cal 计算字段，根据field，temp计算得出
&emsp;&emsp;dataType		|String		|R			|数据类型，1:counter，需要根据上一个监测周期的数据差值计算2：gauge瞬时值 3：string 字符类型
&emsp;&emsp;dataLenth		|Integer	|R			|数据长度
&emsp;&emsp;sort			|Integer	|R			|排序
&emsp;&emsp;oid				|String		|R			|snmp oid
&emsp;&emsp;unit			|String		|R			|单位
&emsp;&emsp;dicType			|Integer	|O			|字典类型
&emsp;&emsp;i18nCode		|String		|R			|name 的国际化 code，不为空时name显示翻译后的内容，为空直接显示name
&emsp;&emsp;remark			|String		|R			|备注
&emsp;deteTypeParams		|Object[]	|R			|类别参数数组
&emsp;&emsp;id				|Integer	|R			|
&emsp;&emsp;name			|String		|R			|参数名称
&emsp;&emsp;typeId			|Integer	|R			|类别id
&emsp;&emsp;param_index			|Integer	|R			|参数索引
&emsp;&emsp;defVal			|String		|R			|参数默认值
&emsp;&emsp;remark			|String		|R			|备注

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "id": 1,
        "name": "enc",
        "method": "脚本",
        "deteInterval": 60,
        "content": "",
        "i18nCode": "cpu监测",
        "remark": "",
        "opTime": "2019-07-10 10:10:10",
        "deteTypeMetas": [{
            "id": 1,
            "name": "earae",
            "fieldName": "earae",
            "typeId": 1,
            "fieldType": "",
            "dataType": "",
            "dataLenth": 1,
            "sort": 1,
            "oid": "",
            "unit": "",
            "dicType": 2,
            "i18nCode": "",
            "remark": ""
        }],
        "deteTypeParams": [{
            "id": 1,
            "name": "cc",
            "typeId": 1,
            "param_index": 1,
            "defVal": "",
            "remark": ""
        }]
    }
}
```

##### 2.3.1.3 监测类别新增

- **接口说明：** 监测类别新增
- **接口地址：** /deteType/save
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
name				|String			|R			|唯一索引
viewLevel			|String			|R			|1:用户组，2：系统内全部人员，3：无限制，默认3（此字段目前不用，预留）
method				|String			|R			|1、脚本，2、snmp，3、内置，默认：1
deteInterval		|Integer		|R			|监控间隔，单位：s，默认：60
content				|String			|R			|1、脚本储存路径，2、oid，可以为空，3、类全路径
i18nCode			|String			|R			|name 的国际化 code，不为空时name显示翻译后的内容，为空直接显示
remark				|String			|R			|备注
deteTypeMetas		|Object[]		|R			|元数据数据
&emsp;name			|String			|R			|显示名称，唯一索引
&emsp;fieldType		|String			|R			|字段分类，1:Tag 数据库添加索引 ,2:field 普通字段, 3:temp 临时字段，数据传输不入库, 4:cal 计算字段，根据field，temp计算得出
&emsp;dataType		|String			|R			|数据类型，1:counter，需要根据上一个监测周期的数据差值计算2：gauge瞬时值 3：string 字符类型
&emsp;dataLenth		|Integer		|R			|数据长度
&emsp;sort			|Integer		|R			|排序
&emsp;oid			|String			|R			|snmp oid
&emsp;unit			|String			|R			|单位
&emsp;dicType		|Integer		|O			|字典类型
&emsp;remark		|String			|R			|备注
deteTypeParams		|Object[]		|R			|类别参数数组
&emsp;name			|String			|R			|参数名称
&emsp;paramIndex	|Integer		|R			|参数索引
&emsp;defVal		|String			|R			|参数默认值
&emsp;remark		|String			|R			|备注

示例：

```
    {
        "name": "enc",
        "viewLevel": "3",
        "method": 1,
        "deteInterval": "",
        "content": "",
        "i18nCode": "",
        "remark": "",
        "deteTypeMetas": [{
            "name": "earae",
            "fieldType": "",
            "dataType": "",
            "dataLenth": 1,
            "sort": 1,
            "oid": "",
            "unit": "",
            "dicType": 2,
            "remark": ""
        }],
        "deteTypeParams": [{
            "name": "cc",
            "paramIndex": 1,
            "defVal": "",
            "remark": ""
        }]
    }
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```

##### 2.3.1.4 监测类别修改

- **接口说明：** 监测类别修改
- **接口地址：** /deteType/update
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id
name				|String			|R			|唯一索引
viewLevel			|String			|R			|1:用户组，2：系统内全部人员，3：无限制，默认2
method				|String			|R			|1、脚本，2、snmp，3、内置，默认：1
deteInterval		|Integer		|R			|监控间隔，单位：s，默认：60
content				|String			|R			|1、脚本储存路径，2、oid，可以为空，3、类全路径
i18nCode			|String			|R			|name 的国际化 code，不为空时name显示翻译后的内容，为空直接显示
remark				|String			|R			|备注
deteTypeMetas		|Object[]		|R			|元数据数据
&emsp;id			|Integer		|R			|&nbsp;
&emsp;name			|String			|R			|显示名称，唯一索引
&emsp;fieldName		|String		|R			|字段名
&emsp;typeId		|Integer		|R			|类别id
&emsp;fieldType		|String			|R			|字段分类，1:Tag 数据库添加索引 ,2:field 普通字段, 3:temp 临时字段，数据传输不入库, 4:cal 计算字段，根据field，temp计算得出
&emsp;dataType		|String			|R			|数据类型，1:counter，需要根据上一个监测周期的数据差值计算2：gauge瞬时值 3：string 字符类型
&emsp;dataLenth		|Integer		|R			|数据长度
&emsp;sort			|Integer		|R			|排序
&emsp;oid			|String			|R			|snmp oid
&emsp;unit			|String			|R			|单位
&emsp;dicType		|Integer		|O			|字典类型
&emsp;i18nCode		|String			|R			|name 的国际化 code，不为空时name显示翻译后的内容，为空直接显示name
&emsp;remark		|String			|R			|备注
&emsp;delFlag       |String         |O          |删除标识
deteTypeParams		|Object[]		|R			|类别参数数组
&emsp;id			|Integer		|R			|
&emsp;name			|String			|R			|参数名称
&emsp;typeId		|Integer		|R			|类别id
&emsp;paramIndex	|Integer		|R			|参数索引
&emsp;defVal		|String			|R			|参数默认值
&emsp;remark		|String			|R			|备注
&emsp;delFlag       |String         |O          |删除标识

示例：

```
    {
        "id": 223
        "name": "enc",
        "typeId": 1,
        "fieldType": "1",
        "dataType": "2",
        "dataLenth": 1,
        "viewLevel": "2",
        "sort": 1,
        "oid": "",
        "unit": "",
        "fieldName": "",
        "i18nCode": "",
        "remark": "",
		"deteTypeMetas": [{
            "id": 1,
            "name": "earae",
            "fieldName": "earae",
            "typeId": 1,
            "fieldType": "",
            "dataType": "",
            "dataLenth": 1,
            "sort": 1,
            "oid": "",
            "unit": "",
            "dicType": 2,
            "i18nCode": "",
            "remark": "",
            "delFlag": "1"
        }],
        "deteTypeParams": [{
            "id": 1,
            "name": "cc",
            "typeId": 1,
            "paramIndex": 1,
            "defVal": "",
            "remark": "",
            "delFlag": "1"
        }]
    }
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```

##### 2.3.1.5 监测类别删除

- **接口说明：** 监测类别删除
- **接口地址：** /deteType/delete
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
ids					|Integer[]		|R			|id

示例：

```
{
    "ids": [35,24,1]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.3.1.6 元数据字典查询

- **接口说明：** 元数据字典查询，用于元数据选择字典或者字典管理；用于选择字典时要一次性查出全部记录，limit=999
- **接口地址：** /deteType/dicList
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
type				|Integer		|C			|类型，字典管理用
page				|Integer		|C			|页码，为空时默认为1，字典管理用
limit				|Integer		|C			|每页记录数，为空时默认为10，字典管理用
sidx				|String			|C			|排序字段，字典管理用
order	 			|String 		|C			|排序方式(asc/desc)，字典管理用

示例：

```
GET /deteType/dicList
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;totalCount			|int		|C			|字典管理用
&emsp;totalPage				|int		|C			|字典管理用
&emsp;currPage				|int		|C			|字典管理用
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;type			|String		|R			|映射类型
&emsp;&emsp;mappings		|Object[]	|R			|映射内容
&emsp;&emsp;&emsp;id		|String		|R			|mapping表主键
&emsp;&emsp;&emsp;val		|String		|R			|原值
&emsp;&emsp;&emsp;mapping	|String		|R			|映射后值

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "type": "name",
            "mappings": [{
                "id": 11,
                "val": "1",
                "mapping": "是"
            }]
        }]
    }
}
```

##### 2.3.1.7 元数据字典新增

- **接口说明：** 元数据字典新增
- **接口地址：** /deteType/saveDic
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
type				|String			|R			|映射类型，前端页面上可选择、可新增
mappings			|Object[]		|R			|映射值
&emsp;val			|String			|R			|原值
&emsp;mapping		|String			|R			|映射后值

示例：

```
{
    "type": "cpuuu",
    "mappings": [{
        "val": "2",
        "mapping": "不正常"
	}]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.3.1.8 元数据字典修改

- **接口说明：** 元数据字典修改，type不允许修改
- **接口地址：** /deteType/updateDic
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
mappings			|Object[]		|R			|映射值
&emsp;id			|Object			|O			|id 为空表示这一条映射是新增的
&emsp;val			|String			|R			|原值
&emsp;delFlag		|String			|R			|删除标识
&emsp;mapping		|String			|R			|映射后值

示例：

```
{
    "mappings": [{
        "id": 1,
        "val": "2",
        "mapping": "不正常",
        "delFlag": "1"
    },
    {
        "id": 2,
        "val": "1",
        "mapping": "正常的",
        "delFlag": "0"
    },
    {
        "val": "2",
        "mapping": "不正常的"
    }
    ]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.3.1.9 元数据字典删除

- **接口说明：** 元数据字典删除
- **接口地址：** /deteType/deleteDic
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
types				|String[]		|R			|类型

示例：

```
{
    "types": ["a","b"]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.3.1.10 监测类别名称校验

- **接口说明：** 监测类别名称校验，不能重复
- **接口地址：** /deteType/nameCheck
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id       			|String 		|O			|唯一标识，为空表示正在新增监测类别
name				|String			|R			|名称

示例：

```
GET /deteType/nameCheck?id=5&name=cpu
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.3.1.11 元数据字典type校验

- **接口说明：** 元数据字典type校验，不能重复，新增字典时使用
- **接口地址：** /deteType/dicNameCheck
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
type				|String			|R			|名称

示例：

```
GET /deteType/dicNameCheck?name=testtp
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```


#### 2.3.2 监测设置

##### 2.3.2.1 监测设置列表查询

- **接口说明：** 监测类别列表查询
- **接口地址：** /deteSet/list
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
name				|String			|O			|监测设置
typeId				|Integer		|O			|监测类别ID

示例：

```
GET /deteSet/list?limit=10&page=2&name=cpu
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;&emsp;list			|Object[]	|R			|&nbsp;
&emsp;&emsp;id				|Integer	|R			|主键
&emsp;&emsp;name			|String		|R			|设置名称，唯一索引
&emsp;&emsp;type			|Object		|R			|类别
&emsp;&emsp;&emsp;id		|Integer	|R			|类别ID
&emsp;&emsp;&emsp;name		|String		|R			|类别名称
&emsp;&emsp;buildIn			|String		|R			|1:内置，2：用户自定义，默认2
&emsp;&emsp;params			|String		|R			|类别定义的参数，多个逗号分隔，参数内逗号需要转义
&emsp;&emsp;viewLevel		|String		|R			|1:用户组，2：系统内全部人员，3：无限制，默认2
&emsp;&emsp;viewer			|Object[]	|O			|查看人，viewLevel=1或2时有值
&emsp;&emsp;&emsp;id		|Integer	|O			|业务系统/用户组id
&emsp;&emsp;&emsp;name		|String		|O			|业务系统/用户组名称
&emsp;&emsp;state			|String		|R			|状态，1：删除，2：停止，3：监控中
&emsp;&emsp;remark			|String		|R			|备注
&emsp;&emsp;i18nCode		|String		|R			| name i18n code值
&emsp;&emsp;operator		|Integer	|R			|操作人
&emsp;&emsp;opTime			|Date		|R			|操作时间

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "id": 1,
            "name": "cpu",
            "type": {
                "id": 2,
                "name": "cpu"
            },
            "buildIn": "1",
            "params": "",
            "viewLevel": "3",
            "state": "",
            "remark": "",
            "i18nCode": ""
        }]
    }
}
```

##### 2.3.2.2 监测设置详情查询

- **接口说明：** 监测设置详情查询
- **接口地址：** /deteSet/detail
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|

示例：

```
GET /deteSet/detail?id=2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;id					|Integer	|R			|主键
&emsp;name					|String		|R			|设置名称，唯一索引
&emsp;type					|Object		|R			|类别
&emsp;&emsp;id				|Integer	|R			|类别ID
&emsp;&emsp;name			|String		|R			|类别名称
&emsp;&emsp;deteTypeParams	|Object[]	|R			|类别参数
&emsp;&emsp;&emsp;id		|Integer	|R			|参数id
&emsp;&emsp;&emsp;name		|String		|R			|参数名称
&emsp;&emsp;&emsp;def_val	|String		|R			|参数默认值
&emsp;buildIn				|String		|R			|1:内置，2：用户自定义，默认2
&emsp;params				|String		|R			|类别定义的参数，多个逗号分隔，参数内逗号需要转义
&emsp;viewLevel				|String		|R			|1:用户组，2：系统内全部人员，3：无限制，默认2
&emsp;viewer			    |Object[]	|O			|查看人，viewLevel=1或2时有值
&emsp;&emsp;id		        |Integer	|O			|业务系统/用户组id
&emsp;&emsp;name		    |String		|O			|业务系统/用户组名称
&emsp;state					|String		|R			|状态，1：删除，2：停止，3：监控中
&emsp;remark				|String		|R			|备注
&emsp;i18nCode				|String		|R			| name i18n code值
&emsp;opTime				|Date		|R			|操作时间
&emsp;nodeGroups			|Object[]	|R			|节点组
&emsp;&emsp;id				|Integer	|R			|节点组id
&emsp;&emsp;name			|String		|R			|节点组名称
&emsp;nodes					|Object[]	|R			|节点
&emsp;&emsp;uuid			|Integer	|R			|节点id
&emsp;&emsp;name			|String		|R			|节点名称
&emsp;&emsp;ip				|String		|R			|节点ip

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "id": 1,
        "name": "cpu",
        "type": {
            "id": 2,
            "name": "cpu",
            "deteTypeParams": [{
                "id": 2,
                "name": "a",
                "def_val": "12"
            }]
        },
        "buildIn": "1",
        "params": "",
        "viewLevel": "2",
        "viewer": [{"id": 1, "name": "global"}],
        "state": "",
        "remark": "",
        "i18nCode": "",
        "nodeGroups": [{
            "id": 1,
            "name": "group1"
        }],
        "nodes": [{
            "uuid": 9,
            "name": "node1",
            "ip": "10.20.30.40"
        }]
    }
}
```

##### 2.3.2.3 监测设置新增

- **接口说明：** 监测设置新增
- **接口地址：** /deteSet/save
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
name				|String			|R			|设置名称，唯一索引
typeId				|Integer		|R			|类别id
params				|String			|R			|类别定义的参数，多个逗号分隔，参数内逗号需要转义
viewLevel			|String			|R			|1:用户组，2：系统内全部人员，3：无限制，默认2
viewerId            |Integer[]      |O          |查看人，viewLevel=1时有值，表示用户组id；viewLevel=2时，业务系统id从后台取得
remark				|String			|R			|备注
i18nCode			|String			|R			| name i18n code值
nodeGroupIds		|Integer[]		|R			|节点组id
nodeIds				|Integer[]		|R			|节点id

示例：

```
{
    "name": "",
    "typeId": 1,
    "params": "1,'a',3",
    "viewLevel": "1",
    "viewerId": [2,3],
    "remark": "",
    "i18nCode": "",
    "nodeGroupIds": [1,2,3],
    "nodeIds": [1,2,4]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```

##### 2.3.2.4 监测设置修改

- **接口说明：** 监测设置修改
- **接口地址：** /deteSet/update
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id
name				|String			|R			|设置名称，唯一索引
typeId				|Integer		|R			|类别id
params				|String			|R			|类别定义的参数，多个逗号分隔，参数内逗号需要转义
remark				|String			|R			|备注
i18nCode			|String			|R			| name i18n code值
nodeGroupIds		|Integer[]		|R			|节点组id
nodeIds				|Integer[]		|R			|节点id

示例：

```
{
	"id": 3
    "name": "eeee",
    "typeId": 1,
    "params": "1,'a',3",
    "remark": "",
    "i18nCode": "",
    "nodeGroupIds": [1,2,3],
    "nodes": [4,5,6]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```

##### 2.3.2.5 监测设置状态变更

- **接口说明：** 监测设置状态变更，1删除、2停用、3监控中
- **接口地址：** /deteSet/changeState
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
ids					|Integer[]		|R			|id
state               |String         |R          |状态，1删除、2停用、3监控中

示例：

```
{
    "id": 35,
    "state": "2"
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.3.2.6 监测设置名称校验

- **接口说明：** 监测类别名称校验，不能重复
- **接口地址：** /deteSet/nameCheck
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id       			|Integer 		|O			|唯一标识，为空表示正在新增监测类别
name				|String			|R			|名称

示例：

```
GET /deteSet/nameCheck?id=5&name=cpu
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "true/false"
}
```


#### 2.3.3 告警设置

##### 2.3.3.1 告警设置列表查询

- **接口说明：** 监测类别列表查询
- **接口地址：** /deteWarn/list
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
setId				|Integer		|O			|监测设置ID
typeId				|Integer		|O			|监测类别ID

示例：

```
GET /deteWarn/list?limit=10&page=2&setId=12
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:-----------				|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;id				|Integer	|R			|&nbsp;
&emsp;&emsp;name			|String		|R			|&nbsp;
&emsp;&emsp;deteType		|Object		|R			|监测类别
&emsp;&emsp;&emsp;id		|Integer	|R			|类别id
&emsp;&emsp;&emsp;name		|String		|R			|类别名称
&emsp;&emsp;deteSet			|Object[]	|O			|监测设置
&emsp;&emsp;&emsp;id		|Integer	|R			|设置id
&emsp;&emsp;&emsp;name		|String		|R			|设置名称
&emsp;&emsp;meta			|Object		|R			|告警字段
&emsp;&emsp;&emsp;id		|Integer	|R			|字段id
&emsp;&emsp;&emsp;name		|String		|R			|字段名称
&emsp;&emsp;trigger			|String		|R			|1:阈值触发,2：变化触发，当本次监测数值与上次不一致时触发，用于配置文件是否修改等,3：主动，默认：1
&emsp;&emsp;warnMode		|String		|R			|告警模式，1、单台，2、汇总
&emsp;&emsp;statType		|String		|R			|1:avg 2:count 3:sum 4:min 5:max，默认：1
&emsp;&emsp;symbol			|String		|R			|1:> 2:< 3:= 4:equals 5:include 6:exclude 默认：1
&emsp;&emsp;threshold		|String		|R			|阈值
&emsp;&emsp;tips			|String		|R			|告警提示信息
&emsp;&emsp;warnLevel		|String		|R			|告警级别，1:normal，2:info，3:warning，4:error，默认：3
&emsp;&emsp;callbackType	|String		|R			|回调方式，0:无，1：shell，2：http，默认：0
&emsp;&emsp;viewLevel		|String		|R			|1:用户组，2：系统内全部人员，3：无限制，默认2
&emsp;&emsp;remark			|String		|R			|备注

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "id": 1,
            "name": "",
            "deteType": {
                "id": 1,
                "name": "22ww"
            },
            "deteSet": [{
                "id": 2,
                "name": "2211"
            }],
            "meta": {
                "id": 2, 
                "name": "使用率"
            },
            "trigger": "1",
            "warnMode": "2",
            "statType": "1",
            "symbol": ">",
            "threshold": "15",
            "tips": "enen",
            "warnLevel": "1",
            "callbackType": "",
            "viewLevel": "",
            "remark": ""
        }]
    }
}
```

##### 2.3.3.2 告警设置详情查询

- **接口说明：** 告警设置详情查询
- **接口地址：** /deteWarn/detail
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|&nbsp;

示例：

```
GET /deteWarn/detail?id=2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;id					|Integer	|R			|&nbsp;
&emsp;name					|String		|R			|&nbsp;
&emsp;deteType				|Object		|R			|监测类别
&emsp;&emsp;id				|Integer	|R			|类别id
&emsp;&emsp;name			|String		|R			|类别名称
&emsp;deteSet				|Object[]	|O			|监测设置
&emsp;&emsp;id				|Integer	|R			|设置id
&emsp;&emsp;name			|String		|R			|设置名称
&emsp;meta					|Object		|R			|告警字段
&emsp;&emsp;id				|Integer	|R			|字段id
&emsp;&emsp;name			|String		|R			|字段名称
&emsp;trigger				|String		|R			|1:阈值触发,2：变化触发，当本次监测数值与上次不一致时触发，用于配置文件是否修改等,3：主动，默认：1
&emsp;warnMode				|String		|R			|告警模式，1、单台，2、汇总
&emsp;statType				|String		|R			|1:avg 2:count 3:sum 4:min 5:max，默认：1
&emsp;symbol				|String		|R			|1:> 2:< 3:= 4:equals 5:include 6:exclude 默认：1
&emsp;threshold				|String		|R			|阈值
&emsp;tips					|String		|R			|告警提示信息
&emsp;warnLevel			    |String		|R			|告警级别，1:normal，2:info，3:warning，4:error，默认：3
&emsp;callbackType			|String		|R			|回调方式，0:无，1：shell，2：http，默认：0
&emsp;callbackContent		|String		|R			|回调内容
&emsp;viewLevel				|String		|R			|1:用户组，2：系统内全部人员，3：无限制，默认2
&emsp;remark				|String		|R			|备注

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "id": 1,
        "name": "",
        "deteType": {
            "id": 1,
            "name": "22ww"
        },
        "deteSet": [{
            "id": 2,
            "name": "2211"
        }],
        "meta": {
            "id": 2, 
            "name": "使用率"
        },
        "trigger": "1",
        "warnMode": "2",
        "statType": "1",
        "symbol": ">",
        "threshold": "15",
        "tips": "enen",
        "warnLevel": "1",
        "callbackType": "",
        "viewLevel": "",
        "remark": ""
    }
}
```

##### 2.3.3.3 告警设置新增

- **接口说明：** 告警设置新增
- **接口地址：** /deteWarn/save
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
name				|String			|R			|&nbsp;
deteTypeId			|Integer		|R			|监测类别id
deteSetIds			|Integer[]		|O			|监测设置id
metaId				|Integer		|R			|告警字段id
trigger				|String			|R			|1:阈值触发,2：变化触发，当本次监测数值与上次不一致时触发，用于配置文件是否修改等,3：主动，默认：1
warnMode			|String			|R			|告警模式，1、单台，2、汇总
statType			|String			|R			|1:avg 2:count 3:sum 4:min 5:max，默认：1
symbol				|String			|R			|1:> 2:< 3:= 4:equals 5:include 6:exclude 默认：1
threshold			|String			|R			|阈值
tips				|String			|R			|告警提示信息
warnLevel			|String			|R			|告警级别，1:normal，2:info，3:warning，4:error，默认：3
callbackType		|String			|R			|回调方式，0:无，1：shell，2：http，默认：0
callbackContent		|String			|R			|回调内容
viewLevel			|String			|R			|1:用户组，2：系统内全部人员，3：无限制，默认2
remark				|String			|R			|备注

示例：

```
{
    "name": "",
    "deteTypeId": 32,
    "deteSetIds": [1,2,3],
    "metaId": 1,
    "trigger": "",
    "warnMode": "",
    "statType": "",
    "symbol": "",
    "threshold": "",
    "tips": "",
    "warnLevel": "",
    "callbackType": "",
    "callbackContent": "",
    "viewLevel": "",
    "remark": ""
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```

##### 2.3.3.4 告警设置修改

- **接口说明：** 告警设置修改
- **接口地址：** /deteWarn/update
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|主键
name				|String			|R			|&nbsp;
metaId				|Integer		|R			|告警字段id
trigger				|String			|R			|1:阈值触发,2：变化触发，当本次监测数值与上次不一致时触发，用于配置文件是否修改等,3：主动，默认：1
warnMode			|String			|R			|告警模式，1、单台，2、汇总
statType			|String			|R			|1:avg 2:count 3:sum 4:min 5:max，默认：1
symbol				|String			|R			|1:> 2:< 3:= 4:equals 5:include 6:exclude 默认：1
threshold			|String			|R			|阈值
tips				|String			|R			|告警提示信息
warnLevel			|String			|R			|告警级别，1:normal，2:info，3:warning，4:error，默认：3
callbackType		|String			|R			|回调方式，0:无，1：shell，2：http，默认：0
callbackContent		|String			|R			|回调内容
viewLevel			|String			|R			|1:用户组，2：系统内全部人员，3：无限制，默认2
remark				|String			|R			|备注

示例：

```
{
    "id": 133,
    "name": "",
    "metaId": 1,
    "trigger": "",
    "mode": "",
    "statType": "",
    "symbol": "",
    "threshold": "",
    "tips": "",
    "warnLevel": "",
    "callbackType": "",
    "callbackContent": "",
    "viewLevel": "",
    "remark": ""
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```

##### 2.3.3.5 告警设置删除

- **接口说明：** 告警类别删除
- **接口地址：** /deteWarn/delete
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
ids					|Integer[]		|R			|id

示例：

```
{
    "ids": [35,24,1]
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.3.3.6 告警名称校验

- **接口说明：** 监测类别名称校验，不能重复
- **接口地址：** /deteWarn/nameCheck
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id       			|String 		|O			|唯一标识，为空表示正在新增监测类别
name				|String			|R			|名称

示例：

```
GET /deteWarn/nameCheck?id=5&name=cpu
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A

示例：

```
{
    "code": 200/xxx,
    "msg": "true/false"
}
```


### 2.4 任务

#### 2.4.1 任务

##### 2.4.1.1 任务列表查询

- **接口说明：** 任务列表查询
- **接口地址：** /mission/list
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
isLoop				|String			|O			|是否周期任务 0：不是，1：是
type				|String			|O			|任务类型 1：文件推送，2：命令执行，3：升级部署
isLoop				|String			|O			|是否周期任务 0：不是，1：是
name				|String			|O			|任务名称

示例：

```
GET /usergroup/list?limit=10&page=2&name=file&isLoop=0
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;id				|Integer	|R			|&nbsp;
&emsp;&emsp;name			|String		|R			|任务名称
&emsp;&emsp;type			|String		|R			|任务类型，1、文件推送，2、命令执行，3、升级部署
&emsp;&emsp;state			|String		|R			|任务状态，周期任务有效，0、非周期任务，1、运行，2、暂停，3、终止
&emsp;&emsp;stateDesc		|Integer[]	|R			|任务状态描述，成功几个失败几个等
&emsp;&emsp;viewLevel		|String		|R			|查看权限 1:用户组，2：系统内全部人员，3：无限制，默认2
&emsp;&emsp;viewer			|Object[]	|O			|查看人，viewLevel=1或2时有值
&emsp;&emsp;&emsp;id		|Integer	|O			|业务系统/用户组id
&emsp;&emsp;&emsp;name		|String		|O			|业务系统/用户组名称
&emsp;&emsp;isLoop			|String		|R			|是否周期任务，0：不是，1：是
&emsp;&emsp;loopInterval	|Integer	|R			|周期间隔，单位分钟
&emsp;&emsp;param			|String		|R			|任务参数，json方式保存
&emsp;&emsp;remark			|String		|R			|备注
&emsp;&emsp;operator		|String		|R			|操作人登录名
&emsp;&emsp;opTime			|Date		|R			|操作时间

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "id": 1,
            "name": "task1",
            "type": "2",
            "state": "",
            "stateDesc": [3,0,1],
            "viewLevel": "1",
            "viewer": [{"id": 1, "name": "usergroup1"}, {"id": 2, "name": "usergroup2"}],
            "isLoop": "0",
            "loopInterval": 1,
            "param": "",
            "remark": "",
            "operator": "admin",
            "opTime": "2007-07-07 07:07:07"
        }]
    }
}
```

##### 2.4.1.2 任务详情查询

- **接口说明：** 任务详情查询
- **接口地址：** /mission/detail
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|O			|用户组id

示例：

```
GET /usergroup/detail?id=2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;id					|Integer	|R			|&nbsp;
&emsp;name					|String		|R			|任务名称
&emsp;type					|String		|R			|任务类型，1、文件推送，2、命令执行，3、升级部署
&emsp;state					|String		|R			|任务状态，周期任务有效，0、非周期任务，1、运行，2、暂停，3、终止
&emsp;stateDesc				|Integer[]	|R			|任务状态描述，成功几个失败几个等
&emsp;viewLevel				|String		|R			|查看权限 1:用户组，2：系统内全部人员，3：无限制，默认2
&emsp;viewer				|Object[]	|O			|查看人，viewLevel=1或2时有值
&emsp;&emsp;id				|Integer	|O			|业务系统/用户组id
&emsp;&emsp;name			|String		|O			|业务系统/用户组名称
&emsp;isLoop				|String		|R			|是否周期任务，0：不是，1：是
&emsp;loopInterval			|Integer	|R			|周期间隔，单位分钟
&emsp;param					|String		|R			|任务参数，json方式保存
&emsp;nodeGroups			|Object[]	|R			|节点组
&emsp;&emsp;id				|Integer	|R			|节点组id
&emsp;&emsp;name			|String		|R			|节点组名称
&emsp;nodes					|Object[]	|R			|节点
&emsp;&emsp;uuid			|Integer	|R			|节点id
&emsp;&emsp;ip				|String		|R			|节点ip
&emsp;&emsp;name			|String		|R			|节点名称
&emsp;remark				|String		|R			|备注
&emsp;operator				|String		|R			|操作人登录名
&emsp;opTime				|Date		|R			|操作时间

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "id": 1,
        "name": "task1",
        "type": "2",
        "state": "",
        "stateDesc": [3,0,1],
        "viewLevel": "1",
        "viewer": [{"id": 1, "name": "usergroup1"}, {"id": 2, "name": "usergroup2"}],
        "isLoop": "0",
        "loopInterval": 1,
        "param": "",
        "nodeGroups": [{
            "id": 1,
            "name": "hehe"
        }],
		"nodes": [{
            "uuid": 2,
            "name": "haha",
            "ip": "10.20.20.10"
        }]
        "remark": "",
        "operator": "admin",
        "opTime": "2007-07-07 07:07:07"
    }
}
```

##### 2.4.1.3 任务新增

- **接口说明：** 任务新增
- **接口地址：** /mission/save
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
name				|String			|R			|任务名称
type				|String			|R			|任务类型，1、文件推送，2、命令执行，3、升级部署
state				|String			|R			|任务状态，周期任务有效，0、非周期任务，1、运行，2、暂停，3、终止
viewLevel			|String			|R			|查看权限 1:用户组，2：系统内全部人员，3：无限制，默认2
viewerId            |Integer[]      |O          |查看人，viewLevel=1时有值，表示用户组id；viewLevel=2时，业务系统id从后台取得
isLoop				|String			|R			|是否周期任务，0：不是，1：是
loopInterval		|Integer		|R			|周期间隔，单位分钟
param				|String			|R			|任务参数，json方式保存
nodeGroupIds		|Integer[]		|R			|节点组id
nodeIds				|Integer[]		|R			|节点uuid
remark				|String			|R			|备注
commandName         |String         |O          |当type!=1时 必须有值
commandType         |String         |O          |当type!=1时 必须有值

示例：

```
{
    "name": "",
    "type": "",
    "state": "",
    "viewLevel": "",
    "isLoop": "",
    "loopInterval": 1,
    "param": "",
    "remark": "",
    "nodeGroupIds": [1,2,3],
    "nodeIds": [7,8],
    "commandName":"",
    "commandType":""
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```

##### 2.4.1.4 任务修改

- **接口说明：** 任务修改，只支持改名称、备注
- **接口地址：** /mission/update
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id
name				|String			|R			|名称
remark				|String			|O			|备注

示例：

```
{
    "id": 9,
    "name": "cab9",
    "remark": "en"
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```

##### 2.4.1.5 周期任务停用启用

- **接口说明：** 周期任务停用/启用
- **接口地址：** /mission/loopStateChange
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
ids					|Integer[]		|R			|ids
state				|String			|R			|0: 停用，1：启用

示例：

```
{
    "ids": [35],
    "state": "0"
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/?,
    "msg": "success"
}
```

##### 2.4.1.6 新增逆向任务

- **接口说明：** 获取逆向任务内容，用于升级部署任务回退。获取内容后，提交任务接口等同于2.4.1.3 任务新增
- **接口地址：** /mission/converse
- **请求方式：** GET

###### 请求参数

参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|O			|需要逆向的任务的id

示例：

```
GET /mission/converse?id=2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;id					|Integer	|R			|&nbsp;
&emsp;name					|String		|R			|任务名称
&emsp;type					|String		|R			|任务类型，1、文件推送，2、命令执行，3、升级部署
&emsp;state					|String		|R			|任务状态，周期任务有效，0、非周期任务，1、运行，2、暂停，3、终止
&emsp;stateDesc				|Integer[]	|R			|任务状态描述，成功几个失败几个等
&emsp;viewLevel				|String		|R			|查看权限 1:用户组，2：系统内全部人员，3：无限制，默认2
&emsp;viewer				|Integer[]	|R			|查看人，viewLevel为1时有值，为用户组id
&emsp;isLoop				|String		|R			|是否周期任务，0：不是，1：是
&emsp;loopInterval			|Integer	|R			|周期间隔，单位分钟
&emsp;param					|String		|R			|任务参数，json方式保存
&emsp;nodeGroups			|Object[]	|R			|节点组
&emsp;&emsp;id				|Integer	|R			|节点组id
&emsp;&emsp;name			|String		|R			|节点组名称
&emsp;nodes					|Object[]	|R			|节点
&emsp;&emsp;uuid			|Integer	|R			|节点uuid
&emsp;&emsp;ip				|String		|R			|节点ip
&emsp;&emsp;name			|String		|R			|节点名称
&emsp;remark				|String		|R			|备注
&emsp;operator				|String		|R			|操作人登录名
&emsp;opTime				|Date		|R			|操作时间

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": [{
        "id": 1,
        "name": "task1",
        "type": "2",
        "state": "",
        "stateDesc": [3,0,1],
        "viewLevel": "1",
        "viewer": "group1",
        "isLoop": "0",
        "loopInterval": 1,
        "param": "",
		"nodeGroups": [{
			"id": 1,
			"name": "hehe"
		}],
		"nodes": [{
			"uuid": 2,
			"name": "haha",
			"ip": "10.20.20.10"
		}]
        "remark": "",
        "operator": "admin",
        "opTime": "2007-07-07 07:07:07"
    }]
}
```

##### 2.4.1.7 结果查看

- **接口说明：** 查看节点的任务执行情况
- **接口地址：** /mission/result
- **请求方式：** GET

###### 请求参数

参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
id					|Integer		|R			|任务id

示例：

```
GET /mission/result?id=2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;id				|Integer	|R			|&nbsp;
&emsp;&emsp;missionId		|Integer	|R			|&nbsp;
&emsp;&emsp;node			|Object		|R			|节点
&emsp;&emsp;&emsp;uuid		|Integer	|R			|节点标识
&emsp;&emsp;&emsp;ip		|String		|R			|节点ip
&emsp;&emsp;&emsp;name		|String		|R			|节点名称
&emsp;&emsp;descr   		|String		|R			|任务结果描述信息
&emsp;&emsp;state			|String		|R			|任务执行状态
&emsp;&emsp;cycle			|Integer	|R			|第几周期
&emsp;&emsp;file			|String		|R			|回传文件路径
&emsp;&emsp;opTime			|Date		|R			|操作时间

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "id": 1,
            "missionId": 1,
            "node": {
                "uuid": 4,
                "ip": "10.20.30.40",
                "name": "node1"
            },
            "descr": "",
            "state": "",
            "cycle": 1,
            "file": "",
            "opTime": "2019-07-10 10:10:10"
        }]
    }
}
```


### 2.5 拓扑图

#### 2.5.1 拓扑图配置

##### 2.5.1.1 拓扑图列表查询

- **接口说明：** 拓扑图列表查询
- **接口地址：** /topo/list
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|O			|拓扑图id
systemId			|Integer		|O			|业务系统id

示例：

```
GET /topo/list?systemId=3
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;id				|Integer	|R			|主键
&emsp;&emsp;name			|String		|R			|拓扑图名称
&emsp;&emsp;systemId		|Integer	|R			|业务系统ID
&emsp;&emsp;width			|Integer	|R			|图片宽度
&emsp;&emsp;height			|Integer	|R			|图片高度
&emsp;&emsp;class			|String		|R			|样式
&emsp;&emsp;opTime			|Date		|R			|创建时间
&emsp;&emsp;operator		|Integer	|R			|创建人
&emsp;&emsp;remarks			|String		|R			|备注

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "list": [{
            "id": 1,
            "name": "",
            "systemId": 1,
            "width": 1,
            "height": 1,
            "class": "",
            "opTime": "2019-07-10 10:10:10",
            "operator": 1,
            "remarks": ""
        }]
    }
}
```

##### 2.5.1.2 拓扑图详情查询

- **接口说明：** 拓扑图详情查询，查出所有点、线
- **接口地址：** /topo/detail
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|拓扑图id

示例：

```
GET /topo/detail?id=2
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;id					|Integer	|R			|主键
&emsp;name					|String		|R			|拓扑图名称
&emsp;systemId				|Integer	|R			|业务系统ID
&emsp;width					|Integer	|R			|图片宽度
&emsp;height				|Integer	|R			|图片高度
&emsp;class					|String		|R			|样式
&emsp;opTime				|Date		|R			|创建时间
&emsp;operator				|Integer	|R			|创建人
&emsp;remarks				|String		|R			|备注
&emsp;topoNodes				|Object[]	|R			|拓扑节点
&emsp;&emsp;id				|Integer	|R			|拓扑节点id
&emsp;&emsp;img				|String		|R			|字典表code值，code,sys_dict 表关联，字典type=topo-img
&emsp;&emsp;type			|Integer	|R			|NODE类型 1：节点组，2：节点，3：其它 4:topo
&emsp;&emsp;typeId			|Integer	|R			|NODE对应的节点组或节点ID 当：TYPE = 1时，为节点组ID，TYPE = 2时，为节点ID，TYPE =3 时，无意义 type=4时 topo
&emsp;&emsp;x				|Integer	|R			|横坐标
&emsp;&emsp;y				|Integer	|R			|纵坐标
&emsp;&emsp;width			|Integer	|R			|图片宽度
&emsp;&emsp;height			|Integer	|R			|图片高度
&emsp;&emsp;text			|String		|R			|NODE提示文本信息
&emsp;&emsp;class			|String		|R			|样式
&emsp;&emsp;threshold		|String		|R			|阀值
&emsp;topoLines				|Object[]	|R			|拓扑连线
&emsp;&emsp;id				|Integer	|R			|主键
&emsp;&emsp;src				|Integer	|R			|线起点 TOPO_NODE_INFO 表的ID
&emsp;&emsp;dest			|Integer	|R			|线终点 TOPO_NODE_INFO 表的ID
&emsp;&emsp;class			|String		|R			|线的样式
&emsp;&emsp;text			|String		|R			|线条文本内容
&emsp;&emsp;topoId			|Integer	|R			|TOPO图ID 与TOPO_INFO关联

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "id": 1,
        "name": "",
        "systemId": 1,
        "width": 1,
        "height": 1,
        "class": "",
        "opTime": "2019-07-10 10:10:10",
        "operator": 1,
        "remarks": "",
        "topoNodes": [{
            "id": 1,
            "img": "",
            "topoId": 1,
            "type": 1,
            "typeId": 1,
            "x": 1,
            "y": 1,
            "width": 1,
            "height": 1,
            "text": "",
            "class": "",
            "threshold": ""
        }],
        "topoLines": [{
            "id": 1,
            "src": 1,
            "dest": 1,
            "class": "",
            "text": "",
            "topoId": 1
        }]
    }
}
```

##### 2.5.1.3 拓扑图节点新增

- **接口说明：** 拓扑图节点新增
- **接口地址：** /topo/saveNode
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
img					|String			|R			|字典表code值，code,sys_dict 表关联，字典type=topo-img
topoId				|Integer		|R			|topo图ID 与TOPO_INFO关联
type				|Integer		|R			|NODE类型 1：节点组，2：节点，3：其它 4:topo
typeId				|Integer		|R			|NODE对应的节点组或节点ID 当：TYPE = 1时，为节点组ID，TYPE = 2时，为节点ID，TYPE =3 时，无意义 type=4时 topo
x					|Integer		|R			|横坐标
y					|Integer		|R			|纵坐标
width				|Integer		|R			|图片宽度
height				|Integer		|R			|图片高度
text				|String			|R			|NODE提示文本信息
class				|String			|R			|样式
threshold			|String			|R			|阀值

示例：

```
{
    "img": "",
    "topoId": 1,
    "type": 1,
    "typeId": 1,
    "x": 1,
    "y": 1,
    "width": 1,
    "height": 1,
    "text": "",
    "class": "",
    "threshold": ""
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```

##### 2.5.1.4 拓扑图节点修改

- **接口说明：** 拓扑图节点修改
- **接口地址：** /topo/updateNode
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id
type				|Integer		|R			|NODE类型 1：节点组，2：节点，3：其它 4:topo
typeId				|Integer		|R			|NODE对应的节点组或节点ID 当：TYPE = 1时，为节点组ID，TYPE = 2时，为节点ID，TYPE =3 时，无意义 type=4时 topo
x					|Integer		|R			|横坐标
y					|Integer		|R			|纵坐标
width				|Integer		|R			|图片宽度
height				|Integer		|R			|图片高度
text				|String			|R			|NODE提示文本信息
class				|String			|R			|样式
threshold			|String			|R			|阀值

示例：

```
{
    "id": 1,
    "type": 1,
    "typeId": 1,
    "x": 1,
    "y": 1,
    "width": 1,
    "height": 1,
    "text": "",
    "class": "",
    "threshold": ""
}
```

##### 2.5.1.5 拓扑图节点删除

- **接口说明：** 拓扑图节点删除
- **接口地址：** /topo/deleteNode
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id

示例：

```
{
	"id": 35
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.5.1.6 拓扑图连线新增

- **接口说明：** 拓扑图连线新增
- **接口地址：** /topo/saveLine
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
src					|Integer		|R			|线起点 TOPO_NODE_INFO 表的ID
dest				|Integer		|R			|线终点 TOPO_NODE_INFO 表的ID
class				|String			|R			|线的样式
text				|String			|R			|线条文本内容
topoId				|Integer		|R			|TOPO图ID 与TOPO_INFO关联

示例：

```
{
    "src": 1,
    "dest": 1,
    "class": "",
    "text": "",
    "topoId": 1
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```

##### 2.5.1.7 拓扑图连线修改

- **接口说明：** 拓扑图节点修改
- **接口地址：** /topo/updateLine
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id
src					|Integer		|R			|线起点 TOPO_NODE_INFO 表的ID
dest				|Integer		|R			|线终点 TOPO_NODE_INFO 表的ID
class				|String			|R			|线的样式
text				|String			|R			|线条文本内容

示例：

```
{
    "id": 1,
    "src": 1,
    "dest": 1,
    "class": "",
    "text": ""
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200/xxx,
    "msg": "success"
}
```

##### 2.5.1.8 拓扑图连线删除

- **接口说明：** 拓扑图节点删除
- **接口地址：** /topo/deleteLine
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id

示例：

```
{
	"id": 35
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.5.1.9 拓扑节点静态图片列表查询

- **接口说明：** 拓扑节点静态图片列表查询，查询sys_dict表获取所有节点图片
- **接口地址：** /topo/imgList
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	

示例：

```
GET /topo/imgList
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|Object		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;code			|String		|R			|字典表的code
&emsp;&emsp;code			|String		|R			|字典表的value，图片地址

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "list": [{
            "code": "img1",
            "value": "/static/img/xxx"
        }]
    }
}
```


### 2.6 仪表盘

#### 2.6.1 仪表盘管理

##### 2.6.1.1 仪表盘列表查询

- **接口说明：** 仪表盘列表查询，data格式见附录B
- **接口地址：** /dashboard/list
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
id       			|String 		|O			|id
systemId			|Integer		|C			|业务系统id，当操作人在global下时，传这个参数可以查看其他业务系统

示例：

```
GET /dashboard/list?limit=20&page=1&systemId

```


###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;id				|Integer	|R			|主键
&emsp;&emsp;name			|String		|R			|图表标题
&emsp;&emsp;chartType		|Integer	|R			|图表类型
&emsp;&emsp;x				|Integer	|R			|x轴起点
&emsp;&emsp;y				|Integer	|R			|y轴起点
&emsp;&emsp;width			|Integer	|R			|宽
&emsp;&emsp;height			|Integer	|R			|高
&emsp;&emsp;data			|String		|R			|图表参数信息，data格式见附录B

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "id": 1,
            "name": "",
            "chartType": 1,
            "x": 1,
            "y": 1,
            "width": 1,
            "height": 1,
            "data": ""
        }]
    }
}
```


##### 2.6.1.2 仪表盘新增

- **接口说明：** 仪表盘新增，data格式见附录B
- **接口地址：** /dashboard/save
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
name				|String			|R			|图表标题
systemId			|Integer		|C			|业务系统id，global操作时传参
chartType			|Integer		|R			|图表类型
x					|Integer		|R			|x轴起点
y					|Integer		|R			|y轴起点
width				|Integer		|R			|宽
height				|Integer		|R			|高
data				|String			|R			|图表参数信息，data格式见附录B


示例：

```
{
    "name": "",
    "systemId": 1,
    "chartType": 1,
    "x": 1,
    "y": 1,
    "width": 1,
    "height": 1,
    "data": "{}"
}
```


###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
成功
{
    "code": 200,
    "msg": "success"
}
```

##### 2.6.1.3 仪表盘修改

- **接口说明：** 仪表盘修改，data格式见附录B
- **接口地址：** /dashboard/update
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|String			|R			|id
name				|String			|R			|图表标题
chartType			|Integer		|R			|图表类型
data				|String			|R			|图表参数信息，data格式见附录B

示例：

```
{
    "id": 232,
    "name": "",
    "systemId": 1,
    "chartType": 1,
    "data": "{}"
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
成功
{
    "code": 200,
    "msg": "success"
}
失败
{
    "code": xxx,
    "msg": "机柜该位置无法使用"
}
```

##### 2.6.1.4 仪表盘删除

- **接口说明：** 仪表盘删除
- **接口地址：** /dashboard/delete
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id

示例：

```
{
	"id": 35
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.6.1.5 仪表盘位置及宽高修改

- **接口说明：** 仪表盘删除
- **接口地址：** /dashboard/modifyShape
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id
x                   |Integer		|R			|x轴
y                   |Integer		|R			|y轴
width               |Integer		|R			|宽度
height              |Integer		|R			|高度

示例：

```
{
	"id": 35,
	"x": 1,
	"y": 3,
	"width": 100,
	"height":200,
	
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```


### 2.7 国际化

#### 2.7.1 国际化内容管理

##### 2.7.1.1 国际化列表查询

- **接口说明：** 仪表盘列表查询，data格式见附录B
- **接口地址：** /sys/i18n/list
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
page				|Integer		|O			|页码，为空时默认为1
limit				|Integer		|O			|每页记录数，为空时默认为10
sidx				|String			|O			|排序字段
order	 			|String 		|O			|排序方式(asc/desc)
code				|String			|O			|标识
value				|String			|O			|国际化值

示例：

```
GET /sys/i18n/list?limit=20&page=1&code=detail

```


###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;
data						|object		|R			|&nbsp;
&emsp;totalCount			|int		|R			|&nbsp;
&emsp;totalPage				|int		|R			|&nbsp;
&emsp;currPage				|int		|R			|&nbsp;
&emsp;list					|Object[]	|R			|&nbsp;
&emsp;&emsp;id				|Integer	|R			|主键
&emsp;&emsp;code			|String		|R			|i18n code
&emsp;&emsp;lang			|String		|R			|语言
&emsp;&emsp;value			|String		|R			|翻译值
&emsp;&emsp;remark			|String		|R			|备注信息

示例：

```
{
    "code": 200,
    "msg": "success",
    "data": {
        "totalCount": 1,
        "totalPage": 1,
        "currPage": 1,
        "list": [{
            "id": 1,
            "code": "",
            "lang": "",
            "value": "",
            "remark": "",
        }]
    }
}
```


##### 2.7.1.2 国际化新增

- **接口说明：** 国际化新增
- **接口地址：** /sys/i18n/save
- **请求方式：** POST

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
code				|String			|R			|i18n code
lang				|String			|R			|语言
value				|String			|R			|翻译值
remark				|String			|R			|备注信息


示例：

```
{
    "code": "lang",
    "lang": "en",
    "value": "language",
    "remark": ""
}
```


###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.7.1.3 国际化修改

- **接口说明：** 国际化修改
- **接口地址：** /sys/i18n/update
- **请求方式：** PUT

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id
code				|String			|R			|i18n code
lang				|String			|R			|语言
value				|String			|R			|翻译值
remark				|String			|R			|备注信息


示例：

```
{
    "id": 2,
    "code": "lang",
    "lang": "en",
    "value": "language",
    "remark": ""
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.7.1.4 国际化删除

- **接口说明：** 国际化删除
- **接口地址：** /sys/i18n/delete
- **请求方式：** DELETE

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id					|Integer		|R			|id

示例：

```
{
	"id": 35
}
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.7.1.5 系统语言切换

- **接口说明：** 系统语言切换
- **接口地址：** /sys/i18n/changeLang
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
lang				|String			|R			|语言

示例：

```
/sys/i18n/changeLang?lang=ru
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A
msg							|string		|R			|&nbsp;

示例：

```
{
    "code": 200,
    "msg": "success"
}
```

##### 2.7.1.6 国际化重复校验

- **接口说明：** 国际化重复校验，code+lang组合不能重复
- **接口地址：** /sys/i18n/check
- **请求方式：** GET

###### 请求参数
  
参数名称			|类型			|出现要求	|描述  
:----				|:---			|:------	|:---	
id       			|String 		|O			|唯一标识，为空表示正在新增监测类别
code				|String			|R			|名称
lang                |String         |R          |语言

示例：

```
GET /sys/i18n/check?id=5&code=delete&lang=en
```

###### 返回结果

参数名称					|类型		|出现要求	|描述  
:----						|:---		|:------	|:---	
code						|int		|R			|响应码，详见 附录A

示例：

```
{
    "code": 200,
    "msg": "success"
}
```


## 3 附录

### A 响应码说明

响应码	|说明  
:----	|:---
200		|处理成功
10xxxx	|系统错误
20xxxx	|节点管理错误
30xxxx	|监测相关错误
40xxxx	|任务相关错误
50xxxx	|dashboard相关错误
60xxxx	|图形化相关错误
999		|通用错误码

### B 仪表盘data格式说明

chartType=3：
```
{
    'color_suffix':#000000,
    'color_prefix':#000000,
    'color_value':#000000,
    'decimal':1,
    'suffix':'suffix font',
    'prefix':'prefix font',
    'suffix_font_size':0,
    'prefix_font_size':0,
    'title':'title',
    'value_font_size':15,
    'descr':'descr',
    'is_gauge':1,
    'is_threshold':1,
    'is_scale':1,
    'max_value':100,
    'min_value':0,
    'threshold':'[[0.2,"#cf1d8e"],[0.3,"#2632d4"],[0.6,"#d11b79"],[1,"#e8214f"]]',
    'series':[
        {"value": 88}
    ],
    'user_sql':'sql'
}
```

chartType=2：
```
{
    'bars':0,
    'lines':0,
    'points':0,
    'fill':1,
    'line_width'2,
    'title':'title',
    'yaxis':1,
    'xaxis':1,
    'yaxis_name':'y_name',
    'xaxis_name':'x_name',
    'legend':1,
    'legend_x_position':'center',
    'legend_y_position':'top',
    'descr':'descr',
    'series':[{
        "value": 93,
        "time": 1547433810000
    },
    {
        "value": 31,
        "time": 1547785766000
    },
    {
        "value": 92,
        "time": 1547788853000
    },
    {
        "value": 40,
        "time": 1547884173000
    }],
    'user_sql':['sql-1','sql-2','sql-3']
}
```

chartType=4：
```
{
    'font_size':15,
    'title':'title',
    'descr':'descr',
    'value_name':'value name',
    'time_name':'time name',
    'decimal':1,
    'time_format':'yyyy-MM-dd hh:mm:ss.SSS',
    'page_size':10,
    'series':[ {
        "value": 93,
        "time": 1547433810000,
        "formatTime": "19/01/14 12:00:00 上午"
    },
    {
        "value": 31,
        "time": 1547785766000,
        "formatTime": "19/01/18 12:00:00 上午"
    },
    {
        "value": 92,
        "time": 1547788853000,
        "formatTime": "19/01/18 12:00:00 上午"
    },
    {
        "value": 40,
        "time": 1547884173000,
        "formatTime": "19/01/19 12:00:00 上午"
    },
    {
        "value": 1,
        "time": 1549858348000,
        "formatTime": "19/02/11 12:00:00 上午"
    },
    {
        "value": 33,
        "time": 1549860694000,
        "formatTime": "19/02/11 12:00:00 上午"
    }],
    'user_sql':'sql'
}
```

### C 任务param格式说明
文件推送

参数名称			    |类型			|出现要求	|描述  
:----				    |:---			|:------	|:---	
fileName				|String			|R			|文件
destPath				|String			|R			|路径
userName				|String			|			|属主
groupName				|String			|			|属组
isCover				    |String			|			|是否覆盖
permisson			    |String			|			|文件权限

```
请求：
[
	{
		"fileName":"th.txt",
		"destPath":"/home/test",
		"username":"admin",
		"permisson":"777",
		"groupName":"shuqun",
		"isCover":"0"
	}
]

返回：
[
    {
        "destPath":"/home/test",
        "fileName":"nc.txt",
        "groupName":"shuqun",
        "isCover":"0",
        "md5Value":"ddeff019463ddf0fdebcd38c09693b8b",
        "permisson":"777",
        "upFileName":"nc_1564992091855.txt",
        "username":"admin"
    }
]
```
命令执行-停用进程（upgrade_kill_process）

参数名称			    |类型			|出现要求	|描述  
:----				    |:---			|:------	|:---	
pidFiles				|String			|R			|停用进程pid


```
请求：
{
	"missionLoopEntity":{
        "startTime":1564646481617,
        "endTime":1764646481617
    },
    "paramForExecuteInstruct":{
        "pidFiles":[
            "/home/pid1",
            "/home/pid2"
        ]
    }
}
返回：
{
    "commandEnname":"upgrade_kill_process",
    "commandType":1,
    "missionLoopEntity":{
        "endTime":1764646481617,
        "startTime":1564646481617
    },
    "paramForExecuteInstruct":{
        "pidFiles":[
            "/home/pid1",
            "/home/pid2"
        ]
    }
}
```
命令执行-备份（upgrade_backup）

参数名称			    |类型			|出现要求	|描述  
:----				    |:---			|:------	|:---	
cover				    |String			|R			|备份路径
source      		    |String			|R			|需要备份的文件
deleteTmpStr     		|String			|			|排除文件
isAbs    	        	|String			|			|相对/绝对路径

```
请求：
{
    "missionLoopEntity":{
        "endTime":1764646481617,
        "startTime":1564646481617
    },
    "paramForExecuteInstructs":[
        {
            "cover":"/home/aaa",
            "deleteTmpStr":"123;456;789",
            "isAbs":"1",
            "source":"/home/test"
        }
    ]
}
返回：
{
    "commandEnname":"upgrade_backup",
    "commandType":1,
    "missionLoopEntity":{
        "endTime":1764646481617,
        "startTime":1564646481617
    },
    "paramForExecuteInstructs":[
        {
            "backup":"/home/aaa",
            "backupTo":"/home/test",
            "except":["123","456","789"],
            "isAbs":"1"
        }
    ]
}
```
命令执行-覆盖更新（upgrade_update）

参数名称			    |类型			|出现要求	|描述  
:----				    |:---			|:------	|:---	
cover				    |String			|R			|备份路径
source      		    |String			|R			|需要备份的文件
deleteTmpStr     		|String			|			|排除文件
isAbs    	        	|String			|			|相对/绝对路径
isCreateCover     		|String			|			|是否创建标识

```
请求：
{
    "missionLoopEntity":{
        "endTime":1764646481617,
        "startTime":1564646481617
    },
    "paramForExecuteInstructs":[
        {
            "cover":"/home/aaa",
            "deleteTmpStr":"123;456;789",
            "isAbs":"1",
            "source":"/home/test",
            "isCreateCover":"1"
        },
        {
            "cover":"/home/bbb",
            "source":"/home/test",
            "isAbs":"0",
            "isCreateCover":"0"
        }
    ]
}
返回：
{
    "commandEnname":"upgrade_update",
    "commandType":1,
    "missionLoopEntity":{
        "endTime":1764646481617,
        "startTime":1564646481617
    },
    "paramForExecuteInstructs":[
        {
            "cover":"/home/aaa",
            "delete":["123","456","789"],
            "isAbs":"1",
            "isCreateCover":"0",
            "source":"/home/test"
        }
    ]
}
```
命令执行-可执行命令/启动任务（upgrade_exec/upgrade_start）

参数名称			    |类型			|出现要求	|描述  
:----				    |:---			|:------	|:---	
execCmd				    |String			|R			|启动文件或命令
execResult      		|String			|R			|执行结果文件
returnPath              |String			|O			|回传文件
forceExec               |String			|			|是否强制执行
residentFlag            |String			|			|是否常驻内存
returnFlag              |String			|			|回传标识
execParamsTmpStr        |String			|			|启动参数
maxWaitTime             |String			|			|最大等待时间
userName				|String			|			|属主

```
请求：
{
    "missionLoopEntity":{
        "endTime":1764646481617,
        "startTime":1564646481617
    },
    "paramForExecuteInstructs":[
        {
            "execCmd":"./start",
            "execResult":"result file",
            "forceExec":"1",
            "residentFlag":"1",
			"returnFlag":"1",
			"execParamsTmpStr":"123;456",
			"returnPath":"result return",
			"maxWaitTime":"3",
			"username":"admin"
        }
    ]
}
返回：
{
    "commandEnname":"upgrade_start",
    "commandType":1,
    "missionLoopEntity":{
        "endTime":1764646481617,
        "startTime":1564646481617
    },
    "paramForExecuteInstructs":[
        {
            "execCmd":"./start",
            "execParams":["123","456"],
            "execResult":"result file",
            "forceExec":"1",
            "maxWaitTime":"3",
            "residentFlag":"1",
            "returnFlag":"1",
            "returnPath":"result return",
            "username":"admin"
        }
    ]
}
```
命令执行-恢复（upgrade_recover）

参数名称			    |类型			|出现要求	|描述  
:----				    |:---			|:------	|:---	
cover				    |String			|R			|覆盖目录
source      		    |String			|R			|源文件或目录
deleteTmpStr     		|String			|			|排除文件
isAbs    	        	|String			|			|相对/绝对路径

```
请求：
{
    "missionLoopEntity":{
        "endTime":1764646481617,
        "startTime":1564646481617
    },
    "paramForExecuteInstructs":[
        {
            "source":"./start",
            "cover":"result file",
            "isAbs":"1",
			"deleteTmpStr":"123;456",
        }
    ]
}
返回：
{
    "commandEnname":"upgrade_recover",
    "commandType":1,
    "missionLoopEntity":{
        "endTime":1764646481617,
        "startTime":1564646481617
    },
    "paramForExecuteInstructs":[
        {
            "cover":"result file",
            "delete":["123","456"],
            "isAbs":"1",
            "source":"./start"
        }
    ]
}
```
命令执行-单次可执行命令（single_exec）

参数名称			    |类型			|出现要求	|描述  
:----				    |:---			|:------	|:---	
execCmd				    |String			|R			|执行命令
returnPath      		|String			|R			|回传文件
returnFlag              |String			|			|回传标识
maxWaitTime             |String			|			|最大等待时间
userName				|String			|			|属主

```
请求：
{
    "missionLoopEntity":{
        "endTime":1764646481617,
        "startTime":1564646481617
    },
    "paramForExecuteInstructs":[
        {
            "execCmd":"./start",
            "returnFlag":"1",
            "returnPath":"1",
			"userName":"admin",
			"maxWaitTime":"3"
        }
    ]
}
返回：
{
    "commandEnname":"single_exec",
    "commandType":2,
    "missionLoopEntity":{
        "endTime":1764646481617,
        "startTime":1564646481617
    },
    "paramForExecuteInstructs":[
        {
            "execCmd":"./start",
            "maxWaitTime":"3",
            "returnFlag":"1",
            "returnPath":"1",
            "username":"admin"
        }
    ]
}
```
升级部署-nc升级（upgrade_agent）

参数名称			    |类型			|出现要求	|描述  
:----				    |:---			|:------	|:---	
cover				    |String			|R			|覆盖/推送路径
fileName          		|String			|R			|文件
backUp                  |String			|O			|需要备份的文件
backUpTo                |String			|O			|备份路径
isAbs    	        	|String			|			|相对/绝对路径
isCreateCover     		|String			|			|是否创建标识
userName				|String			|			|属主
groupName				|String			|			|属组
permisson			    |String			|			|文件权限
deleteTmpStr     		|String			|			|删除文件
exceptTmpStr            |String			|			|排除文件

```
请求：
{
    "paramForUpgrade":
        {
            "cover":"/home/test",
            "isAbs":"1",
            "isCreateCover":"1",
			"userName":"admin",
			"deleteTmpStr":"123;456",
			"groupName":"shuqun",
			"permisson":"777",
			"fileName":"nc.txt",
			"backups":[{
				"backUp":"/home/beifen",
				"backUpTo":"/home/path",
				"isAbs":"1",
				"exceptTmpStr":"111;222"
			}]
        }
}
返回：
{
    "commandEnname":"upgrade_agent",
    "paramForUpgrade":{
        "backups":[
            {
                "backup":"/home/beifen",
                "backupTo":"/home/path",
                "except":["111","222"],
                "isAbs":"1"
            }
        ],
        "cover":"/home/test",
        "delete":["123","456"],
        "fileName":"nc.txt",
        "groupName":"shuqun",
        "isAbs":"1",
        "isCreateCover":"1",
        "md5Value":"ddeff019463ddf0fdebcd38c09693b8b",
        "permisson":"777",
        "upFileName":"nc_1564995729998.txt",
        "username":"admin"
    }
}
```
升级部署-dc升级/第三方升级（upgrade_server/upgrade_other）

参数名称			    |类型			|出现要求	|描述  
:----				    |:---			|:------	|:---	
cover				    |String			|R			|覆盖路径
fileName          		|String			|R			|文件
pidFile                 |String			|R			|PID文件
startupFile             |String			|R			|启动文件或命令
backUp                  |String			|O			|需要备份的文件
backUpTo                |String			|O			|备份路径
isAbs    	        	|String			|			|相对/绝对路径
isCreateCover     		|String			|			|是否创建标识
userName				|String			|			|属主
groupName				|String			|			|属组
permisson			    |String			|			|文件权限
deleteTmpStr     		|String			|			|排除文件
maxWaitTime             |String			|			|最大等待时间
forceExec               |String			|			|是否强制执行
execParamsTmpStr        |String			|			|启动参数
exceptTmpStr            |String			|			|排除文件

```
请求：
{
    "paramForUpgrades":
        [{
            "cover":"/home/test",
            "isAbs":"1",
            "isCreateCover":"1",
			"userName":"admin",
			"deleteTmpStr":"123;456",
			"groupName":"shuqun",
			"permisson":"777",
			"maxWaitTime":"3",
			"startupFile":"./start",
			"forceExec":"1",
			"pidFile":"test.pid",
			"fileName":"dc.txt",
			"execParamsTmpStr":"789;111",
			"backups":[{
				"backUp":"/home/beifen",
				"backUpTo":"/home/path",
				"isAbs":"1",
				"exceptTmpStr":"111;222"
			}]
        }]
}
返回：
{
    "commandEnname":"upgrade_server",
    "paramForUpgrades":[
        {
            "backups":[
                {
                    "backup":"/home/beifen",
                    "backupTo":"/home/path",
                    "except":["111","222"],
                    "isAbs":"1"
                }
            ],
            "cover":"/home/test",
            "delete":["123","456"],
            "fileName":"dc.txt",
            "forceExec":"1",
            "groupName":"shuqun",
            "isAbs":"1",
            "isCreateCover":"1",
            "maxWaitTime":"3",
            "md5Value":"f2103bbb3ad1a858c51cd2d735b4611a",
            "permisson":"777",
            "pidFile":"test.pid",
            "startupFile":"./start",
            "upFileName":"other_1564995903259.txt",
            "username":"admin"
        }
    ]
}
```
