# 参评AI芯片信息

* 厂商：Nvidia

* 产品名称：A100
* 产品型号：A100-40GiB-SXM
* TDP：400W

# 所用服务器配置

* 服务器数量：1
* 单服务器内使用卡数: 1
* 服务器型号：DGX A100
* 操作系统版本：Ubuntu 20.04.4 LTS
* 操作系统内核：linux5.4.0-113
* CPU：AMD EPYC7742-64core
* docker版本：20.10.16
* 内存：1TiB
* 服务器间AI芯片直连规格及带宽：此评测项不涉及服务期间AI芯片直连

# 算子库版本

https://github.com/FlagOpen/FlagGems. Commit ID: 3c10679326b32ea5f037db50cc397d41c0ff1934

# 评测结果

## 核心评测结果

| 评测项  | correctness | TFLOPS(cpu wall clock) | TFLOPS(kernel clock) | FU(FLOPS Utilization)-cputime | FU-kerneltime |
| ---- | -------------- | -------------- | ------------ | ------ | ----- |
| flaggems | True    | 0.48TFLOPS       | 0.49TFLOPS        | 2.48% | 2.5% |
| nativetorch | True    | 0.34TFLOPS      | 0.34TFLOPS      | 1.73%      | 1.72%    |

## 其他评测结果

| 评测项  | cputime | kerneltime | cputime吞吐 | kerneltime吞吐 | 无预热时延 | 预热后时延 |
| ---- | -------------- | -------------- | ------------ | ------------ | -------------- | -------------- |
| flaggems | 2439.16us       | 2423.81us        | 409.98op/s | 412.57op/s | 10596427.43us | 1075.44us |
| nativetorch | 3493.21us       | 3512.32us        | 286.27op/s | 284.71op/s | 16326.47us | 1608.61us |

## 能耗监控结果

| 监控项  | 系统平均功耗  | 系统最大功耗  | 系统功耗标准差 | 单机TDP | 单卡平均功耗 | 单卡最大功耗 | 单卡功耗标准差 | 单卡TDP |
| ---- | ------- | ------- | ------- | ----- | ------------ | ------------ | ------------- | ----- |
| nativetorch监控结果 | 1540.5W | 1638.0W | 85.0W   | /     | 217.87W       | 233.0W      | 18.73W        | 400W  |
| flaggems监控结果 | 1540.5W | 1638.0W | 85.0W   | /     | 217.5W       | 249.0W      | 17.74W        | 400W  |

## 其他重要监控结果

| 监控项  | 系统平均CPU占用 | 系统平均内存占用 | 单卡平均温度 | 单卡最大显存占用 |
| ---- | --------- | -------- | ------------ | -------------- |
| nativetorch监控结果 | 1.984%    | 1.283%   | 44.0°C       | 8.622%        |
| flaggems监控结果 | 0.855%    | 1.283%   | 44.09°C       | 4.981%        |