# SSD测试工具和平台


----
## 5.1 测试的硬件平台





-----

## 5.2 SSD测试软件

- 基础性能测试软件:Crystal Disk Mark、ATTO Disk Benchmark等
- 高级性能测试软件:fio、iometer等
- 综合测试软件:
- 专业测试平台:DriveMaster、SANBlaze、PyNVMe3等

### 5.2.1 Crystal Disk Mark

### 5.2.2 fio (https://github.com/axboe/fio)

对于企业级SSD来说，fio提供大量参数来实现IO负载，工作稳定，数据全面。所以在SSD企业级研发、测试和新品中广泛引入，包括但不限于功能测试、性能评估、可靠性测试方面。

fio支持命令行和job文件两种使用方式。以下是一个例子展现如何使用fio进行SSD的顺序写入测试
` sudo fio --name=seqwrite --filename=/dev/nvme0n1 --rw=write --bs=4k --size=1G --direct=1 --runtime=60 --time_based`

上述测试也可通过job文件定义。如下test.fio:
```
[seqwrite]
filename=/dev/nvme0n1
rw=write
bs=4k
size=1G
direct=1
runtime=60
time_based
```
可通过如下命令执行job文件
sudo fio test.fio

### 5.2.3 PyNVMe3

----

## 5.3 专业测试平台





-----

## 5.4 PyNVMe3脚本开发



