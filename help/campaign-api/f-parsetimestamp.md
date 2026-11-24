---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 9%
---
# parseTimeStamp

将包含根据ISO 8601标准的简化版本制定的日期的字符串转换为Date类型对象。

```text
parseTimeStamp (aString)
```

## 参数

**aString**&#x200B;日期作为ISO 8601格式的字符串。

## 返回值

匹配日期集作为参数的日期类型对象。

## 备注

语法如下：

```javascript
              date
              time[time-zone]
            
```

或者

```javascript
              dateTtime[time-zone]
            
```

日期必须具有以下格式：

```javascript
YYYY-MM-DD
```

出于兼容性原因，还接受以下格式：

```javascript
YYYY/MM/DD
```

时间必须具有以下格式：

```javascript
hh:mm:ss
hh:mm:ss.nnn
```

时区（如果已指定）必须具有以下格式：

```javascript
Z
+hh:mm
-hh:mm
+hh
-hh
```

如果未指定时区，日期将转换为当前时区（具体取决于上下文）。 示例：

```javascript
2005-03-02 00:00:00
2005-03-02
2005-03-02T14:32:26
2005-03-02T14:32:26.0000
2005-03-02T14:32:26.0000000+01:00
2005-03-02T14:32:26+01:00
2005-03-02T14:32:26Z
2005-03-02T14:32:26.0005Z
2005/03/02 14:32:25
```

如果日期格式无效，则会引发异常。

## 功能

**可用位置：**

* 内容管理
* 投放属性
* 投放消息
* 类型规则
* 导入
* JSSP
* SOAP方法
* WebApp
* 工作流
