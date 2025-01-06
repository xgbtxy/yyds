# 收集开源好用的安全工具，对比，验证，来更好的帮助使用工具



## URLFinder
https://github.com/pingc0y/URLFinder
此工具可以帮助我们获取js文件中泄露的接口地址以及敏感信息，更针对于网站后台的js文件提取，并且支持针对目标ip批量提取，将结果批量导出。

### 快速使用
单url

```
显示全部状态码
URLFinder.exe -u http://www.baidu.com -s all -m 3

显示200和403状态码
URLFinder.exe -u http://www.baidu.com -s 200,403 -m 3
```

批量url
```
结果分开保存
导出全部
URLFinder.exe -s all -m 3 -f url.txt -o .
只导出html
URLFinder.exe -s all -m 3 -f url.txt -o res.html

结果统一保存
URLFinder.exe -s all -m 3 -ff url.txt -o .
```
参数（更多参数使用 -i 配置）：
```
-a  自定义user-agent请求头  
-b  自定义baseurl路径  
-c  请求添加cookie  
-d  指定获取的域名,支持正则表达式
-f  批量url抓取,需指定url文本路径  
-ff 与-f区别：全部抓取的数据,视为同一个url的结果来处理（只打印一份结果 | 只会输出一份结果） 
-h  帮助信息   
-i  加载yaml配置文件,可自定义请求头、抓取规则等（不存在时,会在当前目录创建一个默认yaml配置文件）  
-m  抓取模式：
        1  正常抓取（默认）
        2  深入抓取 （URL深入一层 JS深入三层 防止抓偏）
        3  安全深入抓取（过滤delete,remove等敏感路由） 
-max 最大抓取数
-o  结果导出到csv、json、html文件,需指定导出文件目录（.代表当前目录）
-s  显示指定状态码,all为显示全部  
-t  设置线程数（默认50）
-time 设置超时时间（默认5,单位秒）
-u  目标URL  
-x  设置代理,格式: http://username:password@127.0.0.1:8877
-z  提取所有目录对404链接进行fuzz(只对主域名下的链接生效,需要与 -s 一起使用）  
        1  目录递减fuzz  
        2  2级目录组合fuzz
        3  3级目录组合fuzz（适合少量链接使用）
```
