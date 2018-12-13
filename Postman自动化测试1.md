### Postman自动化测试1

postman内置测试沙盒，提供了一系列现成库，该沙盒不能支持独立扩展。

**现成库有**：

1. atob->base64解码库

2. btoa->base64编码库

3. chaijs->断言库

4. cheerio->jquery核心简洁的实现库，对dom进行操作，获取

5. crypto-js->加解密库

6. csv-parse/lib/sync->csv格式解析

7. lodash->一套工具库，内部封装了很多字符串、数组、对象等常见数据类型的处理函数

8. moment->日期处理类库

9. tv4 ->检验json格式是否正确

10. uuid->uuid生成

11. xml2js->xml解析


**postman也提供了一些常用的代码片段**：

```javascript
pm.globals.unset("variable_key"); 清除全局变量
pm.environment.unset("variable_key");  清除环境变量
pm.globals.get("variable_key");      获取全局变量
pm.variables.get("variable_key");    获取一个变量
pm.environment.get("variable_key");      获取环境变量
pm.sendRequest("https://postman-echo.com/get", function (err, response) {
    console.log(response.json());
});  发送一个请求
pm.globals.set("variable_key", "variable_value");  设置环境变量

```

**基本断言**：PASS表示通过，FAIL表示断言失败

```javascript
//格式：为true则成功,false则失败
// pm.test(断言信息), () => {
//   断言判断
// })

// 响应成功
pm.test('Status code is 200', () => {
  pm.response.to.have.status(200)
})

// 响应成功 chai.expect
pm.test('Status code is 200', () => {
  chai.expect(pm.response).to.have.property('code', 200)
})

//方式二 tests["消息"]=true/false
tests["Body matches code"]=true
```

了解了上述的一些写法后我们就可以开始接口的测试了。测试用例写到Postman的Tests项中。

```javascript
//将数据解析成json格式
var data=JSON.parse(responseBody);
//获取token值
var token=data.token;
//设置成环境变量
pm.environment.set("token", token);
```



![WX20181212-120125](/Users/macos/Documents/Work/doc/marckdown/postman步步为营/images/WX20181212-120125.png)



上图：写好测试代码就点击send发送请求，查看测试结果。先解析返回的数据，判断数据是否返回正常，并判断异常状态码是否存在，存在异常状态码则断言设置为false，标记接口失败。接口返回符合预期则设置token到环境变量或者全局变量中去，让依赖的接口可以使用该参数。

**通用测试用例**

```javascript
//验证接口返回的状态码:判断jsonData.err_code等于0
tests["Check respose value err_code"] = jsonData.err_code === 0;
//接口响应时间：
tests["Response time is less than 500ms"] = responseTime < 500;
//判断Http的响应状态码是否为200
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

**前置脚本**：前置脚本可以让我们对接口做一些请求前的工作，例如对参数的参数做随机化，对参数做校验等等。

对于接口参数的随机化我整理了一篇常用脚本，内置如下全局变量：

bankNumber：银行卡号，

birthday：生日，

devince：设备，

email：邮箱，

height：身高，

weight：体重，

idcard：身份证，

nickname：姓名/昵称，

phone：手机号，

privince：省份，

sex:性别0/1，

str:字符串



1.使用步骤一：先在Pre-request Script里添加前置脚本

![WX20181212-143725](/Users/macos/Documents/Work/doc/marckdown/postman步步为营/images/WX20181212-143725.png)

2.使用步骤二：在参数中使用{{}}引用变量

![WX20181212-143621](/Users/macos/Documents/Work/doc/marckdown/postman步步为营/images/WX20181212-143621.png)



**集合测试**：每个项目的接口都不少，不可能一个个点击去测试,postman提供了集合模块测试。

![image-20181212140524539](/Users/macos/Library/Application Support/typora-user-images/image-20181212140524539.png)

![WX20181212-140613](/Users/macos/Documents/Work/doc/marckdown/postman步步为营/images/WX20181212-140613.png)

在上图我们可以选择不同的模块进行测试，也可以测试全部的接口。