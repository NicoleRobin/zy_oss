# zy_oss
zy_oss是一个分布式对象存储系统.

# 验证
## 启动服务
```
LISTEN_ADDRESS=:12345 STORAGE_ROOT=/data/home/nicojwzhang/go/zy_oss/data go run main.go
```
## 创建对象
```
curl -v -X PUT -d "this is a test object" 127.0.0.1:12345/objects/test
* About to connect() to 127.0.0.1 port 12345 (#0)
*   Trying 127.0.0.1...
* Connected to 127.0.0.1 (127.0.0.1) port 12345 (#0)
> PUT /objects/test HTTP/1.1
> User-Agent: curl/7.29.0
> Host: 127.0.0.1:12345
> Accept: */*
> Content-Length: 21
> Content-Type: application/x-www-form-urlencoded
> 
* upload completely sent off: 21 out of 21 bytes
< HTTP/1.1 200 OK
< Date: Wed, 19 May 2021 00:06:00 GMT
< Content-Length: 0
< 
* Connection #0 to host 127.0.0.1 left intact
```

## 获取对象
```
$ curl -v 127.0.0.1:12345/objects/test                                  
* About to connect() to 127.0.0.1 port 12345 (#0)
*   Trying 127.0.0.1...
* Connected to 127.0.0.1 (127.0.0.1) port 12345 (#0)
> GET /objects/test HTTP/1.1
> User-Agent: curl/7.29.0
> Host: 127.0.0.1:12345
> Accept: */*
> 
< HTTP/1.1 200 OK
< Date: Wed, 19 May 2021 00:06:09 GMT
< Content-Type: text/plain; charset=utf-8
< Transfer-Encoding: chunked
< 
* Connection #0 to host 127.0.0.1 left intact
this is a test object%
```
