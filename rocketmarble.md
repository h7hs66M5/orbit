# Navigator Index

Navigator Index 是一个面向技术研究者与开发者的结构化外链与知识索引系统。该项目不存储任何原始内容，而是通过人工筛选与分类聚合的方式，将分散于互联网各处的优质技术文章、教程、案例分析与参考文档进行统一编目与持久化归档。

项目定位为技术阅读与研究的辅助导航工具，主要服务于以下三类用户：

- 需要系统化查阅特定技术领域深度文章的中高级开发者；
- 在项目调研或技术选型阶段需要大量参考案例的架构师与技术负责人；
- 希望建立个人知识检索体系但缺乏维护索引能力的效率型学习者。

Navigator Index 不依赖动态后端服务，所有索引数据以纯文本形式存储于仓库中，支持完整的版本追溯与离线浏览，能够与各类静态站点生成器无缝集成。

## 功能概览

**多级分类索引体系** - 按照技术领域、应用场景与阅读难度对收录链接进行三级分类，每个条目附带简要的标签系统，便于快速定位。

**原始链接永久归档** - 每条记录均保留发布者提供的原始 URL 与文章标题，确保引用路径的完整可追溯性，不进行任何形式的短链转换或重定向封装。

**批次化增量更新机制** - 采用批次（Batch）为单位进行资源导入，每个批次包含 200 至 300 条链接，并附带导入时间戳与审核标记，保证数据更新的可审计性。

**纯文本可移植数据结构** - 所有索引条目存储于 YAML 与 Markdown 混合格式的文件中，无需数据库环境即可完整运行，支持跨平台同步与版本管理。

**多维度检索与过滤支持** - 提供按文章编号、关键字匹配、分类路径、时间范围四种查询模式，满足不同精度的检索需求。

**静态站点生成友好输出** - 索引数据可一键导出为 HTML 目录页面或 JSON 结构化数据，便于集成到现有文档站点或个人知识库系统中。

**人工审核标记与质量评级** - 每个链接均附带可用性状态（有效/失效/需复查）与内容质量评分（基础/进阶/深度），帮助用户甄别阅读优先级。

**自动生成统计摘要** - 按分类、状态、批次维度自动生成资源分布统计报告，以 Markdown 表格形式呈现于项目根目录。

## 应用场景

**技术调研阶段的全网资料聚合** - 当开发团队需要评估某一技术栈（如嵌入式系统、WebAssembly 或分布式存储）的成熟度时，可借助 Navigator Index 快速获取该领域下数百篇经过初筛的参考文章，大幅减少搜索引擎的重复劳动。

**个人开发者建立每周阅读清单** - 用户可按批次或分类标签导出链接列表，配合 cron 任务或 GitHub Actions 生成每周阅读推荐文档，形成规律性的技术输入习惯。

**离线知识库的种子数据源** - 在无网络或内网受限的环境中，用户可将 Navigator Index 作为爬虫种子列表，预先批量获取对应的文章内容并存入本地归档系统，实现可控的知识缓存。

**开源文档站点的侧边栏补充** - 将 Navigator Index 生成的 JSON 目录挂载至 VuePress、Docusaurus 或 MkDocs 等静态站点的侧边栏，作为外部参考文献的快捷入口，丰富文档生态。

## 快速开始

以下命令演示了从仓库克隆到本地运行索引检查的完整流程。

```bash
# 克隆仓库至本地
git clone https://github.com/your-org/navigator-index.git
cd navigator-index

# 安装依赖（仅需 Python 3.9+ 及标准库，推荐使用虚拟环境）
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install pyyaml markdown-link-extractor

# 执行索引完整性检查与统计报告生成
python scripts/validate_index.py --batch 278
python scripts/generate_summary.py --output ./SUMMARY.md
```

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.9 或更高 | 核心脚本运行环境，用于索引校验与统计生成 |
| Git | 2.25 或更高 | 用于克隆仓库与提交更新日志 |
| PyYAML | 6.0 或更高 | 解析索引条目元数据文件 |
| markdown-link-extractor | 1.0 或更高 | 用于提取文档中的原始链接进行可用性检查 |
| 操作系统 | Linux / macOS / Windows WSL2 | 脚本在主流 POSIX 环境及 Windows Git Bash 中测试通过 |
| 磁盘空间 | 最小 50 MB | 仓库体积约为 12 MB，索引生成临时文件需额外 30 MB |

## 文档导航

| 层面 | 目录 / 文档 | 回答的问题 |
|---|---|---|
| 用户入门 | docs/quick-start.md | 如何首次使用 Navigator Index、如何导出个人阅读清单 |
| 索引维护 | docs/maintenance-guide.md | 如何新增批次、如何更新链接状态、如何处理失效 URL |
| 数据格式 | docs/data-schema.md | 索引文件的字段定义、分类规则、YAML 模板样例 |
| 自动化流程 | docs/automation.md | 如何配置 GitHub Actions 进行定期链接检查与统计更新 |

## 资源列表

### 第 278 批次索引条目（共 250 个链接）

以下列表按照原始导入顺序排列，所有 URL 均保持原样输出，未做任何格式化修改。

http://www.blog.puhvjy.cn/Article/details/682247.sHtML
http://www.blog.puhvjy.cn/Article/details/228159.sHtML
http://www.blog.puhvjy.cn/Article/details/8326.sHtML
http://www.blog.puhvjy.cn/Article/details/8682.sHtML
http://www.blog.puhvjy.cn/Article/details/476733.sHtML
http://www.blog.puhvjy.cn/Article/details/1855.sHtML
http://www.blog.puhvjy.cn/Article/details/868662.sHtML
http://www.blog.puhvjy.cn/Article/details/4305639.sHtML
http://www.blog.puhvjy.cn/Article/details/0881.sHtML
http://www.blog.puhvjy.cn/Article/details/6261713.sHtML
http://www.blog.puhvjy.cn/Article/details/41964.sHtML
http://www.blog.puhvjy.cn/Article/details/17356.sHtML
http://www.blog.puhvjy.cn/Article/details/740380.sHtML
http://www.blog.puhvjy.cn/Article/details/81725.sHtML
http://www.blog.puhvjy.cn/Article/details/2829.sHtML
http://www.blog.puhvjy.cn/Article/details/28806.sHtML
http://www.blog.puhvjy.cn/Article/details/852374.sHtML
http://www.blog.puhvjy.cn/Article/details/566278.sHtML
http://www.blog.puhvjy.cn/Article/details/114816.sHtML
http://www.blog.puhvjy.cn/Article/details/1245078.sHtML
http://www.blog.puhvjy.cn/Article/details/4607.sHtML
http://www.blog.puhvjy.cn/Article/details/8284177.sHtML
http://www.blog.puhvjy.cn/Article/details/0983.sHtML
http://www.blog.puhvjy.cn/Article/details/8869738.sHtML
http://www.blog.puhvjy.cn/Article/details/3878852.sHtML
http://www.blog.puhvjy.cn/Article/details/3930722.sHtML
http://www.blog.puhvjy.cn/Article/details/192446.sHtML
http://www.blog.puhvjy.cn/Article/details/2086903.sHtML
http://www.blog.puhvjy.cn/Article/details/880121.sHtML
http://www.blog.puhvjy.cn/Article/details/7675.sHtML
http://www.blog.puhvjy.cn/Article/details/1088.sHtML
http://www.blog.puhvjy.cn/Article/details/7910.sHtML
http://www.blog.puhvjy.cn/Article/details/13486.sHtML
http://www.blog.puhvjy.cn/Article/details/352083.sHtML
http://www.blog.puhvjy.cn/Article/details/48317.sHtML
http://www.blog.puhvjy.cn/Article/details/298853.sHtML
http://www.blog.puhvjy.cn/Article/details/0266531.sHtML
http://www.blog.puhvjy.cn/Article/details/945158.sHtML
http://www.blog.puhvjy.cn/Article/details/7549192.sHtML
http://www.blog.puhvjy.cn/Article/details/01363.sHtML
http://www.blog.puhvjy.cn/Article/details/73682.sHtML
http://www.blog.puhvjy.cn/Article/details/099029.sHtML
http://www.blog.puhvjy.cn/Article/details/808920.sHtML
http://www.blog.puhvjy.cn/Article/details/698333.sHtML
http://www.blog.puhvjy.cn/Article/details/70405.sHtML
http://www.blog.puhvjy.cn/Article/details/194341.sHtML
http://www.blog.puhvjy.cn/Article/details/420731.sHtML
http://www.blog.puhvjy.cn/Article/details/7362063.sHtML
http://www.blog.puhvjy.cn/Article/details/6694178.sHtML
http://www.blog.puhvjy.cn/Article/details/323999.sHtML
http://www.blog.puhvjy.cn/Article/details/83512.sHtML
http://www.blog.puhvjy.cn/Article/details/169974.sHtML
http://www.blog.puhvjy.cn/Article/details/409051.sHtML
http://www.blog.puhvjy.cn/Article/details/358157.sHtML
http://www.blog.puhvjy.cn/Article/details/280682.sHtML
http://www.blog.puhvjy.cn/Article/details/066920.sHtML
http://www.blog.puhvjy.cn/Article/details/35077.sHtML
http://www.blog.puhvjy.cn/Article/details/41602.sHtML
http://www.blog.puhvjy.cn/Article/details/0613510.sHtML
http://www.blog.puhvjy.cn/Article/details/427825.sHtML
http://www.blog.puhvjy.cn/Article/details/799196.sHtML
http://www.blog.puhvjy.cn/Article/details/42510.sHtML
http://www.blog.puhvjy.cn/Article/details/0404.sHtML
http://www.blog.puhvjy.cn/Article/details/59300.sHtML
http://www.blog.puhvjy.cn/Article/details/9758.sHtML
http://www.blog.puhvjy.cn/Article/details/3325435.sHtML
http://www.blog.puhvjy.cn/Article/details/537384.sHtML
http://www.blog.puhvjy.cn/Article/details/21481.sHtML
http://www.blog.puhvjy.cn/Article/details/5259816.sHtML
http://www.blog.puhvjy.cn/Article/details/8113.sHtML
http://www.blog.puhvjy.cn/Article/details/3346.sHtML
http://www.blog.puhvjy.cn/Article/details/8816647.sHtML
http://www.blog.puhvjy.cn/Article/details/0038036.sHtML
http://www.blog.puhvjy.cn/Article/details/114209.sHtML
http://www.blog.puhvjy.cn/Article/details/8284269.sHtML
http://www.blog.puhvjy.cn/Article/details/7078.sHtML
http://www.blog.puhvjy.cn/Article/details/9050533.sHtML
http://www.blog.puhvjy.cn/Article/details/0737729.sHtML
http://www.blog.puhvjy.cn/Article/details/1984546.sHtML
http://www.blog.puhvjy.cn/Article/details/0256.sHtML
http://www.blog.puhvjy.cn/Article/details/69459.sHtML
http://www.blog.puhvjy.cn/Article/details/1582.sHtML
http://www.blog.puhvjy.cn/Article/details/41370.sHtML
http://www.blog.puhvjy.cn/Article/details/96734.sHtML
http://www.blog.puhvjy.cn/Article/details/774355.sHtML
http://www.blog.puhvjy.cn/Article/details/2592.sHtML
http://www.blog.puhvjy.cn/Article/details/958917.sHtML
http://www.blog.puhvjy.cn/Article/details/416547.sHtML
http://www.blog.puhvjy.cn/Article/details/733915.sHtML
http://www.blog.puhvjy.cn/Article/details/6689.sHtML
http://www.blog.puhvjy.cn/Article/details/9346830.sHtML
http://www.blog.puhvjy.cn/Article/details/96094.sHtML
http://www.blog.puhvjy.cn/Article/details/9155.sHtML
http://www.blog.puhvjy.cn/Article/details/4297217.sHtML
http://www.blog.puhvjy.cn/Article/details/4264129.sHtML
http://www.blog.puhvjy.cn/Article/details/0633379.sHtML
http://www.blog.puhvjy.cn/Article/details/248367.sHtML
http://www.blog.puhvjy.cn/Article/details/078207.sHtML
http://www.blog.puhvjy.cn/Article/details/59583.sHtML
http://www.blog.puhvjy.cn/Article/details/232618.sHtML
http://www.blog.puhvjy.cn/Article/details/19248.sHtML
http://www.blog.puhvjy.cn/Article/details/30057.sHtML
http://www.blog.puhvjy.cn/Article/details/6665.sHtML
http://www.blog.puhvjy.cn/Article/details/46961.sHtML
http://www.blog.puhvjy.cn/Article/details/785155.sHtML
http://www.blog.puhvjy.cn/Article/details/583629.sHtML
http://www.blog.puhvjy.cn/Article/details/0140.sHtML
http://www.blog.puhvjy.cn/Article/details/776893.sHtML
http://www.blog.puhvjy.cn/Article/details/1272.sHtML
http://www.blog.puhvjy.cn/Article/details/48894.sHtML
http://www.blog.puhvjy.cn/Article/details/95145.sHtML
http://www.blog.puhvjy.cn/Article/details/7332986.sHtML
http://www.blog.puhvjy.cn/Article/details/70846.sHtML
http://www.blog.puhvjy.cn/Article/details/4384.sHtML
http://www.blog.puhvjy.cn/Article/details/64735.sHtML
http://www.blog.puhvjy.cn/Article/details/74013.sHtML
http://www.blog.puhvjy.cn/Article/details/4208.sHtML
http://www.blog.puhvjy.cn/Article/details/8686.sHtML
http://www.blog.puhvjy.cn/Article/details/783116.sHtML
http://www.blog.puhvjy.cn/Article/details/58770.sHtML
http://www.blog.puhvjy.cn/Article/details/07004.sHtML
http://www.blog.puhvjy.cn/Article/details/7916029.sHtML
http://www.blog.puhvjy.cn/Article/details/771156.sHtML
http://www.blog.puhvjy.cn/Article/details/4746.sHtML
http://www.blog.puhvjy.cn/Article/details/6495001.sHtML
http://www.blog.puhvjy.cn/Article/details/3475.sHtML
http://www.blog.puhvjy.cn/Article/details/16831.sHtML
http://www.blog.puhvjy.cn/Article/details/445841.sHtML
http://www.blog.puhvjy.cn/Article/details/654497.sHtML
http://www.blog.puhvjy.cn/Article/details/3132.sHtML
http://www.blog.puhvjy.cn/Article/details/8899933.sHtML
http://www.blog.puhvjy.cn/Article/details/260900.sHtML
http://www.blog.puhvjy.cn/Article/details/807756.sHtML
http://www.blog.puhvjy.cn/Article/details/50668.sHtML
http://www.blog.puhvjy.cn/Article/details/9512.sHtML
http://www.blog.puhvjy.cn/Article/details/8072.sHtML
http://www.blog.puhvjy.cn/Article/details/4231.sHtML
http://www.blog.puhvjy.cn/Article/details/33907.sHtML
http://www.blog.puhvjy.cn/Article/details/93380.sHtML
http://www.blog.puhvjy.cn/Article/details/38888.sHtML
http://www.blog.puhvjy.cn/Article/details/420970.sHtML
http://www.blog.puhvjy.cn/Article/details/23495.sHtML
http://www.blog.puhvjy.cn/Article/details/478688.sHtML
http://www.blog.puhvjy.cn/Article/details/9668339.sHtML
http://www.blog.puhvjy.cn/Article/details/5685.sHtML
http://www.blog.puhvjy.cn/Article/details/64738.sHtML
http://www.blog.puhvjy.cn/Article/details/637444.sHtML
http://www.blog.puhvjy.cn/Article/details/771892.sHtML
http://www.blog.puhvjy.cn/Article/details/8342842.sHtML
http://www.blog.puhvjy.cn/Article/details/6384.sHtML
http://www.blog.puhvjy.cn/Article/details/9608.sHtML
http://www.blog.puhvjy.cn/Article/details/7523097.sHtML
http://www.blog.puhvjy.cn/Article/details/13127.sHtML
http://www.blog.puhvjy.cn/Article/details/8668855.sHtML
http://www.blog.puhvjy.cn/Article/details/81115.sHtML
http://www.blog.puhvjy.cn/Article/details/545090.sHtML
http://www.blog.puhvjy.cn/Article/details/445179.sHtML
http://www.blog.puhvjy.cn/Article/details/74812.sHtML
http://www.blog.puhvjy.cn/Article/details/995065.sHtML
http://www.blog.puhvjy.cn/Article/details/1989.sHtML
http://www.blog.puhvjy.cn/Article/details/8516318.sHtML
http://www.blog.puhvjy.cn/Article/details/2367.sHtML
http://www.blog.puhvjy.cn/Article/details/826288.sHtML
http://www.blog.puhvjy.cn/Article/details/52678.sHtML
http://www.blog.puhvjy.cn/Article/details/5461.sHtML
http://www.blog.puhvjy.cn/Article/details/271690.sHtML
http://www.blog.puhvjy.cn/Article/details/9465538.sHtML
http://www.blog.puhvjy.cn/Article/details/172693.sHtML
http://www.blog.puhvjy.cn/Article/details/81961.sHtML
http://www.blog.puhvjy.cn/Article/details/357769.sHtML
http://www.blog.puhvjy.cn/Article/details/5107.sHtML
http://www.blog.puhvjy.cn/Article/details/9961970.sHtML
http://www.blog.puhvjy.cn/Article/details/8532.sHtML
http://www.blog.puhvjy.cn/Article/details/72445.sHtML
http://www.blog.puhvjy.cn/Article/details/7821964.sHtML
http://www.blog.puhvjy.cn/Article/details/400685.sHtML
http://www.blog.puhvjy.cn/Article/details/430509.sHtML
http://www.blog.puhvjy.cn/Article/details/0822431.sHtML
http://www.blog.puhvjy.cn/Article/details/31339.sHtML
http://www.blog.puhvjy.cn/Article/details/2893452.sHtML
http://www.blog.puhvjy.cn/Article/details/3785.sHtML
http://www.blog.puhvjy.cn/Article/details/0053.sHtML
http://www.blog.puhvjy.cn/Article/details/4066795.sHtML
http://www.blog.puhvjy.cn/Article/details/7324.sHtML
http://www.blog.puhvjy.cn/Article/details/1734541.sHtML
http://www.blog.puhvjy.cn/Article/details/0077352.sHtML
http://www.blog.puhvjy.cn/Article/details/3543886.sHtML
http://www.blog.puhvjy.cn/Article/details/4034.sHtML
http://www.blog.puhvjy.cn/Article/details/833327.sHtML
http://www.blog.puhvjy.cn/Article/details/73945.sHtML
http://www.blog.puhvjy.cn/Article/details/99586.sHtML
http://www.blog.puhvjy.cn/Article/details/6824.sHtML
http://www.blog.puhvjy.cn/Article/details/09945.sHtML
http://www.blog.puhvjy.cn/Article/details/4236073.sHtML
http://www.blog.puhvjy.cn/Article/details/7534.sHtML
http://www.blog.puhvjy.cn/Article/details/8843.sHtML
http://www.blog.puhvjy.cn/Article/details/636005.sHtML
http://www.blog.puhvjy.cn/Article/details/28518.sHtML
http://www.blog.puhvjy.cn/Article/details/4666978.sHtML
http://www.blog.puhvjy.cn/Article/details/35623.sHtML
http://www.blog.puhvjy.cn/Article/details/59115.sHtML
http://www.blog.puhvjy.cn/Article/details/521751.sHtML
http://www.blog.puhvjy.cn/Article/details/731686.sHtML
http://www.blog.puhvjy.cn/Article/details/5098191.sHtML
http://www.blog.puhvjy.cn/Article/details/7669111.sHtML
http://www.blog.puhvjy.cn/Article/details/5165303.sHtML
http://www.blog.puhvjy.cn/Article/details/724405.sHtML
http://www.blog.puhvjy.cn/Article/details/1203872.sHtML
http://www.blog.puhvjy.cn/Article/details/70202.sHtML
http://www.blog.puhvjy.cn/Article/details/851584.sHtML
http://www.blog.puhvjy.cn/Article/details/338497.sHtML
http://www.blog.puhvjy.cn/Article/details/6388304.sHtML
http://www.blog.puhvjy.cn/Article/details/0768.sHtML
http://www.blog.puhvjy.cn/Article/details/36531.sHtML
http://www.blog.puhvjy.cn/Article/details/455725.sHtML
http://www.blog.puhvjy.cn/Article/details/3521.sHtML
http://www.blog.puhvjy.cn/Article/details/5270493.sHtML
http://www.blog.puhvjy.cn/Article/details/0004.sHtML
http://www.blog.puhvjy.cn/Article/details/83933.sHtML
http://www.blog.puhvjy.cn/Article/details/1249084.sHtML
http://www.blog.puhvjy.cn/Article/details/90047.sHtML
http://www.blog.puhvjy.cn/Article/details/694958.sHtML
http://www.blog.puhvjy.cn/Article/details/5775.sHtML
http://www.blog.puhvjy.cn/Article/details/00160.sHtML
http://www.blog.puhvjy.cn/Article/details/05609.sHtML
http://www.blog.puhvjy.cn/Article/details/33598.sHtML
http://www.blog.puhvjy.cn/Article/details/953804.sHtML
http://www.blog.puhvjy.cn/Article/details/642465.sHtML
http://www.blog.puhvjy.cn/Article/details/216678.sHtML
http://www.blog.puhvjy.cn/Article/details/5463.sHtML
http://www.blog.puhvjy.cn/Article/details/767323.sHtML
http://www.blog.puhvjy.cn/Article/details/516045.sHtML
http://www.blog.puhvjy.cn/Article/details/7494688.sHtML
http://www.blog.puhvjy.cn/Article/details/5026625.sHtML
http://www.blog.puhvjy.cn/Article/details/03132.sHtML
http://www.blog.puhvjy.cn/Article/details/4897.sHtML
http://www.blog.puhvjy.cn/Article/details/968882.sHtML
http://www.blog.puhvjy.cn/Article/details/73903.sHtML
http://www.blog.puhvjy.cn/Article/details/0006.sHtML
http://www.blog.puhvjy.cn/Article/details/7448819.sHtML
http://www.blog.puhvjy.cn/Article/details/9368.sHtML
http://www.blog.puhvjy.cn/Article/details/2428645.sHtML
http://www.blog.puhvjy.cn/Article/details/362100.sHtML
http://www.blog.puhvjy.cn/Article/details/4886540.sHtML
http://www.blog.puhvjy.cn/Article/details/0868371.sHtML
http://www.blog.puhvjy.cn/Article/details/3324.sHtML
http://www.blog.puhvjy.cn/Article/details/7674.sHtML
http://www.blog.puhvjy.cn/Article/details/6625934.sHtML
http://www.blog.puhvjy.cn/Article/details/56444.sHtML
http://www.blog.puhvjy.cn/Article/details/4610810.sHtML

## 项目结构

```
navigator-index/
├── README.md                       # 项目概述与快速入口
├── SUMMARY.md                      # 自动生成的统计摘要（含批次分布、分类统计）
├── LICENSE                         # MIT 许可文件
├── .github/
│   └── workflows/
│       └── link-check.yml          # GitHub Actions 定时链接可用性检查
├── scripts/                        # 可执行工具脚本目录
│   ├── validate_index.py           # 校验索引文件格式与链接完整性
│   ├── generate_summary.py         # 根据索引数据生成统计摘要 Markdown
│   └── export_json.py              # 将索引导出为 JSON 供第三方使用
├── data/                           # 核心索引数据存储目录
│   ├── batches/                    # 按批次存放原始链接列表
│   │   ├── batch_278.yaml          # 第 278 批次元数据（含导入时间、审核状态）
│   │   ├── batch_279.yaml          # 第 279 批次（占位）
│   │   └── batch_280.yaml          # 第 280 批次（占位）
│   ├── categories/                 # 分类映射定义文件
│   │   ├── system.md               # 操作系统与底层技术分类
│   │   ├── network.md              # 网络协议与通信分类
│   │   └── algorithm.md            # 算法与数据结构分类
│   └── status/                     # 链接可用性状态记录（自动更新）
│       ├── valid.list              # 当前有效的链接编号列表
│       └── expired.list            # 已失效或需复查的链接编号列表
├── docs/                           # 用户文档目录
│   ├── quick-start.md              # 快速开始指南
│   ├── maintenance-guide.md        # 索引维护操作手册
│   ├── data-schema.md              # 数据格式规范与字段说明
│   └── automation.md               # CI/CD 自动化配置说明
└── tests/                          # 单元测试与集成测试脚本
    ├── test_validator.py           # 校验器功能测试
    └── test_exporter.py            # 导出器功能测试
```

## 贡献指南

**第一步：阅读数据格式规范**  
在新增或修改索引条目之前，请完整阅读 docs/data-schema.md 文档，了解 YAML 文件中每个字段的含义、合法取值以及分类标签的使用约定。

**第二步：创建新的批次文件**  
如果拟新增的链接属于新批次，请在 data/batches/ 目录下创建名为 batch_编号.yaml 的文件，并按照模板填写导入日期、审核人及链接列表。若属于已有批次，则直接编辑对应文件。

**第三步：运行本地校验脚本**  
提交前必须执行 scripts/validate_index.py 脚本，确保新增或修改的数据格式正确、无重复链接、且文章编号与 URL 一一对应。校验失败时请根据错误提示修正数据。

**第四步：更新统计摘要**  
执行 scripts/generate_summary.py 重新生成 SUMMARY.md 文件，使项目根目录的统计信息与最新数据保持同步。该步骤确保其他用户能够通过摘要快速了解资源整体情况。

**第五步：提交拉取请求**  
将变更内容以分支形式提交至仓库，并在拉取请求中注明本次操作的批次编号、变更类型（新增/更新/删除）以及自检结果。请求合并前需要至少一名维护者进行复核。

## 常见问题

**Q：为什么部分链接显示为失效状态？**  
A：由于外部站点可能进行结构调整或内容迁移，部分 URL 会随时间失效。项目通过定期运行 .github/workflows/link-check.yml 中的自动化任务对全部链接进行可用性检测，并将结果记录于 data/status/expired.list 中。用户可参考该列表决定是否查找替代来源或向维护者报告新的失效链接。

**Q：如何快速查找特定主题的相关文章？**  
A：推荐使用 grep 结合正则表达式对 data/batches/ 目录下的 YAML 文件进行关键字检索。例如，搜索包含 "kernel" 的所有条目可使用命令：`grep -i "kernel" data/batches/*.yaml`。此外，导出为 JSON 后也可通过 jq 工具进行更复杂的过滤查询。

**Q：我能否将该项目用于商业产品中的参考文献管理？**  
A：可以。Navigator Index 本身采用 MIT 许可证授权，您可以将索引数据与脚本集成到商业或非商业项目中。但请注意，索引中收录的原始文章版权归各自作者所有，使用时应遵循原始内容发布者的授权条款。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 16:29:58
