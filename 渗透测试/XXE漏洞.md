## XXE

**简介**

XXE：XML External Entity 即外部实体，从安全角度理解成XML External Entity attack（外部实体注入
攻击）。由于程序在解析输入的XML数据时，解析了攻击者伪造的外部实体而产生的。

**危害**

当允许引用外部实体时，通过构造恶意内容，可导致读取任意文件、执行系统命令、探测内网端口、
攻击内网网站等危害。
读取任意文件&执行系统命令

**XXE的防御**

1 使用开发语言提供的禁用外部实体的方法

PHP：libxml_disable_entity_loader(true);
其他语言:
https://www.owasp.org/index.php/XML_External_Entity_(XXE)_Prevention_Cheat_Sheet


2 过滤用户提交的XML数据
	关键词：，SYSTEM和PUBLIC。



无论是WEB程序，还是PC程序，只要处理用户可控的XML都可能存在危害极大的XXE漏洞，开发人员在处理XML时需谨慎，在用户可控的XML数据里禁止引用外部实体。


​	文中涉及到的代码和技术细节，只限用于技术交流，切勿用于非法用途。欢迎探讨交流，行文仓促，不足之处，敬请不吝批评指正。

**参考**

https://cloud.tencent.com/developer/article/2090744
https://www.freebuf.com/articles/web/267506.html