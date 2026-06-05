# Launch Listing MVP 设计说明

## 设计原则

当前页面拆成“首页直接开始入口”和“生成工作区”两种视图，整体视觉对齐 Luckee Listing：

- 深森林色 hero
- oat / white / soft 分段
- Instrument Serif + Montserrat
- pill CTA
- 细线分隔、轻阴影、少卡片
- connected step flow

信息架构原则：

- 首屏直接提供开始入口：New listing / Amazon URL，用户不用滚到页面底部才开始。
- 功能介绍页只负责解释产品价值、工作方式、输出包和价格，同时每个关键段落都引导回开始动作。
- 顶部 CTA、Hero CTA、Feature CTA、How CTA、Final CTA 都进入工作区。
- Why 区每个核心卖点都配一张产品内展示图，并提供对应的开始入口，避免只做抽象介绍。
- 进入工作区后导航切换为 Intake -> Summary -> Plan -> Generate -> Results。
- 工作区提供 Back to overview 返回介绍页。
- 不在用户理解产品价值之前强制付费。免费给计划和预览，付费解锁可交付资产。

核心原则：

- 少卡片，只保留主表单和 Amazon 预览容器。
- 每一步像日常确认清单一样往下走。
- 默认展示重点，但每一行都可以展开查看完整执行要求。
- Strategy Map 和产品准确性检查都是后台能力，不作为主步骤。
- 用户只需要确认两次：系统是否理解产品、生成方案是否正确。
- Amazon conversational shopping 只作为趋势和结构化内容背景，不承诺被官方推荐。

## 宣传重点

产品名：

> Launch Listing

页面标题：

> Launch Listing

一句话定位：

> Turn product details, shopper intent and agent-ready answers into a complete Amazon listing package.

页面核心卖点：

- Map human and agent intent：先理解材质、规格、尺寸、使用场景、套装内容和图片细节，再把 human shopper intent 和 shopping-agent answer intent 精细匹配到 listing 内容
- Plan before creating：先给可审核的 listing strategy，再生成文案和视觉资产
- Complete package：标题、五点、搜索词、组图、A+、预览、导出和 ready checklist
- Answer buyer doubts：把尺寸、适配、清洁、耐用、安全、安装、售后等购买疑虑变成 listing 内容
- Position real differences：区分真正影响购买判断的差异和泛泛卖点，再决定放到标题、五点、图片或 A+

## 页面结构

1. **Hero**
   - 产品定位：把产品细节、买家意图和 agent-ready answer coverage 转成完整 Amazon listing 资产
   - 首屏直接提供 `Start your listing` 输入区
   - 不再在 Hero 文案下方放重复 CTA；Start panel 是唯一主入口
   - 支持 New listing 和 Amazon URL 两种开始方式
   - CTA 进入工作区并把首屏输入带入 Intake
   - 右侧展示生成包 mockup

2. **Why**
   - 每个卖点配一个商品案例展示图和一个引导使用入口
   - 使用同一个盐胡椒研磨器案例贯穿，避免抽象 UI mockup
   - Map human and agent intent：Amazon shopper question simulation + needs proof answer + title / bullet / image / A+ routing
   - Plan before creating：商品场景 + title / image / A+ 的生成前规划
   - Complete package：无品牌真实感商品主图、gallery 缩略图、A+ banner 缩略图 + title、bullets、search terms、checklist；不使用外部竞品或 Amazon 图片
   - Answer buyer doubts：Amazon shopper questions coverage simulation，展示多个常见疑虑如何进入 bullets / image / A+
   - Position real differences：Your product vs similar option 的双产品对比，使用无品牌自绘电动研磨器和手动研磨器，展示差异如何进入 Image / Bullet / A+ placement

3. **Differentiation**
   - 标题：Beautiful images are not enough.
   - 对比 Typical image generator 和 Launch Listing
   - 强调我们先做 product facts、human + agent intent、buyer doubts、proof routing，再生成 copy / gallery images / A+
   - 页面只表达 shopping assistant / shopper question simulation，不承诺官方 Alexa 或 Amazon 一定这样展示

4. **How it works**
   - Understand
   - Position
   - Create
   - Check
   - 段落底部 CTA 回到产品资料输入

5. **What you get**
   - Listing text：Title、5 bullets、backend search terms、editable text file
   - Listing images：7 images、1024 x 1024 · 1K、briefs/prompts
   - A+：Standard 970 x 600 · 1K；Premium 1464 x 600 · 4K + 600 x 450 mobile crops
   - Ready checklist：product accuracy、benefit wording、image dimensions、upload order、ZIP

6. **Packages**
   - Listing Generator
   - Listing + Standard A+
   - Listing + Premium A+

7. **Final CTA**
   - 回到工作区开始生成

8. **Workspace view**
   - 点击 CTA 后进入，不在介绍页默认展示
   - 保留完整生成流程
   - Intake -> Summary -> Plan -> Generate -> Results
   - 支持 Create from scratch 和 Improve existing listing 两个入口

## 主流程

1. **Product Intake**
   - 产品基础信息
   - 卖点
   - 产品图片素材
   - 套餐选择
   - 如果选择 Improve existing listing，则先输入 Amazon URL / ASIN 并 Fetch
   - 创建或抓取方案前提示：免费账号包含 1 个 launch plan，复制和下载需确认 Luckee credits

2. **Listing Snapshot**（仅已有链接模式）
   - 按 Amazon listing 结构顺序展示 fetch 结果：Title -> Five bullet points -> Product images -> A+ content
   - 每个模块展示抓取状态和后续处理方式
   - 如果抓到 A+ 图片，A+ content 轻量展示 2-6 个模块缩略图，不做成和商品组图同等权重
   - 底部轻量展示 Generation scope：Images + A+、Listing text only、A+ only、Full rebuild
   - 默认选择 Images + A+
   - 同一区域展示默认保护项：Keep main image unchanged、Match current visual style
   - 用户确认后进入 Product Summary

3. **Product Summary**
   - 系统理解的产品定位
   - 核心优势
   - 素材准备度
   - 最终上传前需要补充的信息

4. **Launch Plan**
   - Listing text
   - Listing image plan
   - A+ plan
   - Product accuracy rules
   - 每行默认只显示重点，点击 Details 展开完整要求

5. **Generate**
   - 免费生成 preview
   - 文案 preview
   - 商品组图 preview
   - A+ preview
   - 产品准确性后台检查
   - Results 准备

6. **Results**
   - 顶部状态条显示 Ready checklist 状态
   - Listing text：Title、5 bullets、backend search terms
   - Images：Listing images、A+ images
   - Preview：Amazon page desktop / mobile preview
   - 默认状态为 preview ready，但复制、高清图和 ZIP 处于 locked 状态
   - Unlock final files：确认对应 generation bundle credits 后解锁 copyable text、listing images、A+、ZIP

## 付费转化逻辑

商业化原则：

- 未注册用户可以浏览页面、填写输入、选择套餐、上传本地素材。
- 未注册用户不能执行会产生成本或需要保存的动作：Fetch listing、Create free launch plan、Generate preview、Export。
- 用户可以免费开始，但免费只覆盖“理解产品 + 生成方案 + 预览结果”。
- 第一次需要后端保存和生成计划时要求注册 / 登录，而不是一进页面就拦截。
- 每个注册用户默认 1 次免费 launch plan。
- 不免费交付完整可商用资产：复制按钮、高清图片、A+ 图片和 ZIP 下载都需要确认对应 Luckee credits 消耗。
- 付费点放在 Results 和 plan confirmation 后，不在首屏强压付费。

推荐漏斗：

```text
Landing -> Intake -> Sign in / create free account -> Free launch plan -> Free preview -> Unlock final files modal -> Final files unlocked
```

登录触发点：

- `Create free launch plan`
- `Fetch listing`
- 后续如果用户直接从链接进入已有项目并尝试 `Generate preview`
- `Unlock final files`

弹窗主文案：

```text
Create a free account to continue
Save your launch plan, use your free preview, and keep the project available for export.
```

Google 授权页：

- 点击 `Continue with Google` 后不直接通过，先进入授权确认页。
- 页面展示当前 Google account、Launch Listing 将使用的权限和继续按钮。
- 授权范围只表达账号创建、保存项目、接收 credits/export receipt。
- 明确说明不请求 Google Drive、Gmail 或广告账号权限。

关键文案：

```text
Sign in with Google
Authorize Launch Listing to create your workspace account.
We do not request Google Drive, Gmail or advertising account access in this flow.
```

免费账号：

- 1 saved launch plan
- preview generation
- ready checklist preview
- text copying 和 downloads locked

Luckee credits pricing：

- First loop free：$0/month，1,500 Credits，包含 1 个 launch plan 和 1 个 listing kit preview
- Seller：$29.25/month（Yearly · Save 25%），30,000 Credits，适合持续修 listing 和生成导出
- Agency：$74.25/month（Yearly · Save 25%），100,000 Credits，适合多 ASIN、批量报告和团队协作
- Credit Pack：$39.9，100,000 Credits，可单独购买补充额度

结果页解锁交互：

- Results 里的 `Unlock final files` 不跳转到 Pricing 页面。
- 点击后打开当前 listing 的 checkout modal。
- Modal 里选择 Listing Generator / Listing + Standard A+ / Listing + Premium A+ 对应的 credits bundle。
- 点击 `Use credits and unlock` 后进入 credits confirmation 状态。
- credits 确认后显示 `Exports unlocked`。
- 点击 `Back to results` 回到同一个 Results 页面，并原地解锁 text copying、image downloads 和 ZIP。

结果页解锁后提供：

- Text copying
- high-resolution listing images
- high-resolution A+ images
- ZIP package for Seller Central upload
- Ready checklist

## Product Sources

素材区不拆成多个上传入口。

用户只看到一个多图上传区：

- Drop images or click to upload
- JPG、PNG、WebP、HEIC
- Up to 8 images

说明只保留最关键规则：

- Required：one clear product photo, ideally on white
- Recommended：close-ups, package contents, size references
- Optional：logo、packaging、brand colors、lifestyle or mood references

系统在后台识别素材类型，而不是要求用户按类别分开上传。白底产品图用于锁定产品外观。AI 生成时不允许重新设计产品主体，只能生成背景、场景、阴影、布局和非产品元素。

品牌素材是 optional，不作为必填项。没有 logo、包装、品牌色或风格参考时，系统不应该强行生成“高级品牌感”，而是优先保证产品表达清楚、卖点可信和视觉干净。

## Marketing Direction

MVP 不让用户选择抽象的 Marketing direction。

默认策略：

- 系统默认按 Conversion clarity 生成：先保证产品类型、核心卖点、证明和购买理由清楚。
- 如果用户上传 logo、品牌色、包装、官网风格或品牌参考图，再在 Launch Plan 中体现品牌调性。
- 不用一个 `Premium brand feel` 下拉项直接触发“高级品牌感”，否则缺少品牌素材时容易生成廉价、泛化的伪品牌视觉。
- 需要品牌控制时，后续应该做成 Brand Assets / Brand Guidelines 输入，而不是营销方向选择。

## Package 与 Scope

不单独展示 Output Scope，避免和 Package 冲突。

套餐直接决定输出范围；实际消耗走 Luckee credits：

- Listing Generator：Title、5 bullets、backend search terms、description、checklist、7 张商品组图（1024 x 1024 · 1K），无 A+
- Listing + Standard A+：Title、5 bullets、backend search terms、description、checklist、7 张商品组图（1024 x 1024 · 1K），加 6 个 Standard A+ 模块（970 x 600 · 1K），推荐默认
- Listing + Premium A+：Title、5 bullets、backend search terms、description、checklist、7 张商品组图（1024 x 1024 · 1K），加 Premium A+（1464 x 600 · 4K）、600 x 450 mobile crops、文案多版本；需要更高 credits 或付费计划

如需自定义范围，放在折叠的 Customize 里。

## Launch Plan 的展示方式

不要做模块卡片。

用线性清单展示：

```text
01 Main image — product-only white background
02 Core benefit — one-touch rechargeable seasoning
03 Feature proof — adjustable coarseness / mechanism
```

每行可展开完整内容：

```text
Why this matters
Buyer question
Sales role
```

这样用户可以先扫重点，需要时再看完整方案。

Launch Plan 必须支持生成前手动调整：

- 用户可以进入 Edit plan 状态，直接改标题方向、图片方案、A+ 模块方向和细节说明
- 修改发生在当前确认清单上，不新增复杂配置页
- 用户点 Done editing 后再 Approve & generate

## Generation Guardrails

产品准确性检查保留为后台机制，但页面不把它做成大模块。用户看到的是更清楚的 Product accuracy rules：

- Keep the product body unchanged from the source photo.
- Only generate supporting scenes, backgrounds, shadows and text-safe layouts.
- Do not add unprovided items, certificates, ratings, awards or competitor marks.
- Results include a ready checklist for product accuracy, wording, dimensions and upload order.

## Results

生成 preview 完成后进入 Results，不直接只显示 Amazon Preview。

Results 只保留 3 个 tab：

- Listing text：Title、5 bullets、backend search terms；免费状态下可预览但复制按钮 locked
- Images：Listing images 和 A+ images，展示用途和尺寸；免费状态下显示 preview 水印 / locked
- Preview：Amazon page desktop / mobile preview

默认打开 Listing text，因为这是用户最快能使用的内容。

Unlock final files 后的 ZIP 只包含：

- `copy.md`
- `listing-images/`
- `aplus/`

MVP 先不做：

- regenerate
- prompt export
- extra reports
- upload-order.md
- version history

Landing 里的 Pricing 对齐 Luckee 主账号和 credits，不引入独立钱包或独立订阅。页面展示为：

- First loop free：$0/month，1,500 Credits
- Seller：$29.25/month，30,000 Credits，Most Popular
- Agency：$74.25/month，100,000 Credits
- Credit Pack：$39.9，100,000 Credits

Results 里的解锁弹窗使用 Luckee credits confirmation，不作为独立单次下载钱包来设计。

生成后自动准备：

- Product accuracy
- Claim wording
- Mobile readability
- Image dimensions
- Upload order

Results 里显示 Ready checklist：

```text
Ready checklist complete
Mobile readable
```

Checklist 默认折叠，展开后显示：

- Product accuracy
- Claim wording
- Image dimensions
- Upload order

## 当前文件

- `index.html`：静态交互原型
- `DESIGN.md`：本设计说明
