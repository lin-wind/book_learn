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

PyNVMe3 是专为NVMe SSD开发和测试工程师设计更全面的工具。PyNVMe不单面向**性能测试**，更可以实现**功能**，**协议**，**注错**，**可靠性**，**压力**，**功耗**，**安全**，**带外管理**，**固件白盒**等测试。

PyNVMe3 提供了一个类似于fio的ioworker模块，用来构造各种IO负载。ioworker基于SPDK的用户态NVMe驱动实现，能比fio获得更高的性能和更低的延迟。ioworker还提供Python API接口，便于Python脚本实现测试，并收集处理可视化测试数据。

----

## 5.3 专业测试平台

### 5.3.1 研发测试和产品检测


### 5.3.2 研发测试需求


### 5.3.3 测试平台介绍
- SANBlaze
- OakGate
- DriveMaster
- dnvme
- nvme-cli
- fio
- Pynvme3

### 5.3.4 专业测试平台设计
1. 测试覆盖率

2. 测试准确性

3. 高可靠性

4. 可扩展性

5. 设备兼容性

6. 研发友好

-----

## 5.4 PyNVMe3脚本开发

### 5.4.1 平台介绍


### 5.4.2 类和方法概述


### 5.4.3 驱动的特性


### 5.4.4 实例解析


