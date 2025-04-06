# 数字作物 (Digital Crop)

新一代作物精细仿真平台

## 项目介绍

数字作物是一个模块化、高性能、易于使用且可视化效果出众的三维精细作物生长仿真平台，融合L-System的严谨性、RGG的灵活性、OpenAlea的模块化思想以及现代游戏引擎的渲染能力。

## 核心功能

- **模块化架构**：环境、结构、生理、分配、可视化等功能模块相对独立
- **高性能计算核心**：C++实现的计算密集型任务，支持并行计算
- **灵活的建模语言**：基于Python的高级脚本接口，支持增强型L-System
- **顶尖的三维可视化**：集成现代游戏引擎，实现高质量渲染和交互
- **科学严谨性**：基于公认科学理论和方程的生理模型
- **用户友好界面**：提供图形化用户界面，简化模型配置和结果分析

## 技术架构

- **核心引擎（C++）**：高性能计算库、结构生成规则解释器、生理过程求解器
- **逻辑与脚本层（Python）**：模型配置、生长规则定义、仿真流程控制
- **可视化与交互层（Unity/Unreal Engine）**：三维场景渲染、用户交互、数据可视化

## 安装说明

### 依赖项

- Python 3.8+
- C++ 17 编译器
- CMake 3.15+
- Unity 2022.3 LTS 或 Unreal Engine 5.1+

### 安装步骤

```bash
# 克隆仓库
git clone https://github.com/yourusername/digital-crop.git
cd digital-crop

# 安装Python依赖
pip install -r requirements.txt

# 编译C++核心库
mkdir build && cd build
cmake ..
make
cd ..

# 启动应用
python src/main.py
```

## 开发进度

目前项目处于初始开发阶段，按照阶段性计划推进中。

## 许可证

本项目采用 [MIT 许可证](LICENSE)。 