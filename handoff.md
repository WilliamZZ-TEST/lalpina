# L'Alpina 中国大陆品牌手册 · Handoff

## 交付状态

- 交付物：`lalpina-china-launch-playbook.html`、`index.html`、`assets/`、`output/pdf/lalpina-china-launch-playbook.pdf`、`prd.md`
- 发布仓库：`https://github.com/WilliamZZ-TEST/lalpina`
- GitHub Pages：`https://williamzz-test.github.io/lalpina/`
- 页面入口：根目录 `index.html` 自动跳转到主手册；直接打开主 HTML 也可访问。
- 适配：桌面宽度 1280px 与手机宽度 390px 已检查；页面无横向溢出。

## 交接范围

本版本包含品牌首屏、第二屏主视觉、品牌历史、可验证的全球品牌资产、定位、Brand System、人群画像、电商市场证据、鞋履产品架构、鞋型开发参考、品牌故事、托斯卡纳 2026FW 官网形象组与上市治理内容。产品和市场数字均在页面中注明口径、来源或“公开货架快照而非销售 Top10”的限制。

## 关键实现

- 所有站内 Logo 统一使用 `assets/lalpina-kangaroo-logo.png`。该文件由用户提供的 Logo 附件裁切并透明化，深色背景使用 CSS `filter: invert(1)`；未重新绘制品牌轮廓。
- 首屏是深色品牌定位页，导航固定在首屏顶端；原主视觉移至第二屏。
- 参考目录 `D:\工作\L'alpina\参考` 的图片已复制到 `assets/lalpina-reference-*.png`，分别用于全球品牌资产、定位、Brand System 与人群画像模块。
- 托斯卡纳官网形象组的 landscape 图片使用 `aspect-ratio: 4/3`，portrait 图片使用 `4/5`；手机端横图仍保持 4:3。
- 鞋履产品图、设计参考图保留点击放大 Lightbox；键盘 Enter/Space 也可打开，Esc 或关闭按钮退出。
- `市场验证` 为页面对“小幅测试/小批测试”的统一替换文案，避免对外呈现未经验证的“测试规模”承诺。
- 电商图表以 SVG 实色柱形呈现，并提供 SVG 下载链接。

## 资源索引

### Logo 与图表

| 文件 | 用途 |
|---|---|
| `assets/lalpina-kangaroo-logo.png` | 顶部导航、首屏 Logo、页脚 Logo；附件轮廓的透明化版本 |
| `assets/charts/lalpina-sports-ecommerce-market.svg` | 四平台体育用品电商规模图 |
| `assets/charts/lalpina-running-price-band.svg` | 抖音跑鞋销售额价格带图 |

### 页面原有与新增图片

| 文件 | 使用位置 |
|---|---|
| `assets/lalpina-website-hero-tennis-italy.png` | 第二屏主视觉 |
| `assets/lalpina-reference-global-tennis.png` | 可验证的全球品牌资产模块 |
| `assets/lalpina-reference-positioning-man.png` | 不止复古 / 定位模块 |
| `assets/lalpina-reference-brand-system-couple.png` | Brand System 模块 |
| `assets/lalpina-reference-brand-system-woman.png` | Brand System 模块 |
| `assets/lalpina-reference-audience-woman.png` | 人群画像模块 |
| `assets/lalpina-reference-audience-vineyard.png` | 人群画像模块 |
| `assets/lalpina-reference-audience-lake.png` | 人群画像模块 |
| `assets/lalpina-tuscany-male-2026fw.png` | 托斯卡纳官网形象组：男性 |
| `assets/lalpina-tuscany-female-portrait-2026fw.png` | 托斯卡纳官网形象组：女性 |
| `assets/lalpina-tuscany-couple-walk-2026fw.png` | 托斯卡纳官网形象组：双人山径 |
| `assets/lalpina-tuscany-couple-vineyard-2026fw.png` | 托斯卡纳官网形象组：葡萄园 |
| `assets/lalpina-tuscany-female-terrace-2026fw.png` | 托斯卡纳官网形象组：露台 |

## 运行与发布

这是无构建步骤的静态站点。预览命令：

```powershell
python -m http.server 8765 --bind 127.0.0.1
```

生产发布通过 GitHub Pages 的 `main` 分支根目录完成。若新增资源，必须同时更新 HTML 相对路径并提交资源文件。Pages 404 排查顺序：确认仓库根目录存在 `index.html`、确认 Pages Source 为 `main / (root)`、等待部署工作流完成、再访问 `https://williamzz-test.github.io/lalpina/`。

## QA 证据

- 页面标题：`L'Alpina 中国大陆品牌策略与上市手册`
- 桌面 1280×900：导航、首屏 Logo、品牌模块图片与 4:3 横图加载正常。
- 手机 390×844：`scrollWidth=375`，小于 viewport，无水平溢出；3 张横图实际比例均为 1.333。
- 新增模块图片 7/7 加载；Logo 3 处加载；控制台无 error/warn。
- 导航点击 `人群` 后 URL hash 为 `#audience`，目标标题“人群画像 / 与验证信号”可见。

## 后续维护注意

1. 品牌方发布前复核年份、合作、商标、Logo 授权与产品性能表述。
2. 电商部分的销售 Top10 仍明确标注为“公开货架快照”，如取得生意参谋、抖音罗盘或京东商智权限，再替换为可审计成交数据。
3. 参考图均为视觉方向资产；正式商业拍摄需确认人物肖像、场地与商用授权。
4. 不要把 `__pycache__/`、`output/` 中的临时文件、`reports/` 或本地构建脚本批量加入站点仓库。
