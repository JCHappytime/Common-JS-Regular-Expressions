# Common-JS-Reqular-Expressions
这里主要是为了分享一些在开发或者日常工作中用到的一些正则表达式。

在线测试地址：[正则表达式在线测试](https://regexper.com/)

## 密码类
1. 6-16位，区分大小写（不能是9位以下的纯数字，不含空格）
```
reg=/^(?!\d{6,8}$)(?! )(?=.*[a-z])(?=.*[0-9])[a-zA-Z0-9_]{6,16}$/

reg.test(12345b);   //=>true
```


## 数字类
1. 电话号码
```
reg=/^[0-9]+[0-9_*#+-]+[0-9]+$/

reg.test(19300213435);   //=>true
```

1. 域名： /^(?=^.{3,255}$)[a-z0-9][-a-z0-9]{0,62}(\.[a-z0-9][-a-z0-9]{0,62})+$/
