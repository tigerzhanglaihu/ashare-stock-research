# A-Share Stock Research / A股资料分析

**纯提示词 Agent Skill · 中文报告 · 实验版0.1.0**

从六位沪深A股代码开始，查询可核实资料，按固定口径计算最近60个交易记录的反弹高点（ERH），并整理价格走势、连续上涨、公司经营、分红、融资及新闻。

Instruction-only skill for mainland China A-share research, with source-linked Chinese reports and a defined 60-session rebound-high method. No application runtime or custom executable scripts are included.

## 功能与要求

- ERH使用最近60条完整已完成日线，逐条确认、替换和检查突破失效。
- 较长窗口价格走势与ERH分别计算，默认使用最多260条日线近似窗口。
- 新闻每次查询，保留实际发布日期、来源和原文链接。
- 解释通常1～2句，用日常语言，缺失数据保持未知。
- 默认测试输出附完整60条输入和关键确认记录，便于核验。

需要宿主模型提供联网、行情查询或文件读取能力。联网不是Skill自带服务；本仓库不提供行情接口、API密钥、收费数据订阅或独立计算程序。

没有联网时可以分析用户提供的完整数据，但须说明时效及独立核验限制。无需安装本地Stock项目或其Python环境。

## 使用

源仓库：[tigerzhanglaihu/ashare-stock-research](https://github.com/tigerzhanglaihu/ashare-stock-research)。

支持skills CLI的环境可以安装：

```text
npx skills add tigerzhanglaihu/ashare-stock-research
```

这是可选的技能安装器，不是运行本Skill所需的分析程序。也可使用下述文件导入方式。

将本仓库目录作为技能文件夹放入宿主支持的skills目录，或通过其技能导入功能选择本目录。支持与否及目录位置以宿主文档为准。

没有技能导入能力的对话工具，可完整粘贴SKILL.md后输入请求。全部计算规则和报告格式均包含在同一个文件中。

示例请求：

> 使用ashare-stock-research分析300170。重新获取资料；完整取得60条日线后计算ERH，新闻逐条附日期与原文链接。无法取得的部分保留未知。

> 根据我提供的日线表分析这只股票，使用既定ERH规则。只核实能够访问的资料，不补造缺失价格。

## 文件

| 文件 | 用途 |
| --- | --- |
| [SKILL.md](SKILL.md) | 完整提示词、全部计算规则、报告格式与验算要求 |
| [LICENSE](LICENSE) | MIT许可 |

所有规则均为Markdown文档，没有scripts目录及可执行程序。

## 当前验证状态

0.1.0为实验说明稿。此前单次模型试用曾偏离ERH规则；本版本加强了数据前提、失败处理和验算证据，尚未完成目标模型行为验收。

目录格式检查不等于算法执行正确，也不证明联网接口可用。不同模型仍可能漏读规则、误算或引用过期资料。应核对报告中的输入、来源和确认记录。

50%参考价是用户指定的比较规则，没有经过投资收益验证，不是价格预测或交易指令。本Skill不执行交易，不要求提供账户凭据或私人持仓。

## 反馈

反馈问题时提供所用模型、分析日期、实际读取的公共来源、必要日线及错误结果。请勿提交密钥、账户信息、私人持仓或含隐私的完整对话。

## 发布定位

适合按需查询资料、阅读通俗报告和人工复核。当前版本不宣称替代经过程序校验的确定性计算、数据库存储、批量服务或DOCX渲染。

## 许可

[MIT License](LICENSE)，Copyright (c) 2026 tigerzhanglaihu。
