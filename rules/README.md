# 协议列表
1. [**host** (设置host)](host.html)
2. [**req** (修改请求属性)](req.html)
3. [**rule** (设置响应规则)](rule/index.html)
	- [**请求替换**](rule/replace.html)
	- [**file** (替换本地文件)](rule/file.html)
	- [**xfile** (替换本地文件，如果本地文件不存在，则请求线上)](rule/xfile.html)
	- [**rawfile** (替换本地http响应内容格式的文件)](rule/rawfile.html)
	- [**xrawfile** (替换本地http响应内容格式的文件，如果本地文件不存在，则请求线上)](rule/xrawfile.html)
	- [**tpl** (替换本地目标文件，可用于模拟jsonp请求)](rule/tpl.html)
	- [**xtpl** (同上，与xfile类似)](rule/xtpl.html)
	- [**proxy** (代理到其它http代理服务器)](rule/proxy.html)
	- [**socks** (代理到其它socks代理服务器)](rule/socks.html)
	- [**自定义**](rule/custom.html)
4. [**res** (修改响应属性)](res.html)
5. [**weinre** (设置weinre，调试手机页面)](weinre.html)
6. [**filter** (过滤规则，隐藏请求等)](filter.html)
6. [**disable** (禁用缓存、cookie等)](disable.html)
7. [**log** (打印网页js错误或者调试信息)](log.html)
8. [**exports** (导出请求数据到指定文件)](exports.html)
8. [**exportsUrl** (把请求的url列表按顺序导出到指定文件)](exportsUrl.html)
9. [**hostname** (修改请求头部的host字段)](hostname.html)
8. [**referer** (修改请求referer)](referer.html)
9. [**auth** (修改请求用户名密码)](auth.html)
10. [**ua** (修改请求user-agent)](ua.html)
11. [**etag** (修改请求头部的etag)](etag.html)
11. [**urlParams** (修改请求url的参数)](urlParams.html)
12. [**dispatch** (动态修改请求url的参数)](dispatch.html)
12. [**params** (修改请求参数)](params.html)
13. [**statusCode** (直接响应)](statusCode.html)
14. [**replaceStatus** (替换后台的响应状态码)](replaceStatus.html)
14. [**redirect** (302重定向)](redirect.html)
15. [**method** (修改请求方法)](method.html)
16. [**cache** (修改缓存策略)](cache.html)
16. [**attachment** (设置下载头部)](attachment.html)
17. [**location** (设置响应头部的location字段)](location.html)
17. [**accept** (修改请求头的accept)](accept.html)
17. [**reqDelay** (延迟请求)](reqDelay.html)
18. [**resDelay** (延迟响应)](resDelay.html)
19. [**reqSpeed** (限制请求速度)](reqSpeed.html)
20. [**resSpeed** (限制响应速度)](resSpeed.html)
21. [**reqType** (修改请求类型)](reqType.html)
22. [**resType** (修改响应类型)](resType.html)
23. [**reqCharset** (修改请求的编码)](reqCharset.html)
24. [**resCharset** (修改响应的编码)](resCharset.html)
23. [**reqCookies** (修改请求cookies)](reqCookies.html)
24. [**resCookies** (修改响应cookies)](resCookies.html)
25. [**reqCors** (修改请求cors)](reqCors.html)
26. [**resCors** (修改响应cors)](resCors.html)
27. [**reqHeaders** (修改请求头)](reqHeaders.html)
28. [**resHeaders** (修改响应头)](resHeaders.html)
29. [**reqPrepend** (往请求内容前面添加数据)](reqPrepend.html)
30. [**resPrepend** (往响应内容前面添加数据)](resPrepend.html) 
31. [**reqBody** (替换请求内容)](reqBody.html)
32. [**resBody** (替换响应内容)](resBody.html)
33. [**reqAppend** (往请求内容后面追加数据)](reqAppend.html)
34. [**resAppend** (往响应内容后面追加数据)](resAppend.html)
35. [**reqReplace** (通过正则或字符串替换请求文本内容，类似str.replace)](reqReplace.html)
36. [**resReplace** (通过正则或字符串替换响应文本内容，类似str.replace)](resReplace.html)
35. [**reqWrite** (将请求内容写入指定的文件)](reqWrite.html)
36. [**resWrite** (将响应内容写入指定的文件)](resWrite.html)
37. [**reqWriteRaw** (将请求的完整内容写入指定的文件)](reqWriteRaw.html)
38. [**resWriteRaw** (将响应的完整内容写入指定的文件)](resWriteRaw.html)
35. [**css** (往响应为html或css的内容后面追加数据)](css.html)
36. [**html** (往响应为html的内容后面追加数据)](html.html)
37. [**js** (往响应为html或js的内容后面追加数据)](js.html)