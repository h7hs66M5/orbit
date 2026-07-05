# WebLink Navigator

WebLink Navigator 是一个面向技术研究者、开源贡献者和内容聚合平台运营者的外链资源导航系统。该项目并非一个简单的书签管理工具，而是一套基于文章标识符（ID）体系构建的深度链接索引中间层。它旨在解决技术社区中优质外链资源分散、检索效率低下以及跨平台引用缺乏统一入口的问题。

项目定位为技术资源的外链汇总站与智能路由网关，通过标准化的 URL 模式将用户请求精准导向具体的文章详情页。其核心目标用户包括需要维护大量技术文档引用的开发者博客作者、需要为开源项目建立外部依赖清单的维护者，以及需要从海量技术文章中提取价值信息的爬虫与数据分析工程师。本系统不产生原创内容，而是通过整理和归类外部资源，为用户提供一个稳定、可扩展、可编程的参考链接集合。

## 功能概览

**统一 ID 路由体系**：系统根据文章唯一标识符生成标准的访问路径，所有外部资源均通过统一的域名和路径模式进行引用，确保链接结构的一致性和可预测性。

**多层级详情页渲染**：每个文章 ID 对应一个独立的详情页面，页面中包含文章标题、摘要、正文内容、作者信息、发表日期及版权声明等完整元数据字段。

**批量链接状态检测**：内置链接有效性检查模块，可定期对资源列表中的 URL 进行 HTTP 状态码扫描，自动标记失效或重定向的链接。

**按类别分类导航**：支持将收录的外链按技术领域、内容类型或来源站点进行逻辑分组，提供多维度筛选与排序功能，方便用户快速定位相关资源。

**全文检索与过滤**：基于文章标题、ID 和内容摘要构建倒排索引，支持关键词搜索和正则表达式过滤，提高在海量链接中的信息查找效率。

**RESTful API 接口**：对外提供基于 JSON 格式的标准化 API 端点，支持第三方应用通过程序化方式获取链接列表、文章详情及分类目录数据。

**访问统计与热度分析**：记录每个链接的点击次数、引用来源和访问时间分布，生成简单的热度排行，辅助判断资源的实际参考价值。

## 应用场景

**技术博客的参考文献管理**：技术博主在撰写深度教程或解决方案时，需要在文末列出大量外部引用链接。WebLink Navigator 可作为一个集中的链接仓库，博主只需在文章中引用系统生成的标准化 URL，既保证了链接的统一性，又便于后期统一更新或修复失效链接。

**开源项目的外部依赖清单**：开源软件通常依赖于第三方库、工具或文档站点。项目维护者可使用本系统整理所有外部依赖的官方文档链接、镜像源地址和社区讨论帖，形成一份结构化的依赖资源清单，方便新贡献者快速了解项目的生态依赖。

**数据分析语料采集入口**：数据科学家或 NLP 工程师在构建技术语料库时，需要从大量技术文章中提取文本内容。本系统提供的链接集合可作为爬虫的初始种子 URL 列表，配合 ID 路由规则实现增量式采集，降低种子链接的管理成本。

**企业内部技术知识库索引**：企业研发团队可将内部沉淀的技术文档、故障排查记录和最佳实践文章通过本系统的 ID 映射机制统一编目，与外部公开资源形成互补，构建内部专属的技术知识导航页。

## 快速开始

以下步骤指导您在本地环境中快速部署 WebLink Navigator 服务。

```bash
# 克隆项目仓库至本地
git clone https://github.com/weblink-navigator/weblink-navigator.git

# 进入项目根目录
cd weblink-navigator

# 安装项目依赖（使用 pip 和 requirements.txt）
pip install -r requirements.txt

# 初始化数据库表结构并导入示例链接数据
python manage.py migrate
python manage.py loaddata initial_links.json

# 启动本地开发服务器，默认监听 8000 端口
python manage.py runserver 0.0.0.0:8000
```

服务启动后，访问 http://localhost:8000 即可进入系统首页。您可以通过 `/Article/details/{id}.sHtML` 的路径格式访问具体的文章详情页，其中 `{id}` 替换为对应的文章数字标识符。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.9 及以上 | 核心运行时环境，用于执行后端逻辑与 API 服务 |
| Django | 4.2 LTS | 主 Web 框架，提供 ORM、路由、模板渲染及管理后台 |
| SQLite / PostgreSQL | SQLite 3.35+ / PostgreSQL 13+ | 数据存储引擎，开发环境默认使用 SQLite，生产环境建议切换至 PostgreSQL |
| Redis | 6.2 及以上 | 缓存与会话存储后端，用于提升高频访问场景下的响应性能（可选，但强烈推荐） |
| Celery | 5.3 及以上 | 分布式任务队列，用于执行链接状态检测、访问统计等异步后台任务 |
| uWSGI / Gunicorn | uWSGI 2.0+ / Gunicorn 21+ | WSGI 生产级应用服务器，用于部署时替代内置 runserver |
| Nginx | 1.22 及以上 | 反向代理与静态文件服务，用于生产环境的路由转发和资源缓存 |
| Git | 2.30 及以上 | 版本控制工具，用于克隆仓库和版本回滚 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | /docs/user-guide/ | 如何添加新的链接条目？如何按分类浏览资源？如何查看链接的访问统计？ |
| 开发指南 | /docs/developer-guide/ | 系统的目录结构是怎样的？如何扩展新的文章详情页模板？API 接口的认证方式是什么？ |
| 部署运维 | /docs/deployment/ | 生产环境需要哪些系统依赖？如何配置 Nginx 和 uWSGI 进行高并发部署？如何备份和恢复数据库？ |
| 架构设计 | /docs/architecture/ | 系统的整体分层设计是怎样的？ID 路由机制如何实现？缓存策略如何保证数据一致性？ |

## 资源列表

以下为 WebLink Navigator 项目当前收录的全部外部资源链接，按来源分类排列。所有链接均保留原始格式，未经任何改写。

技术文章聚合

http://www.blog.cmcvrr.cn/Article/details/9845.sHtML
http://www.blog.cmcvrr.cn/Article/details/6266971.sHtML
http://www.blog.cmcvrr.cn/Article/details/1879.sHtML
http://www.blog.cmcvrr.cn/Article/details/0642501.sHtML
http://www.blog.cmcvrr.cn/Article/details/4270983.sHtML
http://www.blog.cmcvrr.cn/Article/details/075873.sHtML
http://www.blog.cmcvrr.cn/Article/details/92979.sHtML
http://www.blog.cmcvrr.cn/Article/details/5753342.sHtML
http://www.blog.cmcvrr.cn/Article/details/9205458.sHtML
http://www.blog.cmcvrr.cn/Article/details/6322742.sHtML
http://www.blog.cmcvrr.cn/Article/details/351201.sHtML
http://www.blog.cmcvrr.cn/Article/details/971572.sHtML
http://www.blog.cmcvrr.cn/Article/details/4929065.sHtML
http://www.blog.cmcvrr.cn/Article/details/5741239.sHtML
http://www.blog.cmcvrr.cn/Article/details/8296.sHtML
http://www.blog.cmcvrr.cn/Article/details/41299.sHtML
http://www.blog.cmcvrr.cn/Article/details/93640.sHtML
http://www.blog.cmcvrr.cn/Article/details/8299899.sHtML
http://www.blog.cmcvrr.cn/Article/details/7451.sHtML
http://www.blog.cmcvrr.cn/Article/details/22959.sHtML
http://www.blog.cmcvrr.cn/Article/details/5417.sHtML
http://www.blog.cmcvrr.cn/Article/details/9565142.sHtML
http://www.blog.cmcvrr.cn/Article/details/513202.sHtML
http://www.blog.cmcvrr.cn/Article/details/6710933.sHtML
http://www.blog.cmcvrr.cn/Article/details/3955.sHtML
http://www.blog.cmcvrr.cn/Article/details/322273.sHtML
http://www.blog.cmcvrr.cn/Article/details/5490.sHtML
http://www.blog.cmcvrr.cn/Article/details/7770518.sHtML
http://www.blog.cmcvrr.cn/Article/details/923759.sHtML
http://www.blog.cmcvrr.cn/Article/details/7323.sHtML
http://www.blog.cmcvrr.cn/Article/details/1689097.sHtML
http://www.blog.cmcvrr.cn/Article/details/624169.sHtML
http://www.blog.cmcvrr.cn/Article/details/01559.sHtML
http://www.blog.cmcvrr.cn/Article/details/0720895.sHtML
http://www.blog.cmcvrr.cn/Article/details/12317.sHtML
http://www.blog.cmcvrr.cn/Article/details/95363.sHtML
http://www.blog.cmcvrr.cn/Article/details/235280.sHtML
http://www.blog.cmcvrr.cn/Article/details/6427434.sHtML
http://www.blog.cmcvrr.cn/Article/details/11900.sHtML
http://www.blog.cmcvrr.cn/Article/details/9407.sHtML
http://www.blog.cmcvrr.cn/Article/details/4703.sHtML
http://www.blog.cmcvrr.cn/Article/details/0153407.sHtML
http://www.blog.cmcvrr.cn/Article/details/5373519.sHtML
http://www.blog.cmcvrr.cn/Article/details/943239.sHtML
http://www.blog.cmcvrr.cn/Article/details/530383.sHtML
http://www.blog.cmcvrr.cn/Article/details/5330.sHtML
http://www.blog.cmcvrr.cn/Article/details/71008.sHtML
http://www.blog.cmcvrr.cn/Article/details/924747.sHtML
http://www.blog.cmcvrr.cn/Article/details/7615.sHtML
http://www.blog.cmcvrr.cn/Article/details/4228.sHtML
http://www.blog.cmcvrr.cn/Article/details/9696.sHtML
http://www.blog.cmcvrr.cn/Article/details/2692009.sHtML
http://www.blog.cmcvrr.cn/Article/details/0306.sHtML
http://www.blog.cmcvrr.cn/Article/details/2885189.sHtML
http://www.blog.cmcvrr.cn/Article/details/941818.sHtML
http://www.blog.cmcvrr.cn/Article/details/157864.sHtML
http://www.blog.cmcvrr.cn/Article/details/838609.sHtML
http://www.blog.cmcvrr.cn/Article/details/50281.sHtML
http://www.blog.cmcvrr.cn/Article/details/3360.sHtML
http://www.blog.cmcvrr.cn/Article/details/5805252.sHtML
http://www.blog.cmcvrr.cn/Article/details/106132.sHtML
http://www.blog.cmcvrr.cn/Article/details/516519.sHtML
http://www.blog.cmcvrr.cn/Article/details/31304.sHtML
http://www.blog.cmcvrr.cn/Article/details/6172.sHtML
http://www.blog.cmcvrr.cn/Article/details/2432539.sHtML
http://www.blog.cmcvrr.cn/Article/details/8074795.sHtML
http://www.blog.cmcvrr.cn/Article/details/633822.sHtML
http://www.blog.cmcvrr.cn/Article/details/4767581.sHtML
http://www.blog.cmcvrr.cn/Article/details/41447.sHtML
http://www.blog.cmcvrr.cn/Article/details/80509.sHtML
http://www.blog.cmcvrr.cn/Article/details/19927.sHtML
http://www.blog.cmcvrr.cn/Article/details/7869668.sHtML
http://www.blog.cmcvrr.cn/Article/details/0252574.sHtML
http://www.blog.cmcvrr.cn/Article/details/309290.sHtML
http://www.blog.cmcvrr.cn/Article/details/027464.sHtML
http://www.blog.cmcvrr.cn/Article/details/0514503.sHtML
http://www.blog.cmcvrr.cn/Article/details/9057587.sHtML
http://www.blog.cmcvrr.cn/Article/details/0849656.sHtML
http://www.blog.cmcvrr.cn/Article/details/33853.sHtML
http://www.blog.cmcvrr.cn/Article/details/5258748.sHtML
http://www.blog.cmcvrr.cn/Article/details/8505326.sHtML
http://www.blog.cmcvrr.cn/Article/details/83838.sHtML
http://www.blog.cmcvrr.cn/Article/details/9189.sHtML
http://www.blog.cmcvrr.cn/Article/details/7868.sHtML
http://www.blog.cmcvrr.cn/Article/details/3839.sHtML
http://www.blog.cmcvrr.cn/Article/details/63160.sHtML
http://www.blog.cmcvrr.cn/Article/details/5127781.sHtML
http://www.blog.cmcvrr.cn/Article/details/724217.sHtML
http://www.blog.cmcvrr.cn/Article/details/1318142.sHtML
http://www.blog.cmcvrr.cn/Article/details/2197.sHtML
http://www.blog.cmcvrr.cn/Article/details/194259.sHtML
http://www.blog.cmcvrr.cn/Article/details/802270.sHtML
http://www.blog.cmcvrr.cn/Article/details/0270.sHtML
http://www.blog.cmcvrr.cn/Article/details/2245.sHtML
http://www.blog.cmcvrr.cn/Article/details/79776.sHtML
http://www.blog.cmcvrr.cn/Article/details/04421.sHtML
http://www.blog.cmcvrr.cn/Article/details/2527005.sHtML
http://www.blog.cmcvrr.cn/Article/details/43735.sHtML
http://www.blog.cmcvrr.cn/Article/details/9565.sHtML
http://www.blog.cmcvrr.cn/Article/details/43243.sHtML
http://www.blog.cmcvrr.cn/Article/details/3504.sHtML
http://www.blog.cmcvrr.cn/Article/details/9283.sHtML
http://www.blog.cmcvrr.cn/Article/details/215097.sHtML
http://www.blog.cmcvrr.cn/Article/details/8830451.sHtML
http://www.blog.cmcvrr.cn/Article/details/89235.sHtML
http://www.blog.cmcvrr.cn/Article/details/02923.sHtML
http://www.blog.cmcvrr.cn/Article/details/366119.sHtML
http://www.blog.cmcvrr.cn/Article/details/43310.sHtML
http://www.blog.cmcvrr.cn/Article/details/55620.sHtML
http://www.blog.cmcvrr.cn/Article/details/07743.sHtML
http://www.blog.cmcvrr.cn/Article/details/2955.sHtML
http://www.blog.cmcvrr.cn/Article/details/3522933.sHtML
http://www.blog.cmcvrr.cn/Article/details/51344.sHtML
http://www.blog.cmcvrr.cn/Article/details/0082846.sHtML
http://www.blog.cmcvrr.cn/Article/details/2328737.sHtML
http://www.blog.cmcvrr.cn/Article/details/46515.sHtML
http://www.blog.cmcvrr.cn/Article/details/4838062.sHtML
http://www.blog.cmcvrr.cn/Article/details/19277.sHtML
http://www.blog.cmcvrr.cn/Article/details/147426.sHtML
http://www.blog.cmcvrr.cn/Article/details/1490.sHtML
http://www.blog.cmcvrr.cn/Article/details/880347.sHtML
http://www.blog.cmcvrr.cn/Article/details/3478752.sHtML
http://www.blog.cmcvrr.cn/Article/details/198823.sHtML
http://www.blog.cmcvrr.cn/Article/details/50032.sHtML
http://www.blog.cmcvrr.cn/Article/details/35075.sHtML
http://www.blog.cmcvrr.cn/Article/details/820972.sHtML
http://www.blog.cmcvrr.cn/Article/details/963900.sHtML
http://www.blog.cmcvrr.cn/Article/details/7071.sHtML
http://www.blog.cmcvrr.cn/Article/details/3162940.sHtML
http://www.blog.cmcvrr.cn/Article/details/39473.sHtML
http://www.blog.cmcvrr.cn/Article/details/9016.sHtML
http://www.blog.cmcvrr.cn/Article/details/35149.sHtML
http://www.blog.cmcvrr.cn/Article/details/147890.sHtML
http://www.blog.cmcvrr.cn/Article/details/674552.sHtML
http://www.blog.cmcvrr.cn/Article/details/077701.sHtML
http://www.blog.cmcvrr.cn/Article/details/6163.sHtML
http://www.blog.cmcvrr.cn/Article/details/5644945.sHtML
http://www.blog.cmcvrr.cn/Article/details/4849.sHtML
http://www.blog.cmcvrr.cn/Article/details/97631.sHtML
http://www.blog.cmcvrr.cn/Article/details/11047.sHtML
http://www.blog.cmcvrr.cn/Article/details/73435.sHtML
http://www.blog.cmcvrr.cn/Article/details/5291948.sHtML
http://www.blog.cmcvrr.cn/Article/details/7963343.sHtML
http://www.blog.cmcvrr.cn/Article/details/3455.sHtML
http://www.blog.cmcvrr.cn/Article/details/86363.sHtML
http://www.blog.cmcvrr.cn/Article/details/482366.sHtML
http://www.blog.cmcvrr.cn/Article/details/8134945.sHtML
http://www.blog.cmcvrr.cn/Article/details/54833.sHtML
http://www.blog.cmcvrr.cn/Article/details/9977.sHtML
http://www.blog.cmcvrr.cn/Article/details/4067827.sHtML
http://www.blog.cmcvrr.cn/Article/details/6201.sHtML
http://www.blog.cmcvrr.cn/Article/details/6295757.sHtML
http://www.blog.cmcvrr.cn/Article/details/160891.sHtML
http://www.blog.cmcvrr.cn/Article/details/42328.sHtML
http://www.blog.cmcvrr.cn/Article/details/9395.sHtML
http://www.blog.cmcvrr.cn/Article/details/69986.sHtML
http://www.blog.cmcvrr.cn/Article/details/53119.sHtML
http://www.blog.cmcvrr.cn/Article/details/5948.sHtML
http://www.blog.cmcvrr.cn/Article/details/8020009.sHtML
http://www.blog.cmcvrr.cn/Article/details/9323235.sHtML
http://www.blog.cmcvrr.cn/Article/details/171445.sHtML
http://www.blog.cmcvrr.cn/Article/details/72350.sHtML
http://www.blog.cmcvrr.cn/Article/details/60494.sHtML
http://www.blog.cmcvrr.cn/Article/details/770482.sHtML
http://www.blog.cmcvrr.cn/Article/details/7511.sHtML
http://www.blog.cmcvrr.cn/Article/details/67374.sHtML
http://www.blog.cmcvrr.cn/Article/details/9652783.sHtML
http://www.blog.cmcvrr.cn/Article/details/8393.sHtML
http://www.blog.cmcvrr.cn/Article/details/7860.sHtML
http://www.blog.cmcvrr.cn/Article/details/887574.sHtML
http://www.blog.cmcvrr.cn/Article/details/7050.sHtML
http://www.blog.cmcvrr.cn/Article/details/0210708.sHtML
http://www.blog.cmcvrr.cn/Article/details/5942891.sHtML
http://www.blog.cmcvrr.cn/Article/details/2237.sHtML
http://www.blog.cmcvrr.cn/Article/details/6352409.sHtML
http://www.blog.cmcvrr.cn/Article/details/09365.sHtML
http://www.blog.cmcvrr.cn/Article/details/7337654.sHtML
http://www.blog.cmcvrr.cn/Article/details/6912.sHtML
http://www.blog.cmcvrr.cn/Article/details/0357912.sHtML
http://www.blog.cmcvrr.cn/Article/details/327718.sHtML
http://www.blog.cmcvrr.cn/Article/details/40682.sHtML
http://www.blog.cmcvrr.cn/Article/details/47360.sHtML
http://www.blog.cmcvrr.cn/Article/details/1260849.sHtML
http://www.blog.cmcvrr.cn/Article/details/16552.sHtML
http://www.blog.cmcvrr.cn/Article/details/7397.sHtML
http://www.blog.cmcvrr.cn/Article/details/4391.sHtML
http://www.blog.cmcvrr.cn/Article/details/350200.sHtML
http://www.blog.cmcvrr.cn/Article/details/70827.sHtML
http://www.blog.cmcvrr.cn/Article/details/902771.sHtML
http://www.blog.cmcvrr.cn/Article/details/887280.sHtML
http://www.blog.cmcvrr.cn/Article/details/38611.sHtML
http://www.blog.cmcvrr.cn/Article/details/2630.sHtML
http://www.blog.cmcvrr.cn/Article/details/2906.sHtML
http://www.blog.cmcvrr.cn/Article/details/1334030.sHtML
http://www.blog.cmcvrr.cn/Article/details/05701.sHtML
http://www.blog.cmcvrr.cn/Article/details/016911.sHtML
http://www.blog.cmcvrr.cn/Article/details/6473.sHtML
http://www.blog.cmcvrr.cn/Article/details/5142.sHtML
http://www.blog.cmcvrr.cn/Article/details/0293758.sHtML
http://www.blog.cmcvrr.cn/Article/details/511829.sHtML
http://www.blog.cmcvrr.cn/Article/details/3884.sHtML
http://www.blog.cmcvrr.cn/Article/details/90400.sHtML
http://www.blog.cmcvrr.cn/Article/details/9243839.sHtML
http://www.blog.cmcvrr.cn/Article/details/0775.sHtML
http://www.blog.cmcvrr.cn/Article/details/142943.sHtML
http://www.blog.cmcvrr.cn/Article/details/3879.sHtML
http://www.blog.cmcvrr.cn/Article/details/4827631.sHtML
http://www.blog.cmcvrr.cn/Article/details/61676.sHtML
http://www.blog.cmcvrr.cn/Article/details/63579.sHtML
http://www.blog.cmcvrr.cn/Article/details/9112615.sHtML
http://www.blog.cmcvrr.cn/Article/details/0855108.sHtML
http://www.blog.cmcvrr.cn/Article/details/9647157.sHtML
http://www.blog.cmcvrr.cn/Article/details/6229990.sHtML
http://www.blog.cmcvrr.cn/Article/details/0587.sHtML
http://www.blog.cmcvrr.cn/Article/details/2504.sHtML
http://www.blog.cmcvrr.cn/Article/details/8266.sHtML
http://www.blog.cmcvrr.cn/Article/details/6897192.sHtML
http://www.blog.cmcvrr.cn/Article/details/50064.sHtML
http://www.blog.cmcvrr.cn/Article/details/0260333.sHtML
http://www.blog.cmcvrr.cn/Article/details/367975.sHtML
http://www.blog.cmcvrr.cn/Article/details/871335.sHtML
http://www.blog.cmcvrr.cn/Article/details/7348377.sHtML
http://www.blog.cmcvrr.cn/Article/details/0395.sHtML
http://www.blog.cmcvrr.cn/Article/details/0389.sHtML
http://www.blog.cmcvrr.cn/Article/details/66294.sHtML
http://www.blog.cmcvrr.cn/Article/details/02989.sHtML
http://www.blog.cmcvrr.cn/Article/details/783812.sHtML
http://www.blog.cmcvrr.cn/Article/details/09449.sHtML
http://www.blog.cmcvrr.cn/Article/details/77773.sHtML
http://www.blog.cmcvrr.cn/Article/details/224401.sHtML
http://www.blog.cmcvrr.cn/Article/details/429031.sHtML
http://www.blog.cmcvrr.cn/Article/details/8295.sHtML
http://www.blog.cmcvrr.cn/Article/details/5458.sHtML
http://www.blog.cmcvrr.cn/Article/details/9523078.sHtML
http://www.blog.cmcvrr.cn/Article/details/7481143.sHtML
http://www.blog.cmcvrr.cn/Article/details/46045.sHtML
http://www.blog.cmcvrr.cn/Article/details/6712026.sHtML
http://www.blog.cmcvrr.cn/Article/details/8817.sHtML
http://www.blog.cmcvrr.cn/Article/details/442342.sHtML
http://www.blog.cmcvrr.cn/Article/details/9726353.sHtML
http://www.blog.cmcvrr.cn/Article/details/3732937.sHtML
http://www.blog.cmcvrr.cn/Article/details/4442932.sHtML
http://www.blog.cmcvrr.cn/Article/details/620181.sHtML
http://www.blog.cmcvrr.cn/Article/details/2315561.sHtML
http://www.blog.cmcvrr.cn/Article/details/7643229.sHtML
http://www.blog.cmcvrr.cn/Article/details/0345851.sHtML
http://www.blog.cmcvrr.cn/Article/details/757716.sHtML
http://www.blog.cmcvrr.cn/Article/details/0947.sHtML
http://www.blog.cmcvrr.cn/Article/details/5591452.sHtML
http://www.blog.cmcvrr.cn/Article/details/075798.sHtML

## 项目结构

```
weblink-navigator/
├── manage.py                      # Django 项目管理入口，用于启动服务、迁移数据库等
├── requirements.txt               # Python 依赖清单，包含 Django、Celery、Redis 客户端等
├── config/                        # 项目全局配置目录
│   ├── settings.py                # 主配置文件，包含数据库连接、中间件、INSTALLED_APPS 等
│   ├── urls.py                    # 根 URL 路由映射，定义 /Article/details/ 模式的路由规则
│   ├── celery.py                  # Celery 应用实例配置，定义任务队列名称和代理地址
│   └── wsgi.py                    # WSGI 网关入口，供 uWSGI 或 Gunicorn 调用
├── apps/                          # 所有自定义应用存放目录
│   ├── articles/                  # 文章详情页核心应用
│   │   ├── models.py              # 文章数据模型，包含标题、正文、发布日期、作者外键等字段
│   │   ├── views.py               # 详情页视图函数，根据 ID 查询数据库并渲染模板
│   │   ├── urls.py                # 应用内路由，匹配 /Article/details/<id>.sHtML 格式的请求
│   │   ├── serializers.py         # Django REST Framework 序列化器，用于 API 输出
│   │   └── admin.py               # 后台管理配置，注册 Article 模型至 Admin 界面
│   ├── categories/                # 分类管理应用，维护技术领域、内容类型等分类维度
│   │   ├── models.py              # 分类树模型，支持父子级无限嵌套
│   │   └── utils.py               # 分类路径生成与解析工具函数
│   ├── stats/                     # 访问统计与热度分析应用
│   │   ├── models.py              # 点击日志模型，记录 IP、时间、Referer 等字段
│   │   ├── tasks.py               # Celery 异步任务，定时聚合统计并更新热度缓存
│   │   └── middleware.py          # 请求拦截中间件，记录每个详情页的访问事件
│   └── apis/                      # RESTful API 应用，对外提供 JSON 接口
│       ├── views.py               # 基于类视图的 API 端点，支持分页和过滤
│       └── permissions.py         # 权限控制类，定义 API 访问的认证策略
├── templates/                     # 全局 HTML 模板存放目录
│   ├── base.html                  # 基础布局模板，包含公共头部、尾部及 CSS/JS 引用
│   └── articles/                  # 文章相关模板子目录
│       └── detail.html            # 文章详情页主体模板，渲染标题、正文及元数据
├── static/                        # 静态资源目录，包含 CSS、JavaScript 和图片文件
│   ├── css/                       # 基于 Bootstrap 5 的自定义样式表
│   ├── js/                        # 前端交互脚本，包含搜索联想和统计图表渲染
│   └── images/                    # 项目 Logo 及默认占位图
├── scripts/                       # 运维与辅助脚本
│   ├── health_check.py            # 链接健康度检查脚本，扫描资源列表并记录异常
│   └── import_links.py            # 批量导入外部链接至数据库的脚本，支持 CSV 格式
├── logs/                          # 日志文件存储目录（默认 git 忽略）
│   ├── access.log                 # 访问日志，记录所有 HTTP 请求
│   └── error.log                  # 错误日志，记录系统异常和数据库查询错误
├── docker-compose.yml             # Docker Compose 编排文件，定义 web、redis、postgres 等服务
└── Dockerfile                     # 项目容器镜像构建文件，基于 python:3.9-slim 基础镜像
```

## 贡献指南

我们欢迎并鼓励社区开发者为本项目提交贡献。无论是修复缺陷、优化性能、补充文档还是增加新特性，请遵循以下标准化流程以确保代码质量和协作效率。

第一，在 GitHub 上 Fork 本仓库至您的个人账户，并将 Fork 后的仓库克隆至本地开发环境。请确保您的本地分支与主仓库的 main 分支保持同步，避免出现大量冲突。

第二，创建新的功能分支或缺陷修复分支，分支命名应遵循语义化规范，例如 `feature/add-api-pagination` 或 `fix/routing-404-issue`。所有代码改动必须在此分支上进行，严禁直接向 main 分支提交。

第三，编写或修改代码后，请确保通过项目的全部单元测试用例。运行 `python manage.py test` 命令执行测试套件，并保证测试覆盖率达到 80% 以上。新增功能必须附带对应的测试用例。

第四，提交代码前，请清理调试语句和无关的临时文件，并按照 Conventional Commits 规范撰写提交信息，格式为 `<type>(<scope>): <subject>`，其中 type 可选值包括 feat、fix、docs、style、refactor、perf、test、chore 等。

第五，发起 Pull Request 至主仓库的 main 分支，并在 PR 描述中清晰说明本次改动的目的、实现方式、测试结果以及可能的破坏性影响。PR 将由项目维护者进行 Code Review，通过后即合并入主干。

## 常见问题

Q: 访问文章详情页时返回 404 状态码，但确认该 ID 存在于数据库中，是什么原因？

A: 此情况通常由 URL 路径大小写敏感或后缀名格式不匹配导致。系统路由规则严格匹配 `/Article/details/{id}.sHtML` 格式，其中 `sHtML` 后缀区分大小写。请检查请求路径是否与规则完全一致，例如正确格式为 `/Article/details/9845.sHtML`。此外，请确认数据库中的 ID 字段类型为整数，若传入带有前导零的字符串（如 `"0041"`），系统会自动转换为整型 `41` 进行查询，若数据库中不存在该整型 ID 同样会返回 404。

Q: 如何批量添加新的外链资源到系统中，而不需要通过后台管理界面逐条录入？

A: 项目提供了命令行导入脚本 `scripts/import_links.py`，支持从 CSV 或 JSON 格式的文件中批量读取链接数据并写入数据库。您需要准备一个包含 `title`、`url`、`category_id` 和 `description` 字段的数据文件，然后执行 `python scripts/import_links.py --file links.csv --format csv` 命令。系统会自动进行去重校验，若某条链接的 URL 已存在于数据库中，则会跳过并输出警告日志。

Q: 生产环境下，链接健康度检测任务如何配置周期性自动执行？

A: 系统基于 Celery 实现了周期性任务调度。您需要在生产服务器上启动 Celery Beat 服务，并在 `config/settings.py` 中配置 `CELERY_BEAT_SCHEDULE` 选项，将 `health_check` 任务设置为每天凌晨 2:00 执行。具体配置示例为：`'health-check': {'task': 'stats.tasks.health_check', 'schedule': crontab(hour=2, minute=0)}`。执行结果会通过日志记录，并可配置邮件告警通知维护人员。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 16:28:06
