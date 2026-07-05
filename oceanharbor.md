# ResourceBridge

ResourceBridge 是一个面向技术团队与独立开发者的外链资源归集与导航系统。该项目不对任何外部资源做内容镜像或二次分发，而是提供结构化的链接索引、分类标签与状态监控能力，帮助使用者从大量分散的优质技术文章、博客与文档中快速定位所需信息。ResourceBridge 本身不生产内容，仅作为连接用户与外部知识库的桥梁。

项目定位为轻量级、可自托管的技术资源目录服务，适用于需要维护内部技术知识地图、管理团队收藏夹或构建项目文档外链体系的场景。通过统一的条目格式与可扩展的分类体系，ResourceBridge 能将散落在不同域名下的优质外链转化为可检索、可追踪、可分享的资产清单。

## 功能概览

- **外链条目结构化存储**：每个资源条目包含标题、原始 URL、来源域名、摘要标签与收录时间，支持 Markdown 与 YAML 两种元数据格式。

- **多维度分类与筛选**：内置按技术领域、文章类型、发布年份、作者组织等维度的标签系统，支持组合筛选与快速检索。

- **链接可用性健康检查**：定时对已收录的 URL 发起 HEAD 请求，检测 4xx、5xx 状态码及 TLS 证书有效性，标记异常链接。

- **纯静态站点生成**：基于模板引擎将资源数据渲染为 HTML 页面，无需数据库，可部署于任何支持静态文件的 Web 服务器或对象存储。

- **导入与批量追加**：支持从 CSV、JSON Lines 及标准书签导出文件（Netscape HTML 格式）批量导入链接，适用于现有收藏夹迁移。

- **自定义输出样式**：提供多种主题配色与卡片布局选项，可通过 CSS 变量或主题配置文件调整界面风格，适应不同团队门户的视觉规范。

- **访问统计与热门排序**：记录各资源条目的点击次数（基于前端埋点或服务端日志解析），支持按热度、时间、字母序排列。

- **增量更新机制**：支持通过 Webhook 触发增量构建，仅重新处理新增或变更的条目，大幅缩短大型资源库的构建时间。

## 应用场景

1. **技术团队内部知识库索引**：团队在研发过程中积累了大量外部参考文档、博客教程与 API 手册，ResourceBridge 可将这些分散链接统一整理为团队门户的知识导航页，新人入职时可快速了解常用技术资料分布。

2. **开源项目文档外链管理**：开源项目在 README、Wiki 中引用了众多第三方依赖、参考实现或社区讨论帖，使用 ResourceBridge 可生成独立的外链附录页面，避免 README 过长且便于版本追踪。

3. **个人技术博客资源聚合**：技术博主或自媒体作者可在博客侧栏或独立子站点中嵌入 ResourceBridge 生成的资源卡片，向读者推荐经过筛选的高质量外链，增强博客的内容深度。

4. **技术社区活动资源归档**：在举办技术沙龙、黑客松或线上分享会后，组织者可将演讲材料、视频回放链接、相关代码仓库与参考阅读清单录入 ResourceBridge，形成活动资源沉淀。

5. **多项目依赖文档统一入口**：中大型企业内部的多个服务项目各自维护独立的部署文档与运维手册，ResourceBridge 可作为统一入口层，将各项目的外部依赖说明、环境配置参考链接汇总至单一页面。

## 快速开始

以下命令演示如何从 GitHub 克隆 ResourceBridge 源码、安装依赖并启动开发服务器。

```bash
git clone https://github.com/resourcebridge/resourcebridge.git
cd resourcebridge
npm install
npm run dev
```

执行上述命令后，开发服务器默认监听 127.0.0.1:3000。打开浏览器访问该地址即可查看示例资源列表。生产环境构建请使用 `npm run build` 并将输出目录 `dist/` 部署至 Web 服务器。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Node.js | 18.x LTS 或更高 | 运行时环境，用于执行构建脚本与开发服务器 |
| npm | 9.x 或更高 | 包管理器，用于安装项目依赖 |
| Git | 2.30 或更高 | 版本控制工具，用于克隆仓库与管理补丁 |
| 现代 Web 浏览器 | Chromium 110+ / Firefox 115+ | 开发调试与最终渲染效果验证 |
| 静态 Web 服务器 | Nginx 1.22+ / Caddy 2.6+ | 生产环境推荐，用于托管构建生成的静态文件 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | docs/user-guide/ | 如何录入资源、管理分类、执行健康检查与自定义主题 |
| 运维指南 | docs/operations/ | 如何部署生产环境、配置 SSL 证书、设置定时构建与监控告警 |
| 开发者文档 | docs/developer/ | 项目架构设计、插件开发接口、API 路由约定与测试规范 |
| 设计决策 | docs/decisions/ | 为何选择静态生成方案、元数据格式设计依据与性能优化策略 |

## 资源列表

本批次（第 28/280 批）共收录 250 个外链资源，全部来自 blog.fuvxie.cn 域下的技术文章页面。所有 URL 均按原样列出，未做任何协议、域名或路径改写。

技术文章主目录

http://www.blog.fuvxie.cn/Article/details/341119.sHtML
http://www.blog.fuvxie.cn/Article/details/604395.sHtML
http://www.blog.fuvxie.cn/Article/details/5733.sHtML
http://www.blog.fuvxie.cn/Article/details/02204.sHtML
http://www.blog.fuvxie.cn/Article/details/77517.sHtML
http://www.blog.fuvxie.cn/Article/details/27319.sHtML
http://www.blog.fuvxie.cn/Article/details/6649.sHtML
http://www.blog.fuvxie.cn/Article/details/482160.sHtML
http://www.blog.fuvxie.cn/Article/details/4605.sHtML
http://www.blog.fuvxie.cn/Article/details/679775.sHtML
http://www.blog.fuvxie.cn/Article/details/3699545.sHtML
http://www.blog.fuvxie.cn/Article/details/315601.sHtML
http://www.blog.fuvxie.cn/Article/details/66251.sHtML
http://www.blog.fuvxie.cn/Article/details/1172078.sHtML
http://www.blog.fuvxie.cn/Article/details/485141.sHtML
http://www.blog.fuvxie.cn/Article/details/1802.sHtML
http://www.blog.fuvxie.cn/Article/details/0233.sHtML
http://www.blog.fuvxie.cn/Article/details/212480.sHtML
http://www.blog.fuvxie.cn/Article/details/1024.sHtML
http://www.blog.fuvxie.cn/Article/details/2267876.sHtML
http://www.blog.fuvxie.cn/Article/details/936476.sHtML
http://www.blog.fuvxie.cn/Article/details/05273.sHtML
http://www.blog.fuvxie.cn/Article/details/2866721.sHtML
http://www.blog.fuvxie.cn/Article/details/0130962.sHtML
http://www.blog.fuvxie.cn/Article/details/10645.sHtML
http://www.blog.fuvxie.cn/Article/details/3587.sHtML
http://www.blog.fuvxie.cn/Article/details/8423.sHtML
http://www.blog.fuvxie.cn/Article/details/0579395.sHtML
http://www.blog.fuvxie.cn/Article/details/74388.sHtML
http://www.blog.fuvxie.cn/Article/details/1775585.sHtML
http://www.blog.fuvxie.cn/Article/details/08182.sHtML
http://www.blog.fuvxie.cn/Article/details/549774.sHtML
http://www.blog.fuvxie.cn/Article/details/4697.sHtML
http://www.blog.fuvxie.cn/Article/details/623812.sHtML
http://www.blog.fuvxie.cn/Article/details/9045.sHtML
http://www.blog.fuvxie.cn/Article/details/07111.sHtML
http://www.blog.fuvxie.cn/Article/details/476187.sHtML
http://www.blog.fuvxie.cn/Article/details/06780.sHtML
http://www.blog.fuvxie.cn/Article/details/65324.sHtML
http://www.blog.fuvxie.cn/Article/details/3272.sHtML
http://www.blog.fuvxie.cn/Article/details/56100.sHtML
http://www.blog.fuvxie.cn/Article/details/545615.sHtML
http://www.blog.fuvxie.cn/Article/details/5949.sHtML
http://www.blog.fuvxie.cn/Article/details/35985.sHtML
http://www.blog.fuvxie.cn/Article/details/7300668.sHtML
http://www.blog.fuvxie.cn/Article/details/7672256.sHtML
http://www.blog.fuvxie.cn/Article/details/241554.sHtML
http://www.blog.fuvxie.cn/Article/details/22501.sHtML
http://www.blog.fuvxie.cn/Article/details/5705040.sHtML
http://www.blog.fuvxie.cn/Article/details/6155522.sHtML
http://www.blog.fuvxie.cn/Article/details/13732.sHtML
http://www.blog.fuvxie.cn/Article/details/42290.sHtML
http://www.blog.fuvxie.cn/Article/details/08033.sHtML
http://www.blog.fuvxie.cn/Article/details/6883890.sHtML
http://www.blog.fuvxie.cn/Article/details/1322.sHtML
http://www.blog.fuvxie.cn/Article/details/4584566.sHtML
http://www.blog.fuvxie.cn/Article/details/1863.sHtML
http://www.blog.fuvxie.cn/Article/details/7476.sHtML
http://www.blog.fuvxie.cn/Article/details/8819393.sHtML
http://www.blog.fuvxie.cn/Article/details/5886.sHtML
http://www.blog.fuvxie.cn/Article/details/8291790.sHtML
http://www.blog.fuvxie.cn/Article/details/38977.sHtML
http://www.blog.fuvxie.cn/Article/details/056670.sHtML
http://www.blog.fuvxie.cn/Article/details/2387.sHtML
http://www.blog.fuvxie.cn/Article/details/4835722.sHtML
http://www.blog.fuvxie.cn/Article/details/8468.sHtML
http://www.blog.fuvxie.cn/Article/details/164296.sHtML
http://www.blog.fuvxie.cn/Article/details/5172.sHtML
http://www.blog.fuvxie.cn/Article/details/32360.sHtML
http://www.blog.fuvxie.cn/Article/details/0711.sHtML
http://www.blog.fuvxie.cn/Article/details/39118.sHtML
http://www.blog.fuvxie.cn/Article/details/3453107.sHtML
http://www.blog.fuvxie.cn/Article/details/1632689.sHtML
http://www.blog.fuvxie.cn/Article/details/240581.sHtML
http://www.blog.fuvxie.cn/Article/details/39646.sHtML
http://www.blog.fuvxie.cn/Article/details/07585.sHtML
http://www.blog.fuvxie.cn/Article/details/071664.sHtML
http://www.blog.fuvxie.cn/Article/details/19402.sHtML
http://www.blog.fuvxie.cn/Article/details/20421.sHtML
http://www.blog.fuvxie.cn/Article/details/40378.sHtML
http://www.blog.fuvxie.cn/Article/details/3692.sHtML
http://www.blog.fuvxie.cn/Article/details/9841.sHtML
http://www.blog.fuvxie.cn/Article/details/262002.sHtML
http://www.blog.fuvxie.cn/Article/details/82549.sHtML
http://www.blog.fuvxie.cn/Article/details/3718.sHtML
http://www.blog.fuvxie.cn/Article/details/6383540.sHtML
http://www.blog.fuvxie.cn/Article/details/859606.sHtML
http://www.blog.fuvxie.cn/Article/details/47699.sHtML
http://www.blog.fuvxie.cn/Article/details/10707.sHtML
http://www.blog.fuvxie.cn/Article/details/2952844.sHtML
http://www.blog.fuvxie.cn/Article/details/8847260.sHtML
http://www.blog.fuvxie.cn/Article/details/5122291.sHtML
http://www.blog.fuvxie.cn/Article/details/65997.sHtML
http://www.blog.fuvxie.cn/Article/details/6024911.sHtML
http://www.blog.fuvxie.cn/Article/details/04458.sHtML
http://www.blog.fuvxie.cn/Article/details/5400.sHtML
http://www.blog.fuvxie.cn/Article/details/07529.sHtML
http://www.blog.fuvxie.cn/Article/details/082195.sHtML
http://www.blog.fuvxie.cn/Article/details/4855676.sHtML
http://www.blog.fuvxie.cn/Article/details/2622.sHtML
http://www.blog.fuvxie.cn/Article/details/48009.sHtML
http://www.blog.fuvxie.cn/Article/details/009335.sHtML
http://www.blog.fuvxie.cn/Article/details/9570.sHtML
http://www.blog.fuvxie.cn/Article/details/7232.sHtML
http://www.blog.fuvxie.cn/Article/details/891423.sHtML
http://www.blog.fuvxie.cn/Article/details/81023.sHtML
http://www.blog.fuvxie.cn/Article/details/9435588.sHtML
http://www.blog.fuvxie.cn/Article/details/77312.sHtML
http://www.blog.fuvxie.cn/Article/details/86602.sHtML
http://www.blog.fuvxie.cn/Article/details/0329674.sHtML
http://www.blog.fuvxie.cn/Article/details/5510.sHtML
http://www.blog.fuvxie.cn/Article/details/93958.sHtML
http://www.blog.fuvxie.cn/Article/details/3017397.sHtML
http://www.blog.fuvxie.cn/Article/details/86600.sHtML
http://www.blog.fuvxie.cn/Article/details/660845.sHtML
http://www.blog.fuvxie.cn/Article/details/0637691.sHtML
http://www.blog.fuvxie.cn/Article/details/47020.sHtML
http://www.blog.fuvxie.cn/Article/details/6158.sHtML
http://www.blog.fuvxie.cn/Article/details/26487.sHtML
http://www.blog.fuvxie.cn/Article/details/56079.sHtML
http://www.blog.fuvxie.cn/Article/details/573796.sHtML
http://www.blog.fuvxie.cn/Article/details/32451.sHtML
http://www.blog.fuvxie.cn/Article/details/299351.sHtML
http://www.blog.fuvxie.cn/Article/details/373308.sHtML
http://www.blog.fuvxie.cn/Article/details/598580.sHtML
http://www.blog.fuvxie.cn/Article/details/404001.sHtML
http://www.blog.fuvxie.cn/Article/details/1359044.sHtML
http://www.blog.fuvxie.cn/Article/details/4854130.sHtML
http://www.blog.fuvxie.cn/Article/details/1091.sHtML
http://www.blog.fuvxie.cn/Article/details/2432.sHtML
http://www.blog.fuvxie.cn/Article/details/3638.sHtML
http://www.blog.fuvxie.cn/Article/details/824676.sHtML
http://www.blog.fuvxie.cn/Article/details/252995.sHtML
http://www.blog.fuvxie.cn/Article/details/0474127.sHtML
http://www.blog.fuvxie.cn/Article/details/866829.sHtML
http://www.blog.fuvxie.cn/Article/details/34068.sHtML
http://www.blog.fuvxie.cn/Article/details/04654.sHtML
http://www.blog.fuvxie.cn/Article/details/627104.sHtML
http://www.blog.fuvxie.cn/Article/details/3679361.sHtML
http://www.blog.fuvxie.cn/Article/details/20950.sHtML
http://www.blog.fuvxie.cn/Article/details/40940.sHtML
http://www.blog.fuvxie.cn/Article/details/2526.sHtML
http://www.blog.fuvxie.cn/Article/details/332838.sHtML
http://www.blog.fuvxie.cn/Article/details/110474.sHtML
http://www.blog.fuvxie.cn/Article/details/80332.sHtML
http://www.blog.fuvxie.cn/Article/details/4503.sHtML
http://www.blog.fuvxie.cn/Article/details/7253.sHtML
http://www.blog.fuvxie.cn/Article/details/4300.sHtML
http://www.blog.fuvxie.cn/Article/details/648289.sHtML
http://www.blog.fuvxie.cn/Article/details/54103.sHtML
http://www.blog.fuvxie.cn/Article/details/4265118.sHtML
http://www.blog.fuvxie.cn/Article/details/170943.sHtML
http://www.blog.fuvxie.cn/Article/details/9471373.sHtML
http://www.blog.fuvxie.cn/Article/details/374897.sHtML
http://www.blog.fuvxie.cn/Article/details/596821.sHtML
http://www.blog.fuvxie.cn/Article/details/67241.sHtML
http://www.blog.fuvxie.cn/Article/details/9425.sHtML
http://www.blog.fuvxie.cn/Article/details/9781.sHtML
http://www.blog.fuvxie.cn/Article/details/6975151.sHtML
http://www.blog.fuvxie.cn/Article/details/6119222.sHtML
http://www.blog.fuvxie.cn/Article/details/5796695.sHtML
http://www.blog.fuvxie.cn/Article/details/412670.sHtML
http://www.blog.fuvxie.cn/Article/details/25668.sHtML
http://www.blog.fuvxie.cn/Article/details/6426.sHtML
http://www.blog.fuvxie.cn/Article/details/6873.sHtML
http://www.blog.fuvxie.cn/Article/details/86315.sHtML
http://www.blog.fuvxie.cn/Article/details/93085.sHtML
http://www.blog.fuvxie.cn/Article/details/3673.sHtML
http://www.blog.fuvxie.cn/Article/details/92419.sHtML
http://www.blog.fuvxie.cn/Article/details/2778.sHtML
http://www.blog.fuvxie.cn/Article/details/7352.sHtML
http://www.blog.fuvxie.cn/Article/details/1508439.sHtML
http://www.blog.fuvxie.cn/Article/details/463691.sHtML
http://www.blog.fuvxie.cn/Article/details/10640.sHtML
http://www.blog.fuvxie.cn/Article/details/146606.sHtML
http://www.blog.fuvxie.cn/Article/details/7524905.sHtML
http://www.blog.fuvxie.cn/Article/details/8925.sHtML
http://www.blog.fuvxie.cn/Article/details/3026.sHtML
http://www.blog.fuvxie.cn/Article/details/4295871.sHtML
http://www.blog.fuvxie.cn/Article/details/277414.sHtML
http://www.blog.fuvxie.cn/Article/details/98942.sHtML
http://www.blog.fuvxie.cn/Article/details/2898751.sHtML
http://www.blog.fuvxie.cn/Article/details/160491.sHtML
http://www.blog.fuvxie.cn/Article/details/49903.sHtML
http://www.blog.fuvxie.cn/Article/details/714026.sHtML
http://www.blog.fuvxie.cn/Article/details/3765.sHtML
http://www.blog.fuvxie.cn/Article/details/645650.sHtML
http://www.blog.fuvxie.cn/Article/details/18351.sHtML
http://www.blog.fuvxie.cn/Article/details/210010.sHtML
http://www.blog.fuvxie.cn/Article/details/943173.sHtML
http://www.blog.fuvxie.cn/Article/details/8210.sHtML
http://www.blog.fuvxie.cn/Article/details/6276528.sHtML
http://www.blog.fuvxie.cn/Article/details/0783667.sHtML
http://www.blog.fuvxie.cn/Article/details/2184219.sHtML
http://www.blog.fuvxie.cn/Article/details/777495.sHtML
http://www.blog.fuvxie.cn/Article/details/75788.sHtML
http://www.blog.fuvxie.cn/Article/details/831101.sHtML
http://www.blog.fuvxie.cn/Article/details/193701.sHtML
http://www.blog.fuvxie.cn/Article/details/33090.sHtML
http://www.blog.fuvxie.cn/Article/details/9144.sHtML
http://www.blog.fuvxie.cn/Article/details/4404169.sHtML
http://www.blog.fuvxie.cn/Article/details/22608.sHtML
http://www.blog.fuvxie.cn/Article/details/34194.sHtML
http://www.blog.fuvxie.cn/Article/details/8512.sHtML
http://www.blog.fuvxie.cn/Article/details/9598.sHtML
http://www.blog.fuvxie.cn/Article/details/11313.sHtML
http://www.blog.fuvxie.cn/Article/details/9885761.sHtML
http://www.blog.fuvxie.cn/Article/details/50521.sHtML
http://www.blog.fuvxie.cn/Article/details/7626.sHtML
http://www.blog.fuvxie.cn/Article/details/4849033.sHtML
http://www.blog.fuvxie.cn/Article/details/2724.sHtML
http://www.blog.fuvxie.cn/Article/details/088331.sHtML
http://www.blog.fuvxie.cn/Article/details/7890205.sHtML
http://www.blog.fuvxie.cn/Article/details/282651.sHtML
http://www.blog.fuvxie.cn/Article/details/684236.sHtML
http://www.blog.fuvxie.cn/Article/details/1579665.sHtML
http://www.blog.fuvxie.cn/Article/details/4469621.sHtML
http://www.blog.fuvxie.cn/Article/details/440322.sHtML
http://www.blog.fuvxie.cn/Article/details/23823.sHtML
http://www.blog.fuvxie.cn/Article/details/78423.sHtML
http://www.blog.fuvxie.cn/Article/details/7904.sHtML
http://www.blog.fuvxie.cn/Article/details/1450717.sHtML
http://www.blog.fuvxie.cn/Article/details/5765.sHtML
http://www.blog.fuvxie.cn/Article/details/9081.sHtML
http://www.blog.fuvxie.cn/Article/details/9423.sHtML
http://www.blog.fuvxie.cn/Article/details/51785.sHtML
http://www.blog.fuvxie.cn/Article/details/787887.sHtML
http://www.blog.fuvxie.cn/Article/details/2603.sHtML
http://www.blog.fuvxie.cn/Article/details/4860.sHtML
http://www.blog.fuvxie.cn/Article/details/26631.sHtML
http://www.blog.fuvxie.cn/Article/details/104062.sHtML
http://www.blog.fuvxie.cn/Article/details/71456.sHtML
http://www.blog.fuvxie.cn/Article/details/36410.sHtML
http://www.blog.fuvxie.cn/Article/details/26163.sHtML
http://www.blog.fuvxie.cn/Article/details/3994309.sHtML
http://www.blog.fuvxie.cn/Article/details/787258.sHtML
http://www.blog.fuvxie.cn/Article/details/4377520.sHtML
http://www.blog.fuvxie.cn/Article/details/6255324.sHtML
http://www.blog.fuvxie.cn/Article/details/5985250.sHtML
http://www.blog.fuvxie.cn/Article/details/311220.sHtML
http://www.blog.fuvxie.cn/Article/details/487577.sHtML
http://www.blog.fuvxie.cn/Article/details/0997858.sHtML
http://www.blog.fuvxie.cn/Article/details/15323.sHtML
http://www.blog.fuvxie.cn/Article/details/46098.sHtML
http://www.blog.fuvxie.cn/Article/details/7661.sHtML
http://www.blog.fuvxie.cn/Article/details/6028993.sHtML
http://www.blog.fuvxie.cn/Article/details/3932.sHtML
http://www.blog.fuvxie.cn/Article/details/15786.sHtML
http://www.blog.fuvxie.cn/Article/details/8484782.sHtML
http://www.blog.fuvxie.cn/Article/details/9745.sHtML

## 项目结构

```
resourcebridge/
├── src/                           # 核心源码目录
│   ├── core/                      # 核心业务逻辑
│   │   ├── collector.js           # 资源条目收集与去重
│   │   ├── checker.js             # 链接健康检查引擎
│   │   └── resolver.js            # URL 规范化解析
│   ├── loaders/                   # 数据加载适配器
│   │   ├── csv-loader.js          # CSV 格式导入
│   │   ├── jsonl-loader.js        # JSON Lines 格式导入
│   │   └── bookmark-loader.js     # Netscape 书签导入
│   ├── generators/                # 静态站点生成器
│   │   ├── page-builder.js        # HTML 页面组装
│   │   ├── sitemap-generator.js   # sitemap.xml 生成
│   │   └── rss-generator.js       # RSS 订阅源生成
│   ├── templates/                 # 模板引擎与主题文件
│   │   ├── default/               # 默认主题目录
│   │   └── custom/                # 用户自定义主题占位
│   └── utils/                     # 通用工具函数
│       ├── logger.js              # 日志记录
│       ├── config.js              # 配置加载
│       └── hash.js                # 内容哈希与缓存键
├── data/                          # 资源数据存储目录
│   ├── entries/                   # 条目元数据文件（按日期分片）
│   └── tags/                      # 标签索引文件
├── docs/                          # 项目文档（用户手册、运维、开发）
├── tests/                         # 单元测试与集成测试用例
│   ├── unit/                      # 单元测试
│   └── fixtures/                  # 测试用样例数据
├── scripts/                       # 辅助脚本（构建、迁移、导入导出）
├── config/                        # 配置文件目录
│   ├── default.yaml               # 默认配置
│   └── custom.yaml.example        # 自定义配置示例
├── dist/                          # 构建输出目录（由 build 生成）
├── package.json                   # npm 包声明与依赖管理
├── README.md                      # 项目说明（本文件）
└── LICENSE                        # MIT 许可证文件
```

## 贡献指南

1. 在 GitHub 上 Fork 本仓库，并克隆到本地开发环境。确保本地 Node.js 版本符合安装要求，执行 `npm install` 安装全部依赖。

2. 创建新的功能分支，分支命名请遵循 `feature/功能简述` 或 `fix/问题简述` 的格式。所有代码变更需包含对应的单元测试，测试用例放置于 `tests/unit/` 目录下。

3. 在提交 Pull Request 之前，运行 `npm run lint` 检查代码风格，运行 `npm test` 确保所有测试通过。若新增或修改了用户可见的功能，请同步更新 `docs/user-guide/` 中的相关章节。

4. 提交 PR 时请填写清晰的变更描述，关联相关 Issue（如有）。PR 标题需简洁概括改动内容，正文应说明改动动机、实现方式与影响范围。

5. 项目维护者会在 7 个工作日内审阅 PR，可能提出修改意见。请及时响应审阅反馈，合并后您的贡献将列入项目致谢列表。

## 常见问题

**Q：ResourceBridge 是否存储外部资源的完整内容或做网页存档？**

A：ResourceBridge 仅存储用户主动录入的 URL 及其元数据（标题、标签、摘要等），不抓取、不缓存、不镜像任何外部网页的实际内容。所有链接在展示时均以原始 URL 直链方式呈现，用户点击后直接跳转至源站。

**Q：如何批量导入已有的大量书签？**

A：ResourceBridge 内置了 Netscape HTML 书签解析器，您可以从主流浏览器（Chrome、Firefox、Edge）导出书签为 HTML 文件，然后通过 CLI 命令 `npm run import -- --format=bookmark --file=bookmarks.html` 进行批量导入。同时支持 CSV 与 JSON Lines 格式，适用于从数据库或电子表格迁移数据。

**Q：链接健康检查的频率和策略是怎样的？**

A：健康检查默认每 24 小时执行一次，仅对状态码为 2xx 的响应视为正常。对于 3xx 重定向，系统会跟随至最终地址并记录重定向链，但最终地址非 2xx 仍标记为异常。检查结果会写入 `data/health/` 目录下的 JSON 日志，您可以在管理后台或通过 API 查看异常链接列表。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 16:26:27
