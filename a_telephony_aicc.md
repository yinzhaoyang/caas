# 说明
本文简要介绍一种中小型、单数据中心的云端智能电话呼叫管理系统的设计。如需进一步了解，可邮件咨询：jonny.yin@outlook.com

# 需求概述
+ 系统可以通过SIP与SIP Gateway对接，实现与PSTN电话号码（手机号码，固定电话号码）进行呼叫通话。
+ 系统提供AI对话机器人，实现自动对话。
+ 人工坐席可以通过浏览器接听电话，实现人工对话。
+ 系统可进行预测式外呼：即先呼叫电话号码，号码接通后再呼叫人工坐席以节省坐席占用。系统可根据人工坐席数量及号码接通率自动调整并发呼叫数量以优化人工坐席效率。
+ 对话过程中实时判断用户意图，根据意图将AI机器人对话的通话转移到人工坐席。
+ 语音的识别处理，用户意图的判断准确率满足典型场景要求。
+ 支持多租户。
+ 随着客户/用户增加，系统可通过服务扩展正常运行。
+ 系统具有高可用性。

# 架构

基于云原生开发的DevOps流程，除了aicc系统架构，下图同时展示了开发和运维架构。


![aicc_architecture](aicc_architecture.drawio.png)

<a href="https://app.diagrams.net/#Hyinzhaoyang%2Faicc%2Fmaster%2Faicc_architecture.drawio.png" target="_blank">Edit in diagrams.net</a>

## 开发架构(DEV Domain)
git -- 代码管理  
jenkins -- 编译测试部署自动化jobs管理  
jira -- 需求及开发任务管理  
conflunce -- 共享文档管理  
对于个人开发者及小团队，建议直接使用DevOps-SaaS，如[阿里云云效DevOps平台](https://devops.aliyun.com/)  


## 运维架构(OPS Domain)
运维架构基于Kubernates，具有以下优点：
+ 屏蔽不同运行环境(本地，不同云服务)差异。在本地环境可以先部署Kubernetes底座，其他云环境的Kubernate服务的部署运行基本一致。
+ Kubernates提供了强大的服务调度，配置管理能力。

## 业务系统架构

