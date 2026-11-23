---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 7%
---
# setOption

更改选项表中选项的值。

```text
setOption (name, value, description )
```

## 参数

**名称**&#x200B;选项的名称。

**值**&#x200B;选项的值。

**description**&#x200B;说明的值（可选）。

## 返回值

无。

## 备注

不同的数据类型包括：

* 文本，
* 整数，
* 浮点数，
* 日期+时间，
* 长文本

请注意，无法从API创建longText和整数类型。

对于这两种类型，您首先需要从控制台创建选项，然后可以通过setOption API管理值。

**示例：**

```javascript
               //create option of type Date+Time'
               var ourDate = getCurrentDate();
               setOption("testOptionDateTime",ourDate,"option of type Date+Time");
                              
               //create option of type Floating point'
               setOption("testOptionFloat",1,"option of type Floating point");
               
               //create option of type Text'
               setOption("testOptionText","I am a text","option of type Text");               
           
```

如果要删除描述，则需要使用空描述(setOption(name，value，&quot;))调用API。

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 类型规则
* JSSP
* SOAP方法
* WebApp
* 工作流
