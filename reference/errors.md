# 错误速查表

## 错误（ERR）

### 000

```
[ERR(000)] 创建机器人实例失败
[ERR(000)] 请检查网络连接，随后重启机器人
```

::: warning
这个错误码一般不会出现。遇到这个错误可能在前台进程有相关提示，请查阅 [CLI 常见问题](/starter/cli#常见问题)。
:::

机器人没有正确创建Client或WebSocket实例。
如果在排查后未找到原因，请检查网络连接，随后重启机器人。

### 002

```
[ERR(002)] 不是有效的IPC通道
```

::: warning
这个错误码一般不会出现。遇到这个错误可能是因为你没有遵循 [快速开始](/starter/quickstart) 中的步骤使用Cocotais Bot。
:::

后台进程不存在与前台进程的IPC通道。

### 004

```
[ERR(004)] 自动加载插件出现错误
```

自动加载的插件中存在问题。请查看详细的报错信息以确定问题，或尝试使用`--no-autoload`模式启动机器人。

### 005

```
[ERR(005)] 应用插件出现错误
[ERR(005)] 应用插件出现错误(运行时)
```

应用插件时发生错误。请查看详细的报错信息以确定问题并联系插件开发者解决。

### 006

```
[ERR(006)] 卸载插件出现错误
[ERR(006)] 卸载插件出现错误(运行时)
```

卸载插件时发生错误。请查看详细的报错信息以确定问题并联系插件开发者解决。

### 007

```
[ERR(007)] 重载插件(装载时)出现错误
```

重载插件时装载插件发生错误。请查看详细的报错信息以确定问题并联系插件开发者解决。

### 008

```
[ERR(008)] 重载插件(卸载时)出现错误
```

重载插件时卸载插件发生错误。请查看详细的报错信息以确定问题。

如果报错信息为`机器人未运行`，则你的机器人可能已经下线。

否则，请联系插件开发者解决。

### 009

```
[ERR(009)] 重载插件出现错误
```

请尝试手动重新加载你的插件。如出现问题，请联系开发者。

### 010

```
[ERR(010)] 连接到服务器失败
```

请查阅 [CLI 常见问题](/starter/cli#常见问题) 的`连接已死亡，请检查网络或重启`以解决。

## 警告（WARN）

### 001

```
[WARN(001)] 无法向守护进程发送保活消息
[WARN(001)] 遇到问题: TypeError
[WARN(001)] 错误信息: Cannot read property 'send' of undefined
[WARN(001)] 错误堆栈: at keepAlive (/home/cocotais/bot/node_modules/cocotais-bot/bot.js:8:13)
[WARN(001)] // == 省略 == //
```

::: warning
这个错误码一般不会出现。遇到这个警告时一般会伴随错误`[ERR(002)]`，请参阅相关错误码。
:::

后台进程无法与前台进程建立保活消息通信。

### 003

```
[WARN(003)] 不安全的执行抛出了错误
[WARN(003)] 执行函数 myFunction
[WARN(003)] 携带参数 my,func,tion
[WARN(003)] 遇到问题: TypeError
[WARN(003)] 错误信息: Cannot read property 'toString' of undefined
[WARN(003)] 堆栈信息: at myFunction (/home/cocotais/bot/plugins/my-plugin/index.js:5:15)
[WARN(003)] // == 省略 == //
```

这不会影响你的机器人执行。如果出现影响机器人执行的情况，请联系开发者。

### 011

```
[WARN(011)] 解析到未知的 WebSocket 事件
[WARN(011)] 事件名称: <AN_UNKNOWN_EVENT>
[WARN(011)] 跳过中......
```

这不会影响你的机器人执行。但是，这意味着机器人框架收到了未曾被测试过的事件，请将事件名称反馈给开发者。

### 012

```
[WARN(012)] 尝试卸载内置插件
```

一般来说，用户不应卸载内置插件。如果这不是你所期望的，说明你可能安装了一些恶意插件。请联系开发者获取帮助。
