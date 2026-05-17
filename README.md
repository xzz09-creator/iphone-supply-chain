[index.html](https://github.com/user-attachments/files/27904131/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>EconLens — Learn AP Economics Through Real Brands</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #F2F0EB;
  --surface: #FFFFFF;
  --surface2: #F7F6F2;
  --border: rgba(0,0,0,0.07);
  --border2: rgba(0,0,0,0.13);
  --text: #1A1A1A;
  --muted: #666;
  --faint: #AAA;
  --blue: #185FA5;
  --teal: #0F6E56;
  --amber: #BA7517;
  --red: #A32D2D;
}
* { box-sizing: border-box; margin: 0; padding: 0; }
html, body { height: 100%; }
body { font-family: 'DM Sans', sans-serif; background: var(--bg); color: var(--text); font-size: 14px; }

.shell { display: grid; grid-template-rows: 52px 1fr; height: 100vh; }

/* TOPBAR */
.topbar {
  background: var(--surface); border-bottom: 1px solid var(--border);
  display: flex; align-items: center; padding: 0 1.5rem; gap: 1rem;
  position: sticky; top: 0; z-index: 100;
}
.logo { font-size: 15px; font-weight: 500; letter-spacing: -0.01em; }
.logo span { color: var(--blue); }
.tagline { font-size: 12px; color: var(--faint); margin-left: 4px; }
.search-wrap { flex: 1; max-width: 300px; position: relative; margin-left: auto; }
.search-wrap input {
  width: 100%; height: 32px; border: 1px solid var(--border2); border-radius: 8px;
  padding: 0 12px 0 32px; font-family: 'DM Sans', sans-serif; font-size: 13px;
  background: var(--surface2); color: var(--text); outline: none;
}
.search-wrap input:focus { border-color: var(--blue); }
.s-icon { position: absolute; left: 10px; top: 50%; transform: translateY(-50%); width: 13px; height: 13px; stroke: var(--faint); fill: none; stroke-width: 2; }
.lang-sw { display: flex; gap: 4px; }
.lang-btn { padding: 4px 12px; font-size: 12px; font-family: 'DM Sans', sans-serif; border: 1px solid var(--border2); border-radius: 20px; background: transparent; color: var(--muted); cursor: pointer; }
.lang-btn.active { background: var(--text); color: #fff; border-color: var(--text); }

/* MAIN */
.main { display: grid; grid-template-columns: 240px 1fr; overflow: hidden; }

/* SIDEBAR */
.sidebar { background: var(--surface); border-right: 1px solid var(--border); overflow-y: auto; padding: 0.75rem 0; }
.chapter-group { margin-bottom: 4px; }
.chapter-header {
  font-size: 10px; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase;
  color: var(--faint); padding: 8px 1rem 4px; display: flex; align-items: center; gap: 6px;
}
.chapter-tag { display: inline-block; font-size: 9px; padding: 1px 6px; border-radius: 10px; font-weight: 500; }
.tag-micro { background: #E6F1FB; color: #0C447C; }
.tag-macro { background: #E1F5EE; color: #085041; }
.nav-item {
  display: flex; align-items: center; gap: 10px; width: 100%;
  padding: 9px 1rem; background: none; border: none; border-left: 2px solid transparent;
  text-align: left; cursor: pointer; font-family: 'DM Sans', sans-serif;
  font-size: 13px; color: var(--muted); transition: all 0.12s;
}
.nav-item:hover { background: var(--surface2); color: var(--text); }
.nav-item.active { background: var(--surface2); color: var(--text); font-weight: 500; border-left-color: var(--text); }
.nav-num { font-family: 'DM Mono', monospace; font-size: 11px; color: var(--faint); width: 20px; flex-shrink: 0; }
.nav-item.active .nav-num { color: var(--text); }

/* CONTENT */
.content { overflow-y: auto; padding: 2rem; }
.lesson { max-width: 800px; }

/* LESSON HEADER */
.lesson-tag { display: inline-block; font-size: 11px; font-weight: 500; padding: 3px 10px; border-radius: 20px; margin-bottom: 12px; }
.lesson-title { font-size: 26px; font-weight: 500; letter-spacing: -0.02em; margin-bottom: 6px; line-height: 1.2; }
.lesson-sub { font-size: 14px; color: var(--muted); margin-bottom: 2rem; line-height: 1.6; }

/* SECTIONS */
.lesson-section { margin-bottom: 2rem; }
.section-label { font-size: 10px; font-weight: 500; text-transform: uppercase; letter-spacing: 0.1em; color: var(--faint); margin-bottom: 10px; display: flex; align-items: center; gap: 8px; }
.section-label::after { content: ''; flex: 1; height: 1px; background: var(--border); }
.theory-box { background: var(--surface); border: 1px solid var(--border); border-radius: 12px; padding: 1.25rem 1.5rem; margin-bottom: 1rem; }
.theory-text { font-size: 14px; color: var(--muted); line-height: 1.8; }
.theory-text strong { color: var(--text); font-weight: 500; }
.key-terms { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 1rem; }
.key-term { background: var(--surface2); border: 1px solid var(--border); border-radius: 6px; padding: 4px 10px; font-size: 12px; color: var(--muted); }
.key-term strong { color: var(--text); }

/* CHART */
.chart-card { background: var(--surface); border: 1px solid var(--border); border-radius: 12px; padding: 1.25rem 1.5rem; margin-bottom: 1rem; }
.chart-title { font-size: 13px; font-weight: 500; margin-bottom: 12px; }
.chart-wrap { position: relative; width: 100%; height: 240px; }

/* CASE STUDY */
.case-card { background: var(--surface); border: 1px solid var(--border); border-radius: 12px; overflow: hidden; margin-bottom: 1rem; }
.case-header { padding: 1rem 1.5rem; border-bottom: 1px solid var(--border); display: flex; align-items: center; gap: 12px; }
.case-icon { width: 36px; height: 36px; border-radius: 8px; display: flex; align-items: center; justify-content: center; font-size: 18px; flex-shrink: 0; }
.case-brand { font-size: 13px; font-weight: 500; }
.case-topic { font-size: 12px; color: var(--muted); }
.case-body { padding: 1.25rem 1.5rem; font-size: 14px; color: var(--muted); line-height: 1.8; }
.case-body strong { color: var(--text); font-weight: 500; }
.case-insight { background: var(--surface2); border-left: 3px solid var(--text); border-radius: 0 8px 8px 0; padding: 10px 14px; font-size: 13px; color: var(--muted); line-height: 1.7; margin-top: 1rem; }

/* AP TIP */
.ap-tip { background: #EEF4FC; border: 1px solid #B5D4F4; border-radius: 10px; padding: 1rem 1.25rem; margin-top: 1rem; }
.ap-tip-label { font-size: 10px; font-weight: 500; text-transform: uppercase; letter-spacing: 0.1em; color: var(--blue); margin-bottom: 6px; }
.ap-tip-text { font-size: 13px; color: #185FA5; line-height: 1.7; }

/* METRICS */
.metrics { display: grid; grid-template-columns: repeat(3,1fr); gap: 10px; margin-bottom: 1rem; }
.metric { background: var(--surface); border: 1px solid var(--border); border-radius: 10px; padding: 14px; }
.metric-label { font-size: 11px; color: var(--muted); text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 4px; }
.metric-val { font-size: 20px; font-weight: 300; font-family: 'DM Mono', monospace; }
.metric-sub { font-size: 11px; color: var(--faint); margin-top: 2px; }

/* NAV BUTTONS */
.lesson-nav { display: flex; justify-content: space-between; margin-top: 2rem; padding-top: 1.5rem; border-top: 1px solid var(--border); }
.nav-btn { padding: 8px 16px; font-size: 13px; font-family: 'DM Sans', sans-serif; border: 1px solid var(--border2); border-radius: 8px; background: transparent; color: var(--muted); cursor: pointer; transition: all 0.15s; }
.nav-btn:hover { background: var(--surface2); color: var(--text); }
.nav-btn.primary { background: var(--text); color: #fff; border-color: var(--text); }
.nav-btn:disabled { opacity: 0.3; cursor: default; }

@media (max-width: 768px) {
  .main { grid-template-columns: 1fr; }
  .sidebar { display: none; }
  .content { padding: 1.25rem; }
  .metrics { grid-template-columns: repeat(2,1fr); }
  .tagline { display: none; }
}
</style>
</head>
<body>
<div class="shell">
<div class="topbar">
  <span class="logo">Econ<span>Lens</span></span>
  <span class="tagline" data-en="AP Economics through real brands" data-zh="用真实品牌学习AP经济学">AP Economics through real brands</span>
  <div class="search-wrap">
    <svg class="s-icon" viewBox="0 0 24 24"><circle cx="11" cy="11" r="8"/><path d="m21 21-4.35-4.35"/></svg>
    <input type="text" data-placeholder-en="Search concepts..." data-placeholder-zh="搜索概念..." placeholder="Search concepts..." oninput="doSearch(this.value)">
  </div>
  <div class="lang-sw">
    <button class="lang-btn active" onclick="setLang('en')">EN</button>
    <button class="lang-btn" onclick="setLang('zh')">中文</button>
  </div>
</div>

<div class="main">
  <div class="sidebar" id="sidebar"></div>
  <div class="content" id="content"></div>
</div>
</div>

<script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.1/dist/chart.umd.min.js"></script>
<script>
let currentLang = 'en';
let currentLesson = 0;
let chartObjs = {};

const LESSONS = [
  {
    id: 'supply-demand', type: 'micro', num: '01',
    title: { en: 'Supply & Demand', zh: '供给与需求' },
    sub: { en: 'The foundation of all economics — how prices emerge from the interaction of buyers and sellers.', zh: '所有经济学的基础——价格如何在买卖双方的互动中形成。' },
    theory: {
      en: 'The <strong>demand curve</strong> shows how much of a good consumers want to buy at each price — it slopes downward because lower prices attract more buyers. The <strong>supply curve</strong> shows how much producers are willing to sell — it slopes upward because higher prices make production more profitable. Where they intersect is the <strong>equilibrium</strong>: the price where quantity supplied equals quantity demanded. When either curve shifts, the equilibrium changes.',
      zh: '<strong>需求曲线</strong>显示消费者在每个价格愿意购买的数量——向下倾斜，因为价格越低吸引的买家越多。<strong>供给曲线</strong>显示生产者愿意出售的数量——向上倾斜，因为价格越高利润越大。两条曲线的交点是<strong>均衡点</strong>：供给量等于需求量时的价格。任一曲线移动，均衡点就会改变。'
    },
    terms: [
      { en: 'Demand Curve', zh: '需求曲线' }, { en: 'Supply Curve', zh: '供给曲线' },
      { en: 'Equilibrium', zh: '均衡' }, { en: 'Shortage', zh: '供不应求' }, { en: 'Surplus', zh: '供过于求' }
    ],
    chart: { type: 'supply-demand' },
    caseIcon: '📱', caseBrand: 'Apple', caseBg: '#F0F0F0',
    caseTopic: { en: 'iPhone launch day scalper prices', zh: 'iPhone 发布日的黄牛价格' },
    caseBody: {
      en: 'Every September, Apple releases a new iPhone. On launch day, Apple sets a fixed price — say $999 for the Pro model. But demand far exceeds supply at that price: Apple\'s factories can\'t produce enough units immediately. This creates a <strong>shortage</strong>. Scalpers exploit this gap: they buy iPhones at $999 and resell them for $1,400+ — the true market-clearing price where demand meets available supply. Apple deliberately restricts supply not by accident, but because scarcity reinforces the premium brand image.',
      zh: '每年九月，苹果发布新款 iPhone。发布当天，苹果设定固定价格——比如 Pro 版 $999。但在这个价格下，需求量远超供应量：工厂无法立即生产足够数量，形成<strong>供不应求</strong>。黄牛利用这个缺口：以 $999 购入，再以 $1400 以上转售——这才是市场出清的真实价格。苹果刻意限制供应，不是偶然，而是因为稀缺性能强化高端品牌形象。'
    },
    caseInsight: {
      en: 'Apple\'s launch-day pricing is a deliberate supply restriction — creating artificial scarcity to signal premium value. The scalper price reveals the true demand curve.',
      zh: '苹果发布日定价是刻意限制供给——通过人为制造稀缺来传递高端价值信号。黄牛价格揭示了真实的需求曲线。'
    },
    apTip: {
      en: 'On the AP exam: when supply decreases (curve shifts left) with unchanged demand, price rises and quantity falls. Always distinguish between a "change in demand" (curve shifts) and a "change in quantity demanded" (movement along the curve).',
      zh: 'AP 考试要点：当供给减少（曲线左移）而需求不变时，价格上涨、数量下降。务必区分"需求变化"（曲线移动）和"需求量变化"（沿曲线移动）。'
    }
  },
  {
    id: 'elasticity', type: 'micro', num: '02',
    title: { en: 'Price Elasticity', zh: '价格弹性' },
    sub: { en: 'How sensitive is demand to price changes? The answer determines whether raising prices helps or hurts a company.', zh: '需求对价格变化有多敏感？答案决定了涨价对企业是利是弊。' },
    theory: {
      en: '<strong>Price elasticity of demand</strong> measures how much quantity demanded changes when price changes. It\'s calculated as: % change in quantity ÷ % change in price. If elasticity > 1, demand is <strong>elastic</strong> — consumers are sensitive to price (luxuries, substitutable goods). If elasticity < 1, demand is <strong>inelastic</strong> — consumers buy regardless of price changes (necessities, addictive goods). Firms with inelastic demand can raise prices without losing many customers.',
      zh: '<strong>需求价格弹性</strong>衡量价格变化时需求量的变化幅度。计算方式：需求量变化百分比 ÷ 价格变化百分比。弹性 > 1，需求具有<strong>弹性</strong>——消费者对价格敏感（奢侈品、有替代品的商品）。弹性 < 1，需求<strong>缺乏弹性</strong>——消费者不管涨价都会购买（生活必需品、成瘾性商品）。需求缺乏弹性的企业可以涨价而不会大量流失客户。'
    },
    terms: [
      { en: 'Price Elasticity', zh: '价格弹性' }, { en: 'Elastic Demand', zh: '富有弹性' },
      { en: 'Inelastic Demand', zh: '缺乏弹性' }, { en: 'Luxury Good', zh: '奢侈品' }, { en: 'Necessity', zh: '必需品' }
    ],
    chart: { type: 'elasticity' },
    caseIcon: '👜', caseBrand: 'Louis Vuitton vs Gasoline', caseBg: '#FFF0E8',
    caseTopic: { en: 'Why LV raises prices every year — and people still buy', zh: '为什么 LV 每年涨价——消费者却照买不误' },
    caseBody: {
      en: 'Louis Vuitton has raised prices over <strong>60% since 2019</strong>. Yet sales keep growing. This is the paradox of <strong>inelastic demand for luxury goods</strong>: for LV\'s core customers, the bag is a status symbol — price itself signals exclusivity. Raising prices doesn\'t reduce demand; it increases desirability. Meanwhile, gasoline is also inelastic for a different reason: people need to drive to work regardless of price. When gas prices spike, demand barely falls. <strong>Contrast this with economy flights</strong>: highly elastic — a 10% price increase can shift many travelers to trains or competing airlines.',
      zh: '路易威登自 <strong>2019 年以来涨价超过 60%</strong>，但销售额持续增长。这是<strong>奢侈品需求缺乏弹性</strong>的悖论：对核心客户而言，包包是身份象征——价格本身就传递了稀缺性。涨价不会减少需求，反而会增加吸引力。与此同时，汽油需求缺乏弹性原因不同：人们需要开车上班，无论油价如何。油价飙升时，需求几乎不下降。<strong>相比之下，经济舱机票</strong>需求高度富有弹性——涨价 10% 可能让大量旅客转向火车或其他航空公司。'
    },
    caseInsight: {
      en: 'Luxury brands deliberately cultivate inelastic demand through scarcity and status signaling. Understanding elasticity tells you whether a price increase will grow or shrink total revenue.',
      zh: '奢侈品牌通过稀缺性和身份信号刻意培养需求的价格缺乏弹性。理解弹性，就能判断涨价会增加还是减少总收入。'
    },
    apTip: {
      en: 'AP exam key: if demand is inelastic, raising price INCREASES total revenue. If demand is elastic, raising price DECREASES total revenue. TR = Price × Quantity.',
      zh: 'AP 考试要点：若需求缺乏弹性，涨价会<strong>增加</strong>总收入；若需求富有弹性，涨价会<strong>减少</strong>总收入。总收入 = 价格 × 数量。'
    }
  },
  {
    id: 'market-structure', type: 'micro', num: '03',
    title: { en: 'Market Structure', zh: '市场结构' },
    sub: { en: 'From perfect competition to monopoly — the structure of a market determines pricing power and profit.', zh: '从完全竞争到垄断——市场结构决定了定价权和利润空间。' },
    theory: {
      en: 'Markets are classified by how many sellers exist and how differentiated their products are. <strong>Perfect competition</strong>: many sellers, identical products, no pricing power (wheat farmers). <strong>Monopolistic competition</strong>: many sellers, differentiated products (restaurants). <strong>Oligopoly</strong>: few dominant sellers who are interdependent (airlines, smartphones). <strong>Monopoly</strong>: one seller with complete pricing power. In oligopolies, firms watch each other carefully — one airline\'s fare change triggers responses from all others.',
      zh: '市场按卖家数量和产品差异化程度分类。<strong>完全竞争</strong>：卖家众多，产品同质，无定价能力（小麦农户）。<strong>垄断竞争</strong>：卖家众多，产品差异化（餐厅）。<strong>寡头竞争</strong>：少数主导卖家，相互依存（航空、智能手机）。<strong>垄断</strong>：单一卖家拥有完全定价权。在寡头市场中，企业密切观察对方——一家航空公司调价会引发所有竞争者的连锁反应。'
    },
    terms: [
      { en: 'Perfect Competition', zh: '完全竞争' }, { en: 'Monopoly', zh: '垄断' },
      { en: 'Oligopoly', zh: '寡头竞争' }, { en: 'Pricing Power', zh: '定价权' }, { en: 'Barriers to Entry', zh: '进入壁垒' }
    ],
    chart: { type: 'market-structure' },
    caseIcon: '🍎', caseBrand: 'Apple App Store', caseBg: '#F0F0F0',
    caseTopic: { en: "Apple's App Store — monopoly within a duopoly", zh: 'Apple App Store——双寡头中的垄断' },
    caseBody: {
      en: 'The smartphone OS market is a <strong>duopoly</strong>: Apple (iOS) and Google (Android) control nearly 100% of the market. Within iOS, Apple operates a <strong>monopoly</strong> over app distribution — developers have no alternative platform to reach iPhone users. Apple charges a <strong>30% commission</strong> on all App Store purchases, a margin only possible with monopoly power. Epic Games (Fortnite) sued Apple in 2021 over this, arguing it was anticompetitive. Courts partially agreed — but Apple still controls the platform.',
      zh: '智能手机操作系统市场是<strong>双寡头</strong>：苹果（iOS）和谷歌（Android）控制了近 100% 的市场。在 iOS 生态内，苹果对应用分发拥有<strong>垄断地位</strong>——开发者没有其他途径触达 iPhone 用户。苹果对所有 App Store 购买收取 <strong>30% 佣金</strong>，这样的利润率只有垄断才能实现。Epic Games（堡垒之夜）于 2021 年以反竞争为由起诉苹果，法院部分支持了该主张——但苹果仍掌控着平台。'
    },
    caseInsight: {
      en: 'Apple operates two market structures simultaneously: an oligopolist in smartphones, and a monopolist in iOS app distribution. The 30% commission is only sustainable because switching costs for iPhone users are extremely high.',
      zh: '苹果同时处于两种市场结构中：智能手机市场的寡头，以及 iOS 应用分发的垄断者。30% 的佣金之所以可持续，是因为 iPhone 用户的转换成本极高。'
    },
    apTip: {
      en: 'AP exam: monopolists produce where MR=MC (not P=MC like perfect competition), resulting in higher prices and lower quantities — a "deadweight loss" to society.',
      zh: 'AP 考试：垄断者在 MR=MC 处生产（不像完全竞争的 P=MC），导致价格更高、数量更少——对社会造成"无谓损失"。'
    }
  },
  {
    id: 'costs', type: 'micro', num: '04',
    title: { en: 'Production Costs', zh: '生产成本' },
    sub: { en: 'Fixed costs, marginal costs, and economies of scale — the building blocks of every business decision.', zh: '固定成本、边际成本与规模经济——每个商业决策的基础。' },
    theory: {
      en: '<strong>Fixed costs</strong> don\'t change with output (factory rent, equipment). <strong>Variable costs</strong> change with output (materials, labor per unit). <strong>Marginal cost</strong> is the cost of producing one more unit — the most important concept in production decisions. <strong>Economies of scale</strong> occur when average costs fall as output increases — spreading fixed costs over more units. This is why large manufacturers have a competitive advantage over small ones.',
      zh: '<strong>固定成本</strong>不随产量变化（工厂租金、设备）。<strong>变动成本</strong>随产量变化（材料、每单位人工）。<strong>边际成本</strong>是多生产一单位的成本——生产决策中最重要的概念。<strong>规模经济</strong>指随产量增加，平均成本下降——将固定成本分摊到更多单位上。这就是大型制造商相对小制造商具有竞争优势的原因。'
    },
    terms: [
      { en: 'Fixed Cost', zh: '固定成本' }, { en: 'Marginal Cost', zh: '边际成本' },
      { en: 'Economies of Scale', zh: '规模经济' }, { en: 'Average Total Cost', zh: '平均总成本' }, { en: 'Sunk Cost', zh: '沉没成本' }
    ],
    chart: { type: 'costs' },
    caseIcon: '🚗', caseBrand: 'Tesla', caseBg: '#F0FFF5',
    caseTopic: { en: "Tesla's Shanghai factory — localisation as cost strategy", zh: '特斯拉上海工厂——本土化即降本策略' },
    caseBody: {
      en: 'When Tesla opened its Shanghai Gigafactory in 2019, it had enormous <strong>fixed costs</strong>: $2 billion in construction, equipment, and setup. But once running, each additional Model 3 produced has dramatically lower <strong>marginal cost</strong> than in the US — Chinese labor, local suppliers, and no import tariffs. Within 3 years, Tesla sourced <strong>90%+ of parts locally</strong>, cutting per-unit costs significantly. The factory now produces 750,000 cars/year — spreading those fixed costs over a massive volume, achieving powerful <strong>economies of scale</strong>.',
      zh: '特斯拉 2019 年开设上海超级工厂时，承担了巨额<strong>固定成本</strong>：约 20 亿美元的建设、设备和启动费用。但一旦投产，每多生产一辆 Model 3 的<strong>边际成本</strong>远低于美国——中国劳动力、本地供应商、无进口关税。三年内，特斯拉实现了 <strong>90% 以上的本土化采购</strong>，大幅压低单车成本。工厂现年产 75 万辆——将固定成本分摊到庞大的产量上，实现了强大的<strong>规模经济</strong>。'
    },
    caseInsight: {
      en: "Tesla's Shanghai factory is a masterclass in cost strategy: accept high fixed costs upfront to achieve low marginal costs at scale. The break-even point came faster than anyone expected.",
      zh: '特斯拉上海工厂是成本策略的教科书案例：前期接受高固定成本，换取规模化后的低边际成本。盈亏平衡点的到来比所有人预期的都要快。'
    },
    apTip: {
      en: 'AP exam: firms maximize profit by producing where MR = MC. Never produce a unit where marginal cost exceeds marginal revenue — that unit loses money.',
      zh: 'AP 考试：企业在 MR = MC 处实现利润最大化。绝不生产边际成本超过边际收益的单位——那会亏损。'
    }
  },
  {
    id: 'comparative-advantage', type: 'micro', num: '05',
    title: { en: 'Comparative Advantage', zh: '比较优势' },
    sub: { en: 'Why countries specialize and trade — the economic logic behind globalization.', zh: '为什么国家选择专业化分工和贸易——全球化背后的经济逻辑。' },
    theory: {
      en: '<strong>Comparative advantage</strong> means producing a good at a lower <strong>opportunity cost</strong> than others — not necessarily being absolutely better. Even if one country is better at producing everything, both countries benefit from specializing in what they\'re relatively better at and trading. This is the foundation of global trade. The <strong>smile curve</strong> maps comparative advantage across a supply chain: each country/company does what it has comparative advantage in.',
      zh: '<strong>比较优势</strong>是指以比他人更低的<strong>机会成本</strong>生产某种商品——不一定是绝对意义上更好。即使一个国家在所有方面都更强，双方通过专注于各自相对擅长的领域并进行贸易，仍然都能获益。这是全球贸易的基础。<strong>微笑曲线</strong>展示了供应链中的比较优势分布：每个国家/企业做自己有比较优势的事。'
    },
    terms: [
      { en: 'Comparative Advantage', zh: '比较优势' }, { en: 'Opportunity Cost', zh: '机会成本' },
      { en: 'Specialization', zh: '专业化分工' }, { en: 'Smile Curve', zh: '微笑曲线' }, { en: 'Global Value Chain', zh: '全球价值链' }
    ],
    chart: { type: 'smile' },
    caseIcon: '📱', caseBrand: 'iPhone Global Supply Chain', caseBg: '#F0F0F0',
    caseTopic: { en: 'Why is iPhone designed in California but assembled in China?', zh: '为什么 iPhone 在加州设计、却在中国组装？' },
    caseBody: {
      en: 'Apple has <strong>comparative advantage in design and software</strong>: Silicon Valley engineering talent, decades of UX research, and brand building. China has <strong>comparative advantage in manufacturing</strong>: scale, infrastructure, supply chain density (thousands of component suppliers within a day\'s drive of Shenzhen), and labor costs. Taiwan\'s TSMC has comparative advantage in <strong>advanced chip fabrication</strong>. So the iPhone is designed in Cupertino, chips made in Taiwan, batteries in Shenzhen, assembled in Zhengzhou. Each participant does what they\'re relatively best at.',
      zh: '苹果在<strong>设计和软件上具有比较优势</strong>：硅谷的工程人才、数十年的用户体验研究积累和品牌建设。中国在<strong>制造上具有比较优势</strong>：规模、基础设施、供应链密度（深圳周边一天车程内有数千家零部件供应商），以及劳动力成本。台积电在<strong>先进芯片制造</strong>上具有比较优势。因此，iPhone 在库比蒂诺设计，芯片在台湾制造，电池在深圳生产，整机在郑州组装。每个参与者都在做自己相对最擅长的事。'
    },
    caseInsight: {
      en: 'The iPhone is the ultimate case study in comparative advantage — a single product built by 6 countries, each contributing what it does best. Disrupting any link (e.g. US sanctions on TSMC) breaks the entire chain.',
      zh: 'iPhone 是比较优势的终极案例——一款产品由 6 个国家共同构建，每个国家贡献各自最擅长的环节。破坏任何一环（如美国制裁台积电）都会打断整条链。'
    },
    apTip: {
      en: 'AP exam: comparative advantage is about opportunity cost, NOT absolute productivity. A country should export goods where its opportunity cost is lowest.',
      zh: 'AP 考试：比较优势关乎机会成本，而非绝对生产率。一个国家应出口机会成本最低的商品。'
    }
  },
  {
    id: 'market-failure', type: 'micro', num: '06',
    title: { en: 'Market Failure & Externalities', zh: '市场失灵与外部性' },
    sub: { en: 'When markets produce too much or too little — and why governments intervene.', zh: '当市场生产过多或过少时——以及政府为何介入。' },
    theory: {
      en: '<strong>Market failure</strong> occurs when free markets allocate resources inefficiently. The most common cause is <strong>externalities</strong> — costs or benefits that affect parties not involved in the transaction. <strong>Negative externalities</strong> (pollution): markets overproduce because producers don\'t pay the full social cost. <strong>Positive externalities</strong> (education, vaccines): markets underproduce because producers can\'t capture all the social benefit. Governments correct this through taxes (Pigou tax), subsidies, or regulation.',
      zh: '<strong>市场失灵</strong>发生在自由市场未能有效配置资源时。最常见的原因是<strong>外部性</strong>——影响交易之外第三方的成本或收益。<strong>负外部性</strong>（污染）：生产者不承担全部社会成本，市场因此过度生产。<strong>正外部性</strong>（教育、疫苗）：生产者无法获取全部社会收益，市场因此生产不足。政府通过税收（庇古税）、补贴或监管来纠正这一问题。'
    },
    terms: [
      { en: 'Externality', zh: '外部性' }, { en: 'Negative Externality', zh: '负外部性' },
      { en: 'Positive Externality', zh: '正外部性' }, { en: 'Pigouvian Tax', zh: '庇古税' }, { en: 'Carbon Credit', zh: '碳积分' }
    ],
    chart: { type: 'externality' },
    caseIcon: '⚡', caseBrand: 'Tesla', caseBg: '#F0FFF5',
    caseTopic: { en: "Tesla's carbon credit business — profiting from positive externalities", zh: '特斯拉的碳积分生意——从正外部性中获利' },
    caseBody: {
      en: 'Electric vehicles generate a <strong>positive externality</strong>: less pollution benefits everyone, but the car buyer only pays for their own car. Governments correct this with subsidies and <strong>carbon credit systems</strong>. In the US, EV manufacturers earn regulatory credits for zero-emission vehicles. Tesla, selling only EVs, earns massive credits it doesn\'t need — and <strong>sells them to Ford, GM, and other automakers</strong> who need them to comply with regulations. Tesla earned over <strong>$9 billion from carbon credit sales</strong> between 2013–2023 — this was profit margin that helped Tesla survive its early loss-making years.',
      zh: '电动汽车产生<strong>正外部性</strong>：减少污染造福所有人，但购车者只为自己的车付费。政府通过补贴和<strong>碳积分制度</strong>来纠正这一问题。在美国，电动汽车制造商为零排放车辆赚取监管积分。特斯拉只生产电动车，因此积累了大量自身不需要的积分——并将其<strong>出售给需要合规的福特、通用等传统车企</strong>。2013—2023 年间，特斯拉通过出售碳积分累计获得超过 <strong>90 亿美元</strong>——这是帮助特斯拉度过早期亏损岁月的关键利润来源。'
    },
    caseInsight: {
      en: "Tesla turned a government correction mechanism (carbon credits) into a $9B revenue stream. It's the most profitable example of monetizing positive externalities in corporate history.",
      zh: '特斯拉将政府的纠偏机制（碳积分）变成了 90 亿美元的收入来源。这是企业史上将正外部性变现最成功的案例。'
    },
    apTip: {
      en: 'AP exam: negative externalities → government taxes to reduce output to socially optimal level. Positive externalities → government subsidies to increase output to socially optimal level.',
      zh: 'AP 考试：负外部性 → 政府征税以将产量降至社会最优水平。正外部性 → 政府补贴以将产量提升至社会最优水平。'
    }
  },
  {
    id: 'gdp', type: 'macro', num: '07',
    title: { en: 'GDP & Economic Growth', zh: 'GDP 与经济增长' },
    sub: { en: 'How we measure the size of an economy — and what drives it to grow.', zh: '我们如何衡量经济体量——以及什么驱动它增长。' },
    theory: {
      en: '<strong>GDP (Gross Domestic Product)</strong> is the total value of all goods and services produced in a country in a year. The expenditure approach: <strong>GDP = C + I + G + (X−M)</strong> — consumption, investment, government spending, and net exports. <strong>Real GDP</strong> adjusts for inflation; <strong>nominal GDP</strong> does not. GDP growth signals a healthy economy; contraction for two consecutive quarters is a <strong>recession</strong>. GDP per capita is used to compare living standards across countries.',
      zh: '<strong>GDP（国内生产总值）</strong>是一个国家一年内生产的所有商品和服务的总价值。支出法：<strong>GDP = C + I + G + (X−M)</strong>——消费、投资、政府支出和净出口。<strong>实际 GDP</strong>经过通胀调整；<strong>名义 GDP</strong>未经调整。GDP 增长标志着经济健康；连续两个季度收缩即为<strong>衰退</strong>。人均 GDP 用于比较各国生活水平。'
    },
    terms: [
      { en: 'GDP', zh: '国内生产总值' }, { en: 'Real vs Nominal GDP', zh: '实际GDP vs 名义GDP' },
      { en: 'Recession', zh: '经济衰退' }, { en: 'GDP per Capita', zh: '人均GDP' }, { en: 'Net Exports', zh: '净出口' }
    ],
    chart: { type: 'gdp' },
    caseIcon: '🍎', caseBrand: 'Apple', caseBg: '#F0F0F0',
    caseTopic: { en: "Apple's GDP contribution — one company, the size of a country", zh: '苹果对 GDP 的贡献——一家公司，抵得上一个国家' },
    caseBody: {
      en: "Apple's annual revenue exceeds <strong>$380 billion</strong> — larger than the GDP of countries like Portugal, New Zealand, or Vietnam. In the US, Apple contributes to GDP through the <strong>C (consumption)</strong> component: consumers buying iPhones, Macs, and services. Apple also contributes through <strong>I (investment)</strong>: billions in R&D and capital expenditure. However, because iPhones are manufactured in China, the assembly value is counted in <strong>China's GDP</strong>, not America's. Apple's design and software margin stays in the US — this is how comparative advantage shapes GDP accounting.",
      zh: '苹果年收入超过 <strong>3800 亿美元</strong>——超过葡萄牙、新西兰、越南等国家的 GDP。在美国，苹果通过 <strong>C（消费）</strong>贡献 GDP：消费者购买 iPhone、Mac 和服务。苹果也通过 <strong>I（投资）</strong>贡献：数百亿美元的研发和资本支出。但由于 iPhone 在中国制造，组装环节的价值计入<strong>中国的 GDP</strong>，而非美国。苹果的设计和软件利润留在美国——这正是比较优势如何影响 GDP 核算的体现。'
    },
    caseInsight: {
      en: "Apple sells globally, manufactures in China, and keeps profits in the US. This split shows why GDP accounting is complicated by global supply chains — 'Made in China' captures only the assembly value, not the design profit.",
      zh: '苹果在全球销售，在中国制造，将利润留在美国。这种分割说明了为何全球供应链使 GDP 核算变得复杂——"中国制造"只计入组装价值，不包含设计利润。'
    },
    apTip: {
      en: 'AP exam: only count FINAL goods in GDP, not intermediate goods (to avoid double-counting). A steel company selling to Ford → steel is NOT counted separately; only the car is.',
      zh: 'AP 考试：GDP 只计算<strong>最终产品</strong>，不计中间产品（避免重复计算）。钢铁公司向福特销售钢材→钢材不单独计入；只计算汽车。'
    }
  },
  {
    id: 'inflation', type: 'macro', num: '08',
    title: { en: 'Inflation', zh: '通货膨胀' },
    sub: { en: 'Why prices rise, what it means for purchasing power, and how supply chains can cause inflation.', zh: '为什么物价上涨，这对购买力意味着什么，以及供应链如何引发通胀。' },
    theory: {
      en: '<strong>Inflation</strong> is a sustained increase in the general price level, measured by the <strong>CPI (Consumer Price Index)</strong>. <strong>Demand-pull inflation</strong>: too much money chasing too few goods (economy overheating). <strong>Cost-push inflation</strong>: rising production costs force prices up (supply shock). <strong>Hyperinflation</strong>: extreme, uncontrolled inflation destroying currency value. Central banks target ~2% annual inflation as healthy — enough to encourage spending, not enough to erode savings.',
      zh: '<strong>通货膨胀</strong>是一般价格水平的持续上涨，由<strong>CPI（消费者价格指数）</strong>衡量。<strong>需求拉动型通胀</strong>：过多货币追逐过少商品（经济过热）。<strong>成本推动型通胀</strong>：生产成本上升迫使价格提高（供给冲击）。<strong>恶性通胀</strong>：极端、失控的通胀摧毁货币价值。央行目标约为年通胀率 2%——足以鼓励消费，又不至于侵蚀储蓄。'
    },
    terms: [
      { en: 'CPI', zh: '消费者价格指数' }, { en: 'Demand-Pull Inflation', zh: '需求拉动型通胀' },
      { en: 'Cost-Push Inflation', zh: '成本推动型通胀' }, { en: 'Purchasing Power', zh: '购买力' }, { en: 'Hyperinflation', zh: '恶性通胀' }
    ],
    chart: { type: 'inflation' },
    caseIcon: '💻', caseBrand: 'Global Chip Shortage 2021', caseBg: '#FFF5E0',
    caseTopic: { en: 'How a chip shortage caused inflation across the entire economy', zh: '芯片短缺如何引发全经济范围的通胀' },
    caseBody: {
      en: 'In 2021, a perfect storm hit the semiconductor industry: <strong>COVID disrupted factories</strong>, demand for electronics surged (everyone working from home), and automakers who had cancelled chip orders couldn\'t get them back. The result: a global chip shortage. This was <strong>cost-push inflation</strong> — supply shock raising prices across the economy. A car that normally cost $35,000 sold for $5,000–$10,000 above sticker price. iPhone production was delayed. PS5s sold on eBay for 3× retail. One missing $5 chip could halt a $40,000 car\'s production.',
      zh: '2021 年，半导体行业遭遇完美风暴：<strong>疫情扰乱工厂生产</strong>，电子产品需求激增（所有人居家办公），而提前取消芯片订单的汽车制造商无法恢复供货。结果：全球芯片短缺。这是<strong>成本推动型通胀</strong>——供给冲击推高了整个经济的价格。原本售价 3.5 万美元的汽车涨价 5000—10000 美元。iPhone 生产延迟。PS5 在 eBay 上以零售价 3 倍出售。一块缺失的 5 美元芯片可以叫停一辆 4 万美元汽车的生产。'
    },
    caseInsight: {
      en: 'The 2021 chip shortage is the clearest modern example of cost-push inflation triggered by supply chain disruption. It shows how a shortage in one component can ripple through the entire economy.',
      zh: '2021 年芯片短缺是供应链中断引发成本推动型通胀最典型的现代案例。它展示了单一零部件短缺如何波及整个经济。'
    },
    apTip: {
      en: 'AP exam: distinguish demand-pull (AD shifts right) from cost-push (SRAS shifts left). Cost-push inflation is worse — it causes both higher prices AND lower output simultaneously.',
      zh: 'AP 考试：区分需求拉动（AD 右移）和成本推动（SRAS 左移）。成本推动型通胀更糟糕——它同时导致价格上涨和产出下降。'
    }
  },
  {
    id: 'monetary-policy', type: 'macro', num: '09',
    title: { en: 'Monetary Policy', zh: '货币政策' },
    sub: { en: "The Federal Reserve's tools to control inflation and unemployment — and how interest rates affect every business.", zh: '美联储控制通胀和失业率的工具——以及利率如何影响每家企业。' },
    theory: {
      en: '<strong>Monetary policy</strong> is controlled by the central bank (Federal Reserve in the US). The main tool: the <strong>federal funds rate</strong> — the interest rate banks charge each other. <strong>Expansionary policy</strong>: lower rates → cheaper borrowing → more spending → economic growth. <strong>Contractionary policy</strong>: higher rates → expensive borrowing → less spending → lower inflation. The Fed also uses <strong>quantitative easing</strong> (buying bonds to inject money) and reserve requirements.',
      zh: '<strong>货币政策</strong>由中央银行（美国为美联储）控制。主要工具：<strong>联邦基金利率</strong>——银行间相互借贷的利率。<strong>扩张性政策</strong>：降息 → 借贷成本降低 → 消费增加 → 经济增长。<strong>紧缩性政策</strong>：加息 → 借贷成本提高 → 消费减少 → 通胀下降。美联储还使用<strong>量化宽松</strong>（购买债券向市场注入资金）和存款准备金率工具。'
    },
    terms: [
      { en: 'Federal Funds Rate', zh: '联邦基金利率' }, { en: 'Expansionary Policy', zh: '扩张性政策' },
      { en: 'Contractionary Policy', zh: '紧缩性政策' }, { en: 'Quantitative Easing', zh: '量化宽松' }, { en: 'Reserve Requirement', zh: '存款准备金率' }
    ],
    chart: { type: 'interest-rate' },
    caseIcon: '🚗', caseBrand: 'Tesla', caseBg: '#F0FFF5',
    caseTopic: { en: 'How Fed rate hikes hurt Tesla sales', zh: '美联储加息如何冲击特斯拉销量' },
    caseBody: {
      en: 'In 2022–2023, the Federal Reserve raised interest rates from near 0% to over <strong>5.25%</strong> — the fastest rate hike cycle in 40 years — to fight inflation. For Tesla, this had a direct impact: most car buyers use <strong>auto loans</strong>. When rates rise from 3% to 7%, monthly payments on a $50,000 Model 3 increase by ~$150/month. Many buyers who could afford the car at low rates could no longer afford it. Tesla responded by <strong>cutting prices dramatically</strong> — up to 20% in early 2023 — to offset the affordability squeeze. This compressed Tesla\'s margins but maintained volume.',
      zh: '2022—2023 年，美联储将利率从接近 0% 提升至超过 <strong>5.25%</strong>——40 年来最快的加息周期——以抗击通胀。对特斯拉而言，这直接产生冲击：大多数购车者使用<strong>汽车贷款</strong>。当利率从 3% 升至 7% 时，一辆 5 万美元 Model 3 的月供增加约 150 美元。许多在低利率时期负担得起的买家，此时已无力购买。特斯拉的应对是 2023 年初<strong>大幅降价——最高达 20%</strong>——以抵消购买力下降的压力。这压缩了特斯拉的利润率，但维持了销量。'
    },
    caseInsight: {
      en: "Tesla's 2023 price cuts were not about competition — they were a direct response to Fed rate hikes making car loans unaffordable. Monetary policy reached all the way into EV showrooms.",
      zh: '特斯拉 2023 年的降价并非针对竞争——而是对美联储加息导致汽车贷款负担加重的直接回应。货币政策的影响一直延伸到了电动车展厅。'
    },
    apTip: {
      en: 'AP exam: the Fed uses open market operations as its primary tool. Buying bonds → money supply increases → interest rates fall. Selling bonds → money supply decreases → interest rates rise.',
      zh: 'AP 考试：美联储以公开市场操作为主要工具。购买债券 → 货币供应增加 → 利率下降。出售债券 → 货币供应减少 → 利率上升。'
    }
  },
  {
    id: 'phillips-curve', type: 'macro', num: '10',
    title: { en: 'The Phillips Curve', zh: '菲利普斯曲线' },
    sub: { en: 'The trade-off between inflation and unemployment — one of the most debated relationships in macroeconomics.', zh: '通胀与失业率之间的权衡——宏观经济学中争议最大的关系之一。' },
    theory: {
      en: 'The <strong>Phillips Curve</strong> shows an inverse relationship between inflation and unemployment: when unemployment is low, wages rise, increasing costs and inflation. When unemployment is high, wage pressure falls and inflation cools. This gives policymakers a painful trade-off: fight inflation (raise rates → more unemployment) or fight unemployment (lower rates → more inflation). In the 1970s, <strong>stagflation</strong> (high inflation AND high unemployment) broke the simple Phillips Curve — showing the relationship isn\'t always stable.',
      zh: '<strong>菲利普斯曲线</strong>显示通胀与失业率之间的反向关系：失业率低时，工资上涨，推高成本和通胀；失业率高时，工资压力下降，通胀降温。这给政策制定者带来痛苦的权衡：抗击通胀（加息 → 失业率上升）还是抗击失业（降息 → 通胀上升）。1970 年代的<strong>滞胀</strong>（高通胀+高失业率并存）打破了简单的菲利普斯曲线——表明这种关系并不总是稳定的。'
    },
    terms: [
      { en: 'Phillips Curve', zh: '菲利普斯曲线' }, { en: 'Stagflation', zh: '滞胀' },
      { en: 'NAIRU', zh: '非加速通胀失业率' }, { en: 'Wage-Price Spiral', zh: '工资-价格螺旋' }, { en: 'Trade-off', zh: '权衡取舍' }
    ],
    chart: { type: 'phillips' },
    caseIcon: '💼', caseBrand: 'US Tech Industry 2022', caseBg: '#F5F0FF',
    caseTopic: { en: 'Tech layoffs, inflation, and the Phillips Curve in action', zh: '科技裁员、通胀与菲利普斯曲线的现实演绎' },
    caseBody: {
      en: 'In 2022, US inflation hit <strong>9.1%</strong> — a 40-year high. The Fed aggressively raised rates. Tech companies, whose valuations depended on cheap money, began mass layoffs: <strong>Meta cut 21,000 jobs, Amazon 27,000, Google 12,000</strong>. From the Phillips Curve perspective: the Fed deliberately increased unemployment to cool inflation. It worked — by 2023, inflation fell to ~3%. But 200,000+ tech workers lost jobs in the process. This is the human cost of the inflation-unemployment trade-off that the Phillips Curve describes.',
      zh: '2022 年，美国通胀率达到 <strong>9.1%</strong>——40 年新高。美联储大幅加息。依赖廉价资金支撑估值的科技公司开始大规模裁员：<strong>Meta 裁员 2.1 万人，亚马逊 2.7 万人，谷歌 1.2 万人</strong>。从菲利普斯曲线的视角来看：美联储刻意提高失业率来压制通胀。这奏效了——到 2023 年，通胀降至约 3%。但代价是 20 万以上的科技从业者失业。这正是菲利普斯曲线所描述的通胀与失业权衡的人间代价。'
    },
    caseInsight: {
      en: "The 2022–2023 Fed tightening cycle is the Phillips Curve playing out in real time. Tech layoffs were a side effect of the Fed's inflation fight — a textbook example of the unemployment cost of disinflation.",
      zh: '2022—2023 年美联储紧缩周期是菲利普斯曲线的实时演绎。科技裁员是美联储抗通胀的副作用——是反通胀失业成本的教科书案例。'
    },
    apTip: {
      en: 'AP exam: in the short run, there is a trade-off (lower unemployment = higher inflation). In the long run, the curve is vertical at the NAIRU — monetary policy cannot permanently reduce unemployment below this.',
      zh: 'AP 考试：短期内存在权衡（失业率越低 = 通胀越高）。长期来看，曲线在 NAIRU 处垂直——货币政策无法永久将失业率压低至此水平以下。'
    }
  },
  {
    id: 'exchange-rates', type: 'macro', num: '11',
    title: { en: 'Exchange Rates', zh: '汇率' },
    sub: { en: 'How currency values affect trade, pricing, and corporate profits across borders.', zh: '货币汇率如何影响跨境贸易、定价和企业利润。' },
    theory: {
      en: 'An <strong>exchange rate</strong> is the price of one currency in terms of another. When a currency <strong>appreciates</strong> (gets stronger), exports become more expensive for foreigners (bad for exporters) and imports become cheaper (good for consumers). When it <strong>depreciates</strong>, exports become cheaper (good for exporters) and imports become more expensive (inflationary). Exchange rates are influenced by interest rates, inflation differentials, and trade balances.',
      zh: '<strong>汇率</strong>是一种货币以另一种货币表示的价格。当货币<strong>升值</strong>时，本国出口品对外国人变贵（不利于出口商），进口品变便宜（有利于消费者）。当货币<strong>贬值</strong>时，出口品变便宜（有利于出口商），进口品变贵（导致通胀）。汇率受利率、通胀差异和贸易余额的影响。'
    },
    terms: [
      { en: 'Exchange Rate', zh: '汇率' }, { en: 'Appreciation', zh: '升值' },
      { en: 'Depreciation', zh: '贬值' }, { en: 'Current Account', zh: '经常账户' }, { en: 'Purchasing Power Parity', zh: '购买力平价' }
    ],
    chart: { type: 'exchange' },
    caseIcon: '📱', caseBrand: 'Apple in China', caseBg: '#F0F0F0',
    caseTopic: { en: 'How RMB exchange rate affects iPhone pricing in China', zh: '人民币汇率如何影响 iPhone 在中国的定价' },
    caseBody: {
      en: 'Apple prices iPhones in USD globally, then converts to local currency. When the <strong>RMB depreciates against the dollar</strong> (yuan weakens), Chinese consumers effectively pay more for the same iPhone — because it takes more yuan to buy the same dollars. In 2023, the RMB fell ~8% against the USD. Apple faced a choice: raise yuan prices (risk losing customers) or absorb the loss (compressed margins). Apple also earns revenue in yuan from China sales — when converting back to USD for reporting, yuan depreciation means <strong>lower reported USD revenue</strong>, even if unit sales are unchanged.',
      zh: '苹果在全球以美元定价 iPhone，再换算为当地货币。当<strong>人民币对美元贬值</strong>时，中国消费者购买同款 iPhone 实际需要支付更多——因为需要更多人民币才能换到相同的美元。2023 年，人民币对美元贬值约 8%。苹果面临两难：提高人民币售价（可能流失客户），还是自行吸收损失（利润率受压）。此外，苹果在中国的销售收入以人民币计，换算回美元进行财务报告时，人民币贬值意味着<strong>报告的美元收入降低</strong>，即便实际销量未变。'
    },
    caseInsight: {
      en: 'For multinationals like Apple, currency fluctuations can add or subtract billions from reported profits — even if the underlying business is unchanged. This is why large companies use currency hedging.',
      zh: '对苹果这样的跨国公司而言，汇率波动可以在报告利润中增减数十亿美元——即便业务本身没有变化。这就是大型企业使用货币对冲的原因。'
    },
    apTip: {
      en: 'AP exam: currency depreciation → exports increase, imports decrease → trade balance improves (J-curve effect). Currency appreciation → opposite. Always think about WHO benefits and WHO loses.',
      zh: 'AP 考试：货币贬值 → 出口增加，进口减少 → 贸易差额改善（J 曲线效应）。货币升值 → 相反。始终思考谁受益、谁受损。'
    }
  },
  {
    id: 'trade-policy', type: 'macro', num: '12',
    title: { en: 'Trade Policy & Globalization', zh: '贸易政策与全球化' },
    sub: { en: 'Free trade vs protectionism — and how US-China trade tensions are reshaping supply chains.', zh: '自由贸易 vs 贸易保护主义——以及中美贸易摩擦如何重塑供应链。' },
    theory: {
      en: '<strong>Free trade</strong> allows goods and services to flow across borders without government restriction — maximizing comparative advantage and consumer choice. <strong>Protectionism</strong> uses tariffs, quotas, and subsidies to shield domestic industries. Economists broadly favor free trade (efficiency gains), but it creates winners and losers within countries — displaced workers in import-competing industries lose even as consumers gain from cheaper goods. This political tension drives trade policy debates.',
      zh: '<strong>自由贸易</strong>允许商品和服务在无政府限制的情况下跨境流动——最大化比较优势和消费者选择。<strong>贸易保护主义</strong>通过关税、配额和补贴来保护国内产业。经济学家普遍支持自由贸易（效率收益），但它会在国内制造赢家和输家——进口竞争行业的工人受损，而消费者则因商品更便宜而受益。这种政治张力驱动着贸易政策争论。'
    },
    terms: [
      { en: 'Tariff', zh: '关税' }, { en: 'Quota', zh: '配额' },
      { en: 'Protectionism', zh: '贸易保护主义' }, { en: 'Trade Deficit', zh: '贸易逆差' }, { en: 'Supply Chain Reshoring', zh: '供应链回流' }
    ],
    chart: { type: 'trade' },
    caseIcon: '🏭', caseBrand: 'Shenzhen Manufacturing', caseBg: '#FFF5E0',
    caseTopic: { en: 'How US-China trade tensions are reshaping Shenzhen\'s supply chains', zh: '中美贸易摩擦如何重塑深圳供应链' },
    caseBody: {
      en: 'Since 2018, the US has imposed <strong>tariffs of 25%+</strong> on hundreds of billions of dollars of Chinese goods. For Shenzhen manufacturers, this changed the economics overnight. Companies like Foxconn and BYD Electronic began <strong>shifting some production to Vietnam, India, and Mexico</strong> to avoid tariffs. Apple, under pressure to reduce China dependency, now assembles some iPhones in India. Sunwoda (欣旺达) has expanded battery production in Vietnam. This "China+1" strategy — keeping China as the base but adding one more country — is the defining supply chain trend of the 2020s.',
      zh: '2018 年以来，美国对数千亿美元的中国商品加征 <strong>25% 以上的关税</strong>。对深圳制造商而言，这一夜之间改变了经济算盘。富士康、比亚迪电子等企业开始<strong>将部分产能转移至越南、印度和墨西哥</strong>以规避关税。苹果在降低对中国依赖的压力下，如今已在印度组装部分 iPhone。欣旺达已在越南扩大电池产能。这种"中国+1"策略——以中国为基地，同时增加一个备选国家——是 2020 年代供应链最显著的趋势。'
    },
    caseInsight: {
      en: 'US-China tariffs are the single biggest force reshaping global supply chains right now. Shenzhen manufacturers that built their entire business model around serving US brands are now racing to diversify geographically — not just by customer, but by country.',
      zh: '中美关税是当前重塑全球供应链最重要的力量。以服务美国品牌为核心商业模式的深圳制造商，正在竞相实现地理上的多元化——不仅是客户多元化，更是国家层面的多元化。'
    },
    apTip: {
      en: 'AP exam: tariffs raise domestic prices, reduce imports, and protect domestic producers — but harm domestic consumers and foreign exporters. The net effect is typically a welfare loss (deadweight loss) for the importing country.',
      zh: 'AP 考试：关税提高国内价格、减少进口、保护国内生产商——但损害国内消费者和外国出口商。对进口国而言，净效应通常是福利损失（无谓损失）。'
    }
  }
];

function buildSidebar() {
  const sb = document.getElementById('sidebar');
  let html = '';
  let lastType = null;
  LESSONS.forEach((l, i) => {
    if (l.type !== lastType) {
      const label = l.type === 'micro'
        ? `<span class="chapter-tag tag-micro" data-en="Microeconomics" data-zh="微观经济学">Microeconomics</span>`
        : `<span class="chapter-tag tag-macro" data-en="Macroeconomics" data-zh="宏观经济学">Macroeconomics</span>`;
      html += `<div class="chapter-header">${label}</div>`;
      lastType = l.type;
    }
    html += `<button class="nav-item${i===0?' active':''}" id="nav-${i}" onclick="goLesson(${i})">
      <span class="nav-num">${l.num}</span>
      <span data-en="${l.title.en}" data-zh="${l.title.zh}">${l.title.en}</span>
    </button>`;
  });
  sb.innerHTML = html;
}

function goLesson(i) {
  currentLesson = i;
  document.querySelectorAll('.nav-item').forEach((b,j) => b.classList.toggle('active', j===i));
  renderLesson();
  document.getElementById('content').scrollTop = 0;
}

let activeCharts = {};
function renderLesson() {
  Object.values(activeCharts).forEach(c => { try { c.destroy(); } catch(e){} });
  activeCharts = {};
  const l = LESSONS[currentLesson];
  const t = l.title[currentLang];
  const tagLabel = l.type === 'micro'
    ? `<span class="lesson-tag" style="background:#E6F1FB;color:#0C447C;" data-en="AP Microeconomics" data-zh="AP 微观经济学">AP Microeconomics</span>`
    : `<span class="lesson-tag" style="background:#E1F5EE;color:#085041;" data-en="AP Macroeconomics" data-zh="AP 宏观经济学">AP Macroeconomics</span>`;

  const termsHtml = l.terms.map(term =>
    `<span class="key-term"><strong data-en="${term.en}" data-zh="${term.zh}">${term.en}</strong></span>`
  ).join('');

  document.getElementById('content').innerHTML = `
    <div class="lesson">
      ${tagLabel}
      <h1 class="lesson-title" data-en="${l.title.en}" data-zh="${l.title.zh}">${l.title[currentLang]}</h1>
      <p class="lesson-sub" data-en="${l.sub.en}" data-zh="${l.sub.zh}">${l.sub[currentLang]}</p>

      <div class="lesson-section">
        <div class="section-label" data-en="Theory" data-zh="理论">Theory</div>
        <div class="theory-box">
          <div class="theory-text" data-en="${escHtml(l.theory.en)}" data-zh="${escHtml(l.theory.zh)}">${l.theory[currentLang]}</div>
          <div class="key-terms">${termsHtml}</div>
        </div>
      </div>

      <div class="lesson-section">
        <div class="section-label" data-en="Visualization" data-zh="可视化">Visualization</div>
        <div class="chart-card">
          <div class="chart-wrap"><canvas id="mainChart" role="img" aria-label="${t} chart"></canvas></div>
        </div>
      </div>

      <div class="lesson-section">
        <div class="section-label" data-en="Real-World Case Study" data-zh="真实案例">Real-World Case Study</div>
        <div class="case-card">
          <div class="case-header">
            <div class="case-icon" style="background:${l.caseBg};">${l.caseIcon}</div>
            <div>
              <div class="case-brand">${l.caseBrand}</div>
              <div class="case-topic" data-en="${l.caseTopic.en}" data-zh="${l.caseTopic.zh}">${l.caseTopic[currentLang]}</div>
            </div>
          </div>
          <div class="case-body">
            <div data-en="${escHtml(l.caseBody.en)}" data-zh="${escHtml(l.caseBody.zh)}">${l.caseBody[currentLang]}</div>
            <div class="case-insight" data-en="${escHtml(l.caseInsight.en)}" data-zh="${escHtml(l.caseInsight.zh)}">${l.caseInsight[currentLang]}</div>
          </div>
        </div>
      </div>

      <div class="lesson-section">
        <div class="section-label" data-en="AP Exam Tip" data-zh="AP考试要点">AP Exam Tip</div>
        <div class="ap-tip">
          <div class="ap-tip-label" data-en="AP Exam" data-zh="AP 考试">AP Exam</div>
          <div class="ap-tip-text" data-en="${escHtml(l.apTip.en)}" data-zh="${escHtml(l.apTip.zh)}">${l.apTip[currentLang]}</div>
        </div>
      </div>

      <div class="lesson-nav">
        <button class="nav-btn" onclick="goLesson(${currentLesson-1})" ${currentLesson===0?'disabled':''} data-en="← Previous" data-zh="← 上一节">← Previous</button>
        <span style="font-size:12px;color:var(--faint);align-self:center;">${currentLesson+1} / ${LESSONS.length}</span>
        <button class="nav-btn primary" onclick="goLesson(${currentLesson+1})" ${currentLesson===LESSONS.length-1?'disabled':''} data-en="Next →" data-zh="下一节 →">Next →</button>
      </div>
    </div>
  `;
  renderChart(l);
  if (currentLang === 'zh') applyLang('zh');
}

function escHtml(s) { return s.replace(/"/g,'&quot;'); }

const COLORS = { grid: 'rgba(0,0,0,0.05)', text: '#AAA', blue: '#185FA5', teal: '#0F6E56', amber: '#BA7517', red: '#A32D2D', dark: '#1A1A1A' };

function renderChart(l) {
  const canvas = document.getElementById('mainChart');
  if (!canvas) return;
  const t = l.chart.type;
  let cfg;

  if (t === 'supply-demand') {
    cfg = { type: 'line', data: { labels: ['1','2','3','4','5','6','7'], datasets: [
      { label: currentLang==='zh'?'需求曲线':'Demand', data: [95,80,65,50,35,20,5], borderColor: COLORS.blue, backgroundColor:'transparent', pointRadius:3, tension:0.3, borderWidth:2 },
      { label: currentLang==='zh'?'供给曲线':'Supply', data: [5,20,35,50,65,80,95], borderColor: COLORS.teal, backgroundColor:'transparent', pointRadius:3, tension:0.3, borderWidth:2 },
    ]}, options: chartOpts(currentLang==='zh'?'价格':'Price', currentLang==='zh'?'数量':'Quantity') };
  } else if (t === 'elasticity') {
    cfg = { type: 'line', data: { labels: ['$60','$70','$80','$90','$100','$110','$120'], datasets: [
      { label: currentLang==='zh'?'缺乏弹性（LV）':'Inelastic (LV)', data: [98,97,95,93,92,90,89], borderColor: COLORS.amber, backgroundColor:'transparent', pointRadius:3, tension:0.3, borderWidth:2 },
      { label: currentLang==='zh'?'富有弹性（机票）':'Elastic (Flights)', data: [95,80,60,40,22,10,3], borderColor: COLORS.blue, backgroundColor:'transparent', pointRadius:3, tension:0.3, borderWidth:2 },
    ]}, options: chartOpts(currentLang==='zh'?'价格':'Price', currentLang==='zh'?'需求量':'Quantity Demanded') };
  } else if (t === 'market-structure') {
    cfg = { type: 'bar', data: { labels: currentLang==='zh'?['完全竞争','垄断竞争','寡头','垄断']:['Perfect Competition','Monopolistic Competition','Oligopoly','Monopoly'], datasets: [
      { label: currentLang==='zh'?'定价权（0-100）':'Pricing Power (0-100)', data: [5,30,65,95], backgroundColor: ['#B5D4F4','#85B7EB','#378ADD','#185FA5'] },
    ]}, options: { ...chartOpts('',''), plugins:{ legend:{display:false} } } };
  } else if (t === 'costs') {
    cfg = { type: 'line', data: { labels: ['100','200','300','400','500','600','700','800'], datasets: [
      { label: currentLang==='zh'?'平均总成本':'Average Total Cost', data: [80,55,42,36,34,35,38,43], borderColor: COLORS.blue, backgroundColor:'transparent', pointRadius:3, tension:0.4, borderWidth:2 },
      { label: currentLang==='zh'?'边际成本':'Marginal Cost', data: [30,25,28,34,42,52,65,80], borderColor: COLORS.amber, backgroundColor:'transparent', pointRadius:3, tension:0.4, borderWidth:2, borderDash:[5,3] },
    ]}, options: chartOpts(currentLang==='zh'?'成本($)':'Cost ($)', currentLang==='zh'?'产量':'Output') };
  } else if (t === 'smile') {
    cfg = { type: 'line', data: { labels: currentLang==='zh'?['研发','设计','零部件','组装','物流','品牌','营销']:['R&D','Design','Components','Assembly','Logistics','Branding','Marketing'], datasets: [
      { label: currentLang==='zh'?'附加值':'Value-Added', data: [85,78,42,18,30,80,88], borderColor: COLORS.dark, backgroundColor:'transparent', pointBackgroundColor: COLORS.amber, pointRadius:5, tension:0.45, borderWidth:2 },
    ]}, options: chartOpts(currentLang==='zh'?'附加值指数':'Value-Added Index','') };
  } else if (t === 'externality') {
    cfg = { type: 'line', data: { labels: ['1','2','3','4','5','6','7'], datasets: [
      { label: currentLang==='zh'?'私人成本':'Private Cost', data: [10,20,30,40,50,60,70], borderColor: COLORS.blue, backgroundColor:'transparent', pointRadius:3, tension:0.1, borderWidth:2 },
      { label: currentLang==='zh'?'社会成本（含外部性）':'Social Cost (with externality)', data: [20,35,50,65,80,95,110], borderColor: COLORS.red, backgroundColor:'transparent', pointRadius:3, tension:0.1, borderWidth:2 },
      { label: currentLang==='zh'?'需求':'Demand', data: [100,85,70,55,40,25,10], borderColor: COLORS.teal, backgroundColor:'transparent', pointRadius:3, tension:0.1, borderWidth:2, borderDash:[4,3] },
    ]}, options: chartOpts(currentLang==='zh'?'价格/成本':'Price/Cost', currentLang==='zh'?'数量':'Quantity') };
  } else if (t === 'gdp') {
    cfg = { type: 'bar', data: { labels: ['2019','2020','2021','2022','2023'], datasets: [
      { label: currentLang==='zh'?'C - 消费':'C - Consumption', data: [14.0,13.4,14.8,15.7,16.4], backgroundColor: COLORS.blue },
      { label: currentLang==='zh'?'I - 投资':'I - Investment', data: [3.7,3.4,3.9,4.2,4.3], backgroundColor: COLORS.teal },
      { label: currentLang==='zh'?'G - 政府':'G - Government', data: [3.8,4.2,4.6,4.4,4.5], backgroundColor: COLORS.amber },
      { label: currentLang==='zh'?'X-M - 净出口':'X-M - Net Exports', data: [-0.6,-0.9,-1.2,-1.0,-0.8], backgroundColor: COLORS.red },
    ]}, options: { ...chartOpts(currentLang==='zh'?'万亿美元':'Trillion USD',''), plugins:{ legend:{display:true, labels:{color:'#666',font:{size:11}}}}, scales:{ x:{stacked:true,grid:{color:'rgba(0,0,0,0.04)'},ticks:{color:'#AAA'}}, y:{stacked:true,grid:{color:'rgba(0,0,0,0.04)'},ticks:{color:'#AAA'}} } } };
  } else if (t === 'inflation') {
    cfg = { type: 'line', data: { labels: ['2020','2021 Q1','2021 Q3','2022 Q1','2022 Q3','2023 Q1','2023 Q3'], datasets: [
      { label: currentLang==='zh'?'美国CPI通胀率%':'US CPI Inflation %', data: [1.2,1.7,4.0,7.9,8.3,6.0,3.7], borderColor: COLORS.red, backgroundColor:'transparent', pointBackgroundColor:COLORS.red, pointRadius:4, tension:0.3, borderWidth:2 },
    ]}, options: chartOpts(currentLang==='zh'?'通胀率 (%)':'Inflation Rate (%)','') };
  } else if (t === 'interest-rate') {
    cfg = { type: 'line', data: { labels: ['Jan 22','Mar 22','Jun 22','Sep 22','Dec 22','Mar 23','Jun 23','Sep 23'], datasets: [
      { label: currentLang==='zh'?'联邦基金利率%':'Fed Funds Rate %', data: [0.08,0.33,1.58,3.08,4.33,4.83,5.08,5.33], borderColor: COLORS.blue, backgroundColor:'transparent', pointBackgroundColor:COLORS.blue, pointRadius:4, tension:0.3, borderWidth:2 },
    ]}, options: chartOpts(currentLang==='zh'?'利率 (%)':'Interest Rate (%)','') };
  } else if (t === 'phillips') {
    cfg = { type: 'line', data: { labels: ['3%','4%','5%','6%','7%','8%','9%'], datasets: [
      { label: currentLang==='zh'?'短期菲利普斯曲线':'Short-run Phillips Curve', data: [9,7,5,3.5,2.5,2,1.8], borderColor: COLORS.blue, backgroundColor:'transparent', pointRadius:4, tension:0.4, borderWidth:2 },
    ]}, options: chartOpts(currentLang==='zh'?'通胀率 (%)':'Inflation Rate (%)', currentLang==='zh'?'失业率 (%)':'Unemployment Rate (%)') };
  } else if (t === 'exchange') {
    cfg = { type: 'line', data: { labels: ['Jan 22','Apr 22','Jul 22','Oct 22','Jan 23','Apr 23','Jul 23','Oct 23'], datasets: [
      { label: currentLang==='zh'?'人民币/美元汇率':'RMB per USD', data: [6.36,6.40,6.75,7.12,6.75,6.90,7.15,7.30], borderColor: COLORS.amber, backgroundColor:'transparent', pointBackgroundColor:COLORS.amber, pointRadius:4, tension:0.3, borderWidth:2 },
    ]}, options: chartOpts(currentLang==='zh'?'人民币/美元':'RMB per USD','') };
  } else if (t === 'trade') {
    cfg = { type: 'bar', data: { labels: currentLang==='zh'?['自由贸易','关税 10%','关税 25%','关税 50%']:['Free Trade','10% Tariff','25% Tariff','50% Tariff'], datasets: [
      { label: currentLang==='zh'?'消费者福利':'Consumer Welfare', data: [100,88,72,50], backgroundColor: COLORS.blue },
      { label: currentLang==='zh'?'国内生产商利润':'Domestic Producer Profit', data: [40,55,68,75], backgroundColor: COLORS.teal },
      { label: currentLang==='zh'?'政府关税收入':'Government Tariff Revenue', data: [0,8,12,10], backgroundColor: COLORS.amber },
    ]}, options: { ...chartOpts(currentLang==='zh'?'福利指数':'Welfare Index',''), plugins:{ legend:{display:true, labels:{color:'#666',font:{size:11}}}}, scales:{ x:{grid:{color:'rgba(0,0,0,0.04)'},ticks:{color:'#AAA'}}, y:{grid:{color:'rgba(0,0,0,0.04)'},ticks:{color:'#AAA'}} } } };
  }

  if (cfg) activeCharts['main'] = new Chart(canvas, cfg);
}

function chartOpts(yLabel, xLabel) {
  return { responsive:true, maintainAspectRatio:false, plugins:{ legend:{ display:true, labels:{ color:'#666', font:{ size:11, family:'DM Sans' }}}}, scales:{ x:{ title:{ display:!!xLabel, text:xLabel, color:'#AAA', font:{size:11}}, grid:{color:'rgba(0,0,0,0.04)'}, ticks:{color:'#AAA',font:{size:11}}}, y:{ title:{ display:!!yLabel, text:yLabel, color:'#AAA', font:{size:11}}, grid:{color:'rgba(0,0,0,0.04)'}, ticks:{color:'#AAA',font:{size:11}}}}};
}

function setLang(lang) {
  currentLang = lang;
  document.querySelectorAll('.lang-btn').forEach(b => b.classList.remove('active'));
  document.querySelector(`.lang-btn[onclick="setLang('${lang}')"]`).classList.add('active');
  const si = document.querySelector('.search-wrap input');
  if (si) si.placeholder = si.getAttribute('data-placeholder-'+lang);
  buildSidebar();
  renderLesson();
}

function applyLang(lang) {
  document.querySelectorAll('[data-en]').forEach(el => {
    const v = el.getAttribute('data-'+lang);
    if (v) el.innerHTML = v;
  });
}

function doSearch(val) {
  if (!val.trim()) return;
  const q = val.toLowerCase();
  const idx = LESSONS.findIndex(l =>
    l.title.en.toLowerCase().includes(q) ||
    l.title.zh.includes(q) ||
    l.terms.some(t => t.en.toLowerCase().includes(q) || t.zh.includes(q))
  );
  if (idx >= 0) goLesson(idx);
}

buildSidebar();
renderLesson();
</script>
</body>
</html>
