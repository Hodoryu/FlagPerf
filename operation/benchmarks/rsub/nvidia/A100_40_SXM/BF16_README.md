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
| flaggems | True    | 0.46TFLOPS       | 0.46TFLOPS        | 0.15% | 0.15% |
| nativetorch | True    | 0.45TFLOPS      | 0.45TFLOPS      | 0.15%      | 0.15%    |

## 其他评测结果

| 评测项  | cputime | kerneltime | cputime吞吐 | kerneltime吞吐 | 无预热时延 | 预热后时延 |
| ---- | -------------- | -------------- | ------------ | ------------ | -------------- | -------------- |
| flaggems | 4671.66us       | 4678.66us        | 214.06op/s | 213.74op/s | 831887.47us | 4774.65us |
| nativetorch | 4742.81us       | 4746.24us        | 210.85op/s | 210.69op/s | 16621.52us | 4744.37us |

## 能耗监控结果

| 监控项  | 系统平均功耗  | 系统最大功耗  | 系统功耗标准差 | 单机TDP | 单卡平均功耗 | 单卡最大功耗 | 单卡功耗标准差 | 单卡TDP |
| ---- | ------- | ------- | ------- | ----- | ------------ | ------------ | ------------- | ----- |
| nativetorch监控结果 | 1560.0W | 1638.0W | 78.0W   | /     | 249.1W       | 253.0W      | 3.96W        | 400W  |
| flaggems监控结果 | 1560.0W | 1716.0W | 156.0W   | /     | 294.0W       | 301.0W      | 5.39W        | 400W  |

## 其他重要监控结果

| 监控项  | 系统平均CPU占用 | 系统平均内存占用 | 单卡平均温度 | 单卡最大显存占用 |
| ---- | --------- | -------- | ------------ | -------------- |
| nativetorch监控结果 | 0.638%    | 1.125%   | 41.88°C       | 21.425%        |
| flaggems监控结果 | 0.663%    | 1.149%   | 49.1°C       | 21.238%        |