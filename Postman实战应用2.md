### Postman实践使用2

#### 关联接口

接口与接口之间通常都不是独立的，例如，先登录才有用户信息，才有用户列表。先有列表才有某个项的详情。

**思路：**拿登录和获取用户信息来说，用户列表信息需要依赖登录接口返回的token值作为鉴权，需要先登录，登录成功后获取到用户token，使用该用户token再请求用户列表，才能拿到数据。

如登录成功后获取到如下信息：

![WX20181211-163908](/Users/macos/Documents/Work/doc/marckdown/postman步步为营/images/WX20181211-163908.png)

**方法：**postman可以使用环境变量作为动态参数，postman在接口请求完成后会执行Tests测试。我们可以在Tests测试中动态添加环境变量。示例如下：

```javascript
//将数据解析成json格式
var data=JSON.parse(responseBody);
 
//获取token值
var token=data.token;
 
//设置成环境变量
pm.environment.set("token", token);

```

![WX20181211-165113](/Users/macos/Documents/Work/doc/marckdown/postman步步为营/images/WX20181211-165113.png)

点击运行，运行成功后环境变量中就会多出token这个参数。后续使用{{token}}进行引用作为参数即可。   

如：

![WX20181211-165441](/Users/macos/Documents/Work/doc/marckdown/postman步步为营/images/WX20181211-165441.png)

->

![image-20181211165610033](/Users/macos/Library/Application Support/typora-user-images/image-20181211165610033.png)

