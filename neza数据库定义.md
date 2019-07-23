# 目录

- [仪表盘信息表](#dashboard)
- [监测设置信息表](#dete_set_info)
- [监测信息节点关系表](#dete_set_node_rel)
- [监测类别信息表](#dete_type_info)
- [监测类别元数据表](#dete_type_meta)
- [监测类别元数据值映射表](#dete_type_meta_mapping)
- [监测类别参数表](#dete_type_param)
- [监测告警信息表](#dete_warn_info)
- [监测告警设置关系表](#dete_warn_rel)
- [任务信息表](#mission_info)
- [任务节点关系表](#mission_node_rel)
- [任务结果表](#mission_result)
- [机柜信息表](#node_cabinet)
- [节点节点组关系表](#node_group_rel)
- [节点信息表](#node_info)
- [机房信息表](#node_room)
- [节点组信息表](#nodegroup_info)
- [数据权限表](#permission_info)
- [系统配置表](#sys_config)
- [系统字典表](#sys_dict)
- [i18n信息表](#sys_i18n)
- [系统日志表](#sys_log)
- [系统菜单表](#sys_menu)
- [系统角色表](#sys_role)
- [系统角色菜单关系表](#sys_role_menu)
- [sequence表](#sys_sequence)
- [系统用户表](#sys_user)
- [系统用户角色关系表](#sys_user_role)
- [业务系统信息表](#system_info)
- [业务系统节点关系表](#system_node_rel)
- [业务系统用户组关系表](#system_usergroup_rel)
- [topo信息表](#topo_info)
- [topo线](#topo_line_info)
- [topo节点](#topo_node_info)
- [用户组信息表](#user_group)
- [用户用户组关系表](#user_usergroup)


#  DASHBOARD

|表名|仪表盘信息表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		    |主键	        |BIGINT(19)		|NO	|主键			|
|name		|图表标题	    |VARCHAR(255)	|NO	|图表标题			|
|system_id	|业务系统id	    |BIGINT(19)		|NO	|业务系统id			|
|chart_type	|图表类型	    |INT(10)		|NO	|图表类型			|
|x		    |x轴起点	    |INT(10)		|NO	|x轴起点			|
|y		    |y轴起点	    |INT(10)		|NO	|y轴起点			|
|width		|宽	            |INT(10)		|NO	|宽			|
|height		|高	            |INT(10)		|NO	|高			|
|data		|图表参数信息	|TEXT(65535)	|NO	|图表参数信息			|
|operator	|操作人	        |BIGINT(19)		|NO	|操作人			|
|op_time	|操作时间	    |DATETIME		|NO	|操作时间			|

#  DETE_SET_INFO

|表名|监测设置信息表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|主键			|
|name		|设置名称	|VARCHAR(255)		|NO	|设置名称，唯一索引			|
|type_id	|类别id	|BIGINT(19)		|NO	|类别id			|
|build_in	|是否内置|CHAR(255)		|NO	|1:内置，2：用户自定义，默认2			|
|params		|参数	|VARCHAR(255)		|NO	|类别定义的参数，多个逗号分隔，参数内逗号需要转义			|
|view_level	|查看权限|CHAR(1)		|NO	|1:用户组，2：系统内全部人员，3：无限制，默认2			|
|state		|状态   |CHAR(1)		|NO	|状态，1：删除，2：停止，3：监控中			|
|remark		|备注	|VARCHAR(255)		|NO	|备注			|
|i18n_code	|i18n code值	|VARCHAR(255)		|NO	| name i18n code值			|
|operator	|操作人	|BIGINT(19)		|NO	|操作人			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  DETE_SET_NODE_REL

|表名|监测信息节点关系表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id			|主键		|BIGINT(19)		|NO	|			|
|set_id		|设置id		|BIGINT(19)		|NO	|设置id			|
|type		|关联类型	|BIGINT(19)		|NO	|1、node,2、nodeGroup			|
|rel_id		|关联id		|BIGINT(19)		|NO	|关联id			|
|del_flag	|是否删除	|CHAR(1)		|NO	|是否删除，1：删除，0：未删除，默认：0			|
|operator	|操作人		|BIGINT(19)		|NO	|			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  DETE_TYPE_INFO

|表名|监测类别信息表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id			|			|BIGINT(19)		|NO	|			|
|name		|类别名称	|VARCHAR(255)		|NO	|唯一索引			|
|view_level	|查看权限	|CHAR(1)		|NO	|1:用户组，2：系统内全部人员，3：无限制，默认2			|
|method		|监控方式	|CHAR(1)		|NO	|1、脚本，2、snmp，3、内置，默认：1			|
|dete_interval	|监控间隔	|INT(10)		|NO	|监控间隔，单位：s，默认：60			|
|content	|内容		|VARCHAR(512)		|NO	|1、脚本储存路径，2、oid，可以为空，3、类全路径			|
|build_in	|是否内置	|CHAR(1)		|NO	|1、隐藏界面不显示，2、内置，不允许修改，3、用户自定义，默认3			|
|table_name	|表名		|VARCHAR(255)		|NO	|di_name,用户不在填写			|
|version	|版本号		|INT(10)		|NO	|更新version加1，默认：1			|
|i18n_code	|国际化code	|VARCHAR(255)		|NO	|name 的国际化 code，不为空时name显示翻译后的内容，为空直接显示			|
|remark		|备注	|VARCHAR(255)		|NO	|备注			|
|del_flag	|是否删除	|CHAR(1)		|NO	|是否删除，1：删除，0：未删除，默认：0			|
|operator	|操作人	|BIGINT(19)		|NO	|			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  DETE_TYPE_META

|表名|监测类别元数据表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id			|主键	|BIGINT(19)		|NO	|			|
|name		|显示名称	|VARCHAR(32)		|NO	|显示名称，唯一索引			|
|type_id	|类别id		|BIGINT(19)		|NO	|类别id			|
|field_type	|字段分类	|CHAR(1)		|NO	|字段分类，1:Tag 数据库添加索引 ,2:field 普通字段, 3:temp 临时字段，数据传输不入库, 4:cal 计算字段，根据field，temp计算得出			|
|data_type	|数据类型	|CHAR(1)		|NO	|数据类型，1:counter，需要根据上一个监测周期的数据差值计算2：gauge瞬时值 3：string 字符类型			|
|data_lenth	|数据长度	|INT(10)		|NO	|数据长度			|
|sort		|排序		|INT(10)		|NO	|排序			|
|oid		|snmp oid	|VARCHAR(128)		|NO	|snmp oid			|
|unit		|单位		|VARCHAR(32)		|NO	|单位			|
|dic_type   |字典类型   |VARCHAR(64)     |YES|与DETE_TYPE_META_MAPPING表的type关联|
|field_name	|数据库字段名称	|VARCHAR(64)		|NO	|数据库字段名称，不需要用户填写，使用name值去除特殊字符			|
|i18n_code	|国际化code	|VARCHAR(255)		|NO	|name 的国际化 code，不为空时name显示翻译后的内容，为空直接显示name			|
|remark		|备注		|VARCHAR(255)		|NO	|备注			|
|del_flag	|是否删除	|CHAR(1)		|NO	|是否删除，1：删除，0：未删除，默认：0			|
|operator	|操作人		|BIGINT(19)		|NO	|			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  DETE_TYPE_META_MAPPING

|表名|监测类别元数据值映射表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|			|
|type		|映射类型	|VARCHAR(64)		|NO	|映射类型			|
|val		|原值	|VARCHAR(256)		|NO	|原值			|
|mapping	|映射后值	|VARCHAR(255)		|NO	|映射后值			|
|del_flag	|是否删除	|CHAR(1)		|NO	|是否删除，1：删除，0：未删除，默认：0			|
|operator	|操作人	|BIGINT(19)		|NO	|			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  DETE_TYPE_PARAM

|表名|监测类别参数表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|			|
|name		|参数名称	|VARCHAR(32)		|NO	|参数名称			|
|type_id	|类别id	|BIGINT(19)		|NO	|类别id			|
|param_index|参数索引	|INT(10)		|NO	|参数索引			|
|def_val	|参数默认值	|VARCHAR(256)		|NO	|参数默认值			|
|remark		|备注	|VARCHAR(255)		|NO	|备注			|
|del_flag	|是否删除	|CHAR(1)		|NO	|是否删除，1：删除，0：未删除，默认：0			|
|operator	|操作人	|BIGINT(19)		|NO	|			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  DETE_WARN_INFO

|表名|监测告警信息表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id			|主键		|BIGINT(19)		|NO	|			|
|name		|告警名称	|VARCHAR(255)		|NO	|			|
|meta_id	|告警字段	|BIGINT(19)		|NO	|告警字段			|
|trigger	|触发方式	|CHAR(1)		|NO	|1:阈值触发,2：变化触发，当本次监测数值与上次不一致时触发，用于配置文件是否修改等,3：主动，默认：1	|
|mode		|告警模式	|CHAR(1)		|NO	|告警模式，1、单台，2、汇总			|
|stat_type	|统计方式	|CHAR(1)		|NO	|1:avg，2:count，3:sum，4:min，5:max，默认：1			|
|symbol		|符号		|CHAR(1)		|NO	|1:>，2:<，3:=，4:equals，5:include，6:exclude，默认：1			|
|threshold	|阈值		|VARCHAR(128)		|NO	|阈值			|
|tips		|告警提示信息	|VARCHAR(255)		|NO	|告警提示信息			|
|level		|告警级别	|CHAR(1)		|NO	|告警级别，1:normal，2:info，3:warning，4:error，默认：3			|
|callback_type	|回调方式	|CHAR(1)		|NO	|回调方式，0:无，1：shell，2：http，默认：0			|
|callback_content	|回调内容	|VARCHAR(255)		|NO	|回调内容			|
|view_level	|查看权限	|CHAR(1)		|NO	|1:用户组，2：系统内全部人员，3：无限制，默认2			|
|remark		|备注	|VARCHAR(255)		|NO	|备注			|
|del_flag	|是否删除	|CHAR(1)		|NO	|是否删除，1：删除，0：未删除，默认：0			|
|operator	|操作人	|BIGINT(19)		|NO	|			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  DETE_WARN_REL

|表名|监测告警设置关系表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id			|主键	|BIGINT(19)		|NO	|			|
|warn_id	|告警id	|BIGINT(19)		|NO	|告警id			|
|rel_type	|关联方式	|CHAR(1)		|NO	|关联方式，1、type，2、set			|
|rel_id		|关联id	|BIGINT(19)		|NO	|关联id			|
|del_flag	|是否删除	|CHAR(1)		|NO	|是否删除，1：删除，0：未删除，默认：0			|
|operator	|操作人	|BIGINT(19)		|NO	|			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  MISSION_INFO

|表名|任务信息表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id			|主键	|BIGINT(19)		|NO	|			|
|name		|	|VARCHAR(255)		|NO	|			|
|type		|任务类型	|CHAR(1)		|NO	|任务类型，1、文件推送，2、命令执行，3、升级部署			|
|state		|任务状态	|CHAR(1)		|NO	|任务状态，周期任务有效，0、非周期任务，1、运行，2、暂停，3、终止			|
|view_level	|查看权限	|CHAR(1)		|NO	|1:用户组，2：系统内全部人员，3：无限制，默认2			|
|is_loop	|是否周期任务	|CHAR(1)		|NO	|是否周期任务，0：不是，1：是			|
|loop_interval	|周期间隔	|INT(10)		|NO	|周期间隔，单位分钟			|
|param		|任务参数	|VARCHAR(4096)		|YES	|任务参数，json方式保存			|
|remark		|备注	|VARCHAR(255)		|NO	|备注			|
|del_flag	|是否删除	|CHAR(1)		|NO	|是否删除，1：删除，0：未删除，默认：0			|
|operator	|操作人	|BIGINT(19)		|NO	|			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  MISSION_NODE_REL

|表名|任务节点关系表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id			|主键	|BIGINT(19)		|NO	|			|
|mission_id	|任务id	|BIGINT(19)		|NO	|任务id			|
|type		|关联类型	|CHAR(1)		|NO	|关联类型，1：节点组，2：节点			|
|rel_id		|关联id	|BIGINT(19)		|NO	|关联id			|
|del_flag	|是否删除	|CHAR(1)		|NO	|是否删除，1：删除，0：未删除，默认：0			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  MISSION_RESULT

|表名|任务结果表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id			|主键	|BIGINT(19)		|NO	|			|
|mission_id	|	|BIGINT(19)		|NO	|			|
|uuid		|	|BIGINT(19)		|NO	|			|
|descr		|任务结果描述信息	|VARCHAR(1024)		|NO	|任务结果描述信息			|
|state		|任务执行状态	|CHAR(1)		|NO	|任务执行状态 1成功，2失败，3超时			|
|cycle		|第几周期	|INT(10)		|NO	|第几周期			|
|file		|回传文件路径	|VARCHAR(512)		|NO	|回传文件路径			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  NODE_CABINET

|表名|机柜信息表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id			|主键	|BIGINT(19)		|NO	|主键			|
|name		|机柜名称	|VARCHAR(255)		|NO	|机柜名称			|
|room_id	|机房id	|BIGINT(19)		|NO	|机房id			|
|room_row	|行号	|INT(10)		|NO	|行号			|
|room_col	|列号	|INT(10)		|NO	|列号			|
|ubit		|u位数量	|INT(10)		|YES	|u位数量			|
|remarks	|备注	|VARCHAR(255)		|NO	|备注			|
|operator	|操作人	|BIGINT(19)		|NO	|操作人			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  NODE_GROUP_REL

|表名|节点节点组关系表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|			|
|group_id	|节点组id	|BIGINT(19)		|NO	|节点组id			|
|uuid		|节点uuid	|BIGINT(19)		|NO	|节点uuid			|
|descr		|描述信息	|VARCHAR(128)		|NO	|描述信息			|
|operator	|操作人	|BIGINT(19)		|NO	|操作人			|
|del_flag	|是否删除	|CHAR(1)		|NO	|是否删除，1：删除，0：未删除，默认：0			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  NODE_INFO

|表名|节点信息表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id			|主键	|BIGINT(19)		|NO	|			|
|name		|名称	|VARCHAR(255)		|NO	|			|
|host_name	|主机名	|VARCHAR(255)		|NO	|主机名			|
|ip			|ip		|VARCHAR(255)		|NO	|主机名			|
|ip_long	|ip整形	|BIGINT(19)		|NO	|ip整形			|
|uuid		|全局唯一	|BIGINT(19)		|NO	|全局唯一			|
|type		|设备类型	|CHAR(1)		|NO	|设备类型，1、server,2、net			|
|tag		|设备标签	|varchar(32)	|YES|设备标签，sys_dict code 值			|
|user_name	|snmpv3 用户名	|VARCHAR(128)		|NO	|snmpv3 用户名			|
|password	|snmpv3 密码	|VARCHAR(128)		|NO	|snmpv3 密码			|
|state		|设备状态	|CHAR(1)		|NO	|设备状态，1：在线，2：下线，3：删除			|
|cabinet_id	|机柜id	|BIGINT(19)		|NO	|机柜id			|
|u_size		|u位大小	|INT(10)		|NO	|u位大小			|
|cabinet_start	|机柜起始位置	|INT(10)		|NO	|机柜起始位置			|
|snmp_port	|snmp默认端口号	|INT(10)		|NO	|snmp默认端口号			|
|snmp_community	|snmp团体字	|VARCHAR(32)		|NO	|snmp团体字			|
|remark		|备注	|VARCHAR(255)		|NO	|备注			|
|operator	|操作人	|BIGINT(19)		|NO	|			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  NODE_ROOM

|表名|机房信息表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id			|主键	|BIGINT(19)		|NO	|主键			|
|name		|机房名称	|VARCHAR(255)		|NO	|机房名称			|
|room_rows	|行数	|INT(10)		|NO	|行数			|
|room_cols	|列数	|INT(10)		|NO	|列数			|
|addr		|地区	|BIGINT(19)		|YES	|地区			|
|remarks	|备注	|VARCHAR(255)		|NO	|备注			|
|operator	|操作人	|BIGINT(19)		|NO	|操作人			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  NODEGROUP_INFO

|表名|节点组信息表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id			|主键	|BIGINT(19)		|NO	|			|
|name		|	|VARCHAR(255)		|NO	|			|
|system_id	|	|BIGINT(19)		|NO	|			|
|pid		|父id	|BIGINT(19)		|NO	|默认0			|
|pids		|所有父id	|VARCHAR(1024)		|NO	|默认0，逗号分隔		|
|remark		|备注	|VARCHAR(255)		|NO	|备注			|
|del_flag	|是否删除	|CHAR(1)		|NO	|是否删除，1：删除，0：未删除，默认：0			|
|operator	|操作人id	|BIGINT(19)		|NO	|操作人id			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  PERMISSION_INFO

|表名|数据权限表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|			|
|type		|类型	|CHAR(1)		|NO	|1、dete_type,2、dete_set,3、dete_warn,4、mission			|
|type_id	|类型id	|BIGINT(19)		|NO	|类型id			|
|view_level	|查看权限	|CHAR(1)		|NO	|1:用户组，2：系统内全部人员，3：无限制，默认2			|
|rel_id		|关联id	|BIGINT(19)		|NO	|关联id			|
|del_flag	|是否删除	|CHAR(1)		|NO	|是否删除，1：删除，0：未删除，默认：0			|
|operator	|操作人	|BIGINT(19)		|NO	|操作人			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  SYS_CONFIG

|表名|系统配置表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|			|
|param_key	|key	|VARCHAR(50)		|YES	|key			|
|param_value	|value	|VARCHAR(2000)		|YES	|value			|
|status		|状态	|TINYINT(3)		|YES	|状态   0：隐藏   1：显示			|
|remark		|备注	|VARCHAR(500)		|YES	|备注			|

#  SYS_DICT

|表名|系统字典表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|			|
|name		|字典名称	|VARCHAR(100)		|NO	|字典名称			|
|type		|字典类型	|VARCHAR(100)		|NO	|字典类型			|
|code		|字典码	|VARCHAR(100)		|NO	|字典码			|
|value		|字典值	|VARCHAR(1000)		|NO	|字典值			|
|i18n_code	|i18n code	|VARCHAR(255)		|NO	|i18n code			|
|order_num	|排序	|INT(10)		|NO	|排序			|
|remark		|备注	|VARCHAR(255)		|NO	|备注			|
|del_flag	|删除标记	|TINYINT(3)		|NO	|删除标记  1：删除，0：未删除			|
|operator	|操作人	|BIGINT(19)		|NO	|操作人			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  SYS_I18N

|表名|i18n信息表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|主键			|
|code		|i18n code	|VARCHAR(255)		|NO	|i18n code			|
|lang		|语言	|VARCHAR(16)		|NO	|语言			|
|value		|翻译值	|VARCHAR(1024)		|NO	|翻译值			|
|remark		|备注信息	|VARCHAR(255)		|NO	|备注信息			|
|operator	|操作人	|BIGINT(19)		|NO	|操作人			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  SYS_LOG

|表名|系统日志表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|			|
|username	|用户名	|VARCHAR(50)		|YES	|用户名			|
|operation	|用户操作	|VARCHAR(50)		|YES	|用户操作			|
|method		|请求方法	|VARCHAR(200)		|YES	|请求方法			|
|params		|请求参数	|VARCHAR(5000)		|YES	|请求参数			|
|time		|执行时长(毫秒)	|BIGINT(19)		|NO	|执行时长(毫秒)			|
|ip		|IP地址	|VARCHAR(64)		|YES	|IP地址			|
|message	|响应内容	|VARCHAR(4096)		|YES	|响应内容			|
|create_date	|创建时间	|DATETIME		|YES	|创建时间			|

#  SYS_MENU

|表名|系统菜单表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|menu_id	|	|BIGINT(19)		|NO	|			|
|parent_id	|父菜单ID，一级菜单为0	|BIGINT(19)		|NO	|父菜单ID，一级菜单为0			|
|parent_ids	|所有父id	|VARCHAR(1024)		|NO	|所有父id			|
|name		|菜单名称	|VARCHAR(50)		|NO	|菜单名称			|
|url		|菜单URL	|VARCHAR(200)		|YES	|菜单URL			|
|perms		|授权	|VARCHAR(500)		|YES	|授权(多个用逗号分隔，如：user:list,user:create)			|
|type		|类型	|NO	|类型   0：目录   1：菜单   2：按钮			|
|icon		|菜单图标	|VARCHAR(50)		|YES	|菜单图标			|
|order_num	|排序	|INT(10)		|NO	|排序			|
|i18n_code	|name 国际化 code	|VARCHAR(255)		|NO	|name 国际化 code			|

#  SYS_ROLE

|表名|系统角色表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|role_id	|	|BIGINT(19)		|NO	|			|
|role_name	|角色名称	|VARCHAR(100)		|YES	|角色名称			|
|remark		|备注	|VARCHAR(100)		|YES	|备注			|
|create_time	|创建时间	|DATETIME		|YES	|创建时间			|
|i18n_code	|国际化code	|VARCHAR(255)		|NO	|国际化code			|

#  SYS_ROLE_MENU

|表名|系统角色菜单关系表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|			|
|role_id	|角色ID	|BIGINT(19)		|YES	|角色ID			|
|menu_id	|菜单ID	|BIGINT(19)		|YES	|菜单ID			|

#  SYS_SEQUENCE

|表名|sequence表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|NAME		|序号名称	|VARCHAR(50)		|NO	|序号名称			|
|CURRENT_VALUE	|值	|BIGINT(19)		|NO	|值			|
|INCREMENT	|每次递增数	|INT(10)		|NO	|每次递增数			|

#  SYS_USER

|表名|系统用户表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|user_id	|	|BIGINT(19)		|NO	|			|
|username	|用户名	|VARCHAR(50)		|NO	|用户名			|
|password	|密码	|VARCHAR(100)		|YES	|密码			|
|salt		|盐	|VARCHAR(20)		|YES	|盐			|
|email		|邮箱	|VARCHAR(100)		|YES	|邮箱			|
|status		|状态	|TINYINT(3)		|YES	|状态  0：禁用   1：正常			|
|create_time	|创建时间	|DATETIME		|YES	|创建时间			|
|lang		|默认语言	|BIGINT(19)		|YES	|默认语言			|

#  SYS_USER_ROLE

|表名|系统用户角色关系表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|			|
|user_id	|用户ID	|BIGINT(19)		|YES	|用户ID			|
|role_id	|角色ID	|BIGINT(19)		|YES	|角色ID			|

#  SYSTEM_INFO

|表名|业务系统信息表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|编号	|BIGINT(19)		|NO	|编号			|
|name		|系统名称	|VARCHAR(255)		|NO	|系统名称			|
|built_in	|是否内置	|INT(10)		|NO	|是否内置，内置不可删除，1：内置，0：非内置			|
|create_by	|创建者	|BIGINT(19)		|NO	|创建者			|
|create_date	|创建时间	|DATETIME		|NO	|创建时间			|
|update_by	|更新者	|BIGINT(19)		|NO	|更新者			|
|update_date	|更新时间	|DATETIME		|NO	|更新时间			|
|remarks	|备注信息	|VARCHAR(255)		|YES	|备注信息			|
|del_flag	|删除标记	|INT(10)		|NO	|删除标记			|

#  SYSTEM_NODE_REL

|表名|业务系统节点关系表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|			|
|system_id	|业务系统id	|BIGINT(19)		|NO	|业务系统id			|
|uuid		|节点uuid	|BIGINT(19)		|NO	|节点uuid			|
|operator	|操作人	|BIGINT(19)		|NO	|操作人			|
|del_flag	|是否删除	|CHAR(1)		|NO	|是否删除，1：删除，0：未删除，默认：0			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  SYSTEM_USERGROUP_REL

|表名|业务系统用户组关系表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|主键			|
|system_id	|业务系统id	|BIGINT(19)		|NO	|业务系统id			|
|usergroup_id	|用户组id	|BIGINT(19)		|NO	|用户组id			|
|del_flag	|删除标识	|CHAR(1)		|NO	|删除标识，1：删除，0：未删除			|
|operator	|操作人	|BIGINT(19)		|NO	|操作人			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  TOPO_INFO

|表名|topo信息表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|主键			|
|name		|拓扑图名称	|VARCHAR(255)		|NO	|拓扑图名称			|
|system_id	|业务系统ID	|BIGINT(19)		|YES	|业务系统ID			|
|width		|图片宽度	|INT(10)		|NO	|图片宽度			|
|height		|图片高度	|INT(10)		|NO	|图片高度			|
|class		|样式	|VARCHAR(255)		|NO	|样式			|
|op_time	|创建时间	|DATETIME		|NO	|创建时间			|
|operator	|创建人	|BIGINT(19)		|NO	|创建人			|
|remarks	|备注	|VARCHAR(255)		|YES	|备注			|
|del_flag	|删除标识	|CHAR(1)		|NO	|0：未删除，1：删除，默认：0			|

#  TOPO_LINE_INFO

|表名|topo线|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|INT(10)		|NO	|主键			|
|src		|线起点 TOPO_NODE_INFO 表的ID	|INT(10)		|YES	|线起点 TOPO_NODE_INFO 表的ID			|
|dest		|线终点 TOPO_NODE_INFO 表的ID	|INT(10)		|YES	|线终点 TOPO_NODE_INFO 表的ID			|
|class		|线的样式	|VARCHAR(256)		|YES	|线的样式			|
|text		|线条文本内容	|VARCHAR(64)		|YES	|线条文本内容			|
|topo_id	|TOPO图ID	|INT(10)		|YES	|TOPO图ID 与TOPO_INFO关联			|
|operator	|创建人	|BIGINT(19)		|NO	|创建人			|
|op_time	|创建时间	|DATETIME		|NO	|创建时间			|
|del_flag	|删除标识	|CHAR(1)		|NO	|0：未删除，1：删除，默认：0			|

#  TOPO_NODE_INFO

|表名|topo节点|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|主键			|
|img		|图片	|VARCHAR(32)		|YES	|字典表code值，code,sys_dict 表关联，字典type=topo-img			|
|topo_id	|topo图ID	|BIGINT(19)		|YES	|topo图ID 与TOPO_INFO关联			|
|type		|NODE类型	|INT(10)		|YES	|NODE类型 1：节点组，2：节点，3：其它 4:topo			|
|type_id	|关联id	|INT(10)		|YES	|NODE对应的节点组或节点ID 当：TYPE = 1时，为节点组ID，TYPE = 2时，为节点ID，TYPE =3 时，无意义 type=4时 topo			|
|x			|x轴	|INT(10)		|YES	|			|
|y			|y轴	|INT(10)		|YES	|			|
|width		|图片宽度	|INT(10)		|YES	|图片宽度			|
|height		|图片高度	|INT(10)		|YES	|图片高度			|
|text		|NODE提示文本信息	|VARCHAR(256)		|YES	|NODE提示文本信息			|
|class		|样式	|VARCHAR(512)		|YES	|样式			|
|threshold	|阀值	|DOUBLE(4)		|YES	|阀值			|
|operator	|创建人	|BIGINT(19)		|NO	|创建人			|
|op_time	|创建时间	|DATETIME		|NO	|创建时间			|
|del_flag	|删除标识	|CHAR(1)		|NO	|0：未删除，1：删除，默认：0			|

#  USER_GROUP

|表名|用户组信息表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|主键			|
|name		|用户组名称	|VARCHAR(255)		|NO	|用户组名称			|
|remark		|备注信息	|VARCHAR(255)		|NO	|备注信息			|
|operator	|操作人	|BIGINT(19)		|NO	|操作人			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|

#  USER_USERGROUP

|表名|用户--用户组关系表|
|---|---- |
|功能||
|说明||

|字段名|中文说明|数据类型|是否可空|备注|
|----|----|----|----|----|
|id		|主键	|BIGINT(19)		|NO	|主键			|
|user_id		|用户ID |BIGINT(19)		|NO	|用户ID			|
|group_id		|用户组ID	|BIGINT(19)		|NO	|用户组ID			|
|del_flag	|删除标识	|CHAR(1)		|NO	|删除标识，1：删除，0：未删除			|
|operator	|操作人	|BIGINT(19)		|NO	|操作人			|
|op_time	|操作时间	|DATETIME		|NO	|操作时间			|