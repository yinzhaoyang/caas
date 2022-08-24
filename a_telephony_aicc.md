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

![aicc_architecture](aicc_architecture.drawio.png)

<a href="https://app.diagrams.net/#Hyinzhaoyang%2Faicc%2Fmaster%2Faicc_architecture.drawio.png" target="_blank">Edit in diagrams.net</a>