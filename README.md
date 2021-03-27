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

- [1. 密码类](https://github.com/JCHappytime/Common-JS-Regular-Expressions/issues/3)
- [2. 号码类](https://github.com/JCHappytime/Common-JS-Regular-Expressions/issues/4)
- [3. 地址类](https://github.com/JCHappytime/Common-JS-Regular-Expressions/issues/5)
- [4. 域名类](https://github.com/JCHappytime/Common-JS-Regular-Expressions/issues/6)
- [5. 包含数字，字母和（.-_），特殊字符不能出现在首尾且不能连续](https://github.com/JCHappytime/Common-JS-Regular-Expressions/issues/7)



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


