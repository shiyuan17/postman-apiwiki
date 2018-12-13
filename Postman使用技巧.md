### Postman使用技巧

#### 技巧1：postman+chrome Interceptor插件实现抓取网页请求[插件](https://chrome.google.com/webstore/detail/postman-interceptor/aicmkgpgakddgnaphhhpliifpcfhicfo/)

注意：目前只支持postman for chrome[地址](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop/related?hl=en) ,chrome app没有找到相关的功能。   

使用方式：   

1.下载安装chrome interceptor插件。[地址](https://chrome.google.com/webstore/detail/postman-interceptor/aicmkgpgakddgnaphhhpliifpcfhicfo)

![image-20181210143052920](/Users/macos/Documents/Work/doc/marckdown/postman步步为营/images/image-20181210143052920.png)

2.开启RequestCapture。设置为ON。Filter requests是为过滤规则。可以设置过滤的域名。

3.从postman for chrome的地址中启动postman。设置右上角的Interceptor为开启状态。

![image-20181210143318164](/Users/macos/Library/Application Support/typora-user-images/image-20181210143318164.png)

4.在网页上浏览操作就可以将请求捕获到History列表中了。方便对接口进行测试与记录。

![postman gif](/Users/macos/Documents/Work/doc/marckdown/postman步步为营/images/postman gif.gif)



#### 技巧二

接口调试可以使用console.log()打印信息。使用postman console可以查看调试信息及接口请求信息。

![WX20181212-144437](/Users/macos/Documents/Work/doc/marckdown/postman步步为营/images/WX20181212-144437.png)

![WX20181212-144522](/Users/macos/Documents/Work/doc/marckdown/postman步步为营/images/WX20181212-144522.png)