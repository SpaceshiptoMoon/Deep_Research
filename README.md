# DeepResearch 项目文档

## 项目概述

DeepResearch 是一个基于多智能体协作的自动化研究系统，旨在通过多个专业智能体的分工合作，完成从信息搜集、事实核查到报告生成的完整研究流程。

## 项目结构

markdown

markdown

复制

```markdown
.
├── agents/                # 智能体模块
│   ├── fact_check.py      # 事实核查智能体
│   ├── researcher.py      # 研究信息搜集智能体
│   ├── supervisor.py      # 监督协调智能体
│   └── writer.py          # 报告撰写智能体
│
├── tools/                 # 工具模块
│   └── search.py          # 搜索工具
│
├── config.py              # 配置文件
├── graph.py               # 智能体协作流程图
├── llm.py                 # 大语言模型接口
├── reporter.py            # 报告生成器
├── run.py                 # 主运行文件
├── schemas.py             # 数据结构定义
└── template.py            # 报告模板
```

## 核心功能

### 1. 多智能体协作系统

- **研究智能体(Researcher)**：负责信息搜集和初步分析
- **事实核查智能体(FactChecker)**：验证信息的准确性
- **撰写智能体(Writer)**：生成结构化研究报告
- **监督智能体(Supervisor)**：协调各智能体工作流程

### 2. 核心工具

- **智能搜索工具**：支持多种数据源的精准检索
- **自动验证系统**：交叉验证信息可靠性

## 技术栈

- Python 3.8+
- LangChain/LangGraph 框架
- 大语言模型API (支持OpenAI/Claude等)
- 向量数据库(可选)
- 结构化数据处理(Pydantic)

## 安装与运行

### 前置要求

1. 安装Python 3.8或更高版本
2. 准备大语言模型API密钥

### 安装步骤

bash

bash

复制

```bash
git clone https://github.com/your_username/DeepResearch.git
cd DeepResearch
pip install -r requirements.txt
```

### 配置说明

创建.env文件配置好搜索api和大模型调用api，本项目使用的搜索引擎是duck


### 运行系统


```bash
python run.py --query "您的研究主题"
```

## 使用示例

python

python

复制

```python
from run import drllm

report = drllm(
    query="研究主题或查询内容", 
    file_name="保存研究报告的文件名", 
    breadth=2, depth=3
)
print(report)
```

## 贡献指南

欢迎通过Issue或Pull Request贡献代码。请确保：

1. 代码符合PEP8规范
2. 新增功能附带测试用例
3. 更新相关文档

## 许可证

本项目采用MIT开源许可证。