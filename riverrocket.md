# IndexHub

IndexHub 是一个面向技术研究者、开发者与内容策展人的轻量级外链聚合与导航平台。该项目并非传统的 Web 应用框架，而是一个以结构化数据为核心的资源索引中间件，旨在将分散于各处的技术文章、教程文档与工具站点聚合并归一，以统一的元数据模型对外提供查询与浏览能力。

项目定位为“技术资源的外链数据库”，目标用户包括需要维护团队技术周报的工程师、搭建个人知识库的开发者，以及希望从海量技术内容中快速定位有效信息的阅读者。IndexHub 通过半自动化的收录流程，将原始 URL 转化为带分类标签、摘要字段与质量评分的结构化条目，从而解决“链接收藏即遗忘”与“信息过载难以检索”两大核心痛点。

## 功能概览

**批量外链收录**：支持从纯文本列表、CSV 或 Markdown 表格中批量导入原始 URL，自动去重并生成内部唯一标识符。

**元数据自动补全**：对收录的每一条链接，通过内置的元数据抓取模块尝试提取页面标题、发布时间、内容摘要与关键词，降低人工整理成本。

**分类标签体系**：允许用户为每一条资源定义一级分类（如后端架构、前端工程、运维监控）与自定义标签，支持多标签联合筛选。

**质量评估标记**：内置简易的质量评分机制，可基于页面可读性、内容篇幅与外部引用数量给出参考分值，辅助用户判断资源价值。

**全文检索与过滤**：基于标题、摘要、标签和原始 URL 的倒排索引，提供毫秒级的关键词检索能力，并支持按分类、评分范围与时间区间过滤。

**数据导入导出**：支持将全部索引数据导出为 JSON、CSV 或标准书签 HTML 格式，便于迁移至其他知识管理工具或离线浏览。

**静态化渲染视图**：提供可选的静态页面生成模式，将索引数据渲染为纯 HTML 目录页，适合部署于 Nginx 或 GitHub Pages 作为公开导航站。

## 应用场景

**团队技术周报素材库**：技术负责人或文档工程师可以使用 IndexHub 汇总一周内团队成员推荐的各类技术博文与工具链接，通过标签分类后统一分发给全体成员，替代零散的邮件或即时通讯消息。

**个人知识库外链中心**：在自建笔记系统（如 Logseq、Obsidian）之外，将 IndexHub 作为独立的外链数据库，所有读书笔记、教程参考与项目文档的 URL 均集中存储于此，通过 API 或导出功能与主知识库打通。

**开源项目文档站的外挂资源页**：开源项目维护者可以在项目文档中嵌入 IndexHub 生成的资源列表页面，将相关的社区教程、生态工具与案例实现集中陈列，帮助新用户快速了解项目周边生态。

**技术内容策展平台的后端数据源**：面向技术内容策展人或自媒体编辑，IndexHub 可作为后端数据源，为前端展示页提供经过筛选和排序的高质量外链列表，减少重复的数据整理工作。

## 快速开始

以下步骤将指导您在本地环境完成 IndexHub 的克隆、依赖安装与基础运行。

```bash
# 克隆代码仓库至本地
git clone https://github.com/indexhub/indexhub.git
cd indexhub

# 安装项目依赖（使用 pip 与 requirements.txt）
pip install -r requirements.txt

# 执行数据库初始化与示例数据加载
python manage.py migrate
python manage.py loaddata sample_links.json

# 启动本地开发服务器
python manage.py runserver --host 0.0.0.0 --port 8080
```

启动成功后，访问 http://localhost:8080 即可进入 IndexHub 的 Web 管理界面。首次运行会自动创建 SQLite 数据库文件 indexhub.db，所有收录的链接数据将存储于该文件中。

## 安装要求

IndexHub 基于 Python 3.9 及以上版本开发，核心依赖包括 Web 框架、数据库驱动与 HTML 解析库。正式部署前请确认以下组件已正确安装且版本符合要求。

| 依赖组件 | 必需性 | 说明 |
|---|---|---|
| Python 3.9 或更高版本 | 必需 | 核心运行环境，低于 3.9 版本将无法兼容类型注解语法。 |
| pip 21.0 及以上 | 必需 | Python 包管理工具，用于安装 requirements.txt 中列出的所有依赖。 |
| SQLite 3.35 及以上 | 必需 | 默认数据库引擎，用于存储索引元数据与标签关系，无需额外配置。 |
| BeautifulSoup4 4.10.0 | 必需 | HTML 解析库，用于提取网页标题、摘要与关键词等元数据。 |
| requests 2.28.0 | 必需 | HTTP 客户端库，用于抓取外链页面的 HTML 内容。 |
| whoosh 2.7.4 | 可选 | 全文检索引擎，如不使用检索功能可忽略，但建议安装以提升查询体验。 |
| PyYAML 6.0 | 可选 | 用于解析自定义配置文件，若采用默认 JSON 配置则无需安装。 |
| uvicorn 0.18.0 | 可选 | ASGI 服务器，仅在部署生产环境且使用异步模式时需要。 |

## 文档导航

IndexHub 的文档体系按使用者的角色和任务类型划分为四个层面，每个层面覆盖不同的目录章节，并针对特定问题提供解答。

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 使用者入门 | 安装部署指南、快速开始教程 | 如何下载、安装并首次运行 IndexHub？如何导入第一批外链数据？ |
| 管理员配置 | 配置参数说明、分类管理、用户权限 | 如何修改默认的抓取超时时间？如何新增或删除分类标签？如何设置只读模式？ |
| 开发者扩展 | API 接口文档、插件开发指南、数据模型 | 如何通过 REST API 添加或查询链接？如何编写自定义元数据抓取插件？数据表结构是怎样的？ |
| 运维与调优 | 性能优化建议、日志配置、备份恢复 | 索引数据量达到数万条时如何优化检索速度？如何定期备份数据库？ |

## 资源列表

本节列出 IndexHub 项目收录的全部技术资源原始 URL。所有链接均按来源域名归类，并严格保持原始地址的大小写、协议前缀与路径格式，未做任何改写或规范化处理。

### blog.cmcvrr.cn 文章资源

http://www.blog.cmcvrr.cn/Article/details/322380.sHtML
http://www.blog.cmcvrr.cn/Article/details/37351.sHtML
http://www.blog.cmcvrr.cn/Article/details/096908.sHtML
http://www.blog.cmcvrr.cn/Article/details/44629.sHtML
http://www.blog.cmcvrr.cn/Article/details/6644.sHtML
http://www.blog.cmcvrr.cn/Article/details/4890844.sHtML
http://www.blog.cmcvrr.cn/Article/details/05898.sHtML
http://www.blog.cmcvrr.cn/Article/details/28587.sHtML
http://www.blog.cmcvrr.cn/Article/details/7998296.sHtML
http://www.blog.cmcvrr.cn/Article/details/5199.sHtML
http://www.blog.cmcvrr.cn/Article/details/7731409.sHtML
http://www.blog.cmcvrr.cn/Article/details/1245.sHtML
http://www.blog.cmcvrr.cn/Article/details/179089.sHtML
http://www.blog.cmcvrr.cn/Article/details/8325.sHtML
http://www.blog.cmcvrr.cn/Article/details/3695.sHtML
http://www.blog.cmcvrr.cn/Article/details/82003.sHtML
http://www.blog.cmcvrr.cn/Article/details/1263.sHtML
http://www.blog.cmcvrr.cn/Article/details/7076.sHtML
http://www.blog.cmcvrr.cn/Article/details/2356.sHtML
http://www.blog.cmcvrr.cn/Article/details/9933.sHtML
http://www.blog.cmcvrr.cn/Article/details/44800.sHtML
http://www.blog.cmcvrr.cn/Article/details/19940.sHtML
http://www.blog.cmcvrr.cn/Article/details/4280.sHtML
http://www.blog.cmcvrr.cn/Article/details/956710.sHtML
http://www.blog.cmcvrr.cn/Article/details/03471.sHtML
http://www.blog.cmcvrr.cn/Article/details/345437.sHtML
http://www.blog.cmcvrr.cn/Article/details/10210.sHtML
http://www.blog.cmcvrr.cn/Article/details/9379398.sHtML
http://www.blog.cmcvrr.cn/Article/details/13138.sHtML
http://www.blog.cmcvrr.cn/Article/details/4584137.sHtML
http://www.blog.cmcvrr.cn/Article/details/147213.sHtML
http://www.blog.cmcvrr.cn/Article/details/0281155.sHtML
http://www.blog.cmcvrr.cn/Article/details/0612235.sHtML
http://www.blog.cmcvrr.cn/Article/details/6466263.sHtML
http://www.blog.cmcvrr.cn/Article/details/2109911.sHtML
http://www.blog.cmcvrr.cn/Article/details/92310.sHtML
http://www.blog.cmcvrr.cn/Article/details/057698.sHtML
http://www.blog.cmcvrr.cn/Article/details/868541.sHtML
http://www.blog.cmcvrr.cn/Article/details/3477435.sHtML
http://www.blog.cmcvrr.cn/Article/details/3592.sHtML
http://www.blog.cmcvrr.cn/Article/details/56063.sHtML
http://www.blog.cmcvrr.cn/Article/details/1180.sHtML
http://www.blog.cmcvrr.cn/Article/details/7732.sHtML
http://www.blog.cmcvrr.cn/Article/details/0168.sHtML
http://www.blog.cmcvrr.cn/Article/details/077092.sHtML
http://www.blog.cmcvrr.cn/Article/details/34128.sHtML
http://www.blog.cmcvrr.cn/Article/details/77779.sHtML
http://www.blog.cmcvrr.cn/Article/details/478002.sHtML
http://www.blog.cmcvrr.cn/Article/details/3811.sHtML
http://www.blog.cmcvrr.cn/Article/details/7244510.sHtML
http://www.blog.cmcvrr.cn/Article/details/5096123.sHtML
http://www.blog.cmcvrr.cn/Article/details/4859504.sHtML
http://www.blog.cmcvrr.cn/Article/details/357963.sHtML
http://www.blog.cmcvrr.cn/Article/details/1364.sHtML
http://www.blog.cmcvrr.cn/Article/details/618854.sHtML
http://www.blog.cmcvrr.cn/Article/details/6196882.sHtML
http://www.blog.cmcvrr.cn/Article/details/1464.sHtML
http://www.blog.cmcvrr.cn/Article/details/8708.sHtML
http://www.blog.cmcvrr.cn/Article/details/4047725.sHtML
http://www.blog.cmcvrr.cn/Article/details/99613.sHtML
http://www.blog.cmcvrr.cn/Article/details/51566.sHtML
http://www.blog.cmcvrr.cn/Article/details/70245.sHtML
http://www.blog.cmcvrr.cn/Article/details/4297.sHtML
http://www.blog.cmcvrr.cn/Article/details/38401.sHtML
http://www.blog.cmcvrr.cn/Article/details/1826.sHtML
http://www.blog.cmcvrr.cn/Article/details/1463.sHtML
http://www.blog.cmcvrr.cn/Article/details/7474622.sHtML
http://www.blog.cmcvrr.cn/Article/details/7523747.sHtML
http://www.blog.cmcvrr.cn/Article/details/434095.sHtML
http://www.blog.cmcvrr.cn/Article/details/3520.sHtML
http://www.blog.cmcvrr.cn/Article/details/3443.sHtML
http://www.blog.cmcvrr.cn/Article/details/7598.sHtML
http://www.blog.cmcvrr.cn/Article/details/01245.sHtML
http://www.blog.cmcvrr.cn/Article/details/4245280.sHtML
http://www.blog.cmcvrr.cn/Article/details/1211.sHtML
http://www.blog.cmcvrr.cn/Article/details/411950.sHtML
http://www.blog.cmcvrr.cn/Article/details/816187.sHtML
http://www.blog.cmcvrr.cn/Article/details/77418.sHtML
http://www.blog.cmcvrr.cn/Article/details/549455.sHtML
http://www.blog.cmcvrr.cn/Article/details/18654.sHtML
http://www.blog.cmcvrr.cn/Article/details/69488.sHtML
http://www.blog.cmcvrr.cn/Article/details/0086298.sHtML
http://www.blog.cmcvrr.cn/Article/details/9403966.sHtML
http://www.blog.cmcvrr.cn/Article/details/4456353.sHtML
http://www.blog.cmcvrr.cn/Article/details/0918111.sHtML
http://www.blog.cmcvrr.cn/Article/details/1544.sHtML
http://www.blog.cmcvrr.cn/Article/details/2716641.sHtML
http://www.blog.cmcvrr.cn/Article/details/47971.sHtML
http://www.blog.cmcvrr.cn/Article/details/564441.sHtML
http://www.blog.cmcvrr.cn/Article/details/4467650.sHtML
http://www.blog.cmcvrr.cn/Article/details/97656.sHtML
http://www.blog.cmcvrr.cn/Article/details/0829.sHtML
http://www.blog.cmcvrr.cn/Article/details/95643.sHtML
http://www.blog.cmcvrr.cn/Article/details/2433091.sHtML
http://www.blog.cmcvrr.cn/Article/details/97902.sHtML
http://www.blog.cmcvrr.cn/Article/details/806556.sHtML
http://www.blog.cmcvrr.cn/Article/details/33493.sHtML
http://www.blog.cmcvrr.cn/Article/details/054918.sHtML
http://www.blog.cmcvrr.cn/Article/details/39584.sHtML
http://www.blog.cmcvrr.cn/Article/details/4494.sHtML
http://www.blog.cmcvrr.cn/Article/details/660435.sHtML
http://www.blog.cmcvrr.cn/Article/details/1127.sHtML
http://www.blog.cmcvrr.cn/Article/details/381328.sHtML
http://www.blog.cmcvrr.cn/Article/details/124424.sHtML
http://www.blog.cmcvrr.cn/Article/details/97950.sHtML
http://www.blog.cmcvrr.cn/Article/details/2404.sHtML
http://www.blog.cmcvrr.cn/Article/details/567885.sHtML
http://www.blog.cmcvrr.cn/Article/details/07039.sHtML
http://www.blog.cmcvrr.cn/Article/details/1369.sHtML
http://www.blog.cmcvrr.cn/Article/details/7980646.sHtML
http://www.blog.cmcvrr.cn/Article/details/0128.sHtML
http://www.blog.cmcvrr.cn/Article/details/636788.sHtML
http://www.blog.cmcvrr.cn/Article/details/732333.sHtML
http://www.blog.cmcvrr.cn/Article/details/40605.sHtML
http://www.blog.cmcvrr.cn/Article/details/1866921.sHtML
http://www.blog.cmcvrr.cn/Article/details/2765934.sHtML
http://www.blog.cmcvrr.cn/Article/details/9001810.sHtML
http://www.blog.cmcvrr.cn/Article/details/409141.sHtML
http://www.blog.cmcvrr.cn/Article/details/8366827.sHtML
http://www.blog.cmcvrr.cn/Article/details/19885.sHtML
http://www.blog.cmcvrr.cn/Article/details/5677627.sHtML
http://www.blog.cmcvrr.cn/Article/details/0598141.sHtML
http://www.blog.cmcvrr.cn/Article/details/4347.sHtML
http://www.blog.cmcvrr.cn/Article/details/953631.sHtML
http://www.blog.cmcvrr.cn/Article/details/3981.sHtML
http://www.blog.cmcvrr.cn/Article/details/711555.sHtML
http://www.blog.cmcvrr.cn/Article/details/500751.sHtML
http://www.blog.cmcvrr.cn/Article/details/5892813.sHtML
http://www.blog.cmcvrr.cn/Article/details/0873397.sHtML
http://www.blog.cmcvrr.cn/Article/details/504508.sHtML
http://www.blog.cmcvrr.cn/Article/details/7485.sHtML
http://www.blog.cmcvrr.cn/Article/details/8970621.sHtML
http://www.blog.cmcvrr.cn/Article/details/53630.sHtML
http://www.blog.cmcvrr.cn/Article/details/891159.sHtML
http://www.blog.cmcvrr.cn/Article/details/624085.sHtML
http://www.blog.cmcvrr.cn/Article/details/4443.sHtML
http://www.blog.cmcvrr.cn/Article/details/3138898.sHtML
http://www.blog.cmcvrr.cn/Article/details/1275.sHtML
http://www.blog.cmcvrr.cn/Article/details/3601.sHtML
http://www.blog.cmcvrr.cn/Article/details/8710977.sHtML
http://www.blog.cmcvrr.cn/Article/details/3411040.sHtML
http://www.blog.cmcvrr.cn/Article/details/43746.sHtML
http://www.blog.cmcvrr.cn/Article/details/4448209.sHtML
http://www.blog.cmcvrr.cn/Article/details/78417.sHtML
http://www.blog.cmcvrr.cn/Article/details/035602.sHtML
http://www.blog.cmcvrr.cn/Article/details/3917883.sHtML
http://www.blog.cmcvrr.cn/Article/details/49617.sHtML
http://www.blog.cmcvrr.cn/Article/details/655000.sHtML
http://www.blog.cmcvrr.cn/Article/details/47668.sHtML
http://www.blog.cmcvrr.cn/Article/details/453768.sHtML
http://www.blog.cmcvrr.cn/Article/details/3075697.sHtML
http://www.blog.cmcvrr.cn/Article/details/6544.sHtML
http://www.blog.cmcvrr.cn/Article/details/83470.sHtML
http://www.blog.cmcvrr.cn/Article/details/64319.sHtML
http://www.blog.cmcvrr.cn/Article/details/2556464.sHtML
http://www.blog.cmcvrr.cn/Article/details/0824.sHtML
http://www.blog.cmcvrr.cn/Article/details/3905.sHtML
http://www.blog.cmcvrr.cn/Article/details/05611.sHtML
http://www.blog.cmcvrr.cn/Article/details/4979.sHtML
http://www.blog.cmcvrr.cn/Article/details/11813.sHtML
http://www.blog.cmcvrr.cn/Article/details/0241.sHtML
http://www.blog.cmcvrr.cn/Article/details/74047.sHtML
http://www.blog.cmcvrr.cn/Article/details/023731.sHtML
http://www.blog.cmcvrr.cn/Article/details/438013.sHtML
http://www.blog.cmcvrr.cn/Article/details/2251000.sHtML
http://www.blog.cmcvrr.cn/Article/details/82772.sHtML
http://www.blog.cmcvrr.cn/Article/details/8008945.sHtML
http://www.blog.cmcvrr.cn/Article/details/4525.sHtML
http://www.blog.cmcvrr.cn/Article/details/3954885.sHtML
http://www.blog.cmcvrr.cn/Article/details/6079.sHtML
http://www.blog.cmcvrr.cn/Article/details/06515.sHtML
http://www.blog.cmcvrr.cn/Article/details/242272.sHtML
http://www.blog.cmcvrr.cn/Article/details/828675.sHtML
http://www.blog.cmcvrr.cn/Article/details/64032.sHtML
http://www.blog.cmcvrr.cn/Article/details/1456.sHtML
http://www.blog.cmcvrr.cn/Article/details/5473594.sHtML
http://www.blog.cmcvrr.cn/Article/details/645372.sHtML
http://www.blog.cmcvrr.cn/Article/details/4019.sHtML
http://www.blog.cmcvrr.cn/Article/details/2616.sHtML
http://www.blog.cmcvrr.cn/Article/details/0063379.sHtML
http://www.blog.cmcvrr.cn/Article/details/020419.sHtML
http://www.blog.cmcvrr.cn/Article/details/958331.sHtML
http://www.blog.cmcvrr.cn/Article/details/0650641.sHtML
http://www.blog.cmcvrr.cn/Article/details/81550.sHtML
http://www.blog.cmcvrr.cn/Article/details/2542058.sHtML
http://www.blog.cmcvrr.cn/Article/details/9198.sHtML
http://www.blog.cmcvrr.cn/Article/details/7354.sHtML
http://www.blog.cmcvrr.cn/Article/details/8444.sHtML
http://www.blog.cmcvrr.cn/Article/details/5064.sHtML
http://www.blog.cmcvrr.cn/Article/details/3157257.sHtML
http://www.blog.cmcvrr.cn/Article/details/041991.sHtML
http://www.blog.cmcvrr.cn/Article/details/71696.sHtML
http://www.blog.cmcvrr.cn/Article/details/96018.sHtML
http://www.blog.cmcvrr.cn/Article/details/9973.sHtML
http://www.blog.cmcvrr.cn/Article/details/3312869.sHtML
http://www.blog.cmcvrr.cn/Article/details/2610.sHtML
http://www.blog.cmcvrr.cn/Article/details/140074.sHtML
http://www.blog.cmcvrr.cn/Article/details/64175.sHtML
http://www.blog.cmcvrr.cn/Article/details/204346.sHtML
http://www.blog.cmcvrr.cn/Article/details/464889.sHtML
http://www.blog.cmcvrr.cn/Article/details/1585488.sHtML
http://www.blog.cmcvrr.cn/Article/details/25651.sHtML
http://www.blog.cmcvrr.cn/Article/details/7801.sHtML
http://www.blog.cmcvrr.cn/Article/details/191590.sHtML
http://www.blog.cmcvrr.cn/Article/details/36911.sHtML
http://www.blog.cmcvrr.cn/Article/details/6009.sHtML
http://www.blog.cmcvrr.cn/Article/details/566159.sHtML
http://www.blog.cmcvrr.cn/Article/details/2952826.sHtML
http://www.blog.cmcvrr.cn/Article/details/9539516.sHtML
http://www.blog.cmcvrr.cn/Article/details/826699.sHtML
http://www.blog.cmcvrr.cn/Article/details/849789.sHtML
http://www.blog.cmcvrr.cn/Article/details/002481.sHtML
http://www.blog.cmcvrr.cn/Article/details/7166358.sHtML
http://www.blog.cmcvrr.cn/Article/details/79401.sHtML
http://www.blog.cmcvrr.cn/Article/details/431039.sHtML
http://www.blog.cmcvrr.cn/Article/details/0284.sHtML
http://www.blog.cmcvrr.cn/Article/details/6463842.sHtML
http://www.blog.cmcvrr.cn/Article/details/3152075.sHtML
http://www.blog.cmcvrr.cn/Article/details/290912.sHtML
http://www.blog.cmcvrr.cn/Article/details/1819.sHtML
http://www.blog.cmcvrr.cn/Article/details/0519747.sHtML
http://www.blog.cmcvrr.cn/Article/details/89829.sHtML
http://www.blog.cmcvrr.cn/Article/details/629522.sHtML
http://www.blog.cmcvrr.cn/Article/details/625924.sHtML
http://www.blog.cmcvrr.cn/Article/details/9624035.sHtML
http://www.blog.cmcvrr.cn/Article/details/3509759.sHtML
http://www.blog.cmcvrr.cn/Article/details/6435492.sHtML
http://www.blog.cmcvrr.cn/Article/details/9509.sHtML
http://www.blog.cmcvrr.cn/Article/details/316488.sHtML
http://www.blog.cmcvrr.cn/Article/details/16101.sHtML
http://www.blog.cmcvrr.cn/Article/details/0037878.sHtML
http://www.blog.cmcvrr.cn/Article/details/1140562.sHtML
http://www.blog.cmcvrr.cn/Article/details/34607.sHtML
http://www.blog.cmcvrr.cn/Article/details/6894630.sHtML
http://www.blog.cmcvrr.cn/Article/details/579705.sHtML
http://www.blog.cmcvrr.cn/Article/details/969888.sHtML
http://www.blog.cmcvrr.cn/Article/details/9951897.sHtML
http://www.blog.cmcvrr.cn/Article/details/51514.sHtML
http://www.blog.cmcvrr.cn/Article/details/1602.sHtML
http://www.blog.cmcvrr.cn/Article/details/6329548.sHtML
http://www.blog.cmcvrr.cn/Article/details/69407.sHtML
http://www.blog.cmcvrr.cn/Article/details/7239349.sHtML
http://www.blog.cmcvrr.cn/Article/details/2060.sHtML
http://www.blog.cmcvrr.cn/Article/details/999557.sHtML
http://www.blog.cmcvrr.cn/Article/details/795197.sHtML
http://www.blog.cmcvrr.cn/Article/details/7400.sHtML
http://www.blog.cmcvrr.cn/Article/details/6414211.sHtML
http://www.blog.cmcvrr.cn/Article/details/8190080.sHtML
http://www.blog.cmcvrr.cn/Article/details/9262474.sHtML
http://www.blog.cmcvrr.cn/Article/details/4537.sHtML

## 项目结构

IndexHub 采用模块化的目录组织方式，核心代码与配置文件分离，便于二次开发与定制部署。以下为项目根目录的完整目录树结构。

```
indexhub/
├── app/                                # 主应用模块，包含核心业务逻辑
│   ├── controllers/                    # 控制器层，处理 HTTP 请求与响应
│   │   ├── link_controller.py          # 链接资源的增删改查接口
│   │   └── tag_controller.py           # 标签管理与关联操作接口
│   ├── models/                         # 数据模型层，定义 ORM 实体与关系
│   │   ├── link.py                     # Link 实体，映射外链数据表
│   │   ├── tag.py                      # Tag 实体，标签数据表
│   │   └── category.py                 # Category 实体，分类数据表
│   ├── services/                       # 业务服务层，封装复杂操作逻辑
│   │   ├── fetcher.py                  # 外链元数据抓取服务
│   │   ├── indexer.py                  # 全文索引构建与查询服务
│   │   └── exporter.py                 # 数据导出服务（JSON/CSV/HTML）
│   ├── utils/                          # 工具函数库
│   │   ├── validators.py               # URL 格式校验与规范化工具
│   │   └── parsers.py                  # HTML 内容解析与摘要提取工具
│   └── __init__.py                     # 应用包初始化文件
├── config/                             # 配置目录，存放环境变量与配置文件
│   ├── default.yaml                    # 默认配置（端口、数据库路径、超时时间）
│   └── production.yaml                 # 生产环境覆盖配置
├── data/                               # 数据存储目录
│   ├── indexhub.db                     # SQLite 数据库文件（自动生成）
│   └── whoosh_index/                   # Whoosh 全文索引文件（自动生成）
├── docs/                               # 文档源码目录
│   ├── api/                            # API 接口文档（OpenAPI 规范）
│   ├── guide/                          # 用户指南与运维手册
│   └── examples/                       # 示例数据与导入导出样例
├── scripts/                            # 辅助脚本与运维工具
│   ├── import_links.py                 # 批量导入外链列表的命令行脚本
│   ├── export_static.py                # 生成静态 HTML 目录页的脚本
│   └── clean_duplicates.py             # 清理重复链接的数据维护脚本
├── tests/                              # 单元测试与集成测试目录
│   ├── test_fetcher.py                 # 元数据抓取服务的测试用例
│   ├── test_indexer.py                 # 全文索引服务的测试用例
│   └── fixtures/                       # 测试用的固定数据样本
├── requirements.txt                    # Python 依赖包列表
├── manage.py                           # 项目管理入口（启动、迁移、调试）
└── README.md                           # 项目说明文档（当前文件）
```

## 贡献指南

IndexHub 欢迎来自社区的各种形式的贡献，包括但不限于新增功能、修复缺陷、完善文档和扩充示例数据。请遵循以下步骤参与项目开发。

第一步，在 GitHub 上 Fork 本仓库至个人账户，并将 Fork 后的仓库克隆至本地开发环境。建议在 dev 分支上开展所有修改工作，避免直接操作 main 分支。

第二步，安装开发依赖并配置预提交钩子。运行 `pip install -r requirements-dev.txt` 安装额外开发工具（如 black、pytest、flake8），并执行 `pre-commit install` 启用代码风格自动检查。

第三步，编写或修改代码后，请确保所有现有单元测试通过，并为新增功能补充对应的测试用例。运行 `pytest tests/` 执行全部测试套件，确认无回归问题。

第四步，提交变更时请使用规范的提交信息格式，例如 `feat: add batch import progress bar` 或 `fix: correct URL validation for path segments`。提交信息应简明扼要地描述变更内容与动机。

第五步，推送本地分支至个人 Fork 仓库，并通过 GitHub 界面发起 Pull Request 到主仓库的 dev 分支。PR 描述中请关联相关 Issue（如有），并概述变更的影响范围与测试覆盖情况。

## 常见问题

**Q：IndexHub 能否处理 HTTPS 协议的外链？抓取时是否会因为 SSL 证书问题失败？**

A：IndexHub 底层使用 requests 库，默认会验证 SSL 证书。如果遇到自签名证书或内网环境，可在配置文件中将 `fetcher.verify_ssl` 设置为 `false` 以跳过证书验证。此外，对于 HTTP 协议的外链（如本仓库收录的资源），requests 会自动处理重定向，不会产生额外问题。

**Q：收录的外链数量达到多少时，全文检索性能会出现明显下降？如何优化？**

A：在 SQLite + Whoosh 的默认配置下，单表记录在 5 万条以内时，关键词检索响应时间通常低于 200 毫秒。若预期收录量超过 10 万条，建议迁移至 PostgreSQL 作为数据库后端，并将 Whoosh 索引存放在高速 SSD 存储上。同时，可以启用缓存中间件（如 Redis）对高频查询进行结果缓存。

**Q：元数据抓取模块能否获取需要登录或带有反爬机制的页面内容？**

A：默认的 fetcher 模块仅对公开可访问的页面执行简单的 GET 请求，不支持登录态、Cookie 传递或 JavaScript 渲染。如果目标页面依赖客户端渲染，建议结合 Playwright 或 Selenium 编写自定义抓取插件，并通过 `services/plugin.py` 接口注册到系统中。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 16:28:08
