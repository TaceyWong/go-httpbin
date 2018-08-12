## go-httpbin(1): HTTP 请求&响应 服务

```bash
                   _     _   _         _     _
  __ _  ___       | |__ | |_| |_ _ __ | |__ (_)_ __
 / _` |/ _ \ _____| '_ \| __| __| '_ \| '_ \| | '_ \
| (_| | (_) |_____| | | | |_| |_| |_) | |_) | | | | |
 \__, |\___/      |_| |_|\__|\__| .__/|_.__/|_|_| |_|
 |___/                          |_|

```

用于测试HTTP客户端的请求&响应服务，是参照[httpbin.org](httpbin.org)的Golang实现。

有别于[httpbin.org](httpbin.org)，本项目的目标是在满足httpbin功能的同时，有以下特点：

+ 纯Go及内建库，无第三方库依赖
+ 单个源文件。所有的资源、源代码都在一个文本文件，本机有golang环境可以`go run`直接执行
+ 单个执行程序。编译之后只有一个".exe"文件，本机无golang环境可以`./go-httpbin`直接执行


### 开发进度：


+ ✔️-init-初始代码结构
+ ✔️/ 主页
+ ❎/ip 返回来源IP.
+ ✔️/uuid 返回UUID4.
+ ✔️/user-agent 返回user-agent.
+ ✔️/headers 返回 header 字典.
+ ✔️/get 返回 GET 数据.
+ ✔️/post 返回 POST 数据.
+ ✔️/patch 返回 PATCH 数据.
+ ✔️/put 返回 PUT 数据.
+ ✔️/delete 返回 DELETE 数据
+ ✔️/anything 返回 request（请求） 数据,包括使用的HTTP方法.
+ /base64/:value 解码base64url编码的字符串.
+ /encoding/utf8 返回包含utf-8编码的页面数据.
+ /gzip 返回gzip压缩编码的数据.
+ /deflate 返回 deflate-encoded 数据.
+ /brotli 返回 brotli-encoded 数据.
+ /status/:code 返回传递的 HTTP 状态码.
+ /response-headers?key=val 返回提供的响应headers.
+ /redirect/:n 302 重定向n次.
+ /redirect-to?url=foo 302 重定向到foo URL.
+ /redirect-to?url=foo&status_code=307 307 重定向到 foo URL.
+ /relative-redirect/:n 302 相对重定向n次.
+ /absolute-redirect/:n 302 绝对重定向n次.
+ /cookies 返回 cookie 数据.
+ /cookies/set?name=value 设置一个或多个简单cookie.
+ /cookies/delete?name 删除一个或多个简单cookie.
+ /basic-auth/:user/:passwd 尝试 HTTPBasic Auth.
+ /hidden-basic-auth/:user/:passwd 404的BasicAuth.
+ /digest-auth/:qop/:user/:passwd/:algorithm 尝试 HTTP Digest Auth.
+ /digest-auth/:qop/:user/:passwd 尝试 HTTP Digest Auth.
+ /stream/:n Streams min(n, 100) lines.
+ /delay/:n 延迟min(n, 10)秒进行响应.
+ /drip?numbytes=n&duration=s&delay=s&code=code Drips 数据 over a duration after an optional initial delay, then (optionally) 返回 with the given status code.
+ /range/1024?duration=s&chunk_size=code Streams n bytes, and allows specifying a Range header to select a subset of the 数据. Accepts a chunk_size and request duration parameter.
+ /html Renders an HTML Page.
+ /robots.txt 返回一些robots.txt规则.
+ /deny 被robots.txt文件拒绝.
+ /cache 返回 200 ，除非存在If-Modified-Since 或 If-None-Match header is provided, when it 返回 a 304.
+ /etag/:etag Assumes the resource has the given etag and responds to If-None-Match header with a 200 or 304 and If-Match with a 200 or 412 as appropriate.
+ /cache/:n Sets a Cache-Control header for n seconds.
+ /bytes/:n Generates n random bytes of binary 数据, accepts optional seed integer parameter.
+ /stream-bytes/:n Streams n random bytes of binary 数据 in chunked encoding, accepts optional seed and chunk_size integer parameters.
+ /links/:n 返回 page containing n HTML links.
+ /image 返回 page containing an image based on sent Accept header.
+ /image/png 返回一个 PNG 图片.
+ ✔️/image/jpeg 返回一个 JPEG 图片.
+ ✔️/image/webp 返回一个 WEBP 图片.
+ ✔️/image/gif 返回一个 GIF 图片.
+ ✔️/image/bmp 返回一个 BMP 图片.
+ ✔️/image/svg 返回一个 SVG 图片.
+ /forms/post HTML POST表单提交
+ /xml 返回 XML