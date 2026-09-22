# LunaFlow PPT · Slide 4 商业模式重构方案

| 文档信息 | 内容 |
| --- | --- |
| 版本 | V1.0 |
| 生成日期 | 2026 年 9 月 22 日 |
| 修订目标 | `docs/cover.html` Slide 4(原"5 大变现引擎") |
| 重构依据 | 用户方向讨论 · 审查文档 §9.4 / §9.5 / §10.4 / §10.5 |
| 配套文件 | `LunaFlow_PPT_修订方案_2026-09-22.md` 中的 Slide 1/2/3/5 修订 |
| 关系 | 本文档**整体替换**主修订方案中 §4.1–§4.7 的 6 项 Slide 4 改动 |

---

## 〇、阅读须知

主修订方案中 §4.1–§4.7 把 Slide 4 定位为"5 条变现路径 + LTV 公式 + 各项加'待验证'",新方案处理为:"先验证任务 → 再验证付费 → 最后放大投流"的**三阶段验证路径**,强调广告只能放大已经成立的价值。

这不是**微调**,而是**整页重构**。原方案的 §4.1–§4.7 在新方向下不再适用,被本文档整体替换。

---

## 一、重构理由

### 1.1 原 Slide 4 隐含的定位风险

原 Slide 4(line 1656–1727)把以下五项并列为"5 大变现引擎",并用 LTV 公式把它们相加:

```
LTV = 订阅 (¥99/年) + 电商 (CPS 15-25%) + 广告 (eCPM ¥8-15) + 数据 (B 端年费) + 保险 (CPS 20%)
```

这个表达隐含的逻辑是:**产品上线 → 同时跑 5 条变现路径 → 用 LTV 倒推获客预算**。这正是审查文档 §10.4 明确反对的:

> **"不要先用头部下载量或全球患病率构造巨大分母,再直接乘以设想年费。"**

### 1.2 用户方向讨论指出的三个不可接受的问题

1. **不能用未验证的单位经济计算预算**
   "若免费用户留存不错、付费始终很弱,这说明产品可能有使用价值,却暂时不适合靠付费广告获客。"

2. **不能用健康焦虑换点击**
   "不建议测试'月经不准可能是严重疾病''AI 看出你能不能怀孕''比医生更懂你'之类表达。即使它们吸引点击,也不等于吸引了适合这个记录工具的人。"

3. **不能用一份通用隐私政策处理敏感健康数据**
   "医疗健康信息属于敏感个人信息,涉及充分必要性、严格保护、单独同意等要求。"

### 1.3 新方向的明确边界

- 不再承诺"做好后靠微信投流就能赚钱"
- 重新定位为"值得小额验证的产品"
- 商业计划 = 验证路径,不是 5 条现金流
- 单位经济只展示**情景测算**,不展示已成立数字
- 三阶段验证:任务 → 付费 → 跨周期,每阶段都有止损线

---

## 二、Slide 4 · 整体结构对比

| 维度 | 原 Slide 4(1656–1727) | 新 Slide 4 |
| --- | --- | --- |
| **header** | "PART 04 · BUSINESS MODEL" / "5 大变现引擎" | "PART 04 · VALIDATION PATH" / "先验证,再放大" |
| **右上次数字** | `5` 引擎 / REVENUE STREAMS | `3` 阶段 / VALIDATION PHASES |
| **左主区** | 商业模式公式 + LTV = ¥99 + CPS + eCPM + B端 + 保险 | 付费设计(免费 + 付费增强)+ 单位经济情景表 |
| **右主区** | 5 张变现引擎卡片(¥99 / CPS 15-25% / eCPM / B端 / 健康险) | 3 张阶段卡(任务验证 / 付费验证 / 跨周期)+ 1 张决策规则卡 |
| **footer quote** | "用户用 1 次/月,但她值得 5 条现金流" | "广告只能放大已经成立的价值" |
| **页码标签** | 04 / 05 · BUSINESS | 04 / 05 · VALIDATION |

---

## 三、Slide 4 · 完整 HTML 替换

### 3.1 替换位置

`docs/cover.html` 第 line 1656 至 line 1727(整个 `<section class="slide s4">` 区块,共 72 行)。

### 3.2 新 HTML 代码(直接替换整段 `<section class="slide s4">` ... `</section>`)

```html
  <!-- ============================================================
       Slide 4 · 商业模式重构
       ============================================================
       重构依据:从"5 大变现引擎"→"3 阶段验证路径"
       · 不预设单位经济,只展示情景测算
       · 付费设计:免费基础 + 付费增强(¥59/¥99 为实验方案)
       · 单位经济:有效用户付费率 × 贡献 - 免费用户成本 = 获客成本上限
       · 验证:任务 → 付费 → 跨周期,每阶段设止损线
       · 决策:四种测试结果对应四种动作
       引用:审查文档 §9.4 / §9.5 / §10.3 / §10.4 / §10.5
       ============================================================ -->
  <section class="slide s4">
    <div class="header">
      <div class="header-left">
        <div class="chapter">PART 04 · VALIDATION PATH</div>
        <h1>商业模式 <span class="accent">·</span> <span class="accent">先验证,再放大</span></h1>
        <div class="sub">付费设计 · 单位经济情景 · 三阶段验证 · 决策规则</div>
      </div>
      <div class="header-right">
        <div class="num"><span data-countup="3">3</span><small> 阶段</small></div>
        <div class="label">VALIDATION PHASES</div>
      </div>
    </div>

    <div class="s4-main">
      <!-- 左:付费设计 + 单位经济情景 -->
      <div class="s4-intro">
        <div class="label">PRICING</div>
        <h2>免费基础 <span class="accent">+</span><br>付费增强</h2>
        <div class="desc">
          极简负责让用户愿意开始,AI 负责减少实际负担,
          可信的历史记录负责让用户回来,付费结果负责证明商业价值。
        </div>

        <!-- 免费基础层 -->
        <div class="s4-tier s4-tier-free">
          <div class="tier-head">
            <span class="tier-name">免费基础</span>
            <span class="tier-tag">RELIABLE · 可靠记录</span>
          </div>
          <div class="tier-content">
            日期记录 · 修改 · 历史查看 · 基础导出 · 权限范围内的提醒 · 有限的 AI 整理(用于首日体验)
          </div>
          <div class="tier-value">交付:可靠地把信息记下来</div>
        </div>

        <!-- 付费增强层 -->
        <div class="s4-tier s4-tier-paid">
          <div class="tier-head">
            <span class="tier-name">付费增强</span>
            <span class="tier-tag">¥59 / ¥99 · 实验方案</span>
          </div>
          <div class="tier-content">
            按指定时间段整理记录 · 跨周期对比 · 持续更新的个人摘要 · 可编辑的就诊准备资料
          </div>
          <div class="tier-value">交付:少整理 · 少遗漏 · 需要时容易说清楚</div>
        </div>

        <!-- 关键边界 -->
        <div class="s4-boundary">
          <span class="warn">⚠️</span>
          查阅 · 纠错 · 注销 · 数据删除
          <strong>不应被设计成会员特权</strong>;
          这些涉及个人信息主体权利,不能靠提高迁移难度制造留存。
        </div>

        <!-- 单位经济情景测算 -->
        <div class="s4-unit-econ">
          <div class="ue-title">
            <span class="s5-dot-accent"></span>
            <strong>单位经济 · 情景测算</strong>
            <span class="ue-flag">[非已验证,仅为盈亏平衡上限]</span>
          </div>
          <table class="ue-table">
            <thead>
              <tr>
                <th>有效用户付费率</th>
                <th>59 元年费方案<br><span class="ue-th-sub">获客成本上限</span></th>
                <th>99 元年费方案<br><span class="ue-th-sub">获客成本上限</span></th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td><strong>2%</strong></td>
                <td>0.41 元 / 有效用户</td>
                <td>1.01 元 / 有效用户</td>
              </tr>
              <tr>
                <td><strong>5%</strong></td>
                <td>1.78 元 / 有效用户</td>
                <td>3.28 元 / 有效用户</td>
              </tr>
              <tr>
                <td><strong>10%</strong></td>
                <td>4.05 元 / 有效用户</td>
                <td>7.05 元 / 有效用户</td>
              </tr>
            </tbody>
          </table>
          <div class="ue-note">
            假设:年费扣除支付/退款/直接服务成本后,59 元方案贡献 45 元/人,99 元方案贡献 75 元/人;未付费有效用户消耗 0.50 元/人。
            公式:获客成本上限 = 付费率 × 贡献 − 未付费比例 × 免费成本。
            <strong>未覆盖</strong>:研发、合规、固定人员等费用。
          </div>
        </div>
      </div>

      <!-- 右:三阶段验证 + 决策规则 -->
      <div class="s4-revenue">
        <div class="s4-rev">
          <div class="num">阶段 1<small>~20–30 人</small></div>
          <div class="name">验证任务完成</div>
          <div class="desc">
            找目标用户对比"普通按钮 vs AI 一句话整理";观察能否独立完成、是否需要频繁纠正、是否愿意下次继续用。
            <span class="rev-meta">DISCOVERY · 探索样本(非统计证明)</span>
          </div>
          <div class="stage">任务 · 价值假设</div>
        </div>

        <div class="s4-rev">
          <div class="num">¥3000<small>广告上限</small></div>
          <div class="name">验证陌生用户付费</div>
          <div class="desc">
            固定主要人群 · 产品版本 · 价格;只换素材,不同改人群/价格/权益/页面。
            记录完整漏斗:广告进入 → 页面到达 → 首次真实记录 → 结果确认 → 再次有效使用 → 实付 → 退款。
            <span class="rev-meta">PAYMENT · 首轮实验预算(非平台最低充值)</span>
          </div>
          <div class="stage">付费 · 经济假设</div>
        </div>

        <div class="s4-rev">
          <div class="num">60–90<small>天</small></div>
          <div class="name">验证跨周期留存</div>
          <div class="desc">
            观察同一批用户在自然周期内的实际使用。周期不规律者按真实任务发生统计,不强按 28 天算流失。
            区分三种行为:回来继续记录 / 回来修改错误 / 仅被提醒后点开。
            <span class="rev-meta">RETENTION · 跨周期窗口</span>
          </div>
          <div class="stage">留存 · 时间假设</div>
        </div>

        <div class="s4-rev s4-rev-decision">
          <div class="num">→ <small>决策</small></div>
          <div class="name">四种结果,四种动作</div>
          <div class="decision-list">
            <div class="decision-item">
              <span class="d-tag d-tag-warn">A</span>
              <span class="d-text">点击不错,但很少完成真实记录 → <strong>优先修改承诺与首屏,暂停扩大投放</strong></span>
            </div>
            <div class="decision-item">
              <span class="d-tag d-tag-warn">B</span>
              <span class="d-text">使用与回访不错,但付费很弱 → <strong>继续验证收费价值,不靠买量扩大免费服务成本</strong></span>
            </div>
            <div class="decision-item">
              <span class="d-tag d-tag-warn">C</span>
              <span class="d-text">有真实付费,但 CAC 持续高于上限 → <strong>优化渠道/转化/价值,不假设续费弥补</strong></span>
            </div>
            <div class="decision-item">
              <span class="d-tag d-tag-ok">D</span>
              <span class="d-text">多批用户持续使用,扣除成本后仍有余量,审核与数据处理稳定 → <strong>才考虑逐步扩大预算</strong></span>
            </div>
          </div>
          <div class="decision-foot">
            付费广告带来的用户要单独计算,不要把自然流量、朋友推荐和原有用户回流混进去。
          </div>
        </div>
      </div>
    </div>

    <div class="footer">
      <div class="brand"><span></span><span>LUNAFLOW · VALIDATION</span></div>
      <div class="quote">"广告只能放大已经成立的价值 — 先证明省心,再证明付费,最后放大"</div>
      <div class="page"><span>04</span> / 05 · VALIDATION</div>
    </div>
  </section>
```

---

## 四、CSS 补充(追加到 `<style>` 块末尾)

> 与主修订方案 §1.1 的 `.audit-flag / .audit-data` 配合使用。
> 新增 7 个类: `.s4-tier / .s4-tier-free / .s4-tier-paid / .tier-head / .tier-name / .tier-tag / .tier-content / .tier-value / .s4-boundary / .s4-unit-econ / .ue-title / .ue-flag / .ue-table / .ue-th-sub / .ue-note / .rev-meta / .s4-rev-decision / .decision-list / .decision-item / .d-tag / .d-tag-warn / .d-tag-ok / .decision-foot`

```css
/* ===== Slide 4 重构:付费设计 + 单位经济 + 决策 ===== */
.s4-tier {
  background: rgba(255, 255, 255, 0.78);
  backdrop-filter: blur(8px);
  border: 1px solid rgba(201, 137, 129, 0.22);
  border-radius: var(--r-md);
  padding: 0.9vw 1.1vw;
  margin-bottom: 0.8vw;
  position: relative;
  overflow: hidden;
}
.s4-tier::before {
  content: "";
  position: absolute;
  top: 0; left: 0;
  width: 3px; height: 100%;
  background: var(--c-rose-300);
}
.s4-tier-free::before { background: linear-gradient(to bottom, #a8a8a8, #d4d4d4); }
.s4-tier-paid::before {
  background: linear-gradient(to bottom, var(--c-rose-500), var(--c-rose-300));
}
.tier-head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.4vw;
}
.tier-name {
  font-family: "Source Han Serif", serif;
  font-weight: 700;
  font-size: var(--fs-body);
  color: var(--c-ink-900);
  letter-spacing: 0.05em;
}
.tier-tag {
  font-size: var(--fs-tag-sm);
  color: var(--c-rose-700);
  background: rgba(201, 137, 129, 0.12);
  padding: 0.1vw 0.6vw;
  border-radius: var(--r-pill);
  letter-spacing: 0.08em;
}
.s4-tier-paid .tier-tag {
  background: linear-gradient(135deg, var(--c-rose-500), var(--c-rose-700));
  color: white;
}
.tier-content {
  font-size: var(--fs-tag);
  color: var(--c-ink-700);
  line-height: 1.55;
  margin-bottom: 0.4vw;
}
.tier-value {
  font-size: var(--fs-tag-sm);
  color: var(--c-rose-700);
  font-style: italic;
  letter-spacing: 0.03em;
}

.s4-boundary {
  background: rgba(244, 200, 200, 0.4);
  border: 1px dashed rgba(201, 137, 129, 0.4);
  border-radius: var(--r-sm);
  padding: 0.6vw 0.9vw;
  font-size: var(--fs-tag-sm);
  color: var(--c-ink-700);
  line-height: 1.6;
  margin-bottom: 0.8vw;
  letter-spacing: 0.03em;
}
.s4-boundary strong { color: var(--c-rose-700); }
.s4-boundary .warn {
  margin-right: 0.4vw;
  color: var(--c-rose-500);
}

/* ===== 单位经济情景表 ===== */
.s4-unit-econ {
  background: linear-gradient(135deg, rgba(201, 137, 129, 0.08), rgba(232, 165, 165, 0.05));
  border: 1px solid rgba(201, 137, 129, 0.25);
  border-radius: var(--r-md);
  padding: 0.9vw 1.1vw;
}
.ue-title {
  display: flex;
  align-items: center;
  gap: 0.4vw;
  margin-bottom: 0.5vw;
}
.ue-title strong {
  font-family: "Source Han Serif", serif;
  font-size: var(--fs-h3);
  color: var(--c-ink-900);
}
.ue-flag {
  margin-left: auto;
  font-size: var(--fs-tag-sm);
  color: var(--c-rose-700);
  font-style: italic;
  letter-spacing: 0.05em;
}
.ue-table {
  width: 100%;
  border-collapse: collapse;
  font-family: "Source Han Serif", serif;
  font-size: var(--fs-tag);
  color: var(--c-ink-900);
  margin-bottom: 0.5vw;
}
.ue-table thead th {
  background: rgba(201, 137, 129, 0.12);
  color: var(--c-rose-700);
  padding: 0.4vw 0.6vw;
  text-align: left;
  font-weight: 700;
  letter-spacing: 0.03em;
  border-bottom: 2px solid rgba(201, 137, 129, 0.3);
  font-size: var(--fs-tag-sm);
}
.ue-table tbody td {
  padding: 0.35vw 0.6vw;
  border-bottom: 1px dashed rgba(201, 137, 129, 0.18);
  font-size: var(--fs-tag);
  color: var(--c-ink-800);
}
.ue-table tbody tr:last-child td { border-bottom: none; }
.ue-table tbody td:first-child { color: var(--c-rose-700); }
.ue-table tbody td strong {
  font-size: var(--fs-body);
  letter-spacing: 0.02em;
}
.ue-th-sub {
  display: block;
  font-family: "PingFang SC", sans-serif;
  font-weight: 400;
  font-size: 0.6vw;
  color: var(--c-ink-500);
  margin-top: 0.1vw;
  letter-spacing: 0.05em;
}
.ue-note {
  font-size: var(--fs-tag-sm);
  color: var(--c-ink-600);
  line-height: 1.6;
  letter-spacing: 0.02em;
  padding-top: 0.4vw;
  border-top: 1px dashed rgba(201, 137, 129, 0.2);
}
.ue-note strong { color: var(--c-rose-700); }

/* ===== 阶段卡片 meta 标注 ===== */
.rev-meta {
  display: block;
  margin-top: 0.4vw;
  font-size: 0.65vw;
  color: var(--c-rose-700);
  letter-spacing: 0.08em;
  font-style: italic;
  opacity: 0.75;
}

/* ===== 决策规则卡片 ===== */
.s4-rev-decision {
  grid-column: 1 / -1;
  background: linear-gradient(135deg, rgba(201, 137, 129, 0.1), rgba(244, 200, 200, 0.15));
}
.s4-rev-decision .num {
  font-size: 1.5vw;
  color: var(--c-rose-700);
}
.decision-list {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 0.5vw 1vw;
  margin: 0.4vw 0;
}
.decision-item {
  display: flex;
  align-items: flex-start;
  gap: 0.5vw;
  font-size: var(--fs-tag-sm);
  color: var(--c-ink-700);
  line-height: 1.5;
}
.d-tag {
  flex-shrink: 0;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 1.4vw;
  height: 1.4vw;
  border-radius: 50%;
  font-family: "Source Han Serif", serif;
  font-weight: 700;
  font-size: var(--fs-tag-sm);
  color: white;
}
.d-tag-warn { background: linear-gradient(135deg, #d89595, #c98981); }
.d-tag-ok   { background: linear-gradient(135deg, #9c7878, #7a5858); }
.d-text strong { color: var(--c-ink-900); }
.decision-foot {
  margin-top: 0.4vw;
  font-size: 0.65vw;
  color: var(--c-rose-700);
  letter-spacing: 0.05em;
  font-style: italic;
  padding-top: 0.4vw;
  border-top: 1px dashed rgba(201, 137, 129, 0.3);
}
```

---

## 五、对其他 Slide 的连锁影响(微调,不是重构)

新方向不是只改 Slide 4 就能成立的。其他 Slide 至少有 4 处需要相应调整,但都是措辞级改动,不是结构级重构。

### 5.1 Slide 1(封面)· pillar 3 改写

**位置**: line 1451–1455。

**修订前**:

```html
<div class="s1-pillar">
  <div class="num">03</div>
  <div class="label">商业服务</div>
  <div class="desc">订阅会员 · 卫生用品商城<br>品牌合作 · 健康险引流</div>
</div>
```

**修订后**:

```html
<div class="s1-pillar">
  <div class="num">03</div>
  <div class="label">验证路径</div>
  <div class="desc">免费基础 · 付费增强<br>先验证任务,再验证付费</div>
</div>
```

**引用**: 审查文档 §9.5(三个可优先测试的产品假设)。

### 5.2 Slide 2(痛点市场)· footer quote 改写(配合主修订方案 §6)

**位置**: line 1556,主修订方案 §6 已替换 footer 文本,这里额外调整 quote。

**修订前**(主修订方案 §6 修订后):

```
"万亿赛道里,工具已普及,深层任务仍待完成"
```

**修订后**:

```
"工具已经普及,深层任务仍待完成 — 但商业价值需小额验证,不能先预设投流"
```

**引用**: 用户方向讨论 §四 / 审查文档 §9.4。

### 5.3 Slide 3(产品)· hero h2 微调

**位置**: line 1583。

**修订前**(主修订方案 §3.1):

```html
<h2>让每位女性<br><span class="accent">更懂自己的周期</span></h2>
```

**修订后**(无需大改,可保留):

```html
<h2>把每月「被动应对」<br>变成<span class="accent">「主动规划」</span></h2>
```

**理由**: 用户方向讨论明确"AI 减少操作和整理信息,而不是扮演妇科医生"——把"更懂自己"这种带人格承诺的措辞改为更具体的"主动规划",与 §3.1(10 万+ 用户训练 删除)形成一致的克制口径。

### 5.4 Slide 3(产品)· feat #6 智能商城 删除

**位置**: line 1627–1630(主修订方案未涉及此卡)。

**修订前**:

```html
<div class="s3-feat">
  <div class="feat-icon">🛍️</div>
  <div class="feat-name">智能商城</div>
  <div class="feat-tag">SHOP</div>
  <div class="feat-desc">按周期推荐 · 卫生巾/棉条/暖宫贴/营养品</div>
</div>
```

**修订后**(整张卡片删除,改为 AI 整理):

```html
<div class="s3-feat">
  <div class="feat-icon">✏️</div>
  <div class="feat-name">一句话整理<span class="audit-flag" title="见审查文档 §9.2 / 用户方向讨论">AI 辅助</span></div>
  <div class="feat-tag">DRAFT</div>
  <div class="feat-desc">写一句自动整理为可确认记录卡 · 不猜测未提供字段</div>
</div>
```

**引用**: 审查文档 §9.2 + 用户方向讨论 §二.1("生成一张待确认记录卡")。

### 5.5 Slide 5 ops-hint 已包含在主修订方案 §5.3,无需再改

---

## 六、新 Slide 4 与审查文档的引用对应

| 新 Slide 4 元素 | 主要引用 | 次要引用 |
| --- | --- | --- |
| "先验证,再放大" header | 用户方向讨论 §七 | 审查文档 §9.4 / §10.3 |
| 3 阶段 VALIDATION PHASES | 审查文档 §10.2(三层验证顺序) | 用户方向讨论 §七 |
| 付费设计 · 免费基础 | 审查文档 §9.5(三个产品假设) | 用户方向讨论 §三 |
| 付费设计 · ¥59/¥99 实验方案 | 用户方向讨论 §三 | 审查文档 §9.4 |
| 数据删除不是会员特权 | 审查文档 §9.3(隐私) | 用户方向讨论 §三 |
| 单位经济情景表 | 用户方向讨论 §四.2 | 审查文档 §10.4 |
| "非已验证" 标注 | 审查文档 §10.4 | 用户方向讨论 §四.3 |
| 阶段 1 · 20-30 人验证 | 用户方向讨论 §七.一 | 审查文档 §10.2 |
| 阶段 2 · ¥3000 广告上限 | 用户方向讨论 §七.二 | 审查文档 §9.4 |
| 阶段 3 · 60-90 天跨周期 | 用户方向讨论 §七.三 | 审查文档 §10.3 |
| 决策规则 A/B/C/D | 用户方向讨论 §七.三 | 审查文档 §10.5 |
| footer quote | 用户方向讨论 §七 | 审查文档 §11.6 |

---

## 七、落地检查清单(应用本文档后请逐项确认)

- [ ] Slide 4 整段 `<section class="slide s4">` 已按 §三 替换
- [ ] §四 CSS 已加入 `<style>` 块末尾
- [ ] 7 个新增组件在页面渲染正常(`.s4-tier / .s4-boundary / .s4-unit-econ / .ue-table / .decision-list / .d-tag-warn / .d-tag-ok`)
- [ ] Slide 1 pillar 3 已改为"验证路径"(§五.1)
- [ ] Slide 2 footer quote 已改为"工具已经普及,深层任务仍待完成 — 但商业价值需小额验证"(§五.2)
- [ ] Slide 3 hero h2 已改为"把每月「被动应对」变成「主动规划」"(§五.3)
- [ ] Slide 3 feat #6 已替换为"一句话整理"卡(§五.4)
- [ ] 主修订方案 §4.1–§4.7 标记为"已替换为本文档",不再单独应用
- [ ] 表格中所有数字(¥59/¥99/¥45/¥75/¥0.50)均挂"情景假设 / 非已验证"标识
- [ ] "广告只能放大已经成立的价值"作为 PPT Slide 4 的核心结论,在 footer 与决策卡 D 中一致出现

---

## 八、与原修订方案的关系

| 文件 | 适用范围 | 处理 |
| --- | --- | --- |
| `LunaFlow_PPT_修订方案_2026-09-22.md` §1.1 CSS | Slide 全局审计标记 | **保留,继续应用** |
| 主修订方案 §2 (Slide 2) | 痛点市场 | **保留,继续应用** |
| 主修订方案 §3 (Slide 3) | 产品 5 项 | **保留 5 项**(§3.6 / §3.1 / §3.2 / §3.3 / §3.4 / §3.5),**追加 §五.3 / §五.4 的 2 项微调** |
| **主修订方案 §4 (Slide 4) 6 项** | 商业模式 | **整体替换为本文档** |
| 主修订方案 §5 (Slide 5) | 研报全景 | **保留,继续应用** |
| 主修订方案 §6 (Slide 2 footer) | 数据使用脚注 | **保留,继续应用** |

---

**文档终结论:Slide 4 从"5 大变现引擎"重构为"3 阶段验证路径 + 付费设计 + 单位经济情景 + 决策规则",整体替换主修订方案 §4.1–§4.7。其他 Slide 的连锁影响(§五.1–§五.4 共 4 处微调)需在应用时一并落地。本方案严格遵守"广告只能放大已经成立的价值"——不预设单位经济,不用健康焦虑换点击,不混同自然流量与广告流量。**