## 一、导出客户邮件列表
1. 客户 --> 合计 （最底部33行） --双击统计数量，打开客户列表
2. 全选客户 --> EDM群发 --> 复制群邮件列表  
3. 将列表粘贴到Notepadd++, C-f 查找替换， 选中扩展， 将分号(;)替换为换行(\n)

## 二、剔除不发的邮件(Notepad++中）
1. 按组合键Ctrl + F，查找模式选择 '正则表达式'，不选 '.匹配新行'

2. 查找目标输入：  
 ^.*关键字.*\r?\n    (不保留空行)  
 ^.*关键字.*$        (保留空行)  

4. 替换为：（空）

参考链接：  
https://blog.csdn.net/luoqingyan/article/details/126819710  
https://seaside.blog.csdn.net/article/details/124121603

## 三、用grep中去除匹配内容
**去除包含#  和空行**  
cat test.log | grep -v "#" | grep -v "^$"

**显示匹配的行**  
grep -oP '[\w.-]+@[\w.-]+\.[\w]{2,6}' google-email-list.txt  | grep -E "surpport|contact|admin|domain"

**显示不匹配的行** （grep --help: -v, --invert-match        select non-matching lines）  
grep -oP '[\w.-]+@[\w.-]+\.[\w]{2,6}' google-email-list.txt  | grep -v -E "surpport|contact|admin|domain"

** Error: -P supports only unibyte and UTF-8 locales
在 MSYS2 环境下执行

## split 切分文件
说明：-d 数字 （默认是2位，可以-a 数字）  
split -l 500 -d --additional-suffix=.txt result.txt ./tmp/send-

参考链接：  
https://blog.csdn.net/h4241778/article/details/122527463

