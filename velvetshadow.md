# TechResource Bridge

TechResource Bridge 是一个面向开发者、技术研究人员与开源爱好者的技术文章与资源导航工具。该项目通过对特定技术博客站点的文章进行结构化索引与分类聚合，帮助用户快速定位高质量的深度技术内容，避免在信息海洋中无效检索。

项目定位为轻量级的技术资源外链汇总与导航系统，不对原始内容做转载或二次发布，仅提供元数据索引与链接跳转服务。目标用户包括后端工程师、运维人员、架构师以及技术决策者，尤其适用于需要频繁查阅特定技术领域深度文章的研发团队。

## 功能概览

**文章索引聚合**：自动抓取并整理指定技术博客站点的文章元数据，包括标题、发布时间、摘要及原始链接，形成统一的检索视图。

**多维度分类筛选**：支持按技术领域、文章类型、发布时间范围等维度对索引内容进行筛选与排序。

**全文检索支持**：基于文章标题与摘要内容提供关键词检索能力，帮助用户精确命中感兴趣的技术主题。

**链接健康监测**：定期检查索引链接的有效性，自动标记失效链接并生成报告，确保导航资源的可用性。

**访问统计与热度排序**：记录各文章链接的点击频次，支持按热度排序展示热门技术内容。

**数据导入导出**：支持将索引数据导出为 JSON 或 CSV 格式，便于用户进行离线分析或集成到其他工具链中。

## 应用场景

技术团队内部知识库建设：团队可以将 TechResource Bridge 部署为内部导航入口，成员通过统一界面访问经过筛选的高质量技术文章，减少信息收集成本，提升学习与问题排查效率。

个人技术阅读管理：开发者可以借助本项目的分类与检索功能，建立个人技术阅读清单，集中管理来自特定博客站点的优质内容，避免收藏夹杂乱无章。

技术社区内容推荐：社区运营者或技术博主可利用本项目的数据导出功能，定期生成热门文章榜单或技术专题汇总，用于社区内容推荐或 newsletter 素材采集。

技术调研与竞品分析：研究人员可以通过检索和分类功能，快速获取特定技术方向的文章集合，用于技术趋势分析、竞品功能对比或行业报告撰写。

## 快速开始

以下步骤指导您在本机快速启动 TechResource Bridge 服务。

```bash
# 克隆代码仓库
git clone https://github.com/techresource-bridge/techresource-bridge.git

# 进入项目目录
cd techresource-bridge

# 安装依赖（使用 npm）
npm install

# 启动开发服务器
npm run dev
```

服务启动后，默认监听本机 3000 端口。访问 http://localhost:3000 即可进入索引管理界面。首次启动时，系统会自动执行一次初始数据同步任务，同步完成后即可正常使用检索与导航功能。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Node.js | v18.0.0 或更高 | 项目运行时环境，推荐使用 LTS 版本 |
| npm | v9.0.0 或更高 | 包管理器，用于安装项目依赖 |
| SQLite | 内置（无需额外安装） | 默认轻量级数据库，用于存储索引元数据 |
| PostgreSQL | v14.0 或更高（可选） | 生产环境推荐使用，需自行配置连接 |
| Redis | v7.0 或更高（可选） | 缓存层组件，用于提升检索响应速度 |
| Git | v2.30.0 或更高 | 代码克隆与版本管理工具 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户指南 | docs/user-guide/ | 如何使用检索、分类、导入导出等核心功能 |
| 部署手册 | docs/deployment/ | 如何将项目部署到生产环境，包括容器化与云平台配置 |
| 开发文档 | docs/development/ | 项目架构说明、API 接口文档及二次开发指引 |
| 运维手册 | docs/operations/ | 数据同步配置、链接健康监测及日志管理操作说明 |

## 资源列表

原始文章索引资源（共 250 条）

http://www.blog.ityiqv.cn/Article/details/4298.sHtML
http://www.blog.ityiqv.cn/Article/details/167777.sHtML
http://www.blog.ityiqv.cn/Article/details/8973133.sHtML
http://www.blog.ityiqv.cn/Article/details/359647.sHtML
http://www.blog.ityiqv.cn/Article/details/0949.sHtML
http://www.blog.ityiqv.cn/Article/details/1265.sHtML
http://www.blog.ityiqv.cn/Article/details/8021.sHtML
http://www.blog.ityiqv.cn/Article/details/67460.sHtML
http://www.blog.ityiqv.cn/Article/details/6390.sHtML
http://www.blog.ityiqv.cn/Article/details/2872.sHtML
http://www.blog.ityiqv.cn/Article/details/0496508.sHtML
http://www.blog.ityiqv.cn/Article/details/961243.sHtML
http://www.blog.ityiqv.cn/Article/details/72402.sHtML
http://www.blog.ityiqv.cn/Article/details/2378942.sHtML
http://www.blog.ityiqv.cn/Article/details/23271.sHtML
http://www.blog.ityiqv.cn/Article/details/63182.sHtML
http://www.blog.ityiqv.cn/Article/details/5571658.sHtML
http://www.blog.ityiqv.cn/Article/details/3469833.sHtML
http://www.blog.ityiqv.cn/Article/details/0075160.sHtML
http://www.blog.ityiqv.cn/Article/details/4647.sHtML
http://www.blog.ityiqv.cn/Article/details/4115.sHtML
http://www.blog.ityiqv.cn/Article/details/24707.sHtML
http://www.blog.ityiqv.cn/Article/details/006785.sHtML
http://www.blog.ityiqv.cn/Article/details/632343.sHtML
http://www.blog.ityiqv.cn/Article/details/3603.sHtML
http://www.blog.ityiqv.cn/Article/details/25944.sHtML
http://www.blog.ityiqv.cn/Article/details/898778.sHtML
http://www.blog.ityiqv.cn/Article/details/1857.sHtML
http://www.blog.ityiqv.cn/Article/details/8733.sHtML
http://www.blog.ityiqv.cn/Article/details/179752.sHtML
http://www.blog.ityiqv.cn/Article/details/220381.sHtML
http://www.blog.ityiqv.cn/Article/details/2861.sHtML
http://www.blog.ityiqv.cn/Article/details/977885.sHtML
http://www.blog.ityiqv.cn/Article/details/2117489.sHtML
http://www.blog.ityiqv.cn/Article/details/4351105.sHtML
http://www.blog.ityiqv.cn/Article/details/57006.sHtML
http://www.blog.ityiqv.cn/Article/details/0235.sHtML
http://www.blog.ityiqv.cn/Article/details/106094.sHtML
http://www.blog.ityiqv.cn/Article/details/4808086.sHtML
http://www.blog.ityiqv.cn/Article/details/6464.sHtML
http://www.blog.ityiqv.cn/Article/details/23862.sHtML
http://www.blog.ityiqv.cn/Article/details/018047.sHtML
http://www.blog.ityiqv.cn/Article/details/1501.sHtML
http://www.blog.ityiqv.cn/Article/details/4441.sHtML
http://www.blog.ityiqv.cn/Article/details/3118.sHtML
http://www.blog.ityiqv.cn/Article/details/9110417.sHtML
http://www.blog.ityiqv.cn/Article/details/99349.sHtML
http://www.blog.ityiqv.cn/Article/details/8495.sHtML
http://www.blog.ityiqv.cn/Article/details/3913.sHtML
http://www.blog.ityiqv.cn/Article/details/7697080.sHtML
http://www.blog.ityiqv.cn/Article/details/948459.sHtML
http://www.blog.ityiqv.cn/Article/details/2460338.sHtML
http://www.blog.ityiqv.cn/Article/details/4918.sHtML
http://www.blog.ityiqv.cn/Article/details/12470.sHtML
http://www.blog.ityiqv.cn/Article/details/0528.sHtML
http://www.blog.ityiqv.cn/Article/details/9455.sHtML
http://www.blog.ityiqv.cn/Article/details/7084.sHtML
http://www.blog.ityiqv.cn/Article/details/15976.sHtML
http://www.blog.ityiqv.cn/Article/details/3834420.sHtML
http://www.blog.ityiqv.cn/Article/details/0069.sHtML
http://www.blog.ityiqv.cn/Article/details/1773.sHtML
http://www.blog.ityiqv.cn/Article/details/027729.sHtML
http://www.blog.ityiqv.cn/Article/details/643909.sHtML
http://www.blog.ityiqv.cn/Article/details/45800.sHtML
http://www.blog.ityiqv.cn/Article/details/7633.sHtML
http://www.blog.ityiqv.cn/Article/details/120755.sHtML
http://www.blog.ityiqv.cn/Article/details/069883.sHtML
http://www.blog.ityiqv.cn/Article/details/0489145.sHtML
http://www.blog.ityiqv.cn/Article/details/4740.sHtML
http://www.blog.ityiqv.cn/Article/details/615148.sHtML
http://www.blog.ityiqv.cn/Article/details/872532.sHtML
http://www.blog.ityiqv.cn/Article/details/5404.sHtML
http://www.blog.ityiqv.cn/Article/details/0011.sHtML
http://www.blog.ityiqv.cn/Article/details/006320.sHtML
http://www.blog.ityiqv.cn/Article/details/8403.sHtML
http://www.blog.ityiqv.cn/Article/details/2744.sHtML
http://www.blog.ityiqv.cn/Article/details/2617.sHtML
http://www.blog.ityiqv.cn/Article/details/498164.sHtML
http://www.blog.ityiqv.cn/Article/details/9466467.sHtML
http://www.blog.ityiqv.cn/Article/details/1109.sHtML
http://www.blog.ityiqv.cn/Article/details/6657152.sHtML
http://www.blog.ityiqv.cn/Article/details/20576.sHtML
http://www.blog.ityiqv.cn/Article/details/140585.sHtML
http://www.blog.ityiqv.cn/Article/details/8208917.sHtML
http://www.blog.ityiqv.cn/Article/details/6066582.sHtML
http://www.blog.ityiqv.cn/Article/details/544070.sHtML
http://www.blog.ityiqv.cn/Article/details/1159.sHtML
http://www.blog.ityiqv.cn/Article/details/2600400.sHtML
http://www.blog.ityiqv.cn/Article/details/77703.sHtML
http://www.blog.ityiqv.cn/Article/details/5618.sHtML
http://www.blog.ityiqv.cn/Article/details/0062.sHtML
http://www.blog.ityiqv.cn/Article/details/49061.sHtML
http://www.blog.ityiqv.cn/Article/details/15823.sHtML
http://www.blog.ityiqv.cn/Article/details/07078.sHtML
http://www.blog.ityiqv.cn/Article/details/9680.sHtML
http://www.blog.ityiqv.cn/Article/details/91757.sHtML
http://www.blog.ityiqv.cn/Article/details/0384.sHtML
http://www.blog.ityiqv.cn/Article/details/080170.sHtML
http://www.blog.ityiqv.cn/Article/details/261467.sHtML
http://www.blog.ityiqv.cn/Article/details/1755165.sHtML
http://www.blog.ityiqv.cn/Article/details/102925.sHtML
http://www.blog.ityiqv.cn/Article/details/16395.sHtML
http://www.blog.ityiqv.cn/Article/details/5388302.sHtML
http://www.blog.ityiqv.cn/Article/details/2299167.sHtML
http://www.blog.ityiqv.cn/Article/details/632047.sHtML
http://www.blog.ityiqv.cn/Article/details/63483.sHtML
http://www.blog.ityiqv.cn/Article/details/89297.sHtML
http://www.blog.ityiqv.cn/Article/details/07011.sHtML
http://www.blog.ityiqv.cn/Article/details/5849895.sHtML
http://www.blog.ityiqv.cn/Article/details/2225117.sHtML
http://www.blog.ityiqv.cn/Article/details/475881.sHtML
http://www.blog.ityiqv.cn/Article/details/08240.sHtML
http://www.blog.ityiqv.cn/Article/details/6443517.sHtML
http://www.blog.ityiqv.cn/Article/details/8744695.sHtML
http://www.blog.ityiqv.cn/Article/details/857904.sHtML
http://www.blog.ityiqv.cn/Article/details/838050.sHtML
http://www.blog.ityiqv.cn/Article/details/767547.sHtML
http://www.blog.ityiqv.cn/Article/details/462918.sHtML
http://www.blog.ityiqv.cn/Article/details/6249298.sHtML
http://www.blog.ityiqv.cn/Article/details/18868.sHtML
http://www.blog.ityiqv.cn/Article/details/3788.sHtML
http://www.blog.ityiqv.cn/Article/details/8662.sHtML
http://www.blog.ityiqv.cn/Article/details/609706.sHtML
http://www.blog.ityiqv.cn/Article/details/9372.sHtML
http://www.blog.ityiqv.cn/Article/details/3780.sHtML
http://www.blog.ityiqv.cn/Article/details/513011.sHtML
http://www.blog.ityiqv.cn/Article/details/58845.sHtML
http://www.blog.ityiqv.cn/Article/details/8654.sHtML
http://www.blog.ityiqv.cn/Article/details/5444657.sHtML
http://www.blog.ityiqv.cn/Article/details/6982.sHtML
http://www.blog.ityiqv.cn/Article/details/44153.sHtML
http://www.blog.ityiqv.cn/Article/details/218604.sHtML
http://www.blog.ityiqv.cn/Article/details/2528254.sHtML
http://www.blog.ityiqv.cn/Article/details/8921440.sHtML
http://www.blog.ityiqv.cn/Article/details/1094989.sHtML
http://www.blog.ityiqv.cn/Article/details/74578.sHtML
http://www.blog.ityiqv.cn/Article/details/09185.sHtML
http://www.blog.ityiqv.cn/Article/details/648276.sHtML
http://www.blog.ityiqv.cn/Article/details/5946357.sHtML
http://www.blog.ityiqv.cn/Article/details/004441.sHtML
http://www.blog.ityiqv.cn/Article/details/6123628.sHtML
http://www.blog.ityiqv.cn/Article/details/68167.sHtML
http://www.blog.ityiqv.cn/Article/details/4975.sHtML
http://www.blog.ityiqv.cn/Article/details/0223759.sHtML
http://www.blog.ityiqv.cn/Article/details/1875.sHtML
http://www.blog.ityiqv.cn/Article/details/1215756.sHtML
http://www.blog.ityiqv.cn/Article/details/6143.sHtML
http://www.blog.ityiqv.cn/Article/details/1268.sHtML
http://www.blog.ityiqv.cn/Article/details/18474.sHtML
http://www.blog.ityiqv.cn/Article/details/3969.sHtML
http://www.blog.ityiqv.cn/Article/details/96958.sHtML
http://www.blog.ityiqv.cn/Article/details/324445.sHtML
http://www.blog.ityiqv.cn/Article/details/1990.sHtML
http://www.blog.ityiqv.cn/Article/details/684267.sHtML
http://www.blog.ityiqv.cn/Article/details/71287.sHtML
http://www.blog.ityiqv.cn/Article/details/4055292.sHtML
http://www.blog.ityiqv.cn/Article/details/8018.sHtML
http://www.blog.ityiqv.cn/Article/details/897152.sHtML
http://www.blog.ityiqv.cn/Article/details/5208196.sHtML
http://www.blog.ityiqv.cn/Article/details/904901.sHtML
http://www.blog.ityiqv.cn/Article/details/0327.sHtML
http://www.blog.ityiqv.cn/Article/details/4812184.sHtML
http://www.blog.ityiqv.cn/Article/details/5310798.sHtML
http://www.blog.ityiqv.cn/Article/details/776840.sHtML
http://www.blog.ityiqv.cn/Article/details/637926.sHtML
http://www.blog.ityiqv.cn/Article/details/201177.sHtML
http://www.blog.ityiqv.cn/Article/details/2274544.sHtML
http://www.blog.ityiqv.cn/Article/details/891641.sHtML
http://www.blog.ityiqv.cn/Article/details/1454.sHtML
http://www.blog.ityiqv.cn/Article/details/1200.sHtML
http://www.blog.ityiqv.cn/Article/details/1763.sHtML
http://www.blog.ityiqv.cn/Article/details/9541385.sHtML
http://www.blog.ityiqv.cn/Article/details/8522.sHtML
http://www.blog.ityiqv.cn/Article/details/2935.sHtML
http://www.blog.ityiqv.cn/Article/details/7776851.sHtML
http://www.blog.ityiqv.cn/Article/details/3132484.sHtML
http://www.blog.ityiqv.cn/Article/details/88523.sHtML
http://www.blog.ityiqv.cn/Article/details/871843.sHtML
http://www.blog.ityiqv.cn/Article/details/7626.sHtML
http://www.blog.ityiqv.cn/Article/details/23131.sHtML
http://www.blog.ityiqv.cn/Article/details/770523.sHtML
http://www.blog.ityiqv.cn/Article/details/9517.sHtML
http://www.blog.ityiqv.cn/Article/details/961420.sHtML
http://www.blog.ityiqv.cn/Article/details/3508207.sHtML
http://www.blog.ityiqv.cn/Article/details/62676.sHtML
http://www.blog.ityiqv.cn/Article/details/463765.sHtML
http://www.blog.ityiqv.cn/Article/details/64630.sHtML
http://www.blog.ityiqv.cn/Article/details/1338.sHtML
http://www.blog.ityiqv.cn/Article/details/0505.sHtML
http://www.blog.ityiqv.cn/Article/details/833015.sHtML
http://www.blog.ityiqv.cn/Article/details/135210.sHtML
http://www.blog.ityiqv.cn/Article/details/6976778.sHtML
http://www.blog.ityiqv.cn/Article/details/32418.sHtML
http://www.blog.ityiqv.cn/Article/details/57277.sHtML
http://www.blog.ityiqv.cn/Article/details/518066.sHtML
http://www.blog.ityiqv.cn/Article/details/350511.sHtML
http://www.blog.ityiqv.cn/Article/details/97149.sHtML
http://www.blog.ityiqv.cn/Article/details/859277.sHtML
http://www.blog.ityiqv.cn/Article/details/21602.sHtML
http://www.blog.ityiqv.cn/Article/details/6274.sHtML
http://www.blog.ityiqv.cn/Article/details/88675.sHtML
http://www.blog.ityiqv.cn/Article/details/51369.sHtML
http://www.blog.ityiqv.cn/Article/details/329919.sHtML
http://www.blog.ityiqv.cn/Article/details/6891.sHtML
http://www.blog.ityiqv.cn/Article/details/1660.sHtML
http://www.blog.ityiqv.cn/Article/details/8757.sHtML
http://www.blog.ityiqv.cn/Article/details/89697.sHtML
http://www.blog.ityiqv.cn/Article/details/12198.sHtML
http://www.blog.ityiqv.cn/Article/details/469904.sHtML
http://www.blog.ityiqv.cn/Article/details/2323670.sHtML
http://www.blog.ityiqv.cn/Article/details/6338747.sHtML
http://www.blog.ityiqv.cn/Article/details/5036599.sHtML
http://www.blog.ityiqv.cn/Article/details/2060.sHtML
http://www.blog.ityiqv.cn/Article/details/703181.sHtML
http://www.blog.ityiqv.cn/Article/details/57606.sHtML
http://www.blog.ityiqv.cn/Article/details/32467.sHtML
http://www.blog.ityiqv.cn/Article/details/79174.sHtML
http://www.blog.ityiqv.cn/Article/details/1553414.sHtML
http://www.blog.ityiqv.cn/Article/details/0898461.sHtML
http://www.blog.ityiqv.cn/Article/details/2396.sHtML
http://www.blog.ityiqv.cn/Article/details/217230.sHtML
http://www.blog.ityiqv.cn/Article/details/7817460.sHtML
http://www.blog.ityiqv.cn/Article/details/7921822.sHtML
http://www.blog.ityiqv.cn/Article/details/837869.sHtML
http://www.blog.ityiqv.cn/Article/details/61377.sHtML
http://www.blog.ityiqv.cn/Article/details/288925.sHtML
http://www.blog.ityiqv.cn/Article/details/22932.sHtML
http://www.blog.ityiqv.cn/Article/details/04645.sHtML
http://www.blog.ityiqv.cn/Article/details/486877.sHtML
http://www.blog.ityiqv.cn/Article/details/6004.sHtML
http://www.blog.ityiqv.cn/Article/details/0764.sHtML
http://www.blog.ityiqv.cn/Article/details/2702214.sHtML
http://www.blog.ityiqv.cn/Article/details/11776.sHtML
http://www.blog.ityiqv.cn/Article/details/3987180.sHtML
http://www.blog.ityiqv.cn/Article/details/6964412.sHtML
http://www.blog.ityiqv.cn/Article/details/4819.sHtML
http://www.blog.ityiqv.cn/Article/details/8543523.sHtML
http://www.blog.ityiqv.cn/Article/details/7269.sHtML
http://www.blog.ityiqv.cn/Article/details/5586.sHtML
http://www.blog.ityiqv.cn/Article/details/1145307.sHtML
http://www.blog.ityiqv.cn/Article/details/3383706.sHtML
http://www.blog.ityiqv.cn/Article/details/34238.sHtML
http://www.blog.ityiqv.cn/Article/details/7283.sHtML
http://www.blog.ityiqv.cn/Article/details/2680.sHtML
http://www.blog.ityiqv.cn/Article/details/920698.sHtML
http://www.blog.ityiqv.cn/Article/details/72837.sHtML
http://www.blog.ityiqv.cn/Article/details/07324.sHtML
http://www.blog.ityiqv.cn/Article/details/367473.sHtML
http://www.blog.ityiqv.cn/Article/details/68733.sHtML
http://www.blog.ityiqv.cn/Article/details/7590.sHtML

## 项目结构

```
techresource-bridge/
├── src/
│   ├── core/                           # 核心功能模块
│   │   ├── indexer.js                  # 文章索引构建与更新
│   │   ├── classifier.js               # 分类与标签管理
│   │   └── health.js                   # 链接健康检查
│   ├── api/                            # RESTful API 接口
│   │   ├── routes/                     # 路由定义
│   │   ├── controllers/                # 请求处理器
│   │   └── middleware/                 # 鉴权与日志中间件
│   ├── services/                       # 外部服务集成
│   │   ├── database.js                 # 数据库连接与查询
│   │   ├── cache.js                    # Redis 缓存服务
│   │   └── scheduler.js                # 定时任务调度
│   ├── ui/                             # 前端界面
│   │   ├── pages/                      # 页面视图
│   │   ├── components/                 # 可复用组件
│   │   └── static/                     # 样式表与前端资源
│   └── utils/                          # 工具函数
│       ├── validator.js                # 数据校验
│       ├── logger.js                   # 日志记录
│       └── parser.js                   # HTML 元数据解析
├── config/                             # 配置文件目录
│   ├── default.yaml                    # 默认配置
│   ├── production.yaml                 # 生产环境配置
│   └── development.yaml                # 开发环境配置
├── data/                               # 数据存储目录
│   ├── sqlite/                         # SQLite 数据库文件
│   └── cache/                          # 本地缓存文件
├── tests/                              # 单元测试与集成测试
│   ├── unit/
│   └── integration/
├── docs/                               # 文档目录
├── scripts/                            # 运维脚本
│   ├── sync.sh                         # 数据同步脚本
│   └── backup.sh                       # 数据备份脚本
├── Dockerfile                          # 容器构建文件
├── docker-compose.yml                  # 容器编排配置
├── package.json                        # npm 依赖声明
├── package-lock.json                   # 依赖锁定文件
├── .env.example                        # 环境变量示例
├── .gitignore                          # Git 忽略规则
└── README.md                           # 项目说明文档
```

## 贡献指南

我们欢迎并鼓励社区贡献者参与 TechResource Bridge 的开发与改进。请遵循以下流程提交贡献。

第一步，在 GitHub 上 Fork 本仓库，并将 Fork 后的仓库克隆到本地开发环境中。

第二步，创建新的功能分支，分支命名应遵循 `feature/功能描述` 或 `fix/问题描述` 的格式，确保分支名称简洁明确。

第三步，完成代码开发后，运行完整的测试套件确保现有功能未被破坏，并补充相应的单元测试覆盖新增代码。

第四步，提交代码时遵循 Conventional Commits 规范编写提交信息，格式为 `<类型>: <简短描述>`，类型包括 feat、fix、docs、style、refactor、test、chore 等。

第五步，向本仓库的 main 分支发起 Pull Request，并在 PR 描述中详细说明变更内容、测试结果以及相关 issue 编号，等待项目维护者审阅。

## 常见问题

**问：数据同步任务多久执行一次？是否可以手动触发？**

答：默认情况下，数据同步任务每 6 小时自动执行一次。您也可以通过调用 `/api/sync/trigger` 接口手动触发同步，或在配置文件中调整 `sync.interval` 参数修改同步间隔。

**问：如何切换到 PostgreSQL 作为生产数据库？**

答：在 `config/production.yaml` 中配置 `database.type: postgresql`，并填写对应的 `database.host`、`database.port`、`database.username`、`database.password` 和 `database.name` 字段。首次切换后需执行 `npm run migrate` 完成表结构初始化。

**问：链接健康检查的结果在哪里查看？**

答：健康检查结果存储在数据库的 `link_health` 表中，您也可以通过界面右上角的「系统状态」面板查看概要统计信息，包括总链接数、有效链接数和失效链接数。失效链接的详细报告可通过 `/api/health/report` 接口导出为 JSON 格式。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 16:28:02
