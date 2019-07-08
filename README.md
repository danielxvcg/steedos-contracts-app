# 合同管理系统

华炎合同管理系统是国内首个全功能的开源合同管理解决方案，以合同为中心，通过合同订立、执行、监督、统计及维护跟踪，在规避法律风险的同时实现合同价值最大化。

华炎合同管理系统基于Creator“低代码”平台开发，在提供强大功能的同时，个性化定制也非常方便。系统为每一个业务对象创建的独立配置文件，包含对象的基本属性、字段、权限以及列表视图。开发人员无需编写代码，只需配置调整配置文件，即可快速满足业务部门的需求。如果实现更复杂的业务逻辑，可以为对象编写触发器，在对象新增、修改、删除时执行业务脚本。

系统基于NodeJS开发，可以部署在私有云环境中，您可以随时追加Nodejs代码以便扩充功能或是与第三方系统集成。

### 管合同

对公司所有的合同进行分类管理，包括合同的对方单位、签订日期、金额、履约状态、分类等基本信息，以及合同的应收应付、实收实付、验收状态、开票记录等相关信息。

通过[配置合同对象的业务字段](src/)，可以实现个性化的业务需求。例如对于外资企业，可以增加币种字段；对于上市公司，可以增加是否关联交易字段；对于服务类合同，可以记录合同的开始日期和结束日期。

### 管对方单位

合同台账中可以设定对方单位相关表，将公司的客户、供应商进行统一登记管理。可以记录单位的类别、优先级、基本资料以及相关的联系人等信息，可以对单位的历史信誉进行评分和评价。点击单位名称，可以查看到与此单位签订的所有合同清单、应收应付以及待办任务。新增合同时可从单位主数据库中选择，也可以创建新的单位。

### 管资金

合同台账可以设定应收应付子表，可在合同签订阶段登记合同约定的应收应付日期、合同的开票日期等信息。并在实际付款流程走完之后更新相关信息。通过对应收应付数据的统计，可以实现对未来1个月～1年的应收、应付账款进行预算，帮助财务部门做好资金准备。

### 管进度

对于合同中需要分配的任务和需要提醒的预警信息，可以配置任务子表，对每个合同创建待办任务。任务可以分派给具体的责任人，可以指定提醒日期。责任人可以在统一的界面中汇总查看来自各个合同中的待办任务，并通过月历视图浏览每个月的任务安排。

### 管权限

通过配置合同对象的权限，可以限制经办人只能查看本人负责的合同、公司主管可以查看本单位的合同，集团领导可以查看集团所有合同。对于重要字段，例如金额、对方单位、履约状态等，还可以配置审计功能，对这些字段的任何修改，系统均会自动记录审计日志。

### 管审批

通过配置合同审批流程，从合同的拟稿，部门初审，到相关部门的会审，到自动进入台账，均可自动完成。通过编写配置文件，审批单中的要素可自动映射为合同台账中的字段。开发人员还可以编写触发器，当审批单进入合同台账时进行必要的计算与处理。

### 管统计分析

通过配置合同统计报表，可以按履约状态、按日期、按分类对合同进行多维度的汇总与分析。系统支持普通的列表统计、分类统计、二维表，支持通过可视化的界面对报表样式进行排版。对于复杂需求的报表，也可以通过javascript和html编写报表模版文件，实现完全个性化的统计分析。

![界面效果图](https://steedos.github.com/docs/assets/mac_ipad_iphone_home.png)

### 安装前准备
- [Install NodeJS, v8.0.0 or later.](https://nodejs.org/en/)
- [Install MongoDB Community Server v3.4 or later](https://www.mongodb.com/download-center/community)
- [Install Visual Studio Code](https://code.visualstudio.com/)

### 安装 yarn
```
npm i yarn -g
```

### 国内建议使用npm淘宝镜像
```
npm config set registry http://registry.npm.taobao.org/
```

### 使用yarn安装依赖包
```
yarn
```

### 启动服务器
```
yarn start
```

### docker-compose方式启动服务
```
docker-compose up -d
```
如果修改了代码或者配置，执行`docker-compose build --no-cache`后，`docker-compose up -d`

### 了解更多
- [开发文档](https://steedos.github.io)
