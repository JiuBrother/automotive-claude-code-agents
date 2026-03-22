# Automotive Claude Code Agents — 增强版 (Enhanced Fork)

> **[English README](README.md)** | 中文说明

## Fork 增强说明

本仓库是 [theja0473/automotive-claude-code-agents](https://github.com/theja0473/automotive-claude-code-agents) 的增强 Fork，由张玉新（吉林大学/卓驭科技/驭研科技）维护。

### 原项目能力

- 75+ 技能类别（ADAS, BMS, V2X, Powertrain...）
- 39 个专业智能体（safety engineer, ADAS architect...）
- 33 个 slash 命令
- 115 个标准参考文档（ISO 26262, AUTOSAR, MISRA, ISO 21434, ASPICE...）
- 24 个 pre-commit 安全钩子
- 26 个工作流

### 增强内容

本 Fork 在原项目基础上新增以下内容：

#### 增强方向一：标准法规体系（26项标准，P1-P3分级）

基于专业标准审查，系统化收录了 **15项P1（强烈推荐）+ 7项P2（推荐）+ 4项P3（可选）** 共26项核心标准：

**P1-强烈推荐（15项已发布标准）：**

| 新增目录 | 覆盖标准 |
|---------|---------|
| `skills/china-standards/functional-safety/` | GB/T 34590-2022 道路车辆功能安全（12部分） |
| `skills/china-standards/sotif/` | GB/T 43267-2023 + CSAE 316.1/316.2 + CSAE 336（4项SOTIF标准） |
| `skills/china-standards/scenario-safety/` | ISO 34501/34502 场景安全评估框架 |
| `skills/china-standards/behavioral-safety/` | IEEE 2846-2022 ADS安全假设（含RSS） |
| `skills/china-standards/ai-safety/` | ISO PAS 8800 + ISO/IEC TR 5469（AI安全） |

**P2-推荐入选（7项草案/在制标准）：**

| 新增目录 | 覆盖标准 |
|---------|---------|
| `skills/china-standards/l3-fusa-sotif/` | L3 FuSa+SOTIF联合要求（2025.01草案，中国独创） |
| `skills/china-standards/ads-safety/` | ADS强制安全要求（2025.11征求意见稿） |
| `skills/china-standards/l2-adas-safety/` | L2 ADAS强制安全要求（项目组草案v2.1） |
| `skills/china-standards/odd/` | ODD设计运行条件 |
| `skills/china-standards/multi-pillar/` | "多支柱"标准综合应用指南（152页） |

**P3-可选入选（4项）：** L2 ADAS功能要求16项、ISO 34502中国版、ISO 34503/34504/34505场景标准族、功能安全审核方法

**支撑文件：**

| 文件 | 说明 |
|------|------|
| `agents/china-compliance/` | 中国合规工程师智能体 |
| `rules/china-standards/` | 中国强标合规规则 |
| `knowledge-base/standards/china-standards/` | 标准索引与参考库 |
| `knowledge-base/standards/china-regulatory/` | 国际法规参考（R157/UL4600等） |

#### 增强方向二：SOTIF 深度实践（原项目仅浅层覆盖）

| 新增文件 | 说明 |
|---------|------|
| `skills/automotive-sotif-hazard-scenario/` | SOTIF 危险场景系统化构建方法 |
| `skills/automotive-sotif-audit/` | SOTIF 审核评估与成熟度模型 |
| `skills/automotive-sotif-highway-testing/` | 高速公路 SOTIF 测试评价框架 |
| `skills/automotive-scenario-driven-testing/` | 场景驱动测试评价方法论 |
| `agents/sotif/automotive-sotif-analyst.md` | SOTIF 分析师智能体 |
| `agents/sotif/automotive-scenario-engineer.md` | 场景工程师智能体 |

#### 增强方向三：端到端自动驾驶安全（原项目未涉及）

| 新增文件 | 说明 |
|---------|------|
| `skills/automotive-e2e-safety-analysis/` | 端到端 AD 系统安全分析框架 |
| `skills/automotive-dfm-benchmarking/` | 驾驶员基础模型（DFM）基准评测 |

---

## 快速开始

```bash
# 1. 克隆仓库
git clone https://github.com/zyx312/automotive-claude-code-agents.git
cd automotive-claude-code-agents

# 2. 预览安装内容（不做任何更改）
./install.sh --dry-run

# 3. 安装到你的 ~/.claude 工作区
./install.sh

# 4. 开始使用
claude "分析我的 ACC 系统是否符合中国 L2 强标要求"
claude "为我的 AEB 系统进行 SOTIF 触发条件识别"
claude "评估端到端感知模型的安全性"
```

## 使用示例

### 中国标准合规

```bash
# L2 合规差距分析
claude "对照中国GB组合驾驶辅助安全要求，评估我们的ICA系统合规差距"

# 泊车系统合规
claude "检查我们的APA系统是否满足中国泊车标准的安全要求"

# 准入文档准备
claude "准备工信部L2产品准入所需的技术文件清单"
```

### SOTIF 分析

```bash
# 触发条件识别
claude "系统化识别ACC系统在中国高速公路场景下的SOTIF触发条件"

# 场景构建
claude "构建L2 LCC在弯道+隧道组合场景下的SOTIF危险场景"

# SOTIF 审核
claude "对我们的ADAS产品进行SOTIF成熟度评估"
```

### 场景驱动测试

```bash
# 场景库建设
claude "基于自然驾驶数据，为高速公路ACC验证构建场景库"

# 测试方案设计
claude "设计仿真-场地-道路联合测试方案用于AEB验证"
```

### 端到端安全

```bash
# E2E安全分析
claude "分析端到端自动驾驶系统的功能安全合规策略"

# DFM基准评测
claude "使用DFM框架评估我们的AD系统相对人类驾驶员的安全性"
```

## 项目结构

```
automotive-claude-code-agents/
├── skills/                          # 技能库
│   ├── automotive-adas/             # ADAS 技能（原有）
│   ├── automotive-safety/           # 安全技能（原有）
│   ├── automotive-china-l2-adas-compliance/   # 🆕 中国L2合规
│   ├── automotive-china-l3-ads-compliance/    # 🆕 中国L3合规
│   ├── automotive-china-parking-compliance/   # 🆕 中国泊车合规
│   ├── automotive-china-standards-overview/   # 🆕 中国标准总览
│   ├── automotive-sotif-hazard-scenario/      # 🆕 SOTIF场景构建
│   ├── automotive-sotif-audit/                # 🆕 SOTIF审核
│   ├── automotive-sotif-highway-testing/      # 🆕 高速SOTIF测试
│   ├── automotive-scenario-driven-testing/    # 🆕 场景驱动测试
│   ├── automotive-e2e-safety-analysis/        # 🆕 端到端安全
│   └── automotive-dfm-benchmarking/           # 🆕 DFM评测
├── agents/                          # 智能体定义
│   ├── adas/                        # ADAS智能体（原有）
│   ├── china-compliance/            # 🆕 中国合规智能体
│   └── sotif/                       # 🆕 SOTIF智能体
├── rules/                           # 规则库
│   ├── safety-standards/            # 安全规则（原有）
│   └── china-standards/             # 🆕 中国标准规则
├── knowledge-base/                  # 知识库
│   └── standards/
│       ├── iso26262/                # ISO 26262（原有）
│       ├── sotif/                   # SOTIF（原有）
│       └── china-standards/         # 🆕 中国标准
├── commands/                        # 命令
├── workflows/                       # 工作流
├── hooks/                           # Git钩子
└── docs/                            # 文档
```

## 维护者

- **张玉新 (Yuxin Zhang)** — 吉林大学汽车工程学院教授
  - 研究方向：自动驾驶安全、SOTIF、场景驱动测试评价
  - GitHub: [@zyx312](https://github.com/zyx312)
  - Email: yuxinzhang@jlu.edu.cn
  - 数据集: [DRIVEResearch](https://www.driveresearch.tech/)

## 致谢

- 原项目作者 [Thejeswarareddy R](https://github.com/theja0473)（博世 Lead Engineer）
- 驭研科技团队提供的自然驾驶数据支持
- 吉林大学智能汽车研究团队

## 许可证

MIT License — 与原项目保持一致
