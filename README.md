# 餐饮门头焕新 Skill

将店面现状照片、参考方案和材料素材整理为明确的修改要求，辅助生成餐饮门头概念效果图，并逐项检查文字、入口、门窗、材质和保留区域。

**当前版本：早期原型。最终设计成果为图片。**

## 适合做什么

- 根据现状图与已确认范围，替换门头饰面、品牌文字、灯光或指定陈设。
- 从参考方案识别“哪个区域换什么材料”，优先使用用户已有素材。
- 记录同一品牌可复用的材料规则，同时按每家店重新处理区域边界和现场条件。
- 看图检查错误，保存修订记录，区分工具成功、视觉自检与用户认可。

## 安装

需要本机具有 Node.js/npm，运行：

```bash
npx -y skills add wen0491/restaurant-storefront-skill --skill restaurant-storefront
```

安装器可能需要选择目标 Agent。安装后，在支持 Skill 的 Agent 中调用 `$restaurant-storefront`；也可以让 Agent 直接读取本仓库的 `skills/restaurant-storefront/SKILL.md`。

实际生成或编辑图片需要当前环境可用的 `imagegen` 技能与内置图像工具。本仓库提供工作规则和模板，不附带图像模型、API 服务或品牌素材。

## 最短使用示例

```text
使用 $restaurant-storefront。
这是店面现状图、焕新参考图和材料素材。
先从资料中整理修改区域、对应材料和必须保留的内容，复述给我确认。
范围明确后再编辑图片，检查招牌文字、入口、门窗及非目标区域。
最终交付一张横向概念效果图，并说明未解决的问题。
```

用户提供设计标准并决定审美是否符合要求；Agent负责识别与整理资料、提出适配方式、执行图片编辑和核验。有歧义或规则冲突时先问具体问题，不让用户重复填写已有资料。

## 文件

| 位置 | 用途 |
|---|---|
| [SKILL.md](skills/restaurant-storefront/SKILL.md) | 技能入口与执行流程 |
| [references/](skills/restaurant-storefront/references/) | 设计、区域复用、验收规则及虚构示例 |
| [assets/](skills/restaurant-storefront/assets/) | 需求单与图片检查记录模板 |
| [agents/openai.yaml](skills/restaurant-storefront/agents/openai.yaml) | Codex技能展示信息 |

## 当前验证与边界

已有一次单店场景的两版探索性输出与一次修订记录；仍发现材质匹配和局部编辑影响其他区域的问题，尚未完整通过验收。通用发布包的文件校验与安装验证结果见 [VALIDATION.md](VALIDATION.md)。这不证明任意店面、任意视角或跨店复用均可稳定通过。

概念效果图用于设计讨论，不能替代测绘、施工图或材料性能验证。仓库仅提供通用规则和虚构文字示例，不含实际品牌的方案、素材、Logo、店面照片或生成案例。
