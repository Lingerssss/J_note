# Security tech onboarding

### 0.简单的背景介绍

PwC-办税/移民

### 1.开发环境

Parallel: 先拷个镜像，快速上手。

### 2.业务场景

| 网站             | 用户画像                     | 本地环境URL                     |      |
| ---------------- | ---------------------------- | ------------------------------- | ---- |
| Tiger            | Sofia: 办税/移民干活的人-PwC | https://tigerui.pwc.local/      |      |
| MymobilityHQ(HQ) | Nancy：管理Kayla业务的人     | https://mymobilityhq.pwc.local/ |      |
| Mymobility(MME)  | Kayla：需要办事的员工        | http://mypwc.pwc.local/         |      |

业务流程：Nancy 找Sofia给Kayla办事

### 3.工作流程

1.checkmarx-静态代码检测工具

检测出问题

2.Azure-board：敏捷看板

在board中开卡，做卡，结卡。

### 4.常用工具

codebase: c://workspace

| Codebase          | 业务               |
| ----------------- | ------------------ |
| myPwC             | MME                |
| myMobility        | HQ首页             |
| myMobilityApps-tw | HQ dashboard页面   |
| myMobilityApps    | HQ dashboard详情页 |
| myAccount         | Tiger/HQ登陆       |
| myID              | MME登陆            |
| Myfiles-web       |                    |
|                   |                    |
|                   |                    |



#### 脚本

- gpr: git pull rebase

- pr: 推代码

- ci：commit信息填写

- Azcli：查看pipeline

- .\go.ns.ps： build/migration

  

#### 常用工具

##### Splunk: 

用于监测生产环境下的API调用情况。删API需要在Splunk确认没有被使用。

SAST：https://pwcgms.checkmarx.net/

Username: splunk-admin

password: O4LBzA16YN3JXKUeCdiRH

##### IIS

项目服务

##### Services

系统服务

##### Log: 位于D:\pwc-tiger

错误日志

### 5.Tips

优化开发体验：

parallel设置：

- Snapshot，定期快照，方便回滚
- 可在Configure中调大分配的内存，缓解卡顿
- 可以在Option中关闭“use all displays in full screen”，方便显示器使用。

