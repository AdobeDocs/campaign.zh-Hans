---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 37%
---
# 注册组

将选定的收件人添加到列表

```text
RegisterGroup ( XML groupList, XML recipientList, Boolean register )
```

## 参数

**groupList**&#x200B;列表

**recipientList**&#x200B;收件人列表

**注册**&#x200B;订阅/取消订阅收件人

## 返回值

无。

## 示例

```javascript
//List
var entity = <entityList><key value="24447964"/>
              <where>
                <condition enabledIf="" expr="@id = 24447964"/>
              </where>
            </entityList>
 
//Recipient
var choice = <choiceList><key value="18995462"/>
              <where>
                <condition enabledIf="" expr="@id = 18995462"/>
              </where>
            </choiceList>
nms.recipient.RegisterGroup(entity,choice,true)
        
```

## 功能

**架构：** [nms:recipient](s-nms-recipient.md)

**静态：**

是
