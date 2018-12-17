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
    var str = "";
    var range = min;
    var arr = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'];
 
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

//随机文本
function getRandomText(){
    var texts = ['要使整个人生都过得舒适、愉快，这是不可能的，因为人类必须具备一种能应付逆境的态度','只有把抱怨环境的心情，化为上进的力量，才是成功的保证','少而好学，如日出之阳；壮而好学，如日中之光；志而好学，如炳烛之光。','既然我已经踏上这条道路，那么，任何东西都不应妨碍我沿着这条路走下去。','思念乘风而去，化作不朽的光辉，流至遥远的彼方，淌于陨落的星河。','人生自是有情痴，此恨不关风与月','世界上最远的距离不是生与死的距离而是我站在你的面前你却不知道我爱你','此情可待成追忆，只是当时已惘然','鸿雁在云鱼在水，惆怅此情难寄','一场寂寞凭谁诉。算前言，总轻负','琵琶起舞换新声，总是关山旧别情。撩乱边愁听不尽，高高秋月照长城','葡萄美酒夜光杯，欲饮琵琶马上催。醉卧沙场君莫笑，古来征战几人回','黄河远上白云间，一片孤城万仞山','北风卷地白草折，胡天八月即飞雪','尝试把自己放在对方的立场，当你感觉受到伤害时，很有可能他也在是被伤害。','苍茫大地一剑尽挽破，何处繁华笙歌落。斜倚云端千壶掩寂寞，纵使他人空笑我','听弦断，断那三千痴缠。坠花湮，湮没一朝风涟。花若怜，落在谁的指尖','这次我离开你，是风，是雨，是夜晚；你笑了笑，我摆一摆手，一条寂寞的路便展向两头了。','终于为那一身江南烟雨覆了天下，容华谢后，不过一场，山河永寂','看那天地日月，恒静无言；青山长河，世代绵延；就像在我心中，你从未离去，也从未改变。','环境靠你我他保护，美景由深圳人共赏','全球变暖是由汽车排气，工厂废气，森林毁坏等原因引起的','这时，天色逐渐暗下来了，大地笼罩着一片朦胧的夜色。月亮姑娘悄悄地露出了那圆圆的笑脸，俯视着辽阔的大地。村庄山川田野，好象一座逼真的玉雕，庄严而美丽。奔腾一天的小河，在皎洁的月光下慢慢的流淌。晚风吹来，波光粼粼，就像无数小鱼在水面追逐跳跃欢腾。河边有许多人在那里乘凉，轻松而闲适。孩子们在这月白风清的夜晚下捉迷藏……连歌声笑声说话声也像月亮那样轻柔和谐。','晚上，闲来无事，实在无聊，于是一个人就漫步学校后面的小树林中，独自去享受那夜色之美。抬头望着寂静的夜空，可爱的月亮从树梢后慢慢地爬上半空，光亮圆润，像一块玉琢的盘子。温柔的月光如流水般倾泻而下，仿佛滑过一曲悦耳的琴声','淡淡的月光下，几位小孩在玩耍，那月光照在头发上，使头发好象镀了一层银色的花边','细细密密的月光就像一封封飘飞的“星际特快专递”，那是嫦娥姐姐邀请地球上的小朋友去月宫分享她亲手制作的桂花糕','十五的月亮，又升上了天空。看，一轮明月在深蓝色的天空中微笑着看着大地，大地上一片洁白，好似笼着轻纱','深邃的夜，有了月亮的存在，星星都变得暗淡了。多少人都赞美月亮的美好，而旁边的星星，却总被人忽视和遗忘。的确，一颗星星的光芒，又怎能比得上月亮的光辉呢？在月亮的旁边，星星显得好渺小，微不足道','适逢中秋之夜，我仰望天空，望见一轮圆月，但不是我们常说的一轮皎洁的圆月，天空中有层层清云，如烟似雾，弥蒙在月光下。月晕恰恰是这圆月与清云的红娘，牵于二者之间，淡淡的点上一圈，既不喧宾夺主，又有万般娇态','月牙儿，像把梳子挂在半空。人们都说月亮是位最善良最好伤心和最易受感动的姑娘。谁有什么不幸和哀愁，她总是怜悯地注视着你，有时还会流下泪来！想必她这时是不忍心去看那不幸的人们吧？所以才掩住半个脸；但她那朦胧的淡光，还是同情地从窗户棂间射进来。黑暗的屋子，也变得灰白起来','当她走下那山坡，一片淡清清的月光，洒到她底身脸上来。弯弯的一角新月牙，正在天西垂挂着，距离月尾不远正缀着那颗闪亮的小星星','中秋节的月在小区里显得格外灿烂明亮。安安静静的小区愈发让月亮现出了本色。天空中稀稀拉拉几颗星星，那微弱的光忽闪忽闪，只配在月亮的下面作一个普通人。那月亮好象在说：“哼哼，想和我比，天空惟我独尊！”皎洁的月光泻在树上，把树披上了银纱，轻薄飘逸','我的梦萦绕在淡墨浅韵的江南水乡，我的情遗落在细雨霏霏的江南雨巷，杏花烟雨的街头，弥漫着一帘疏雨的芳香，撑一把油纸伞，从唐风宋雨里出发，轻轻的，轻轻的走进我百折千回的天堂。','流年的秋季，离别的场景，还一一浮现于眼前。萧瑟的秋风吹散所有的缠缠绵绵，枫叶飘飘，落英缤纷，掩盖了一地的心碎！看着愈渐模糊的背影，欲想挽留却泛发无力，泪滑落，心凄然！任凭其颤颤巍巍的身影就这样渐行渐远....','别在树下徘徊，别在雨中沉思，别在黑暗中落泪。向前看，不要回头，只要你勇于面对抬起头来，就会发现，分数的阴霾不过是短暂的雨季。向前看，还有一片明亮的天，不会使人感到彷徨。','在意，所以依恋，失去，才想起珍惜。那摇曳的红花，娇艳千般，那起舞的柔柳，风情万种，在眼前，在身边，又何曾在心里?牵手时，嘘寒送暖寻常事，再堪首，颦眉含笑梦中人，痛憾，更是怆伤。','细雨漫不经心的挥洒着，此岸，彼岸，相望亦牵挂。细雨漫不经心的挥洒着，雨水剪不断，情丝亦相连，那一段段真真切切被搁浅的逝事，在时光的剪影里缓缓地流走'];
    var tmp = getRandomNum(0,texts.length-1);
    return texts[tmp];
}

//获取英文文本
function getEnglishText(){
    var arrys = ['Whatever is worth doing is worth doing well.','Happiness is a way station between too much and too little','In love folly is always sweet','The hard part isn’t making the decision. It’s living with it.','Your happy passer-by all knows, my distressed there is no place hides','You may be out of my sight, but never out of my mind','Love is not a maybe thing. You know when you love someone','In the end, it’s not the years in your life that count. It’s the life in your years','When the whole world is about to rain, let’s make it clear in our heart together','It’s better to be alone than to be with someone you’re not happy to be with','Life is a journey, not the destination, but the scenery along the should be and the mood at the view.','Time goes by so fast, people go in and out of your life. You must never miss the opportunity to tell these people how much they mean to you','I lied when I said I didn’t like you. I lied when I said I didn’t care. I lie every time I try to tell myself I will never fall for you','One needs 3 things to be truly happy living in the world: some thing to do, some one to love, some thing to hope for.','No matter how bad your heart has been broken, the world doesn’t stop for your grief. The sun comes right back up the next day','Accept what was and what is, and you’ll have more positive energy to pursue what will be.','Until you make peace with who you are, you’ll never be content with what you have.','If you would hit the mark, you must aim a little above it. Every arrow that flies feels the attraction of earth. －Henry Wadsworth Longfellow.','If you wish to succeed, you should use persistence as your good friend, experience as your reference, prudence as your brother and hope as your sentry','I’ll think of you every step of the way.',"If you fail, don't forget to learn your lesson.",'Who shuts love out, in turn shall be shut out from love.','A guy who whispers in your ears, saying ” It’s alright, I’m here.” Holds you when you’re sad, and treasures everything about you. That’s the guy I want to give my heart to','Success is the ability to go from one failure to another with no loss of enthusiasm','f you find a path with no obstacles, it probably doesn’t lead anywhere','When there’s no expectation, losing won’t bring hurt, gaining makes you surprised','Getting out of bed in winter is one of life’s hardest mission','Dream what you want to dream; go where you want to go; be what you want to be, because you have only one life and one chance to do all the things you want to do','oday, give a stranger one of your smiles. It might be the only sunshine he sees all day','I can make it through the rain. I can stand up once again on my own','You can’t have a better tomorrow if you don’t stop thinking about yesterday','I love it when I catch you looking at me then you smile and look away',"Don't cry because it is over, smile because it happened."];
    var tmp = getRandomNum(0,arrys.length-1);
    return arrys[tmp];
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

//随机城市
function getCity(){
    var citys = ['上海市','哈尔滨市','天津市','长治市','娄底市','辽阳市','咸阳市','舟山市','茂名市','襄阳市','衢州市','孝感市','扬州市','广州市','清远市','北京市','岳阳市','宁波市','绍兴市','嘉义市','郴州市','台州市','周口市','乐山市','咸阳市','莆田市','南京市','苏州市','徐州市','金华市'];
    var tmp = getRandomNum(0,citys.length-1);
    return citys[tmp];
}

//随机县/区域
function getArea(){
    var areas = ['云梦县','伊吾县','滨海县','桂东县','泾源县','德安县','岑巩县','尼木县','莲花县','武城县','灵石县','高陵县','株洲县','香河县','马山县','舟曲县','余江县','册亨县','平南县','曲松县','永宁县'];
    var tmp = getRandomNum(0,areas.length-1);
    return areas[tmp];
}

//随机范围区域
function getRegion(){
    var regions = ['华中','华南','西南','东北','华北','华中','华东','西北'];
    var tmp = getRandomNum(0,regions.length-1);
    return regions[tmp];
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
    str = str.toLowerCase();
    return str+'@'+emails[tmp];
}

//随机省市区
function privinceCityArea(){
    var arrs = new Array("江西省 萍乡市 湘东区","山西省 晋城市 高平市","黑龙江省 绥化市 望奎县","江苏省 扬州市 高邮市","广东省 惠州市 惠东县","山西省 吕梁市 汾阳市","吉林省 延边朝鲜族自治州 龙井市","福建省 泉州市 泉港区","台湾 高雄市 仁武区","上海 上海市 徐汇区","甘肃省 酒泉市 敦煌市","广东省 清远市 连南瑶族自治县","辽宁省 葫芦岛市 建昌县","湖北省 宜昌市 宜都市","河南省 焦作市 济源市","江苏省 泰州市 兴化市","山东省 德州市 平原县","广西壮族自治区 梧州市 龙圩区","山西省 运城市 稷山县","青海省 海南藏族自治州 贵南县","甘肃省 临夏回族自治州 康乐县","黑龙江省 牡丹江市 林口县","湖北省 荆州市 监利县","湖北省 恩施土家族苗族自治州 宣恩县","吉林省 辽源市 西安区","新疆维吾尔自治区 克拉玛依市 乌尔禾区","湖北省 黄石市 铁山区","贵州省 黔南布依族苗族自治州 荔波县","陕西省 榆林市 神木县");
    var tmp = getRandomNum(0,arrs.length-1);
    var str = arrs[tmp];
    return str;
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

//随机年龄
const age = getRandomNum(18,100);
pm.globals.set("age",age);

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

//随机省市区
const pca = privinceCityArea();
pm.globals.set("pca",pca);

//随机范围区域
const region = getRegion();
pm.globals.set("region",region);

//随机省份
const privince = getProvince();
pm.globals.set("privince",privince);

//随机城市
const city = getCity();
pm.globals.set("city",city);

//随机区域/县区
const area = getArea();
pm.globals.set("area",area);

//随机文本
const text = getRandomText();
pm.globals.set("text",text);

//随机英文文本
const egText = getEnglishText();
pm.globals.set("egText",egText);

//随机日期
const birthday = getBirthday();
pm.globals.set("birthday",birthday);

//随机邮箱
const email = getEmail();
pm.globals.set("email",email);
```

