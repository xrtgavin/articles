﻿# 对使用 C++ 异常处理应具有怎样的态度？

标签（空格分隔）： zhihu

---
问题：https://www.zhihu.com/question/22889420

可适当使用异常，但绝不要作为 error code 来使用，效率太低

适当的在无法完成操作的情况下抛出异常，并在暴露给用户的接口处对异常进行整体封装，提供简单直接的错误信息汇报给用户，即提高开发效率（只在用户接口处有 try...catch...），又做到用户友好

异常最大的好处就是**避免代码中充斥着与业务逻辑无关的错误处理代码，使得代码结构清晰简洁，提高开发效率**。

常见的错误使用异常的代码特征：

 - try...catch 在代码中满天飞，往往都是将异常作为 error code 来用了，每个调用者在调用一个可能抛异常的函数时都 try ... catch ...
 - 逐层向上 rethrow 异常
 - 在循环体内throw、catch异常





