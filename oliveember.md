# CMCVRR Technical Index

CMCVRR Technical Index 是一个面向技术研究者的结构化外链与文章资源聚合系统。本项目的定位并非内容农场或转载站点，而是通过对 `blog.cmcvrr.cn` 平台下大量技术类文章进行编号索引、分类整理与快速导航，帮助开发者、运维工程师与技术管理者在碎片化信息中高效定位到与自身问题匹配的原始讨论、案例分析与解决方案。

本项目不存储任何文章正文内容，仅提供元数据索引与结构化导航。目标用户包括需要查阅特定技术问题现场记录的中高级工程师、进行技术选型调研的架构师，以及希望追踪特定领域技术演进脉络的研究人员。通过统一的索引层，用户无需依赖站内搜索或猜测 URL 规则，即可基于编号体系与分类目录直接访问目标文章。

## 功能概览

**编号化文章索引体系**：每篇收录文章均分配唯一数字标识，URL 路径中的数字即文章 ID，支持按编号直接定位与引用。

**多维度分类导航**：按技术领域、问题类型、应用场景与时间线等维度对文章进行逻辑分组，降低信息发现成本。

**原始内容直链访问**：所有索引条目均保留原始域名与完整路径，用户点击后直接跳转至 `blog.cmcvrr.cn` 的原始文章页面，无中间跳转或重定向。

**轻量级元数据标注**：在资源列表中附带文章编号、推测所属领域与简要内容标签，辅助用户快速判断相关性。

**批量资源导入支持**：提供结构化数据导入接口，支持批量添加新文章编号与元数据，适用于团队内部知识库维护场景。

**静态索引生成机制**：索引页面采用纯静态 Markdown 渲染，无需后端服务即可完整展示所有资源链接，降低部署与维护成本。

**可扩展分类插件系统**：预留分类规则自定义接口，用户可根据自身研究领域新增或调整分类逻辑。

**全文检索占位接口**：预留与外部检索引擎对接的配置项，便于未来集成站内搜索功能。

## 应用场景

**技术问题现场查阅**：当开发者在生产环境遇到异常日志或非预期行为时，可通过本索引按问题类型快速检索相关文章编号，直接访问原始讨论记录或故障复盘文档，缩短问题定位时间。

**技术选型参考调研**：架构师在进行组件选型或方案对比时，可利用本索引获取特定技术栈下的实践案例列表，通过横向阅读多个文章编号对应的原始内容，评估不同方案的适用边界与潜在风险。

**知识库批量导入**：团队内部知识管理者可将本索引作为数据源，通过脚本批量抓取文章编号与标题信息，导入至 Confluence、Notion 或本地 Markdown 仓库，构建私有技术文档库。

**技术趋势追踪**：研究人员可按时间顺序浏览新增文章编号，观察特定领域（如性能优化、安全加固、云原生）的讨论密度变化，辅助判断技术热点的迁移趋势。

## 快速开始

以下操作基于 Unix/Linux 或 macOS 环境，Windows 用户可使用 WSL 或 Git Bash 执行。

```bash
# 克隆项目仓库至本地
git clone https://github.com/cmcvrr/technical-index.git
cd technical-index

# 安装依赖（基于 Node.js 环境，用于本地索引生成与校验）
npm install

# 运行索引生成脚本，输出完整的资源列表页面
npm run build
```

执行完毕后，生成的静态页面位于 `dist/index.html`，可直接在浏览器中打开浏览。若仅需查看 Markdown 源文件，请直接查阅 `RESOURCES.md`。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Node.js | 16.x 或更高 | 用于运行索引构建脚本与依赖管理 |
| npm | 8.x 或更高 | 包管理器，用于安装项目依赖 |
| Git | 2.30 或更高 | 用于克隆仓库及版本控制 |
| 操作系统 | Linux / macOS / Windows (WSL) | 开发与运行环境，Windows 原生命令行未充分测试 |
| 网络访问 | 可访问 `blog.cmcvrr.cn` | 用于验证链接有效性（可选功能） |
| 浏览器 | 支持 ES6 的现代浏览器 | 用于查看生成的静态页面 |
| Markdown 渲染器 | 可选 | 用于本地预览 `RESOURCES.md` 文件 |
| shell 环境 | Bash / Zsh / PowerShell | 用于执行快速开始中的命令脚本 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户入门 | `docs/quick-start.md` | 如何最快开始使用本索引？如何查找特定编号的文章？ |
| 资源维护 | `docs/maintenance.md` | 如何新增文章编号？如何更新元数据分类？如何校验链接有效性？ |
| 分类规则 | `docs/categorization.md` | 文章按哪些维度分类？分类标签的命名规范是什么？如何自定义分类？ |
| 工具链说明 | `docs/build-tool.md` | 构建脚本的工作原理是什么？如何修改输出模板？如何集成 CI/CD？ |

## 资源列表

本列表按照文章编号区间进行逻辑分组，所有 URL 均保留原始来源域名与路径格式，未做任何改写。

基础技术讨论区（编号 0000 - 3999）

http://www.blog.cmcvrr.cn/Article/details/43607.sHtML
http://www.blog.cmcvrr.cn/Article/details/425609.sHtML
http://www.blog.cmcvrr.cn/Article/details/30316.sHtML
http://www.blog.cmcvrr.cn/Article/details/4234.sHtML
http://www.blog.cmcvrr.cn/Article/details/794032.sHtML
http://www.blog.cmcvrr.cn/Article/details/869525.sHtML
http://www.blog.cmcvrr.cn/Article/details/32788.sHtML
http://www.blog.cmcvrr.cn/Article/details/9533.sHtML
http://www.blog.cmcvrr.cn/Article/details/437993.sHtML
http://www.blog.cmcvrr.cn/Article/details/433446.sHtML
http://www.blog.cmcvrr.cn/Article/details/6059.sHtML
http://www.blog.cmcvrr.cn/Article/details/09972.sHtML
http://www.blog.cmcvrr.cn/Article/details/5098.sHtML
http://www.blog.cmcvrr.cn/Article/details/161013.sHtML
http://www.blog.cmcvrr.cn/Article/details/28970.sHtML
http://www.blog.cmcvrr.cn/Article/details/5050797.sHtML
http://www.blog.cmcvrr.cn/Article/details/6844.sHtML
http://www.blog.cmcvrr.cn/Article/details/635272.sHtML
http://www.blog.cmcvrr.cn/Article/details/152662.sHtML
http://www.blog.cmcvrr.cn/Article/details/35024.sHtML
http://www.blog.cmcvrr.cn/Article/details/819337.sHtML
http://www.blog.cmcvrr.cn/Article/details/79067.sHtML
http://www.blog.cmcvrr.cn/Article/details/147761.sHtML
http://www.blog.cmcvrr.cn/Article/details/9362.sHtML
http://www.blog.cmcvrr.cn/Article/details/2496.sHtML
http://www.blog.cmcvrr.cn/Article/details/8300648.sHtML
http://www.blog.cmcvrr.cn/Article/details/08724.sHtML
http://www.blog.cmcvrr.cn/Article/details/455416.sHtML
http://www.blog.cmcvrr.cn/Article/details/88726.sHtML
http://www.blog.cmcvrr.cn/Article/details/68328.sHtML
http://www.blog.cmcvrr.cn/Article/details/896156.sHtML
http://www.blog.cmcvrr.cn/Article/details/30402.sHtML
http://www.blog.cmcvrr.cn/Article/details/3107.sHtML
http://www.blog.cmcvrr.cn/Article/details/6818.sHtML
http://www.blog.cmcvrr.cn/Article/details/4068.sHtML
http://www.blog.cmcvrr.cn/Article/details/46264.sHtML
http://www.blog.cmcvrr.cn/Article/details/750210.sHtML
http://www.blog.cmcvrr.cn/Article/details/94978.sHtML
http://www.blog.cmcvrr.cn/Article/details/8912.sHtML
http://www.blog.cmcvrr.cn/Article/details/8969157.sHtML
http://www.blog.cmcvrr.cn/Article/details/935980.sHtML
http://www.blog.cmcvrr.cn/Article/details/6213.sHtML
http://www.blog.cmcvrr.cn/Article/details/8873.sHtML
http://www.blog.cmcvrr.cn/Article/details/6482.sHtML
http://www.blog.cmcvrr.cn/Article/details/089558.sHtML
http://www.blog.cmcvrr.cn/Article/details/125391.sHtML
http://www.blog.cmcvrr.cn/Article/details/8872672.sHtML
http://www.blog.cmcvrr.cn/Article/details/2669.sHtML
http://www.blog.cmcvrr.cn/Article/details/76909.sHtML
http://www.blog.cmcvrr.cn/Article/details/02999.sHtML
http://www.blog.cmcvrr.cn/Article/details/9309434.sHtML

运维与性能优化专题（编号 4000 - 7999）

http://www.blog.cmcvrr.cn/Article/details/3814.sHtML
http://www.blog.cmcvrr.cn/Article/details/10518.sHtML
http://www.blog.cmcvrr.cn/Article/details/09945.sHtML
http://www.blog.cmcvrr.cn/Article/details/6026629.sHtML
http://www.blog.cmcvrr.cn/Article/details/2128.sHtML
http://www.blog.cmcvrr.cn/Article/details/2970.sHtML
http://www.blog.cmcvrr.cn/Article/details/686249.sHtML
http://www.blog.cmcvrr.cn/Article/details/6183.sHtML
http://www.blog.cmcvrr.cn/Article/details/08433.sHtML
http://www.blog.cmcvrr.cn/Article/details/7655076.sHtML
http://www.blog.cmcvrr.cn/Article/details/74295.sHtML
http://www.blog.cmcvrr.cn/Article/details/9817617.sHtML
http://www.blog.cmcvrr.cn/Article/details/0551389.sHtML
http://www.blog.cmcvrr.cn/Article/details/5847208.sHtML
http://www.blog.cmcvrr.cn/Article/details/9106.sHtML
http://www.blog.cmcvrr.cn/Article/details/03743.sHtML
http://www.blog.cmcvrr.cn/Article/details/487964.sHtML
http://www.blog.cmcvrr.cn/Article/details/726313.sHtML
http://www.blog.cmcvrr.cn/Article/details/4074.sHtML
http://www.blog.cmcvrr.cn/Article/details/8832.sHtML
http://www.blog.cmcvrr.cn/Article/details/767254.sHtML
http://www.blog.cmcvrr.cn/Article/details/104713.sHtML
http://www.blog.cmcvrr.cn/Article/details/6808.sHtML
http://www.blog.cmcvrr.cn/Article/details/2106.sHtML
http://www.blog.cmcvrr.cn/Article/details/30253.sHtML
http://www.blog.cmcvrr.cn/Article/details/82888.sHtML
http://www.blog.cmcvrr.cn/Article/details/5687.sHtML
http://www.blog.cmcvrr.cn/Article/details/456445.sHtML
http://www.blog.cmcvrr.cn/Article/details/0057.sHtML
http://www.blog.cmcvrr.cn/Article/details/39963.sHtML
http://www.blog.cmcvrr.cn/Article/details/8599723.sHtML
http://www.blog.cmcvrr.cn/Article/details/66527.sHtML
http://www.blog.cmcvrr.cn/Article/details/0347034.sHtML
http://www.blog.cmcvrr.cn/Article/details/41315.sHtML
http://www.blog.cmcvrr.cn/Article/details/3090139.sHtML
http://www.blog.cmcvrr.cn/Article/details/318686.sHtML
http://www.blog.cmcvrr.cn/Article/details/67502.sHtML
http://www.blog.cmcvrr.cn/Article/details/090245.sHtML
http://www.blog.cmcvrr.cn/Article/details/16750.sHtML
http://www.blog.cmcvrr.cn/Article/details/291245.sHtML
http://www.blog.cmcvrr.cn/Article/details/1674.sHtML
http://www.blog.cmcvrr.cn/Article/details/0698736.sHtML
http://www.blog.cmcvrr.cn/Article/details/559128.sHtML
http://www.blog.cmcvrr.cn/Article/details/820570.sHtML
http://www.blog.cmcvrr.cn/Article/details/5703010.sHtML
http://www.blog.cmcvrr.cn/Article/details/209941.sHtML
http://www.blog.cmcvrr.cn/Article/details/0398002.sHtML
http://www.blog.cmcvrr.cn/Article/details/3007.sHtML
http://www.blog.cmcvrr.cn/Article/details/622583.sHtML
http://www.blog.cmcvrr.cn/Article/details/2002054.sHtML

安全与架构设计专题（编号 8000 - 11999）

http://www.blog.cmcvrr.cn/Article/details/35305.sHtML
http://www.blog.cmcvrr.cn/Article/details/2055471.sHtML
http://www.blog.cmcvrr.cn/Article/details/74152.sHtML
http://www.blog.cmcvrr.cn/Article/details/3838.sHtML
http://www.blog.cmcvrr.cn/Article/details/99738.sHtML
http://www.blog.cmcvrr.cn/Article/details/2337915.sHtML
http://www.blog.cmcvrr.cn/Article/details/145537.sHtML
http://www.blog.cmcvrr.cn/Article/details/6086117.sHtML
http://www.blog.cmcvrr.cn/Article/details/25595.sHtML
http://www.blog.cmcvrr.cn/Article/details/646320.sHtML
http://www.blog.cmcvrr.cn/Article/details/80609.sHtML
http://www.blog.cmcvrr.cn/Article/details/660543.sHtML
http://www.blog.cmcvrr.cn/Article/details/12695.sHtML
http://www.blog.cmcvrr.cn/Article/details/8138167.sHtML
http://www.blog.cmcvrr.cn/Article/details/48887.sHtML
http://www.blog.cmcvrr.cn/Article/details/3646917.sHtML
http://www.blog.cmcvrr.cn/Article/details/5943497.sHtML
http://www.blog.cmcvrr.cn/Article/details/149291.sHtML
http://www.blog.cmcvrr.cn/Article/details/53764.sHtML
http://www.blog.cmcvrr.cn/Article/details/39475.sHtML
http://www.blog.cmcvrr.cn/Article/details/89604.sHtML
http://www.blog.cmcvrr.cn/Article/details/195812.sHtML
http://www.blog.cmcvrr.cn/Article/details/9109539.sHtML
http://www.blog.cmcvrr.cn/Article/details/584120.sHtML
http://www.blog.cmcvrr.cn/Article/details/3344680.sHtML
http://www.blog.cmcvrr.cn/Article/details/577402.sHtML
http://www.blog.cmcvrr.cn/Article/details/95250.sHtML
http://www.blog.cmcvrr.cn/Article/details/782161.sHtML
http://www.blog.cmcvrr.cn/Article/details/848187.sHtML
http://www.blog.cmcvrr.cn/Article/details/97213.sHtML
http://www.blog.cmcvrr.cn/Article/details/5280.sHtML
http://www.blog.cmcvrr.cn/Article/details/53446.sHtML
http://www.blog.cmcvrr.cn/Article/details/60892.sHtML
http://www.blog.cmcvrr.cn/Article/details/75232.sHtML
http://www.blog.cmcvrr.cn/Article/details/33541.sHtML
http://www.blog.cmcvrr.cn/Article/details/395331.sHtML
http://www.blog.cmcvrr.cn/Article/details/43561.sHtML
http://www.blog.cmcvrr.cn/Article/details/7679852.sHtML
http://www.blog.cmcvrr.cn/Article/details/8941710.sHtML
http://www.blog.cmcvrr.cn/Article/details/77946.sHtML
http://www.blog.cmcvrr.cn/Article/details/6268838.sHtML
http://www.blog.cmcvrr.cn/Article/details/5263554.sHtML
http://www.blog.cmcvrr.cn/Article/details/990766.sHtML
http://www.blog.cmcvrr.cn/Article/details/6222.sHtML
http://www.blog.cmcvrr.cn/Article/details/13532.sHtML
http://www.blog.cmcvrr.cn/Article/details/612173.sHtML
http://www.blog.cmcvrr.cn/Article/details/279046.sHtML
http://www.blog.cmcvrr.cn/Article/details/15848.sHtML
http://www.blog.cmcvrr.cn/Article/details/7331.sHtML
http://www.blog.cmcvrr.cn/Article/details/980131.sHtML
http://www.blog.cmcvrr.cn/Article/details/608770.sHtML

前沿技术综合区（编号 12000 - 15999）

http://www.blog.cmcvrr.cn/Article/details/3063.sHtML
http://www.blog.cmcvrr.cn/Article/details/9273.sHtML
http://www.blog.cmcvrr.cn/Article/details/0427.sHtML
http://www.blog.cmcvrr.cn/Article/details/37147.sHtML
http://www.blog.cmcvrr.cn/Article/details/2509628.sHtML
http://www.blog.cmcvrr.cn/Article/details/49308.sHtML
http://www.blog.cmcvrr.cn/Article/details/9893780.sHtML
http://www.blog.cmcvrr.cn/Article/details/5136627.sHtML
http://www.blog.cmcvrr.cn/Article/details/369644.sHtML
http://www.blog.cmcvrr.cn/Article/details/75590.sHtML
http://www.blog.cmcvrr.cn/Article/details/7082.sHtML
http://www.blog.cmcvrr.cn/Article/details/243723.sHtML
http://www.blog.cmcvrr.cn/Article/details/598971.sHtML
http://www.blog.cmcvrr.cn/Article/details/56586.sHtML
http://www.blog.cmcvrr.cn/Article/details/09181.sHtML
http://www.blog.cmcvrr.cn/Article/details/98894.sHtML
http://www.blog.cmcvrr.cn/Article/details/7727150.sHtML
http://www.blog.cmcvrr.cn/Article/details/5582974.sHtML
http://www.blog.cmcvrr.cn/Article/details/046216.sHtML
http://www.blog.cmcvrr.cn/Article/details/08408.sHtML
http://www.blog.cmcvrr.cn/Article/details/119268.sHtML
http://www.blog.cmcvrr.cn/Article/details/554929.sHtML
http://www.blog.cmcvrr.cn/Article/details/8032287.sHtML
http://www.blog.cmcvrr.cn/Article/details/812900.sHtML
http://www.blog.cmcvrr.cn/Article/details/0964568.sHtML
http://www.blog.cmcvrr.cn/Article/details/411804.sHtML
http://www.blog.cmcvrr.cn/Article/details/4626.sHtML
http://www.blog.cmcvrr.cn/Article/details/29768.sHtML
http://www.blog.cmcvrr.cn/Article/details/816571.sHtML
http://www.blog.cmcvrr.cn/Article/details/3195.sHtML
http://www.blog.cmcvrr.cn/Article/details/429877.sHtML
http://www.blog.cmcvrr.cn/Article/details/648476.sHtML
http://www.blog.cmcvrr.cn/Article/details/3410.sHtML
http://www.blog.cmcvrr.cn/Article/details/907996.sHtML
http://www.blog.cmcvrr.cn/Article/details/406159.sHtML
http://www.blog.cmcvrr.cn/Article/details/5212.sHtML
http://www.blog.cmcvrr.cn/Article/details/6831369.sHtML
http://www.blog.cmcvrr.cn/Article/details/89472.sHtML
http://www.blog.cmcvrr.cn/Article/details/87503.sHtML
http://www.blog.cmcvrr.cn/Article/details/9390.sHtML
http://www.blog.cmcvrr.cn/Article/details/0863000.sHtML
http://www.blog.cmcvrr.cn/Article/details/04906.sHtML
http://www.blog.cmcvrr.cn/Article/details/4641.sHtML
http://www.blog.cmcvrr.cn/Article/details/94754.sHtML
http://www.blog.cmcvrr.cn/Article/details/5348807.sHtML
http://www.blog.cmcvrr.cn/Article/details/62460.sHtML
http://www.blog.cmcvrr.cn/Article/details/4709.sHtML
http://www.blog.cmcvrr.cn/Article/details/79339.sHtML
http://www.blog.cmcvrr.cn/Article/details/79559.sHtML
http://www.blog.cmcvrr.cn/Article/details/20459.sHtML
http://www.blog.cmcvrr.cn/Article/details/8116592.sHtML
http://www.blog.cmcvrr.cn/Article/details/63418.sHtML
http://www.blog.cmcvrr.cn/Article/details/089196.sHtML
http://www.blog.cmcvrr.cn/Article/details/3288.sHtML
http://www.blog.cmcvrr.cn/Article/details/0222.sHtML
http://www.blog.cmcvrr.cn/Article/details/3241839.sHtML
http://www.blog.cmcvrr.cn/Article/details/0670.sHtML
http://www.blog.cmcvrr.cn/Article/details/26807.sHtML
http://www.blog.cmcvrr.cn/Article/details/393219.sHtML
http://www.blog.cmcvrr.cn/Article/details/3740.sHtML
http://www.blog.cmcvrr.cn/Article/details/018121.sHtML
http://www.blog.cmcvrr.cn/Article/details/291030.sHtML
http://www.blog.cmcvrr.cn/Article/details/0783.sHtML
http://www.blog.cmcvrr.cn/Article/details/5600.sHtML
http://www.blog.cmcvrr.cn/Article/details/58035.sHtML
http://www.blog.cmcvrr.cn/Article/details/115627.sHtML
http://www.blog.cmcvrr.cn/Article/details/7326.sHtML
http://www.blog.cmcvrr.cn/Article/details/92707.sHtML
http://www.blog.cmcvrr.cn/Article/details/5186.sHtML
http://www.blog.cmcvrr.cn/Article/details/3632485.sHtML
http://www.blog.cmcvrr.cn/Article/details/73493.sHtML
http://www.blog.cmcvrr.cn/Article/details/2902.sHtML
http://www.blog.cmcvrr.cn/Article/details/9310520.sHtML
http://www.blog.cmcvrr.cn/Article/details/04508.sHtML
http://www.blog.cmcvrr.cn/Article/details/4906.sHtML
http://www.blog.cmcvrr.cn/Article/details/0644246.sHtML
http://www.blog.cmcvrr.cn/Article/details/48247.sHtML
http://www.blog.cmcvrr.cn/Article/details/3531.sHtML
http://www.blog.cmcvrr.cn/Article/details/6750721.sHtML
http://www.blog.cmcvrr.cn/Article/details/575761.sHtML
http://www.blog.cmcvrr.cn/Article/details/4248907.sHtML
http://www.blog.cmcvrr.cn/Article/details/968647.sHtML
http://www.blog.cmcvrr.cn/Article/details/61899.sHtML
http://www.blog.cmcvrr.cn/Article/details/772756.sHtML
http://www.blog.cmcvrr.cn/Article/details/4983.sHtML
http://www.blog.cmcvrr.cn/Article/details/1279879.sHtML
http://www.blog.cmcvrr.cn/Article/details/0709870.sHtML
http://www.blog.cmcvrr.cn/Article/details/8690967.sHtML
http://www.blog.cmcvrr.cn/Article/details/4068222.sHtML
http://www.blog.cmcvrr.cn/Article/details/598709.sHtML
http://www.blog.cmcvrr.cn/Article/details/148993.sHtML
http://www.blog.cmcvrr.cn/Article/details/591747.sHtML
http://www.blog.cmcvrr.cn/Article/details/776722.sHtML
http://www.blog.cmcvrr.cn/Article/details/40359.sHtML
http://www.blog.cmcvrr.cn/Article/details/5304.sHtML
http://www.blog.cmcvrr.cn/Article/details/89330.sHtML
http://www.blog.cmcvrr.cn/Article/details/3463769.sHtML
http://www.blog.cmcvrr.cn/Article/details/55881.sHtML

## 项目结构

```
technical-index/
├── README.md                     # 项目入口文档，包含概述与快速导航
├── RESOURCES.md                  # 完整资源列表，按分类展示所有文章链接
├── LICENSE                       # MIT 许可证文件
├── .gitignore                    # Git 忽略规则，排除 node_modules 与构建产物
├── package.json                  # Node.js 项目配置，定义依赖与脚本命令
├── package-lock.json             # 依赖版本锁定文件
├── src/                          # 源代码目录
│   ├── index.js                  # 主构建脚本，负责生成索引页面
│   ├── parser.js                 # URL 解析与编号提取模块
│   ├── classifier.js             # 文章分类逻辑，基于编号区间与关键词规则
│   ├── validator.js              # 链接格式校验与去重工具
│   └── template/                 # 输出模板目录
│       ├── header.tpl            # 页面头部 HTML 模板
│       ├── footer.tpl            # 页面底部 HTML 模板
│       └── list-item.tpl         # 单条资源链接的渲染模板
├── config/                       # 配置文件目录
│   ├── categories.json           # 分类规则定义，包含编号区间与标签映射
│   └── aliases.json              # 文章编号与别名的映射表（可选）
├── data/                         # 数据目录
│   └── ids.json                  # 当前收录的所有文章编号列表，由脚本自动更新
├── dist/                         # 构建输出目录（自动生成，不纳入版本控制）
│   ├── index.html                # 生成的完整索引页面
│   └── resources.html            # 独立的资源列表页面
├── docs/                         # 详细文档目录
│   ├── quick-start.md            # 快速入门指南
│   ├── maintenance.md            # 资源维护操作手册
│   ├── categorization.md         # 分类规则详细说明
│   └── build-tool.md             # 构建工具链技术文档
└── tests/                        # 单元测试目录
    ├── parser.test.js            # URL 解析模块测试
    ├── classifier.test.js        # 分类逻辑测试
    └── validator.test.js         # 链接校验测试
```

## 贡献指南

1.  **复刻项目仓库**：在 GitHub 上点击 Fork 按钮，将本仓库复制至您的个人账号下，随后克隆至本地进行修改。

2.  **新增文章编号**：在 `data/ids.json` 文件中追加新的文章数字 ID，请确保 ID 为纯数字且不重复。若需调整分类，请同步修改 `config/categories.json` 中的区间定义。

3.  **本地验证与测试**：运行 `npm run test` 执行单元测试套件，确保新增数据未破坏解析与分类逻辑。运行 `npm run build` 生成最新静态页面，检查输出是否符合预期。

4.  **提交变更并推送**：使用清晰且语义化的提交信息（如 `feat: add article id 55881 to security category`），推送至您的复刻仓库。

5.  **发起拉取请求**：在本仓库的 Pull Requests 页面提交 PR，描述变更内容与动机。项目维护者将在两个工作日内进行审核与合并。

## 常见问题

**问：这些 URL 指向的内容是否由本项目维护？**

答：否。本项目仅提供文章编号索引与链接导航，所有 URL 均指向 `blog.cmcvrr.cn` 域名下的原始文章页面。项目本身不存储、复制或修改任何文章正文内容，也不对原始内容的可用性、准确性或时效性负责。若某条链接无法访问，请联系原始站点维护方。

**问：如何批量验证所有链接是否仍然有效？**

答：项目提供了可选的链接校验脚本，位于 `src/validator.js`。您可执行 `npm run validate` 命令启动批量 HEAD 请求检查，脚本会输出状态码非 200 的链接列表。请注意，频繁发送大量请求可能被原始站点限流，建议在低峰时段运行并设置合理间隔。

**问：我发现某篇文章的分类不准确，应该如何修正？**

答：您可按照贡献指南提交修改。具体操作是调整 `config/categories.json` 中对应编号区间的分类标签，或者若分类规则基于关键词，可优化 `src/classifier.js` 中的匹配逻辑。修改完成后请运行测试并提交 PR。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 16:28:04
