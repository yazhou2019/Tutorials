# Torch2Ascend 
## PyTorch全景&NPU介绍
- 有一个PyTorch Adapter
![](./Torch2AscendFigures/PyTorchAdapter.png)

    - 原生PyTorch目录结构
    - ![](./Torch2AscendFigures/原生PyTorch的目录结构.png)


    - 单算子调用流程, CPU和GPU调用，根据Tensor的类型
    - ![](./Torch2AscendFigures/PyTorchAdapter单算子调用流程.png)
        - 根据上述机制，只需要在注册一下？然后就可以运行到NPU上？
    - ![](./Torch2AscendFigures/PytorchAdapter逻辑架构图.png)
    

## PyTorch模型迁移指导
1. 算子满足度分析
2. 手工迁移(单Device、分布式)
3. 自动迁移
- 整体流程
- ![](./Torch2AscendFigures/PyTorch迁移整体流程.png)
### 算子满足度分析
- 两种方式
- ![](./Torch2AscendFigures/两种算子满足度分析.png)
    - 据说百分之九十多的算子都支持，很难遇到不支持的算子。
### 准备环境
- ![](./Torch2AscendFigures/准备Ascend软硬件环境.png)
- PyTorch Adapter 目前是以插件的方式提供，想要合并进PyTorch暂时不成功
###模型迁移的两种方式：自动迁移、手动迁移
- ![](./Torch2AscendFigures/模型迁移的两种方式.png)
#### 手工迁移
- 单GPU
![](./Torch2AscendFigures/模型迁移-手工迁移-单device.png)
- 分布式
![](./Torch2AscendFigures/模型迁移-手工迁移-分布式.png)
#### 自动迁移
- 迁移脚本转换工具
![](./Torch2AscendFigures/模型迁移-自动迁移-脚本转换工具.png
- 导入脚本转换库)
![](./Torch2AscendFigures/模型迁移-自动迁移-脚本转换库.png)
#### 模型迁移-混合精度
![](./Torch2AscendFigures/模型迁移-混合精度.png)
