# 参评AI芯片信息

* 厂商：ILUVATAR

* 产品名称：BI150
* 产品型号：BI150
* TDP：W

# 所用服务器配置

* 服务器数量：1


* 单服务器内使用卡数：1
* 服务器型号：
* 操作系统版本：Ubuntu 20.04.6 LTS
* 操作系统内核：linux5.4.0-148-generic
* CPU：
* docker版本：20.10.25
* 内存：
* 服务器间AI芯片直连规格及带宽：此评测项不涉及服务期间AI芯片直连

# 算子库版本
FlagGems:>联系邮箱: contact-us@iluvatar.com获取版本(FlagGems-0710_pointwise_use_tid)

# 注意事项
测试bmm时必须调节降频问题，因此需要：bash vendors/iluvatar/dvfs.sh && python3 run.py 

# 评测结果

## 核心评测结果

| 评测项  | 平均相对误差(with FP64-CPU) | TFLOPS(cpu wall clock) | TFLOPS(kernel clock) | FU(FLOPS Utilization)-cputime | FU-kerneltime |
| ---- | -------------- | -------------- | ------------ | ------ | ----- |
| flaggems | 1.76E-04    | 89.25TFLOPS       | 88.91TFLOPS        | 46.31% | 46.27% |
| nativetorch | 1.76E-04    | 94.69TFLOPS      | 94.41TFLOPS      | 49.29%      | 49.17%    |

## 其他评测结果

| 评测项  | 相对误差(with FP64-CPU)标准差 | cputime | kerneltime | cputime吞吐 | kerneltime吞吐 | 无预热时延 | 预热后时延 |
| ---- | -------------- | -------------- | ------------ | ------------ | -------------- | -------------- | ------------ |
| flaggems | 1.33E-06    | 1540.0us       | 1545.83us        | 649.35op/s | 646.9op/s | 23206046.88us | 1915.09us |
| nativetorch | 1.33E-06    | 1451.5us       | 1455.83us        | 688.94op/s | 686.89op/s | 2024.32us | 1620.88us |

## 能耗监控结果

| 监控项  | 系统平均功耗  | 系统最大功耗  | 系统功耗标准差 | 单机TDP | 单卡平均功耗 | 单卡最大功耗 | 单卡功耗标准差 | 单卡TDP |
| ---- | ------- | ------- | ------- | ----- | ------------ | ------------ | ------------- | ----- |
| nativetorch监控结果 | 2033.0W | 2033.0W | 0.0W   | /     | 285.27W       | 287.0W      | 1.81W        | 350W  |
| flaggems监控结果 | 2128.0W | 2223.0W | 95.0W   | /     | 274.0W       | 276.0W      | 2.62W        | 350W  |

## 其他重要监控结果

| 监控项  | 系统平均CPU占用 | 系统平均内存占用 | 单卡平均温度 | 单卡最大显存占用 |
| ---- | --------- | -------- | ------------ | -------------- |
| nativetorch监控结果 | 43.107%    | 2.386%   | 80.8°C       | 1.88%        |
| flaggems监控结果 | 47.647%    | 2.446%   | 78.5°C       | 2.24%        |