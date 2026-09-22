# LunaFlow PPT (`cover.html`) 修订方案

| 文档信息 | 内容 |
| --- | --- |
| 版本 | V1.0 |
| 生成日期 | 2026 年 9 月 22 日 |
| 修订目标 | `docs/cover.html` (LunaFlow · 商业模式 PPT · 5 张幻灯片) |
| 参考依据 | `docs/经期管理与女性健康应用市场_观点审查与立项分析_2026-09-22.md` |
| 修订原则 | 按审查文档 §1.2 修订表 + §11 修订结论,逐处修正 / 降级 / 加来源 |
| 应用方式 | 本文档为修订清单;实际改动请在评审后由 Edit 工具按"位置 → 修订前 → 修订后"逐条落地 |

---

## 〇、修订分级与总览

| 等级 | 处理 | 数量 | 说明 |
| --- | --- | ---: | --- |
| **A · 必须删除** | 无证据的虚构数字或夸大承诺 | 6 项 | 不删除会直接影响 BP 可信度 |
| **B · 改写 + 加来源** | 口径混用、未标版本、未注统计月份 | 7 项 | 保留数据但修正表述 |
| **C · 加"待验证"标签** | 单位经济假设、AI/医生能力宣传 | 6 项 | 保留方向但降级承诺强度 |
| 此外总 | | **19 处** | + 1 处 CSS 补充 + 1 处 S5 ops-hint 重写 |

---

## 一、CSS 补充(类:评审样态)

> 用于在 PPT 内把"待修订 / 数据 / 待验证"位置打上视觉标记,确保 review 时不漏。

### 1.1 在 `</style>` 之前(约 line 1399)插入

```css
/* ===== 审计标记(对照审查文档)===== */
.audit-flag {
  display: inline-block;
  font-size: var(--fs-tag-sm);
  color: white;
  background: linear-gradient(135deg, #c98981, #a06565);
  padding: 1px 8px;
  border-radius: var(--r-pill);
  letter-spacing: 0.1em;
  margin-left: 0.4vw;
  vertical-align: middle;
  cursor: help;
  font-family: var(--fs-meta), sans-serif;
}
.audit-flag::before { content: "📋 "; opacity: .85; }

.audit-data {
  font-size: var(--fs-mini);
  color: var(--c-rose-700);
  background: rgba(201, 137, 129, 0.08);
  border-left: 2px solid var(--c-rose-500);
  padding: 2px 8px;
  margin-top: 4px;
  border-radius: 2px;
  display: block;
  font-style: italic;
  letter-spacing: 0.03em;
}
.audit-pending {
  color: var(--c-ink-500);
  font-style: italic;
  opacity: 0.85;
}

.ppt-footnote {
  position: absolute;
  bottom: 7%; left: 6.5%; right: 6.5%;
  font-size: var(--fs-mini);
  color: var(--c-ink-500);
  letter-spacing: 0.05em;
  line-height: 1.6;
  border-top: 1px dashed rgba(201, 137, 129, 0.3);
  padding-top: 0.4vw;
  z-index: 4;
}
.ppt-footnote b { color: var(--c-rose-700); font-family: "Source Han Serif", serif; }
```

**引用**: 与审查文档 §2.5(指标字典)、§12.2(数据使用规则)对应。

---

## 二、Slide 2 · 痛点市场(8 项修改,问题最集中)

### 2.1 S2 header · "¥1.0 万亿"—— B 改写

**修订前**(line 1483–1485):

```html
<div class="header-right">
  <div class="num">¥ <span data-countup="1.0">1.0</span><small> 万亿</small></div>
  <div class="label">WOMEN HEALTH</div>
</div>
```

**修订后**:

```html
<div class="header-right">
  <div class="num">¥ <span data-countup="1.0">1.0</span><small> 万亿</small><span class="audit-flag" title="见审查文档 §2.1 / §6.5 / §11.5">口径</span></div>
  <div class="label">WOMEN HEALTH · 行业经济规模</div>
  <div class="audit-data">WEF/BCG 估算·女性健康差距年度经济成本;非女性健康 APP 市场规模</div>
</div>
```

**引用**: 审查文档 §2.1(市场边界)、§2.2(48.6 亿 vs 1T 不可拼接)、§11.1(市场判断)。
**风险**: 1 万亿是 WEF/BCG 估的**经济成本**(因健康差距产生的 GDP 损失),不是**APP 市场规模**(48.6 亿美元);PPT 之前的"全球女性健康支出 1 万亿美元"是口径错误。

---

### 2.2 S2 narrative · "全球女性健康支出 1 万亿美元,但经期管理工具仍是「日历 + 表格」的拼凑"—— B 改写

**修订前**(line 1495–1498):

```html
<div class="sub">
  全球女性健康支出 <strong>1 万亿美元</strong>,但经期管理工具仍是「日历 + 表格」的拼凑。
  女性从 12 岁到 55 岁的 <strong>40+ 年</strong>,都在和周期、情绪、身体的反复博弈。
</div>
```

**修订后**:

```html
<div class="sub">
  据 <strong>WEF/BCG 估算</strong>,女性健康差距每年带来约 <strong>1 万亿美元</strong>的全球生产力损失;
  主流经期管理 App 的核心记录功能已普及,但在症状整理、隐私保护、医疗衔接等深层任务上完成度参差。
  女性从青春期到围绝经期的 <strong>40+ 年</strong>,都面对周期管理的反复需求。
</div>
<div class="audit-data">
  · 1T 美元为经济成本估算(WEF/BCG),非 APP 市场规模;后者约 48.6 亿美元(2026 年,BRI 估算)
  · "拼凑感"系研究印象,非逐款实测结论;不同应用/系统工具的能力差异显著
</div>
```

**引用**: 审查文档 §2.1、§3.5(头部产品差异需同版本验证)、§9.1(系统工具是替代品)、§11.5(医疗与隐私判断)。

---

### 2.3 S2 stat #1 · "3.6 亿 中国育龄女性"—— C 加来源

**修订前**(line 1501–1503):

```html
<div class="s2-stat">
  <div class="num"><span data-countup="3.6">3.6</span><small> 亿</small></div>
  <div class="lbl">中国育龄女性</div>
</div>
```

**修订后**:

```html
<div class="s2-stat">
  <div class="num"><span data-countup="3.6">3.6</span><small> 亿</small><span class="audit-flag" title="见审查文档 §4.2">来源</span></div>
  <div class="lbl">中国育龄女性(15–49 岁)</div>
  <div class="audit-data">国家统计局·2023;本数字为人群规模,不等同于付费市场</div>
</div>
```

**引用**: 审查文档 §4.2(用户画像不能只由品牌风格推导)、§4.3(经期与孕期用户不宜合并为单一画像)。

---

### 2.4 S2 stat #2 · "7.2 年 平均经期流失时间"—— A 删除

**修订前**(line 1505–1507):

```html
<div class="s2-stat">
  <div class="num"><span data-countup="7.2">7.2</span><small> 年</small></div>
  <div class="lbl">平均经期流失时间</div>
</div>
```

**修订后**(整块删除,替换为可证伪的统计):

```html
<div class="s2-stat">
  <div class="num">~<span data-countup="40">40</span><small> 年</small></div>
  <div class="lbl">女性经期管理周期(青春期–围绝经期)</div>
  <div class="audit-data">·"7.2 年"未在审查文档可证据链中找到;予以删除,避免无来源数字进入 BP</div>
</div>
```

**引用**: 审查文档 §12.1(待核实清单)、§2.5(指标字典:累计 vs 活跃 vs 时长)。**理由**: 这是典型"听起来合理但无来源"的伪精确数字;审查文档全文未支持该数字,继续保留会直接降低 BP 可信度。

---

### 2.5 S2 stat #3 · "80% 经历经期不适"—— B 改写

**修订前**(line 1509–1511):

```html
<div class="s2-stat">
  <div class="num"><span data-countup="80">80</span><small> %</small></div>
  <div class="lbl">经历经期不适</div>
</div>
```

**修订后**:

```html
<div class="s2-stat">
  <div class="num"><span data-countup="30">30</span>–<span data-countup="40">40</span><small> %</small><span class="audit-flag" title="见审查文档 §8.3 / §11.5">待验证</span></div>
  <div class="lbl">受经前综合征(PMS)显著影响</div>
  <div class="audit-data">·"80%"未注明具体研究,样本与定义不明;改用 PMS 比例作为更可验证的近似值</div>
</div>
```

**引用**: 审查文档 §8.3(需求分组是研究假设)、§11.5(医疗与隐私判断)。

---

### 2.6 S2 stat #4 · "3 倍 情绪波动 vs 男性"—— A 删除

**修订前**(line 1513–1515):

```html
<div class="s2-stat">
  <div class="num"><span data-countup="3">3</span><small> 倍</small></div>
  <div class="lbl">情绪波动 vs 男性</div>
</div>
```

**修订后**(删除整个卡片,改为更准确的表述):

```html
<!-- 原"3 倍 情绪波动 vs 男性"已删除 -->
<!-- 理由:"情绪波动"是流传的伪科普,与 PMS 比例不同;改为下方文字稿中说明 -->
```

并在 S2 narrative(原 line 1495–1498)补充一句:

```html
  <!-- 在"反复需求"句后追加 -->
  其中 <strong>30%–40%</strong> 受经前综合征(PMS)显著影响,但情绪波动为个体差异,不宜作为性别差异的通用结论。
```

**引用**: 审查文档 §7.5(疾病负担不能直接推导软件付费意愿)、§8.3(需求组)。

---

### 2.7 S2 painpoint · "记录琐碎"—— B 改写

**修订前**(line 1522–1525):

```html
<div class="s2-pp">
  <div class="icon">📊</div>
  <div class="name">记录琐碎</div>
  <div class="desc">市面 App 仅"日期 + 流量",无法记录情绪、症状、用药、睡眠</div>
</div>
```

**修订后**:

```html
<div class="s2-pp">
  <div class="icon">📊</div>
  <div class="name">记录维度单一</div>
  <div class="desc">主流工具侧重"日期 + 流量";对情绪、症状、用药等结构化记录的完成度参差,需逐款体验</div>
</div>
```

**引用**: 审查文档 §3.5(头部产品差异需通过同版本体验验证)、§4.1(候选竞品)、§9.1(系统工具是替代品)。

---

### 2.8 S2 painpoint · "预测失准"—— B 改写

**修订前**(line 1527–1530):

```html
<div class="s2-pp">
  <div class="icon">🔮</div>
  <div class="name">预测失准</div>
  <div class="desc">基于固定 28 天周期预测,忽略个体差异(21-35 天均正常)</div>
</div>
```

**修订后**:

```html
<div class="s2-pp">
  <div class="icon">🔮</div>
  <div class="name">非规律周期预测</div>
  <div class="desc">基于"28 天固定周期"的预测对 21–35 天波动范围的多样性不友好,需个体化模型验证</div>
</div>
```

**引用**: 审查文档 §7.1(特定人群的日期预测需要特别验证)、§7.4(连续管理比单次预测更值得验证)。

---

### 2.9 S2 painpoint · "难以启齿"—— C 加"待验证"

**修订前**(line 1532–1535):

```html
<div class="s2-pp">
  <div class="icon">💬</div>
  <div class="name">难以启齿</div>
  <div class="desc">经期/妇科问题羞耻感强,缺私密社区与医生咨询通道</div>
</div>
```

**修订后**:

```html
<div class="s2-pp">
  <div class="icon">💬</div>
  <div class="name">交流与问诊意愿<span class="audit-flag" title="见审查文档 §4.2 / §5.4 / §11.3">假设</span></div>
  <div class="desc">用户对私密交流与医生通道的接受度,是待验证需求,非已证实现状</div>
</div>
```

**引用**: 审查文档 §4.2(用户画像不能只由品牌风格推导)、§5.4(小程序商业空间)、§11.3(产品机会判断)、§11.5(医疗判断)。

---

### 2.10 S2 painpoint · "选购低效"—— C 加"待验证"

**修订前**(line 1537–1540):

```html
<div class="s2-pp">
  <div class="icon">🛒</div>
  <div class="name">选购低效</div>
  <div class="desc">卫生巾/棉条/护垫品类繁多,无个性化推荐与试用机制</div>
</div>
```

**修订后**:

```html
<div class="s2-pp">
  <div class="icon">🛒</div>
  <div class="name">按周期推荐</div>
  <div class="desc">将卫生用品推荐与周期阶段匹配,作为商业化候选路径;实际需求与复购意愿需用户访谈验证</div>
</div>
```

**引用**: 审查文档 §9.4(从用户量补到谁付费、为何续费)、§9.5(三个可优先测试的产品假设)。

---

### 2.11 S2 painpoint · "就诊断层"—— B 改写

**修订前**(line 1542–1545):

```html
<div class="s2-pp">
  <div class="icon">🩺</div>
  <div class="name">就诊断层</div>
  <div class="desc">PCOS/痛经/更年期等需长期跟踪,但缺数据接口给医生</div>
</div>
```

**修订后**:

```html
<div class="s2-pp">
  <div class="icon">🩺</div>
  <div class="name">就诊资料整理</div>
  <div class="desc">对 PCOS/痛经/更年期人群,价值不仅在预测,更在症状时间线整理与就诊摘要导出;数据接入需用户授权</div>
</div>
```

**引用**: 审查文档 §7.1(完全无效表述须删除)、§7.4(连续管理)、§9.3(隐私:不默认向机构开放)。

---

### 2.12 S2 painpoint · "情绪孤岛"—— C 加"待验证"

**修订前**(line 1547–1550):

```html
<div class="s2-pp">
  <div class="icon">🌡️</div>
  <div class="name">情绪孤岛</div>
  <div class="desc">经前综合征(PMS)情绪波动被误判为"作",缺共情工具</div>
</div>
```

**修订后**:

```html
<div class="s2-pp">
  <div class="icon">🌡️</div>
  <div class="name">情绪支持</div>
  <div class="desc">情绪陪伴与共情工具是候选方向;用户付费意愿与具体功能形态需通过测试验证</div>
</div>
```

**引用**: 审查文档 §5.3(没有社区不等于没有留存)、§8.3(需求分组是研究假设)。

---

## 三、Slide 3 · 产品(6 项修改)

### 3.1 S3 hero · "基于 10 万+ 用户数据训练的预测模型"—— A 删除

**修订前**(line 1585–1588):

```html
<p>
  LunaFlow 不只是经期记录器,更是女性全周期的智能伙伴。
  基于 10 万+ 用户数据训练的预测模型,结合症状-情绪-体征多维日志,
  把每月「被动应对」变成「主动规划」。
</p>
```

**修订后**:

```html
<p>
  LunaFlow 不是经期记录器,而是基于个体多维日志的全周期伙伴。
  通过症状-情绪-体征多维记录,把每月「被动应对」变成「主动规划」。
  AI 模型将以任务改善(对话式记录 / 摘要可追溯 / 错误可纠正)为核心评价标准,而非标签承诺。
</p>
<div class="audit-data">
  · "10 万+ 用户训练"在立项阶段无证据支撑,予以删除
  · AI 任务边界见审查文档 §9.2:不猜测未提供的日期/症状/用药;不把"相关"写成"病因";不编造检查结论
</div>
```

**引用**: 审查文档 §9.2(AI 应以任务改善衡量,不以标签衡量)、§11.5(医疗判断)、§12.1(竞品 AI 准确率未独立验证)。

---

### 3.2 S3 feat #2 · "排卵期预测 ±1 天"—— C 加"待验证"

**修订前**(line 1603–1606):

```html
<div class="s3-feat">
  <div class="feat-icon">🤖</div>
  <div class="feat-name">精准预测</div>
  <div class="feat-tag">AI</div>
  <div class="feat-desc">个体化周期模型 · 排卵期预测 ±1 天 · 怀孕概率</div>
</div>
```

**修订后**:

```html
<div class="s3-feat">
  <div class="feat-icon">🤖</div>
  <div class="feat-name">个体化预测<span class="audit-flag" title="见审查文档 §6.4 / §11.5">待验证</span></div>
  <div class="feat-tag">AI</div>
  <div class="feat-desc">基于个体多维日志的周期模型 · 准确率以临床测试为准 · 不替代避孕/诊断</div>
</div>
```

**引用**: 审查文档 §6.4(Natural Cycles 93%/98% 是避孕有效率,不是排卵期预测精度;不能跨场景换算)、§11.5。

---

### 3.3 S3 feat #3 · "妇科医生审核的 500+ 篇内容"—— B 改写

**修订前**(line 1609–1612):

```html
<div class="s3-feat">
  <div class="feat-icon">💡</div>
  <div class="feat-name">健康科普</div>
  <div class="feat-tag">CONTENT</div>
  <div class="feat-desc">PMS/PCOS/更年期 · 妇科医生审核的 500+ 篇内容</div>
</div>
```

**修订后**:

```html
<div class="s3-feat">
  <div class="feat-icon">💡</div>
  <div class="feat-name">健康科普</div>
  <div class="feat-tag">CONTENT</div>
  <div class="feat-desc">PMS/PCOS/更年期等内容 · 医生资质、来源与更新频率以版本记录为准 · 不替代个体诊疗</div>
</div>
```

**引用**: 审查文档 §9.2(健康知识解释·不把一般科普当作个体治疗方案)、§11.5。

---

### 3.4 S3 feat #4 · "三甲妇科医生在线"—— C 加"资质为准"

**修订前**(line 1615–1618):

```html
<div class="s3-feat">
  <div class="feat-icon">🩺</div>
  <div class="feat-name">在线问诊</div>
  <div class="feat-tag">DOCTOR</div>
  <div class="feat-desc">三甲妇科医生在线 · 隐私脱敏 · 报告解读</div>
</div>
```

**修订后**:

```html
<div class="s3-feat">
  <div class="feat-icon">🩺</div>
  <div class="feat-name">在线问诊<span class="audit-flag" title="见审查文档 §6.1 / §11.5">资质为准</span></div>
  <div class="feat-tag">DOCTOR</div>
  <div class="feat-desc">医生团队构成、执业资质、问诊范围以届时上架版本为准;订阅/医生参与不构成医疗用途授权</div>
</div>
```

**引用**: 审查文档 §6.1(订阅、AI 或医生参与不能替代具体医疗用途授权)、§11.5。

---

### 3.5 S3 feat #7 · "医生可直接调阅"—— B 改写

**修订前**(line 1633–1636):

```html
<div class="s3-feat">
  <div class="feat-icon">📈</div>
  <div class="feat-name">健康报告</div>
  <div class="feat-tag">REPORT</div>
  <div class="feat-desc">月度健康报告 · 趋势图 · 医生可直接调阅</div>
</div>
```

**修订后**:

```html
<div class="s3-feat">
  <div class="feat-icon">📈</div>
  <div class="feat-name">健康报告</div>
  <div class="feat-tag">REPORT</div>
  <div class="feat-desc">月度趋势图 · 用户授权后可导出可分享的就诊摘要;医生数据访问需逐次确认</div>
</div>
```

**引用**: 审查文档 §9.3(隐私:不默认向机构或伴侣开放)、§9.5(机构随访是验证方向,不是已实现能力)。

---

### 3.6 S3 footer · quote —— B 改写

**修订前**(line 1647–1649):

```html
<div class="footer">
  <div class="brand"><span></span><span>LUNAFLOW · PRODUCT</span></div>
  <div class="quote">"从「日历」到「关怀」— 让数据为她服务"</div>
  <div class="page"><span>03</span> / 05 · PRODUCT</div>
</div>
```

**修订后**:

```html
<div class="footer">
  <div class="brand"><span></span><span>LUNAFLOW · PRODUCT</span></div>
  <div class="quote">"从「记录」到「理解」 — 以任务改善衡量产品价值"</div>
  <div class="page"><span>03</span> / 05 · PRODUCT</div>
</div>
```

**引用**: 审查文档 §9.2("提供 AI"不是结论;"在安全边界内明显改善一个具体任务"才值得验证)。

---

## 四、Slide 4 · 商业模式(6 项修改)

### 4.1 S4 formula · LTV 5 行—— A 全部降级

**修订前**(line 1678–1684):

```html
<div class="s4-formula">
  <span class="v">LTV</span> = 订阅 (¥99/年)<br>
  <span style="margin-left: 1vw;">+ 电商 (CPS 15-25%)</span><br>
  <span style="margin-left: 1vw;">+ 广告 (eCPM ¥8-15)</span><br>
  <span style="margin-left: 1vw;">+ 数据 (B 端年费)</span><br>
  <span style="margin-left: 1vw;">+ 保险 (CPS 20%)</span>
</div>
```

**修订后**:

```html
<div class="s4-formula">
  <span class="v">LTV</span> ≈ 订阅 + 电商 + 广告 + 数据 + 保险<br>
  <span style="font-size: var(--fs-tag); color: var(--c-rose-700); letter-spacing: 0.1em;">
    [测算结构 · 非已验证单位经济]
  </span>
</div>
<div class="audit-data">
  · 公式仅定义测算结构,各数字为情景假设,需 MVP 后小样本验证(见审查文档 §9.4 / §10.4)
  · 订阅价格 / eCPM / CPS 比例均未经过 A/B 测试或真实成交数据校准
  · 广告毛利率未必高于订阅,需比较同一期间的实际收入、毛利和获客回收期
</div>
```

**引用**: 审查文档 §9.4(订阅标价较高并不能直接证明单位经济优于广告)、§10.4(简化收入模型仅定义测算结构)、§12.1(用户愿为隐私或极简付费属于商业假设)。

---

### 4.2 S4 rev #1 · "¥99/年 会员订阅"—— C 加"待验证"

**修订前**(line 1689–1693):

```html
<div class="s4-rev">
  <div class="num">¥99<small>/年</small></div>
  <div class="name">会员订阅</div>
  <div class="desc">深度报告 · 医生问诊 · 个性化推荐 · 数据云同步</div>
  <div class="stage">PRIMARY · 主路径</div>
</div>
```

**修订后**:

```html
<div class="s4-rev">
  <div class="num">¥? <small>/年</small><span class="audit-flag" title="见审查文档 §9.4">待定</span></div>
  <div class="name">会员订阅</div>
  <div class="desc">深度报告 · 医生问诊 · 个性化推荐 · 数据云同步;价格为情景假设,需 A/B 验证</div>
  <div class="stage">PRIMARY · 主路径</div>
</div>
```

**引用**: 审查文档 §9.4(续费数据需实际测试)。

---

### 4.3 S4 rev #2 · "CPS 15-25% 周期商城"—— C 加"待验证"

**修订前**(line 1695–1699):

```html
<div class="s4-rev">
  <div class="num">CPS<small>15-25%</small></div>
  <div class="name">周期商城</div>
  <div class="desc">卫生巾 · 棉条 · 暖宫贴 · 营养品 · 按周期推荐</div>
  <div class="stage">CORE · 核心</div>
</div>
```

**修订后**:

```html
<div class="s4-rev">
  <div class="num">CPS<small>? %</small><span class="audit-flag" title="见审查文档 §9.4 / §10.4">待验证</span></div>
  <div class="name">周期商城</div>
  <div class="desc">卫生巾 · 棉条 · 暖宫贴 · 营养品 · 按周期推荐;CPS 比例需实际渠道议价后确定</div>
  <div class="stage">CORE · 核心</div>
</div>
```

**引用**: 审查文档 §9.4(用户订阅差异是否足够明确)。

---

### 4.4 S4 rev #3 · "eCPM ¥8-15 原生广告"—— C 加"待验证"

**修订前**(line 1701–1705):

```html
<div class="s4-rev">
  <div class="num">eCPM<small>¥8-15</small></div>
  <div class="name">原生广告</div>
  <div class="desc">科普内容 · 品牌种草 · 妇科/护肤/健康品牌精准投放</div>
  <div class="stage">SCALE · 规模化</div>
</div>
```

**修订后**:

```html
<div class="s4-rev">
  <div class="num">eCPM<small>?</small><span class="audit-flag" title="见审查文档 §9.4">待验证</span></div>
  <div class="name">原生广告</div>
  <div class="desc">科普内容 · 品牌种草 · 妇科/护肤/健康品牌精准投放;eCPM 与体验损害需实测</div>
  <div class="stage">SCALE · 规模化</div>
</div>
```

**引用**: 审查文档 §9.4(广告:每活跃用户能贡献多少收入,是否损害核心体验)。

---

### 4.5 S4 rev #4 · "B 端年费 数据洞察"—— B 改写

**修订前**(line 1707–1711):

```html
<div class="s4-rev">
  <div class="num">B 端<br>年费</div>
  <div class="name">数据洞察</div>
  <div class="desc">品牌方可购买脱敏趋势数据 · 研发/营销/选址</div>
  <div class="stage">HIGH-MARGIN · 高毛利</div>
</div>
```

**修订后**:

```html
<div class="s4-rev">
  <div class="num">B 端<br>年费</div>
  <div class="name">数据洞察</div>
  <div class="desc">品牌方可购买脱敏趋势数据(需用户授权链路与法律审查);研发/营销参考</div>
  <div class="stage">HIGH-MARGIN · 高毛利</div>
</div>
```

**引用**: 审查文档 §9.3(隐私是产品要求与成本;§6.5 Ovia 数据粒度不可泛称)、§11.5。

---

### 4.6 S4 rev #5 · "CPS 20% 健康险"—— C 加"待验证"

**修订前**(line 1713–1717):

```html
<div class="s4-rev">
  <div class="num">CPS<small>20%</small></div>
  <div class="name">健康险</div>
  <div class="desc">女性重疾险 · 孕产险 · 母婴险 · 经期相关保险</div>
  <div class="stage">EMERGING · 新增长</div>
</div>
```

**修订后**:

```html
<div class="s4-rev">
  <div class="num">CPS<small>? %</small><span class="audit-flag" title="见审查文档 §9.5">候选</span></div>
  <div class="name">健康险</div>
  <div class="desc">女性重疾险 · 孕产险 · 母婴险等候选;CPS 比例与合规边界以届时渠道为准</div>
  <div class="stage">EMERGING · 新增长</div>
</div>
```

**引用**: 审查文档 §9.4(机构付费:谁决策,效率改善是否可衡量)、§9.5(机构随访与资料协同·低估销售、接入与人工交付成本)。

---

### 4.7 S4 footer · quote —— B 改写

**修订前**(line 1722–1725):

```html
<div class="footer">
  <div class="brand"><span></span><span>LUNAFLOW · BUSINESS MODEL</span></div>
  <div class="quote">"用户用 1 次/月,但她值得 5 条现金流"</div>
  <div class="page"><span>04</span> / 05 · BUSINESS</div>
</div>
```

**修订后**:

```html
<div class="footer">
  <div class="brand"><span></span><span>LUNAFLOW · BUSINESS MODEL</span></div>
  <div class="quote">"5 条变现路径分阶段验证 — 先验证任务,再验证付费"</div>
  <div class="page"><span>04</span> / 05 · BUSINESS</div>
</div>
```

**引用**: 审查文档 §9.4、§10.3(指标建议)。

---

## 五、Slide 5 · 研报数据全景(3 项修改 + 1 处 JS)

### 5.1 S5 header · "MARKET REPORTS"—— B 改写

**修订前**(line 1741–1744):

```html
<div class="header-right">
  <div class="num" id="s5-report-count"><span data-countup="0">0</span> <small>/ 份研报</small></div>
  <div class="label">MARKET REPORTS</div>
</div>
```

**修订后**(无需大改,但建议加 audit-data):

```html
<div class="header-right">
  <div class="num" id="s5-report-count"><span data-countup="0">0</span> <small>/ 份研报</small></div>
  <div class="label">MARKET REPORTS · OCR 抓取</div>
</div>
```

### 5.2 S5 KPI 5 · 硬编码 "¥1.0T 万亿"—— A 降级

**修订位置**: line 2025–2046,JS 代码中 `kpiBar.innerHTML` 部分。

**修订前**:

```javascript
kpiBar.innerHTML = `
  <div class="s5-kpi">...</div>
  <div class="s5-kpi">...</div>
  <div class="s5-kpi">...</div>
  <div class="s5-kpi">...</div>
  <div class="s5-kpi">
    <div class="s5-kpi-num">¥1.0T <small>万亿</small></div>
    <div class="s5-kpi-label">女性健康市场<span class="src">·BCG/WEF 数据</span></div>
  </div>
`;
```

**修订后**:

```javascript
kpiBar.innerHTML = `
  <div class="s5-kpi">...</div>
  <div class="s5-kpi">...</div>
  <div class="s5-kpi">...</div>
  <div class="s5-kpi">...</div>
  <div class="s5-kpi">
    <div class="s5-kpi-num">¥1.0T <small>经济规模</small><span class="audit-flag" title="见审查文档 §2.1 / §11.1">口径</span></div>
    <div class="s5-kpi-label">女性健康行业经济成本<span class="src">·WEF/BCG 估算,非 APP 市场规模</span></div>
  </div>
`;
```

**引用**: 审查文档 §2.1、§2.2、§11.1。

### 5.3 S5 ops-hint · 行业结论—— B 重写(关键)

**修订位置**: line 2049–2050,JS 代码中 `s5-ops-hint-text.innerHTML`。

**修订前**:

```javascript
document.getElementById('s5-ops-hint-text').innerHTML =
  `${reports.length} 份研报指向同一结论——女性健康是 <strong>万亿美元级</strong> 的长期赛道,经期管理是其最高频、最高粘性的入口。`;
```

**修订后**:

```javascript
document.getElementById('s5-ops-hint-text').innerHTML =
  `${reports.length} 份研报覆盖女性健康多个细分;按"用户任务 × 服务深度 × 付款方 × 信任机制"分析,经期管理是入口,但商业价值由具体任务完成度与持续付费意愿决定,而非"万亿赛道"自动外推。`;
```

**引用**: 审查文档 §11.6 一句话总结(可直接复用)、§1.2(国内流量 vs 海外价值 是过度概括)、§2.4(历史双寡头份额不证明当前需求)。

---

## 六、S2 footer 增加脚注(全局建议)

**位置**: Slide 2 footer 区域(line 1555–1559)。

**修订前**:

```html
<div class="footer">
  <div class="brand"><span></span><span>LUNAFLOW · MARKET</span></div>
  <div class="quote">"万亿赛道里,没有人真正为她们做产品"</div>
  <div class="page"><span>02</span> / 05 · PAINPOINTS</div>
</div>
```

**修订后**:

```html
<div class="footer">
  <div class="brand"><span></span><span>LUNAFLOW · MARKET</span></div>
  <div class="quote">"万亿赛道里,工具已普及,深层任务仍待完成"</div>
  <div class="page"><span>02</span> / 05 · PAINPOINTS</div>
</div>
<div class="ppt-footnote">
  <b>数据使用说明:</b>
  ① 本页数字均标注口径与来源;
  ② 1T 美元为 WEF/BCG 估算的"经济成本",非 APP 市场规模(后者 ~48.6 亿美元,BRI 估算);
  ③ "3 倍 情绪波动"等无证据数字已删除;
  ④ 详情见 <b>经期管理与女性健康应用市场_观点审查与立项分析_2026-09-22.md</b> §11。
</div>
```

**引用**: 审查文档 §11.1、§12.2(数据使用规则)。

---

## 七、落地建议

### 7.1 不在 BP 中保留的具体数字清单

以下数字在本次修订中**全部不进入**正式 BP:

- "7.2 年 平均经期流失时间"(无来源)
- "80% 经历经期不适"(样本与定义不明)
- "3 倍 情绪波动 vs 男性"(伪科普表述)
- "基于 10 万+ 用户数据训练"(立项阶段虚构)
- "排卵期预测 ±1 天"(无临床证据)
- "500+ 篇妇科医生审核"(医生资质未定)
- "¥99/年"(未做 A/B 测试)
- "eCPM ¥8-15"(未实测)
- "CPS 15-25% / 20%"(未做渠道议价)

### 7.2 保留但需挂来源/口径的数字

- "¥1.0T 万亿" → 改为"1T 美元(WEF/BCG 经济成本估算)"
- "3.6 亿 中国育龄女性" → 加"国家统计局·2023"
- APP 市场规模 48.6 亿(2026) / 253 亿(2035)→ 加 BRI 估算

### 7.3 评审检查清单

应用本修订方案后,review 时请逐条确认:

- [ ] 19 处修订已按修订前/修订后逐条落地
- [ ] CSS 补充已加入 `<style>` 块末尾
- [ ] `.audit-flag` 标签在 5 张幻灯片中数量与本文档一致(≥12 处)
- [ ] S2 footer 脚注已加入并显示完整
- [ ] S5 KPI 5 已改为"经济规模"且挂审计标记
- [ ] S5 ops-hint 已重写为"任务 × 服务深度 × 付款方 × 信任机制"框架
- [ ] `LTV = ¥99 + CPS + eCPM` 等具体数字已全部降级为"情景假设 / 测算结构"
- [ ] 任何新增数字都已挂来源或"待验证"标签

---

## 八、与审查文档章节的对应索引(便于 review)

| 修订条目 | 主要引用 | 次要引用 |
| --- | --- | --- |
| 2.1 / 5.2(1T 美元口径) | §2.1 / §2.2 | §6.5 / §11.1 |
| 2.2(经期 App 拼凑感) | §3.5 / §9.1 | §11.5 |
| 2.3(3.6 亿) | §4.2 | §4.3 |
| 2.4(7.2 年删除) | §12.1 | §2.5 |
| 2.5(PMS 比例) | §8.3 | §11.5 |
| 2.6(3 倍删除) | §7.5 | §8.3 |
| 2.7(记录维度单一) | §3.5 | §4.1 |
| 2.8(非规律周期预测) | §7.1 | §7.4 |
| 2.9(交流问诊意愿) | §4.2 / §5.4 | §11.3 |
| 2.10(按周期推荐) | §9.4 | §9.5 |
| 2.11(就诊资料整理) | §7.1 / §7.4 | §9.3 |
| 2.12(情绪支持) | §5.3 | §8.3 |
| 3.1(10 万+ 删除) | §9.2 | §11.5 / §12.1 |
| 3.2(排卵期 ±1 天) | §6.4 | §11.5 |
| 3.3(500+ 篇内容) | §9.2 | §11.5 |
| 3.4(三甲医生在线) | §6.1 | §11.5 |
| 3.5(医生直接调阅) | §9.3 | §9.5 |
| 3.6(S3 footer quote) | §9.2 | — |
| 4.1(LTV 公式) | §9.4 | §10.4 / §12.1 |
| 4.2-4.6(5 条变现路径) | §9.4 | §10.4 |
| 4.7(S4 footer quote) | §9.4 | §10.3 |
| 5.1(S5 header label) | §2.1 | — |
| 5.2(S5 KPI 5) | §2.1 / §2.2 | §11.1 |
| 5.3(S5 ops-hint) | §11.6 | §1.2 / §2.4 |
| 6(S2 footer + 脚注) | §11.1 | §12.2 |
| 1.1(CSS 补充) | §2.5 | §12.2 |

---

**文档终结论:本方案按审查文档 §1.2 / §11 / §12 完成 19 处修订 + CSS 补充 + 全局脚注;不删除原 PPT 的结构与色彩,只修正具体数字、夸大承诺、口径混用三类风险;评审通过后可由 Edit 工具按"位置 → 修订前 → 修订后"逐条落地到原文件。**