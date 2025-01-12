## 启动服务
要启动服务，你可以运行以下的脚本命令。请确保在执行这些命令之前你已经位于项目的根目录。

### 启动 Hertz HTTP 服务
``` bash
sh sh/build_and_run.sh hertz-http-server
```

### 启动 Length 服务
``` bash
sh sh/build_and_run.sh length-service
```

### 启动 Substring 服务

``` bash
sh sh/build_and_run.sh substring-service
```

### 启动 Reverse 服务

``` bash
sh sh/build_and_run.sh reverse-service
```

### 启动 Conversion 服务

``` bash
sh sh/build_and_run.sh conversion-service
```

### 清理
要清理所有的可执行文件，你可以运行以下脚本命令：

``` bash
sh sh/clean.sh
```

## 运行测试

### Length 服务
```shell
go test -bench=. test/length_test.go
```

```shell
ab -n 10000 -c 10 -T 'application/x-www-form-urlencoded' -p test/data/length.data "http://127.0.0.1:8088/length"
```

### Conversion服务

```shell
go test -bench=. test/conversion_test.go
```
```shell
ab -n 1000 -c 10 -T 'application/x-www-form-urlencoded' -p test/data/conversion.data "http://127.0.0.1:8088/convert"
```

### Substring服务

```shell
go test -bench=. test/substring_test.go
```
```shell
ab -n 1000 -c 10 -T 'application/x-www-form-urlencoded' -p test/data/substring.data "http://127.0.0.1:8088/substring"
```

### Reverse服务

```shell
go test -bench=. test/reverse_test.go
```
```shell
ab -n 1000 -c 10 -T 'application/x-www-form-urlencoded' -p test/data/reverse.data "http://127.0.0.1:8088/reverse"
```



