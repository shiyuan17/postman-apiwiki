### Postman自动化测试2

#### 集合测试

前置脚本和测试脚本是可以复用的，每一个接口都写同一样的测试用例，维护起来不方便，postman可以在集合中编写通用的脚本。如下：

![WX20181212-141346](https://raw.githubusercontent.com/shiyuan17/postman-apiwiki/master/images/WX20181212-141346.png)

![WX20181212-141420](https://raw.githubusercontent.com/shiyuan17/postman-apiwiki/master/images/WX20181212-141420.png)

```javascript
pm.test('Status code is 200', () => {
  pm.response.to.have.status(200)
})
```



从上图中可以看出，对于通用的鉴权、前置脚本、测试脚本、变量。都可以统一设置。

#### newman 批量运行api，集成ci自动化测试

**安装及使用**：

```javascript
//安装
npm install -g newman
//运行 mycollection.json是postman导出的集合文件
newman run mycollection.json
```

newman的使用选项

-n选项设置运行集合的迭代次数

```javascript
//运行该集合10次
newman run mycollection.json -n 10
```

-e指定运行的环境的请求地址或是文件路径

```javascript
//-e指定运行的环境
newman run mycollection.json -e mycollection-environment.json
```

-r指定生成的测试报告类型，可以为html或者json。需要安装npm install newman-reporter-teamcity

