# Navigator Core

Navigator Core 是一个面向技术调研与文档归档场景的轻量级外链资源导航系统。该项目定位于技术团队、独立开发者与文档维护者，用于集中管理分散在多个来源的参考链接、技术博客与操作手册，并提供结构化的浏览与检索入口。

项目本身不依赖复杂的前端框架，核心输出为静态 Markdown 目录与分类索引，适合集成到现有的文档生成管道或 CI 流程中。通过统一的条目模板与标签体系，Navigator Core 帮助用户将零散的书签收藏转化为可维护的知识资产，降低技术决策中的信息回溯成本。

## 功能概览

**分层分类索引**：支持多级目录与标签双维度组织，每个资源条目可归属至多个分类节点，便于从不同视角定位目标内容。

**原始链接直出**：所有外链在生成过程中保持用户输入的原始格式，不添加协议补全、域名规范化或追踪参数，确保链接行为与源站一致。

**批量条目管理**：支持通过 CSV 或 YAML 格式批量导入资源记录，包含标题、描述、标签、优先级与状态字段，适合处理大批量历史书签数据。

**静态站点生成适配**：输出结构兼容 VuePress、Hugo 与 MkDocs 的主题模板，可直接挂载到现有文档站点中作为独立章节。

**链接可用性检查**：集成可选的 HTTP 状态探测模块，在构建阶段输出失效链接报告，帮助维护者及时清理或更新已迁移的内容。

**自定义元数据扩展**：每个条目允许附加键值对形式的自定义属性，例如适用版本、维护人、更新周期或关联需求编号，满足企业级知识库的定制需求。

## 应用场景

技术团队内部知识库维护。团队在项目迭代过程中积累大量外部参考链接，包括依赖库文档、架构方案博客与故障排查记录。Navigator Core 提供统一的条目模板与变更追踪，使新人能够快速了解技术选型的依据与上下文。

开源项目文档站的外链整合。开源项目的 README 或用户指南中常包含多个外部资源引用。使用 Navigator Core 可以将这些引用集中管理，避免在多个文档页面中重复维护同一链接，同时便于版本升级时批量更新。

个人技术博客的参考链接附录。技术作者在撰写文章时引用大量外部资料。Navigator Core 允许作者为每篇文章生成独立的参考列表，并按发布日期或相关性排序，提升文章的可信度与可追溯性。

企业合规审计中的来源记录。在金融、医疗等合规要求严格的行业中，技术实施需要留存决策依据。Navigator Core 的元数据扩展能力支持记录审批人、生效日期与政策版本，满足内部审计对来源可追溯的要求。

## 快速开始

以下步骤帮助你在本地环境完成 Navigator Core 的克隆、安装与初次运行。请确保系统已安装 Git 与 Node.js 18 及以上版本。

```bash
# 克隆项目仓库
git clone https://github.com/example/navigator-core.git

# 进入项目目录
cd navigator-core

# 安装依赖
npm install

# 执行构建，生成静态目录索引
npm run build

# 启动本地预览服务（默认端口 8080）
npm run serve
```

执行完毕后，打开浏览器访问 localhost:8080 即可查看生成的导航页面。默认数据来源于 `data/sources.yaml`，你可以直接编辑该文件添加或修改资源条目。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Node.js | 18.x 或 20.x LTS | 运行时环境，用于执行构建脚本与依赖管理 |
| npm | 9.x 或 10.x | 包管理器，用于安装项目依赖与运行脚本 |
| Git | 2.30 及以上 | 版本控制工具，用于克隆仓库与提交变更 |
| YAML 解析器 | 项目内置 | 用于解析 `data/` 目录下的条目配置文件 |
| HTTP 探测模块 | 可选 | 若启用链接检查功能，需要网络访问权限 |
| 静态站点生成器 | 可选 | 若部署为独立站点，推荐 Hugo 或 VuePress |
| 操作系统 | Linux / macOS / WSL2 | 构建流程依赖标准 POSIX 环境，Windows 原生未经过充分测试 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 入门指南 | docs/getting-started.md | 如何安装、配置并生成第一个导航页面 |
| 条目格式规范 | docs/entry-spec.md | 资源条目的字段定义、数据类型与示例 |
| 分类设计指南 | docs/taxonomy.md | 如何设计符合项目需求的分类树与标签体系 |
| 部署与集成 | docs/deployment.md | 如何将生成结果部署到 Web 服务器或 CI 流水线 |

## 资源列表

本项目资源列表按内容类别划分，所有 URL 均保持用户提供的原始格式。

技术文章类

http://www.blog.nzfnve.cn/Article/details/7068313.sHtML
http://www.blog.nzfnve.cn/Article/details/9379.sHtML
http://www.blog.nzfnve.cn/Article/details/664787.sHtML
http://www.blog.nzfnve.cn/Article/details/68422.sHtML
http://www.blog.nzfnve.cn/Article/details/2472933.sHtML
http://www.blog.nzfnve.cn/Article/details/7707644.sHtML
http://www.blog.nzfnve.cn/Article/details/0968.sHtML
http://www.blog.nzfnve.cn/Article/details/998260.sHtML
http://www.blog.nzfnve.cn/Article/details/16249.sHtML
http://www.blog.nzfnve.cn/Article/details/8006.sHtML
http://www.blog.nzfnve.cn/Article/details/4425583.sHtML
http://www.blog.nzfnve.cn/Article/details/470070.sHtML
http://www.blog.nzfnve.cn/Article/details/053666.sHtML
http://www.blog.nzfnve.cn/Article/details/3467459.sHtML
http://www.blog.nzfnve.cn/Article/details/4927400.sHtML
http://www.blog.nzfnve.cn/Article/details/2309290.sHtML
http://www.blog.nzfnve.cn/Article/details/95221.sHtML
http://www.blog.nzfnve.cn/Article/details/7254.sHtML
http://www.blog.nzfnve.cn/Article/details/676097.sHtML
http://www.blog.nzfnve.cn/Article/details/158568.sHtML
http://www.blog.nzfnve.cn/Article/details/6456.sHtML
http://www.blog.nzfnve.cn/Article/details/70662.sHtML
http://www.blog.nzfnve.cn/Article/details/744275.sHtML
http://www.blog.nzfnve.cn/Article/details/34379.sHtML
http://www.blog.nzfnve.cn/Article/details/363949.sHtML
http://www.blog.nzfnve.cn/Article/details/631514.sHtML
http://www.blog.nzfnve.cn/Article/details/8440.sHtML
http://www.blog.nzfnve.cn/Article/details/6094491.sHtML
http://www.blog.nzfnve.cn/Article/details/567574.sHtML
http://www.blog.nzfnve.cn/Article/details/03111.sHtML
http://www.blog.nzfnve.cn/Article/details/3700.sHtML
http://www.blog.nzfnve.cn/Article/details/366685.sHtML
http://www.blog.nzfnve.cn/Article/details/7631.sHtML
http://www.blog.nzfnve.cn/Article/details/09287.sHtML
http://www.blog.nzfnve.cn/Article/details/3279.sHtML
http://www.blog.nzfnve.cn/Article/details/9255027.sHtML
http://www.blog.nzfnve.cn/Article/details/6033555.sHtML
http://www.blog.nzfnve.cn/Article/details/5868572.sHtML
http://www.blog.nzfnve.cn/Article/details/966569.sHtML
http://www.blog.nzfnve.cn/Article/details/627577.sHtML
http://www.blog.nzfnve.cn/Article/details/617863.sHtML
http://www.blog.nzfnve.cn/Article/details/4560124.sHtML
http://www.blog.nzfnve.cn/Article/details/717114.sHtML
http://www.blog.nzfnve.cn/Article/details/4591088.sHtML
http://www.blog.nzfnve.cn/Article/details/691408.sHtML
http://www.blog.nzfnve.cn/Article/details/05562.sHtML
http://www.blog.nzfnve.cn/Article/details/608815.sHtML
http://www.blog.nzfnve.cn/Article/details/9087702.sHtML
http://www.blog.nzfnve.cn/Article/details/58576.sHtML
http://www.blog.nzfnve.cn/Article/details/90337.sHtML
http://www.blog.nzfnve.cn/Article/details/01090.sHtML
http://www.blog.nzfnve.cn/Article/details/11420.sHtML
http://www.blog.nzfnve.cn/Article/details/3374.sHtML
http://www.blog.nzfnve.cn/Article/details/6317761.sHtML
http://www.blog.nzfnve.cn/Article/details/5499400.sHtML
http://www.blog.nzfnve.cn/Article/details/7373.sHtML
http://www.blog.nzfnve.cn/Article/details/100045.sHtML
http://www.blog.nzfnve.cn/Article/details/852697.sHtML
http://www.blog.nzfnve.cn/Article/details/2348219.sHtML
http://www.blog.nzfnve.cn/Article/details/0811.sHtML
http://www.blog.nzfnve.cn/Article/details/3692233.sHtML
http://www.blog.nzfnve.cn/Article/details/399892.sHtML
http://www.blog.nzfnve.cn/Article/details/2209799.sHtML
http://www.blog.nzfnve.cn/Article/details/779551.sHtML
http://www.blog.nzfnve.cn/Article/details/25043.sHtML
http://www.blog.nzfnve.cn/Article/details/2859.sHtML
http://www.blog.nzfnve.cn/Article/details/5923497.sHtML
http://www.blog.nzfnve.cn/Article/details/96425.sHtML
http://www.blog.nzfnve.cn/Article/details/7034.sHtML
http://www.blog.nzfnve.cn/Article/details/6854.sHtML
http://www.blog.nzfnve.cn/Article/details/1131.sHtML
http://www.blog.nzfnve.cn/Article/details/664868.sHtML
http://www.blog.nzfnve.cn/Article/details/038392.sHtML
http://www.blog.nzfnve.cn/Article/details/9744348.sHtML
http://www.blog.nzfnve.cn/Article/details/965573.sHtML
http://www.blog.nzfnve.cn/Article/details/7500.sHtML
http://www.blog.nzfnve.cn/Article/details/05845.sHtML
http://www.blog.nzfnve.cn/Article/details/6762911.sHtML
http://www.blog.nzfnve.cn/Article/details/03646.sHtML
http://www.blog.nzfnve.cn/Article/details/90753.sHtML
http://www.blog.nzfnve.cn/Article/details/6645284.sHtML
http://www.blog.nzfnve.cn/Article/details/44294.sHtML
http://www.blog.nzfnve.cn/Article/details/1076743.sHtML
http://www.blog.nzfnve.cn/Article/details/870791.sHtML
http://www.blog.nzfnve.cn/Article/details/82567.sHtML
http://www.blog.nzfnve.cn/Article/details/15817.sHtML
http://www.blog.nzfnve.cn/Article/details/0284641.sHtML
http://www.blog.nzfnve.cn/Article/details/0803.sHtML
http://www.blog.nzfnve.cn/Article/details/8281.sHtML
http://www.blog.nzfnve.cn/Article/details/1188685.sHtML
http://www.blog.nzfnve.cn/Article/details/246673.sHtML
http://www.blog.nzfnve.cn/Article/details/44941.sHtML
http://www.blog.nzfnve.cn/Article/details/7658239.sHtML
http://www.blog.nzfnve.cn/Article/details/3385957.sHtML
http://www.blog.nzfnve.cn/Article/details/6494.sHtML
http://www.blog.nzfnve.cn/Article/details/725637.sHtML
http://www.blog.nzfnve.cn/Article/details/1819.sHtML
http://www.blog.nzfnve.cn/Article/details/6704427.sHtML
http://www.blog.nzfnve.cn/Article/details/44886.sHtML
http://www.blog.nzfnve.cn/Article/details/91216.sHtML
http://www.blog.nzfnve.cn/Article/details/9261.sHtML
http://www.blog.nzfnve.cn/Article/details/5220187.sHtML
http://www.blog.nzfnve.cn/Article/details/496413.sHtML
http://www.blog.nzfnve.cn/Article/details/4672026.sHtML
http://www.blog.nzfnve.cn/Article/details/92251.sHtML
http://www.blog.nzfnve.cn/Article/details/6752100.sHtML
http://www.blog.nzfnve.cn/Article/details/44983.sHtML
http://www.blog.nzfnve.cn/Article/details/60498.sHtML
http://www.blog.nzfnve.cn/Article/details/847421.sHtML
http://www.blog.nzfnve.cn/Article/details/48860.sHtML
http://www.blog.nzfnve.cn/Article/details/8774.sHtML
http://www.blog.nzfnve.cn/Article/details/075970.sHtML
http://www.blog.nzfnve.cn/Article/details/1388542.sHtML
http://www.blog.nzfnve.cn/Article/details/822957.sHtML
http://www.blog.nzfnve.cn/Article/details/480027.sHtML
http://www.blog.nzfnve.cn/Article/details/09070.sHtML
http://www.blog.nzfnve.cn/Article/details/748760.sHtML
http://www.blog.nzfnve.cn/Article/details/86078.sHtML
http://www.blog.nzfnve.cn/Article/details/1349134.sHtML
http://www.blog.nzfnve.cn/Article/details/934214.sHtML
http://www.blog.nzfnve.cn/Article/details/9008738.sHtML
http://www.blog.nzfnve.cn/Article/details/3070.sHtML
http://www.blog.nzfnve.cn/Article/details/409414.sHtML
http://www.blog.nzfnve.cn/Article/details/7274648.sHtML
http://www.blog.nzfnve.cn/Article/details/886316.sHtML
http://www.blog.nzfnve.cn/Article/details/1258.sHtML
http://www.blog.nzfnve.cn/Article/details/06524.sHtML
http://www.blog.nzfnve.cn/Article/details/27501.sHtML
http://www.blog.nzfnve.cn/Article/details/681445.sHtML
http://www.blog.nzfnve.cn/Article/details/278252.sHtML
http://www.blog.nzfnve.cn/Article/details/9105.sHtML
http://www.blog.nzfnve.cn/Article/details/14686.sHtML
http://www.blog.nzfnve.cn/Article/details/2549723.sHtML
http://www.blog.nzfnve.cn/Article/details/5759.sHtML
http://www.blog.nzfnve.cn/Article/details/27761.sHtML
http://www.blog.nzfnve.cn/Article/details/158381.sHtML
http://www.blog.nzfnve.cn/Article/details/5831163.sHtML
http://www.blog.nzfnve.cn/Article/details/987373.sHtML
http://www.blog.nzfnve.cn/Article/details/441607.sHtML
http://www.blog.nzfnve.cn/Article/details/32080.sHtML
http://www.blog.nzfnve.cn/Article/details/7107827.sHtML
http://www.blog.nzfnve.cn/Article/details/07444.sHtML
http://www.blog.nzfnve.cn/Article/details/4926965.sHtML
http://www.blog.nzfnve.cn/Article/details/6658213.sHtML
http://www.blog.nzfnve.cn/Article/details/1818.sHtML
http://www.blog.nzfnve.cn/Article/details/639648.sHtML
http://www.blog.nzfnve.cn/Article/details/1019234.sHtML
http://www.blog.nzfnve.cn/Article/details/0266.sHtML
http://www.blog.nzfnve.cn/Article/details/0295779.sHtML
http://www.blog.nzfnve.cn/Article/details/1401618.sHtML
http://www.blog.nzfnve.cn/Article/details/24359.sHtML
http://www.blog.nzfnve.cn/Article/details/8035643.sHtML
http://www.blog.nzfnve.cn/Article/details/81730.sHtML
http://www.blog.nzfnve.cn/Article/details/53669.sHtML
http://www.blog.nzfnve.cn/Article/details/77229.sHtML
http://www.blog.nzfnve.cn/Article/details/24553.sHtML
http://www.blog.nzfnve.cn/Article/details/5401.sHtML
http://www.blog.nzfnve.cn/Article/details/5936797.sHtML
http://www.blog.nzfnve.cn/Article/details/5088.sHtML
http://www.blog.nzfnve.cn/Article/details/312504.sHtML
http://www.blog.nzfnve.cn/Article/details/1286073.sHtML
http://www.blog.nzfnve.cn/Article/details/5407.sHtML
http://www.blog.nzfnve.cn/Article/details/2359.sHtML
http://www.blog.nzfnve.cn/Article/details/0397214.sHtML
http://www.blog.nzfnve.cn/Article/details/46225.sHtML
http://www.blog.nzfnve.cn/Article/details/1403796.sHtML
http://www.blog.nzfnve.cn/Article/details/426969.sHtML
http://www.blog.nzfnve.cn/Article/details/657687.sHtML
http://www.blog.nzfnve.cn/Article/details/9083455.sHtML
http://www.blog.nzfnve.cn/Article/details/62977.sHtML
http://www.blog.nzfnve.cn/Article/details/05675.sHtML
http://www.blog.nzfnve.cn/Article/details/954816.sHtML
http://www.blog.nzfnve.cn/Article/details/866360.sHtML
http://www.blog.nzfnve.cn/Article/details/3836504.sHtML
http://www.blog.nzfnve.cn/Article/details/44156.sHtML
http://www.blog.nzfnve.cn/Article/details/5577.sHtML
http://www.blog.nzfnve.cn/Article/details/86323.sHtML
http://www.blog.nzfnve.cn/Article/details/0589.sHtML
http://www.blog.nzfnve.cn/Article/details/854667.sHtML
http://www.blog.nzfnve.cn/Article/details/3555.sHtML
http://www.blog.nzfnve.cn/Article/details/63505.sHtML
http://www.blog.nzfnve.cn/Article/details/363660.sHtML
http://www.blog.nzfnve.cn/Article/details/774664.sHtML
http://www.blog.nzfnve.cn/Article/details/055428.sHtML
http://www.blog.nzfnve.cn/Article/details/0807520.sHtML
http://www.blog.nzfnve.cn/Article/details/72701.sHtML
http://www.blog.nzfnve.cn/Article/details/452492.sHtML
http://www.blog.nzfnve.cn/Article/details/6979640.sHtML
http://www.blog.nzfnve.cn/Article/details/5544814.sHtML
http://www.blog.nzfnve.cn/Article/details/1534.sHtML
http://www.blog.nzfnve.cn/Article/details/9484318.sHtML
http://www.blog.nzfnve.cn/Article/details/72067.sHtML
http://www.blog.nzfnve.cn/Article/details/4317.sHtML
http://www.blog.nzfnve.cn/Article/details/075188.sHtML
http://www.blog.nzfnve.cn/Article/details/518954.sHtML
http://www.blog.nzfnve.cn/Article/details/1585.sHtML
http://www.blog.nzfnve.cn/Article/details/34132.sHtML
http://www.blog.nzfnve.cn/Article/details/1934328.sHtML
http://www.blog.nzfnve.cn/Article/details/12077.sHtML
http://www.blog.nzfnve.cn/Article/details/90553.sHtML
http://www.blog.nzfnve.cn/Article/details/22350.sHtML
http://www.blog.nzfnve.cn/Article/details/544185.sHtML
http://www.blog.nzfnve.cn/Article/details/067395.sHtML
http://www.blog.nzfnve.cn/Article/details/9007274.sHtML
http://www.blog.nzfnve.cn/Article/details/314824.sHtML
http://www.blog.nzfnve.cn/Article/details/86591.sHtML
http://www.blog.nzfnve.cn/Article/details/374039.sHtML
http://www.blog.nzfnve.cn/Article/details/7223.sHtML
http://www.blog.nzfnve.cn/Article/details/8498.sHtML
http://www.blog.nzfnve.cn/Article/details/5126.sHtML
http://www.blog.nzfnve.cn/Article/details/5741.sHtML
http://www.blog.nzfnve.cn/Article/details/999573.sHtML
http://www.blog.nzfnve.cn/Article/details/8601.sHtML
http://www.blog.nzfnve.cn/Article/details/07932.sHtML
http://www.blog.nzfnve.cn/Article/details/5152638.sHtML
http://www.blog.nzfnve.cn/Article/details/6658.sHtML
http://www.blog.nzfnve.cn/Article/details/20577.sHtML
http://www.blog.nzfnve.cn/Article/details/6137.sHtML
http://www.blog.nzfnve.cn/Article/details/0333.sHtML
http://www.blog.nzfnve.cn/Article/details/84632.sHtML
http://www.blog.nzfnve.cn/Article/details/5040.sHtML
http://www.blog.nzfnve.cn/Article/details/59251.sHtML
http://www.blog.nzfnve.cn/Article/details/0416.sHtML
http://www.blog.nzfnve.cn/Article/details/850349.sHtML
http://www.blog.nzfnve.cn/Article/details/6544465.sHtML
http://www.blog.nzfnve.cn/Article/details/4400.sHtML
http://www.blog.nzfnve.cn/Article/details/2359248.sHtML
http://www.blog.nzfnve.cn/Article/details/1721.sHtML
http://www.blog.nzfnve.cn/Article/details/38629.sHtML
http://www.blog.nzfnve.cn/Article/details/367004.sHtML
http://www.blog.nzfnve.cn/Article/details/57841.sHtML
http://www.blog.nzfnve.cn/Article/details/866223.sHtML
http://www.blog.nzfnve.cn/Article/details/82025.sHtML
http://www.blog.nzfnve.cn/Article/details/2853.sHtML
http://www.blog.nzfnve.cn/Article/details/379769.sHtML
http://www.blog.nzfnve.cn/Article/details/7897.sHtML
http://www.blog.nzfnve.cn/Article/details/484605.sHtML
http://www.blog.nzfnve.cn/Article/details/885341.sHtML
http://www.blog.nzfnve.cn/Article/details/1892891.sHtML
http://www.blog.nzfnve.cn/Article/details/0269.sHtML
http://www.blog.nzfnve.cn/Article/details/0156357.sHtML
http://www.blog.nzfnve.cn/Article/details/9199.sHtML
http://www.blog.nzfnve.cn/Article/details/7597.sHtML
http://www.blog.nzfnve.cn/Article/details/6017551.sHtML
http://www.blog.nzfnve.cn/Article/details/21443.sHtML
http://www.blog.nzfnve.cn/Article/details/739889.sHtML
http://www.blog.nzfnve.cn/Article/details/1284.sHtML
http://www.blog.nzfnve.cn/Article/details/8789472.sHtML
http://www.blog.nzfnve.cn/Article/details/1490709.sHtML
http://www.blog.nzfnve.cn/Article/details/442110.sHtML

## 项目结构

```
navigator-core/
├── bin/                              # 可执行入口与命令行工具
│   └── cli.js                        # 主入口，解析命令参数并调用构建流程
├── lib/                              # 核心逻辑库
│   ├── parser/                       # 条目解析模块
│   │   ├── yaml-loader.js            # 加载并校验 YAML 数据文件
│   │   └── csv-transformer.js        # 将 CSV 格式转换为内部数据模型
│   ├── generator/                    # 输出生成模块
│   │   ├── markdown-builder.js       # 根据模板生成 Markdown 目录页面
│   │   └── index-renderer.js         # 渲染分类索引与标签聚合页
│   └── checker/                      # 链接检查模块
│       ├── http-probe.js             # 发送 HEAD 请求探测链接状态
│       └── report-formatter.js       # 格式化失效链接报告
├── templates/                        # 输出模板
│   ├── default/                      # 默认主题模板目录
│   │   ├── header.hbs                # 页面头部与导航栏
│   │   ├── entry-list.hbs            # 条目列表渲染结构
│   │   └── footer.hbs                # 页脚与版权信息
│   └── compact/                      # 紧凑型模板，适用于嵌入式展示
├── data/                             # 数据目录
│   ├── sources.yaml                  # 主数据文件，分类与条目定义
│   └── tags.yaml                     # 标签别名与分组配置
├── docs/                             # 项目文档
│   ├── getting-started.md            # 快速入门
│   ├── entry-spec.md                 # 条目格式完整规范
│   ├── taxonomy.md                   # 分类设计方法论
│   └── deployment.md                 # 部署与 CI 集成指南
├── test/                             # 单元测试与集成测试
│   ├── parser.test.js                # 解析器测试用例
│   ├── generator.test.js             # 生成器测试用例
│   └── fixtures/                     # 测试用的静态数据样本
├── .github/                          # GitHub 相关配置
│   └── workflows/                    # CI 工作流定义
│       ├── build.yml                 # 构建验证流水线
│       └── link-check.yml            # 定时链接可用性检查
├── package.json                      # npm 项目配置与依赖声明
├── README.md                         # 项目说明文档（本文件）
└── LICENSE                           # MIT 许可证文本
```

## 贡献指南

贡献者需遵循以下流程以确保项目维护的一致性与代码质量。所有贡献均需通过 Pull Request 提交，并在合并前通过 CI 构建检查。

第一，查阅项目 Issue 列表，确认当前没有重复或正在进行的相关讨论。对于新功能提议或重大变更，建议先创建 Issue 进行方案沟通，避免无效开发。

第二，克隆项目并创建独立特性分支。分支命名应遵循 `feature/` 或 `fix/` 前缀加简要描述，例如 `feature/yaml-schema-extension`。本地开发时请确保已配置 ESLint 与 Prettier 以保持代码风格统一。

第三，编写或更新对应的单元测试。新增解析逻辑或生成器功能时，测试覆盖率不得低于现有基线。测试用例需覆盖正常路径与异常边界情况。

第四，提交 Pull Request 时填写变更摘要，说明解决的问题、实现方案以及对现有 API 或数据格式的影响。若变更涉及数据格式或输出模板，需同步更新 docs/ 目录下的对应文档。

第五，代码审查通过后由项目维护者合并。合并后 CI 将自动触发构建与部署预览，贡献者应关注部署结果并处理可能出现的运行时警告。

## 常见问题

Q: 项目对输入数据中的 URL 格式有何限制？

A: 系统不做任何自动规范化处理。条目中的 URL 字段以字符串形式存储，输出时原样渲染。用户需确保提供的 URL 可访问且符合预期协议。建议在导入前对数据进行基本的格式清洗，例如去除首尾空白字符。

Q: 能否将 Navigator Core 集成到现有的 VuePress 或 MkDocs 站点中？

A: 可以。构建流程默认输出独立的 Markdown 文件，你可以将其放置在站点源码的相应目录下。对于 VuePress，建议将输出放在 `docs/` 下的某个子目录，并在侧边栏配置中引用。对于 MkDocs，可在 `nav` 配置中直接添加生成的 Markdown 文件路径。

Q: 如何处理链接失效或目标站点迁移的情况？

A: 项目提供了可选的 HTTP 探测模块。在构建时添加 `--check` 参数即可启用检查，输出报告会列出所有返回非 2xx 状态码的链接。建议将此检查集成到定期执行的 CI 任务中，以便及时发现失效资源并更新数据文件。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 16:28:28
