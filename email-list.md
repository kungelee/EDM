## 一、导出客户邮件列表
1. 全选客户 --> EDM群发 --> 复制群邮件列表
2.将列表粘贴到Notepadd++, C-f 查找替换， 选中扩展， 将分号(;)替换为换行(\n)

## 二、剔除不发的邮件(Notepad++中）
1、按组合键Ctrl + F，查找模式选择 '正则表达式'，不选 '.匹配新行'

2、查找目标输入 ：

    ^.*关键字.*\r?\n    (不保留空行)
    ^.*关键字.*$        (保留空行)

3、替换为：（空）

参考链接：
https://blog.csdn.net/luoqingyan/article/details/126819710
https://seaside.blog.csdn.net/article/details/124121603

## 三、grep中去除匹配内容
去除包含#  和空行:
cat test.log | grep -v "#" | grep -v "^$"


