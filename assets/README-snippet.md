# EO devo · 状态立面

一个数字胚胎从单细胞到器官 —— 什么时候开始长出层次？

> 拐点 β*≈0.02 · 崩塌 4/8→0/8 · 代价 −0.0076
> 出处：`experiments/exp211_inflection`，8 seeds × 9 档 β × 40 代

![EO devo 状态立面](assets/hero.svg)

## 当前状态

<img src="assets/state-badge.svg" width="480" alt="状态徽章">

六个状态共用同一套视觉 DNA（记忆拓扑：三层节点簇 + 自下而上轨迹 + 拐点台阶），只换颜色与呼吸节奏：

| 状态 | 节奏 | 含义 |
|:--|:--|:--|
| <img src="assets/state-idle.svg" width="24"> **idle** 待命 | 4s 慢呼吸，冷绿低亮 | 在，但没被按 |
| **thinking** 推演 | 0.8s 快脉冲，琥珀偏移 | 正在选 |
| **busy** 运转 | 持续旋转 + 波纹 | 在跑：采样 + 休眠恢复 |
| **blocked** 受阻 | 脉冲冻结，低饱和红 | 动不了，但不是错 |
| **error** 失效 | 红色，一次抽动后静止 | 抽一下就停 |
| **success** 成立 | 短暂暖脉冲，回落 idle | 暖一下就退回待命 |

![六状态对照](assets/states-all.svg)

<details>
<summary>切换状态的做法</summary>

状态由 `assets/status.json` 定义。改徽章状态只需替换 SVG 里的 class 名：
`state-idle.svg` / `state-thinking.svg` / `state-busy.svg` / `state-blocked.svg` / `state-error.svg` / `state-success.svg`。
全部由 `assets/gen_assets.py` 从 `status.json` 生成，改 JSON 后重跑即可，不需要手动画第二遍。

</details>

## Social Preview

![social preview](assets/social-preview.png)

1280×640，缩到 640×320 后最小字号 14px（可读门槛）。

## 设计约束

- **无 JavaScript**：动画只用 SVG 内嵌 CSS `@keyframes`
- **无外部依赖**：字体走 `font-family` 本地回退，不下载
- **同一套 DNA**：所有素材由 `gen_assets.py` 从 `status.json` 一处生成
- **可版本化**：SVG 是纯文本，可 diff、可回滚

详见 [`assets/DESIGN.md`](assets/DESIGN.md)。
