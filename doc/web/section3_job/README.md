任务管理
======

## 查询条件
* 任务ID:根据输入模糊查询显示可选id列表，支持多选
* 任务名称:根据输入模糊查询显示可选任务名称列表，支持多选
* 任务类型:选择任务的类型(Hive、Shell、Java、MapReduce、Dummy)，支持多选
* 状态
    * 启用:任务可用
    * 禁用:任务禁用
    * 过期:任务设置了有效期，并且当前时间大于最大有效日期
    * 删除:任务被删除
    * 暂停:任务已暂停
* 发布者:任务的创建者
* 优先级:任务调度的优先级1(最低)-10(最高)
* 应用:发布此任务的应用，在jarvis页面提交的都未jarvis-web，第三方应用为对应的应用名
* WorkerGroup名:执行任务的分组，每个分组下必须有worker作为实际执行的机器

## 任务列表
* 默认显示任务ID、任务名、应用名、WorkerGroup名称、任务类型、业务标签、任务状态、优先级、提交人、操作等信息
* 操作中可以查看任务依赖、查看任务详情、编辑任务信息、修改任务状态。

## 新增或编辑任务
* 基本信息
    * 任务名称:任务名称，不可重复
    * 部门:此任务所属部门
    * 业务标签:此任务的业务描述，需要在
    * Worker Group:分组
    * 任务类型:当前可选Hive、Shell、Java、MapReduce、dummy
    * 内容类型:可选文本、脚本、jar包(暂不可用)
    * 任务内容:如果内容类型为文本的话可以直接输入，如果内容类型为脚本的话获取脚本的内容
    * 任务参数:任务执行所需的参数
    * 表达式类型
        * Cron表达式:
        * 固定频率:
        * 固定时延:
        * ISO8601:
    * 表达式:调度的表达式配置
    * 优先级:1(最低)-10(最高)
    * 起始日期:有效期的开始日期,不填代表无限制
    * 结束日期:有效期的结束日期,不填代表无限制
    * 失败重试数:任务执行失败的重试次数
    * 失败重试间隔:重试的时间间隔(单位为秒)
    
* 依赖任务
    * 通用策略
        * 全部成功:所依赖的任务的执行必须全部成功才能调用此任务
        * 最后一次成功:依赖的任务的执行任何一次成功就能调用此任务
        * 任何一次成功:所依赖的任务的执行最后一次必须成功才能调用此任务
    * 偏移策略
        * 通用策略的生效时间段。
        * 字母含义:c、m、h、d、w、M、y。
        * cd代表当天，也是默认的偏移参数。
        * d(-1)表示过去一天,d(1)表示未来一天,d(-2,-1)表示两天前到一天前
            
* 报警设置
    * 接收人:可以配置多个
    * 报警类型:可选短信、TT、邮件、微信，支持多选
    * 状态:启用/禁用

