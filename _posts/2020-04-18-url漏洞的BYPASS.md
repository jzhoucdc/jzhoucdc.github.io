## bypass
1.最常用的一条：@绕过。

http://127.0.0.1/url.php?username=1&password=1&password=1&redict=http://www.xiaozhupeiqi.com@www.baidu.com //ssrf也可用
2.绕过一些匹配特定字符。

？绕过

http://127.0.0.1/url.php?username=1&password=1&password=1&redict=http://www.baidu.com?www.xiaozhupeiqi.com
#绕过

http://127.0.0.1/url.php?username=1&password=1&password=1&redict=http://www.baidu.com#www.xiaozhupeiqi.com
3.斜杠/绕过

http://127.0.0.1/url.php?username=1&password=1&password=1&redict=http://www.baidu.com/www.xiaozhupeiqi.com
或者反斜线

http://127.0.0.1/url.php?username=1&password=1&password=1&redict=http://www.baidu.com\www.xiaozhupeiqi.com
4.白名单匹配绕过

比如匹配规则是必须跳转，xiaozhupeiqi.com 域名下，?#等都不行的时候，如果匹配规则为xiaozhupeiqi.com，可以尝试百度inurl:xiaozhupeiqi.com的域名，比如
aaaxiaozhupeiqi.com，这样同样可以绕过。接下来实战中会用到，
5. xip.io绕过

http://127.0.0.1/url.php?username=1&password=1&password=1&redict=http://www.xiaozhupeiqi.com.220.181.57.217.xip.io
会跳转到百度

6. 理想化方法

如果有机会在自己的页面设置url跳转，比如目标网站的bbs论坛自己的资料页面设置url跳转，既然是服务器的网站，那么url是不会限制的，可以用一个漏洞去构造另一个漏洞。
7. 白名单网站可信

如果url跳转点信任百度url，google url或者其他，则可以多次跳转达到自己的恶意界面。
8. 协议绕过

http与https协议转换尝试，或者省略

http://127.0.0.1/url.php?username=1&password=1&password=1&redict=//www.xiaozhupeiqi.com@www.baidu.com
http://127.0.0.1/url.php?username=1&password=1&password=1&redict=////www.xiaozhupeiqi.com@www.baidu.com//多斜线

9. xss跳转
这种就没啥说的了，就是XSS造成的跳转

<meta  content="1;url=http://www.baidu.com" http-equiv="refresh">

## fuzz
redirect
url
redirectUrl
callback
return_url
toUrl
ReturnUrl
fromUrl
redUrl
request
redirect_to
redirect_url
jump
jump_to
target
to
goto
link
linkto
domain
oauth_callback