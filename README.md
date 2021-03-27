# Common-JS-Regular-Expressions

- 这里主要是为了分享一些在开发或者日常工作中用到的一些正则表达式。
- 在线测试地址：[正则表达式在线测试工具](https://c.runoob.com/front-end/854)
- 订阅请点Watch，收藏请点Star 👋👋👋

## （一）正则表达式学习分享

在正式开始正则表达式的内容之前，先分享一些正则的学习资料和简单的正则表达式所表示的意思。

### 目录

1. [简单易懂的正则表达式学习资料-随时唤醒你的正则记忆](https://github.com/JCHappytime/Common-JS-Regular-Expressions/issues/1)
2. [入门级的正则表达式知识](https://github.com/JCHappytime/Common-JS-Regular-Expressions/issues/2)

### （二）一些常用的正则表达式

### 目录

- [1. 密码类](https://github.com/JCHappytime/Common-JS-Regular-Expressions/issues/2)
- [2. 号码类](https://github.com/JCHappytime/Common-JS-Regular-Expressions/issues/4)


## 地址类



## 其他
1. 域名，DNS规定，域名中的标号都由英文歌数字组成，每一个标号不超过63个字符（为了方便记忆，一般也不会超过12个字符），也不区分大小写字母。标号中除了连字符（-）外不能使用其他的标点符号。
```
reg=/^(?=^.{3,255}$)[a-z0-9][-a-z0-9]{0,62}(\.[a-z0-9][-a-z0-9]{0,62})+$/

reg.test('baidu.com');   // =>true
reg.test('baidu中国.com');   // =>false
```

2. 包含数字，字母和特殊字符中的（.-_），但是特殊字符不能出现在首尾且不能连续出现
理解：任意个(数字或字符)后面跟一个(点、减号或下划线)，这组成一个组合，这个组合可以有任意个，最后面是一个(数字或字符)
```
reg1=/^([0-9a-zA-Z]+[\.\-_])*[0-9a-zA-Z]+$/
reg2=/^[0-9a-z]([0-9a-z]|-|_|\.)*[0-9a-z]$/

reg2.test('test---');  // => false
reg.test('test-01');   // => true
```



## 格式化相关

1. 隐藏手机号，中间四位用*号代替
```
function formatPhone(val) {
  if (!val) return;
  return val.replace(/^(\d{3})(\d{4})(\d+)/, '$1****$3');
}
```

测试：

![手机号](https://user-images.githubusercontent.com/10249805/109583433-de21aa80-7b3a-11eb-98dd-c8b09c2f6f74.png)

2. 格式化金额，每三位添加逗号","

```
function formatMoney(val) {
  if (!val) return;
  return val.toString().replace(/(?=\B(?:\d{3})+\b)(\d{3}(?:\.\d+$)?)/g,',$1');
}
```
测试：

![money](https://user-images.githubusercontent.com/10249805/109586683-a7e72980-7b40-11eb-8bd6-f102b7771dea.png)

3. 去掉字符串中的空格

```
let reg=/([^\s])\s+([^\s\b])/g;
let str = 'jc jt jl jm';

str = str.replace(reg, '$1$2');   //=>jcjtjljm
```
测试：

![去掉空格](https://user-images.githubusercontent.com/10249805/109587076-673be000-7b41-11eb-8f9f-e335019cccbd.png)


