### Postman实践使用

1.初始项目，规划项目模块。postman collections。以Akit项目为例：

![image-20181210150524881](https://raw.githubusercontent.com/shiyuan17/postman-apiwiki/master/images/image-20181210150524881.png)

2.一般项目都会分为前台、后台、手机端三个模块。然后每个模块再细分功能区域。

![image-20181210151542807](/Users/macos/Library/Application Support/typora-user-images/image-20181210151542807.png)

3.定义环境变量。项目一般都分为开发期、测试期、线上正式期，其对应不同的api路径，通过定义环境变量的方式减少修改的成本，增加使用的便捷性。项目还有很多参数是可以复用的，也可以通过定义全局的变量以减少维护和修改的成本。

**Environment:**环境变量，一般是针对不同的开发环境设置不同的接口域名

**Globals:**全局变量，一般是通用的参数，如token等的设置。

![WX20181210-153521](https://raw.githubusercontent.com/shiyuan17/postman-apiwiki/master/images/WX20181210-153521.png)

点击add定义环境变量。

![image-20181210155738550](https://raw.githubusercontent.com/shiyuan17/postman-apiwiki/master/images/WX20181210-155510.png)

4.选择环境，通过{{}}引用环境变量。当鼠标悬浮上去的时候会有变量的详细信息显示。

![image-20181210160041456](/Users/macos/Library/Application Support/typora-user-images/image-20181210160041456.png)

5.Ctrl+s保存接口，保存后定义接口需要的参数、并对接口参数作文档说明。

操作文档支持Markdown，规范如下：

```
### 返回参数
字段       |字段类型       |字段说明
------------|-----------|-----------
name       |string        |姓名
phone    |string     |手机号码
```



![image-20181210160937553](/Users/macos/Library/Application Support/typora-user-images/image-20181210160937553.png)

![image-20181210162344963](https://raw.githubusercontent.com/shiyuan17/postman-apiwiki/master/images/image-20181210162344963.png)

