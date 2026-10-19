# EO devo · 演示台

**一个数字胚胎从单细胞发育到器官的过程中，什么时候开始长出层次？**

答案是：**拐点 β\* ≈ 0.02**。独特性只要占总适应度的 2%，种群就从「全挤一层」变成「分层共存」；再加大 80 倍，没有进一步收益。

**这不是宣传页，是一份能自己跑一遍、能自己核对的复现材料。** 每一步都能复算，每一条失败都写在明面上。

---

![渗流阈值成品图](https://raw.githubusercontent.com/zhumeiyan/eo-devo-demo/main/assets/preview-percolation.png)

左：β = 0 —— 只长出孤立小岛，全同色，多样性 0.000。
右：β ≈ 0.02 —— 贯通簇出现，六色分层，多样性 1.011。

---

## 三个关键数字

| 数字 | 含义 |
|---|---|
| **β\* ≈ 0.02** | 拐点。崩塌率从 4/8 直接掉到 0/8 |
| **0.86 → 1.33** | 种群熵在这一格跳升 82%，之后是平台 |
| **−0.0076** | 代价。准确率 0.1497 → 0.1421，一次性付清 |

---

## 在线看

- **演示台（可拖滑块）**：https://zhumeiyan.github.io/eo-devo-demo/
- **Hero 动画**：https://raw.githubusercontent.com/zhumeiyan/eo-devo-demo/main/assets/hero-percolation.svg （浏览器打开才有一格格点亮）
- **六状态**：https://raw.githubusercontent.com/zhumeiyan/eo-devo-demo/main/assets/states-percolation.svg
- **设计说明**：`assets/DESIGN.md` · 状态真相源：`assets/status.json`

---

## 视觉母题为什么是渗流

不是装饰。它是从 211 号实测抽出的五个结构签名（阈值 T / 平台 P / 分层 B / 一到多 O / 不可逆 I）里，**唯一同时命中 T + P + I 三个的母题**。

| 211 实测 | 渗流 |
|---|---|
| β < 0.02 崩塌 4/8 | p < p_c 无贯通簇 |
| β\* ≈ 0.02 台阶 | 临界密度 p_c |
| β 加大 80 倍无趋势 | p ≫ p_c 平台 |

**同构的是形状，不是数值。** p_c ≈ 0.5927 是教科书值，不等于这里的 β\* = 0.02。

---

## 我们不假装完美

- 20 个源域的结构签名标签是**我打的，未经测量**。
- 枝晶（另一版母题）被自己的引擎刷下去了：只命中 T+B+O，缺平台与不可逆。
- SVG 动画在 GitHub 私有仓库走 camo 代理时能否播放，**未验证**。

完整失败记录见私有仓库 `eo-devo` 的 `SELF_FAILURES.md`。

---

稿件 1163 配套 · CC BY 4.0 · 朱美岩
