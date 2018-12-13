### Postman常用脚本

复制以下代码到Postman的Pre-request Script中执行会生成随机的全局变量

变量有：

1. bankNumber：银行卡号

2. birthday：生日

3. devince：设备

4. email：邮箱

5. height：身高

6. weight：体重

7. idcard：身份证

8. nickname：姓名/昵称

9. phone：手机号

10. privince：省份

11. sex:性别0/1

12. str:字符串


```javascript
// 随机整数
function getRandomNum(Min,Max)
{   
    var Range = Max - Min;   
    var Rand = Math.random();   
    return(Min + Math.round(Rand * Range));   
}   
const num = getRandomNum(1,10);

// 生成随机姓名
function getName() {
    var familyNames = new Array("赵", "钱", "孙", "李", "周", "吴", "郑", "王", "冯", "陈", "褚", "卫", "蒋", "沈", "韩", "杨", "朱", "秦", "尤", "许", "何", "吕", "施", "张", "孔", "曹", "严", "华", "金", "魏", "陶", "姜", "戚", "谢", "邹", "喻", "柏", "水", "窦", "章", "云", "苏", "潘", "葛", "奚", "范", "彭", "郎", "鲁", "韦", "昌", "马", "苗", "凤", "花", "方", "俞", "任", "袁", "柳", "酆", "鲍", "史", "唐", "费", "廉", "岑", "薛", "雷", "贺", "倪", "汤", "滕", "殷", "罗", "毕", "郝", "邬", "安", "常", "乐", "于", "时", "傅", "皮", "卞", "齐", "康", "伍", "余", "元", "卜", "顾", "孟", "平", "黄", "和", "穆", "萧", "尹", "欧阳", "上官", "司马", "南宫", "皇甫", "司空", "司徒", "慕容", "东方", "子书");
    var givenNames = new Array("子璇", "淼", "国栋", "夫子", "瑞堂", "甜", "敏", "尚", "国贤", "贺祥", "晨涛", "昊轩", "易轩", "益辰", "益帆", "益冉", "瑾春", "瑾昆", "春齐", "杨", "文昊", "东东", "雄霖", "浩晨", "熙涵", "溶溶", "冰枫", "欣欣", "宜豪", "欣慧", "建政", "美欣", "淑慧", "文轩", "文杰", "欣源", "忠林", "榕润", "欣汝", "慧嘉", "新建", "建林", "亦菲", "林", "冰洁", "佳欣", "涵涵", "禹辰", "淳美", "泽惠", "伟洋", "涵越", "润丽", "翔", "淑华", "晶莹", "凌晶", "苒溪", "雨涵", "嘉怡", "佳毅", "子辰", "佳琪", "紫轩", "瑞辰", "昕蕊", "萌", "明远", "欣宜", "泽远", "欣怡", "佳怡", "佳惠", "晨茜", "晨璐", "运昊", "汝鑫", "淑君", "晶滢", "润莎", "榕汕", "佳钰", "佳玉", "晓庆", "一鸣", "语晨", "添池", "添昊", "雨泽", "雅晗", "雅涵", "清妍", "诗悦", "嘉乐", "晨涵", "天赫", "玥傲", "佳昊", "天昊", "萌萌", "若萌");

    var i = parseInt(10 * Math.random()) * 10 + parseInt(10 * Math.random());
    var familyName = familyNames[i];

    var j = parseInt(10 * Math.random()) * 10 + parseInt(10 * Math.random());
    var givenName = givenNames[i];

    var name = familyName + givenName;

    return name;
}

//随机字符
function randomWord(randomFlag, min, max){
    var str = "",
        range = min,
        arr = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'];
 
    // 随机产生
    if(randomFlag){
        range = Math.round(Math.random() * (max-min)) + min;
    }
    for(var i=0; i<range; i++){
        pos = Math.round(Math.random() * (arr.length-1));
        str += arr[pos];
    }
    return str;
}

//生成随机手机号
function getMobleNumber() {

    var prefixArray = new Array("130", "131", "132", "133", "135", "137", "138", "170", "187", "189");
    var i = parseInt(10 * Math.random());
    var prefix = prefixArray[i];

    for (var j = 0; j < 8; j++) {
        prefix = prefix + Math.floor(Math.random() * 10);
    }

    return prefix
}

// 生成随机身份证号
function getIdCardNo() {
    var coefficientArray = ["7", "9", "10", "5", "8", "4", "2", "1", "6", "3", "7", "9", "10", "5", "8", "4", "2"]; // 加权因子
    var lastNumberArray = ["1", "0", "X", "9", "8", "7", "6", "5", "4", "3", "2"]; // 校验码
    var address = "420101"; // 住址
    var birthday = "19810101"; // 生日
    var s = Math.floor(Math.random() * 10).toString() + Math.floor(Math.random() * 10).toString() + Math.floor(Math.random() * 10).toString();
    var array = (address + birthday + s).split("");
    var total = 0;
    for (var i in array) {
        total = total + parseInt(array[i]) * parseInt(coefficientArray[i]);
    }
    var lastNumber = lastNumberArray[parseInt(total % 11)];
    var id_no_String = address + birthday + s + lastNumber;

    return id_no_String;
}

//生成随机银行卡号
function getBankNumber() {

    var bank_nos = new Array("0102","0103","0105","0301","104","0303","305","0306","0308","0410","302","315","316");
    var tmpindex = getRandomNum(0,bank_nos.length-1);
    var bank_no = bank_nos[tmpindex];
    var prefix = "";
    switch (bank_no) {
    case "0102":
        prefix = "622202";
        break;
    case "0103":
        prefix = "622848";
        break;
    case "0105":
        prefix = "622700";
        break;
    case "0301":
        prefix = "622262";
        break;
    case "104":
        prefix = "621661";
        break;
    case "0303":
        prefix = "622666";
        break;
    case "305":
        prefix = "622622";
        break;
    case "0306":
        prefix = "622556";
        break;
    case "0308":
        prefix = "622588";
        break;
    case "0410":
        prefix = "622155";
        break;
    case "302":
        prefix = "622689";
        break;
    case "304":
        prefix = "622630";
        break;
    case "309":
        prefix = "622908";
        break;
    case "310":
        prefix = "621717";
        break;
    case "315":
        prefix = "622323";
        break;
    case "316":
        prefix = "622309";
        break;
    default:
    }

    for (var j = 0; j < 13; j++) {
        prefix = prefix + Math.floor(Math.random() * 10);
    }
    
    return prefix;
}

//随机设备
function getDevice(){
    var device = ['ios', 'android'];
    var tmp = getRandomNum(0,1);
    return device[tmp];
}

//随机省份
function getProvince(){
    var proince = ['广东省','北京市','河北省','辽宁省','黑龙江省','浙江省','福建省','江西省','重庆市'];
    var tmp = getRandomNum(0,proince.length-1);
    return proince[tmp];
}

//随机日期/生日
function getBirthday(){
    var d = new Date();
    var yearLen = d.getFullYear()-1970;
    var tmp = getRandomNum(1,yearLen);
    var year = d.getFullYear() - tmp;
    
    //月
   var month =  getRandomNum(1,12);
   //日期
   var day = getRandomNum(1,28);
   return year+'-'+month+'-'+day;
}

//随机生成邮箱
function getEmail(){
    var emails = new Array("163.com","qq.com","gmail.com","21cn.com");
    var tmp = getRandomNum(0,emails.length-1);
    var str = randomWord(true, 4, 16);
    return str+'@'+emails[tmp];
}

//随机姓名
const nickname = getName();
pm.globals.set("nickname",nickname);

//随机性别
const sex = getRandomNum(0,1);
pm.globals.set("sex",sex);

//随机身高
const height = getRandomNum(120,221);
pm.globals.set("height",height);

//随机体重
const weight = getRandomNum(40,150);
pm.globals.set("weight",weight);

//随机字符串3-32位
const str = randomWord(true, 3, 32);
pm.globals.set("str",str);

//随机手机号
const phoneNumber = getMobleNumber();
pm.globals.set("phone",phoneNumber);

//随机身份证号
const idcardNumber = getIdCardNo();
pm.globals.set("idcard",idcardNumber);

//随机银行卡号
const bankNumber = getBankNumber();
pm.globals.set("bankNumber",bankNumber);

//随机设备
const devince = getDevice();
pm.globals.set("devince",devince);

//随机省份
const privince = getProvince();
pm.globals.set("privince",privince);

//随机日期
const birthday = getBirthday();
pm.globals.set("birthday",birthday);

//随机邮箱
const email = getEmail();
pm.globals.set("email",email);



```

