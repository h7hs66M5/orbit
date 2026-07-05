# BlogCMCVRR Article Gateway

BlogCMCVRR Article Gateway 是一个轻量级的技术文章聚合与导航系统，专为技术社区、开发者博客和内容创作者设计。该项目将分散的深度技术文章进行结构化索引，提供统一的访问入口和分类浏览能力，帮助技术从业者快速定位特定主题的高质量内容。

本项目定位于中大型技术内容库的导航层，不替代原有博客系统，而是通过构建轻量级元数据索引，解决文章检索效率低、主题分散、收藏管理不便等痛点。目标用户包括技术团队内部知识库管理者、独立博客作者、以及需要定期跟进特定技术领域的工程师。

## 功能概览

**统一文章入口**：将分散在不同目录和编号下的技术文章通过单一网关进行聚合，提供一致的访问路径。

**分类索引引擎**：根据文章元数据自动生成分类标签，支持按技术领域、难度等级、发布时间等多维度筛选。

**全文检索支持**：内置倒排索引，支持对文章标题、摘要和正文内容进行关键词匹配，返回相关度排序结果。

**阅读状态跟踪**：记录用户的浏览历史、收藏标记和阅读进度，支持断点续读和待读列表管理。

**外部链接健康检查**：定期检测资源列表中各文章链接的可达性，自动标记失效或重定向的条目。

**批量导入导出**：支持通过 CSV 或 JSON 格式批量导入文章元数据，也支持将索引数据导出为静态站点文件。

**响应式阅读界面**：针对桌面端和移动端分别优化排版布局，代码块支持语法高亮和行号显示。

**访问统计分析**：基于文章访问日志生成阅读趋势图表，提供热门文章榜单和时段分布数据。

## 应用场景

**技术团队内部知识库导航**：研发团队可将历史技术方案、故障复盘报告、架构设计文档等通过本系统统一编目，新成员入职时可按照分类体系快速了解团队知识资产全貌，避免在零散文档中迷失。

**独立开发者博客内容管理**：个人技术博主使用本系统管理多年积累的数百篇博文，通过检索和分类功能快速找回自己曾写过的特定解决方案，也便于读者按主题订阅内容更新。

**技术社区资源推荐位**：社区运营人员将优质外部技术文章链接纳入本系统索引，配合社区原有的讨论区形成"外部精品内容 + 内部深度讨论"的互补格局，降低用户发现优质内容的成本。

**开源项目文档辅助检索**：大型开源项目可将周边生态的教程、案例分析和最佳实践文章通过本系统聚合，作为官方文档之外的补充学习资源通道，缓解文档站点检索压力。

## 快速开始

以下命令序列可在 Ubuntu 22.04 / macOS Monterey 及以上环境中完成项目的克隆、依赖安装和服务启动。

```bash
git clone https://github.com/your-org/blog-cmcvrr-gateway.git
cd blog-cmcvrr-gateway
pip install -r requirements.txt
python manage.py migrate
python manage.py loaddata articles/fixtures/initial_data.json
python manage.py runserver 0.0.0.0:8000
```

生产环境部署时，建议使用 gunicorn 配合 Nginx 反向代理，具体配置参考 `deploy/` 目录下的示例文件。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---------|---------|------|
| Python | 3.10 及以上 | 核心运行环境，建议使用 pyenv 管理 |
| Django | 4.2 LTS | Web 框架，用于路由、ORM 和模板渲染 |
| PostgreSQL | 14 及以上 | 主数据库，存储文章元数据和用户状态 |
| Redis | 7.0 及以上 | 缓存会话和检索结果，提升响应速度 |
| Elasticsearch | 8.x | 全文检索引擎，可选但强烈建议启用 |
| nodejs | 18.x | 仅用于前端资源构建（Sass 编译） |
| nginx | 1.24 | 生产环境反向代理和静态资源服务 |
| supervisor | 4.2 | 进程守护，确保服务持续运行 |
| git | 2.25 | 版本控制和更新拉取 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|-----------|
| 用户手册 | docs/user-guide/ | 如何浏览文章、使用检索、管理收藏和阅读历史 |
| 管理员指南 | docs/admin-guide/ | 如何配置索引规则、管理文章条目、查看统计报表 |
| 开发参考 | docs/developer-guide/ | 如何扩展分类器、自定义检索算法、开发新插件 |
| API 文档 | docs/api-reference/ | RESTful API 的端点说明、请求参数和响应格式 |
| 部署运维 | docs/deployment/ | 生产环境搭建、性能调优、日志配置和备份策略 |
| 贡献规范 | docs/contributing/ | 代码风格、测试要求、提交信息和 PR 流程 |

## 资源列表

### 核心文章资源

以下链接为 BlogCMCVVR 平台收录的技术文章条目，按原始地址一字不差列示：

http://www.blog.cmcvrr.cn/Article/details/79961.sHtML
http://www.blog.cmcvrr.cn/Article/details/075169.sHtML
http://www.blog.cmcvrr.cn/Article/details/328146.sHtML
http://www.blog.cmcvrr.cn/Article/details/82939.sHtML
http://www.blog.cmcvrr.cn/Article/details/2168054.sHtML
http://www.blog.cmcvrr.cn/Article/details/9898.sHtML
http://www.blog.cmcvrr.cn/Article/details/7276.sHtML
http://www.blog.cmcvrr.cn/Article/details/6815.sHtML
http://www.blog.cmcvrr.cn/Article/details/71394.sHtML
http://www.blog.cmcvrr.cn/Article/details/37605.sHtML
http://www.blog.cmcvrr.cn/Article/details/74874.sHtML
http://www.blog.cmcvrr.cn/Article/details/22227.sHtML
http://www.blog.cmcvrr.cn/Article/details/1045447.sHtML
http://www.blog.cmcvrr.cn/Article/details/704395.sHtML
http://www.blog.cmcvrr.cn/Article/details/749264.sHtML
http://www.blog.cmcvrr.cn/Article/details/9264.sHtML
http://www.blog.cmcvrr.cn/Article/details/599926.sHtML
http://www.blog.cmcvrr.cn/Article/details/0937921.sHtML
http://www.blog.cmcvrr.cn/Article/details/2442786.sHtML
http://www.blog.cmcvrr.cn/Article/details/89831.sHtML
http://www.blog.cmcvrr.cn/Article/details/55193.sHtML
http://www.blog.cmcvrr.cn/Article/details/5274.sHtML
http://www.blog.cmcvrr.cn/Article/details/65846.sHtML
http://www.blog.cmcvrr.cn/Article/details/79796.sHtML
http://www.blog.cmcvrr.cn/Article/details/288242.sHtML
http://www.blog.cmcvrr.cn/Article/details/345200.sHtML
http://www.blog.cmcvrr.cn/Article/details/264049.sHtML
http://www.blog.cmcvrr.cn/Article/details/30721.sHtML
http://www.blog.cmcvrr.cn/Article/details/9686347.sHtML
http://www.blog.cmcvrr.cn/Article/details/7417003.sHtML
http://www.blog.cmcvrr.cn/Article/details/72975.sHtML
http://www.blog.cmcvrr.cn/Article/details/9730076.sHtML
http://www.blog.cmcvrr.cn/Article/details/80857.sHtML
http://www.blog.cmcvrr.cn/Article/details/85434.sHtML
http://www.blog.cmcvrr.cn/Article/details/2289.sHtML
http://www.blog.cmcvrr.cn/Article/details/86197.sHtML
http://www.blog.cmcvrr.cn/Article/details/410275.sHtML
http://www.blog.cmcvrr.cn/Article/details/6120754.sHtML
http://www.blog.cmcvrr.cn/Article/details/096879.sHtML
http://www.blog.cmcvrr.cn/Article/details/988678.sHtML
http://www.blog.cmcvrr.cn/Article/details/0511610.sHtML
http://www.blog.cmcvrr.cn/Article/details/9001521.sHtML
http://www.blog.cmcvrr.cn/Article/details/62860.sHtML
http://www.blog.cmcvrr.cn/Article/details/35611.sHtML
http://www.blog.cmcvrr.cn/Article/details/8518.sHtML
http://www.blog.cmcvrr.cn/Article/details/96052.sHtML
http://www.blog.cmcvrr.cn/Article/details/8730.sHtML
http://www.blog.cmcvrr.cn/Article/details/922223.sHtML
http://www.blog.cmcvrr.cn/Article/details/558902.sHtML
http://www.blog.cmcvrr.cn/Article/details/5079.sHtML
http://www.blog.cmcvrr.cn/Article/details/45043.sHtML
http://www.blog.cmcvrr.cn/Article/details/6631505.sHtML
http://www.blog.cmcvrr.cn/Article/details/19141.sHtML
http://www.blog.cmcvrr.cn/Article/details/7880.sHtML
http://www.blog.cmcvrr.cn/Article/details/442210.sHtML
http://www.blog.cmcvrr.cn/Article/details/3969412.sHtML
http://www.blog.cmcvrr.cn/Article/details/578340.sHtML
http://www.blog.cmcvrr.cn/Article/details/0065931.sHtML
http://www.blog.cmcvrr.cn/Article/details/2077.sHtML
http://www.blog.cmcvrr.cn/Article/details/907811.sHtML
http://www.blog.cmcvrr.cn/Article/details/4855013.sHtML
http://www.blog.cmcvrr.cn/Article/details/42441.sHtML
http://www.blog.cmcvrr.cn/Article/details/80856.sHtML
http://www.blog.cmcvrr.cn/Article/details/26814.sHtML
http://www.blog.cmcvrr.cn/Article/details/1947652.sHtML
http://www.blog.cmcvrr.cn/Article/details/5639230.sHtML
http://www.blog.cmcvrr.cn/Article/details/1557294.sHtML
http://www.blog.cmcvrr.cn/Article/details/522654.sHtML
http://www.blog.cmcvrr.cn/Article/details/162267.sHtML
http://www.blog.cmcvrr.cn/Article/details/642512.sHtML
http://www.blog.cmcvrr.cn/Article/details/44823.sHtML
http://www.blog.cmcvrr.cn/Article/details/3631720.sHtML
http://www.blog.cmcvrr.cn/Article/details/4597.sHtML
http://www.blog.cmcvrr.cn/Article/details/71930.sHtML
http://www.blog.cmcvrr.cn/Article/details/328113.sHtML
http://www.blog.cmcvrr.cn/Article/details/18874.sHtML
http://www.blog.cmcvrr.cn/Article/details/8269175.sHtML
http://www.blog.cmcvrr.cn/Article/details/90877.sHtML
http://www.blog.cmcvrr.cn/Article/details/05738.sHtML
http://www.blog.cmcvrr.cn/Article/details/569060.sHtML
http://www.blog.cmcvrr.cn/Article/details/93082.sHtML
http://www.blog.cmcvrr.cn/Article/details/91805.sHtML
http://www.blog.cmcvrr.cn/Article/details/81360.sHtML
http://www.blog.cmcvrr.cn/Article/details/2694.sHtML
http://www.blog.cmcvrr.cn/Article/details/9204791.sHtML
http://www.blog.cmcvrr.cn/Article/details/448498.sHtML
http://www.blog.cmcvrr.cn/Article/details/9912.sHtML
http://www.blog.cmcvrr.cn/Article/details/7286.sHtML
http://www.blog.cmcvrr.cn/Article/details/7267495.sHtML
http://www.blog.cmcvrr.cn/Article/details/6634813.sHtML
http://www.blog.cmcvrr.cn/Article/details/47840.sHtML
http://www.blog.cmcvrr.cn/Article/details/226931.sHtML
http://www.blog.cmcvrr.cn/Article/details/83105.sHtML
http://www.blog.cmcvrr.cn/Article/details/70627.sHtML
http://www.blog.cmcvrr.cn/Article/details/64320.sHtML
http://www.blog.cmcvrr.cn/Article/details/593562.sHtML
http://www.blog.cmcvrr.cn/Article/details/326196.sHtML
http://www.blog.cmcvrr.cn/Article/details/09255.sHtML
http://www.blog.cmcvrr.cn/Article/details/525619.sHtML
http://www.blog.cmcvrr.cn/Article/details/795766.sHtML
http://www.blog.cmcvrr.cn/Article/details/60437.sHtML
http://www.blog.cmcvrr.cn/Article/details/583106.sHtML
http://www.blog.cmcvrr.cn/Article/details/3397078.sHtML
http://www.blog.cmcvrr.cn/Article/details/8252.sHtML
http://www.blog.cmcvrr.cn/Article/details/62006.sHtML
http://www.blog.cmcvrr.cn/Article/details/6542.sHtML
http://www.blog.cmcvrr.cn/Article/details/0702075.sHtML
http://www.blog.cmcvrr.cn/Article/details/5325.sHtML
http://www.blog.cmcvrr.cn/Article/details/8097.sHtML
http://www.blog.cmcvrr.cn/Article/details/237172.sHtML
http://www.blog.cmcvrr.cn/Article/details/97038.sHtML
http://www.blog.cmcvrr.cn/Article/details/19549.sHtML
http://www.blog.cmcvrr.cn/Article/details/80927.sHtML
http://www.blog.cmcvrr.cn/Article/details/0806820.sHtML
http://www.blog.cmcvrr.cn/Article/details/1280755.sHtML
http://www.blog.cmcvrr.cn/Article/details/76551.sHtML
http://www.blog.cmcvrr.cn/Article/details/6252994.sHtML
http://www.blog.cmcvrr.cn/Article/details/6498.sHtML
http://www.blog.cmcvrr.cn/Article/details/84324.sHtML
http://www.blog.cmcvrr.cn/Article/details/8686.sHtML
http://www.blog.cmcvrr.cn/Article/details/5359792.sHtML
http://www.blog.cmcvrr.cn/Article/details/52397.sHtML
http://www.blog.cmcvrr.cn/Article/details/57264.sHtML
http://www.blog.cmcvrr.cn/Article/details/5154.sHtML
http://www.blog.cmcvrr.cn/Article/details/0125.sHtML
http://www.blog.cmcvrr.cn/Article/details/8071205.sHtML
http://www.blog.cmcvrr.cn/Article/details/332123.sHtML
http://www.blog.cmcvrr.cn/Article/details/7521424.sHtML
http://www.blog.cmcvrr.cn/Article/details/19101.sHtML
http://www.blog.cmcvrr.cn/Article/details/6054660.sHtML
http://www.blog.cmcvrr.cn/Article/details/60152.sHtML
http://www.blog.cmcvrr.cn/Article/details/125026.sHtML
http://www.blog.cmcvrr.cn/Article/details/1335.sHtML
http://www.blog.cmcvrr.cn/Article/details/454680.sHtML
http://www.blog.cmcvrr.cn/Article/details/9312.sHtML
http://www.blog.cmcvrr.cn/Article/details/278326.sHtML
http://www.blog.cmcvrr.cn/Article/details/47770.sHtML
http://www.blog.cmcvrr.cn/Article/details/094897.sHtML
http://www.blog.cmcvrr.cn/Article/details/39718.sHtML
http://www.blog.cmcvrr.cn/Article/details/12401.sHtML
http://www.blog.cmcvrr.cn/Article/details/5768.sHtML
http://www.blog.cmcvrr.cn/Article/details/953530.sHtML
http://www.blog.cmcvrr.cn/Article/details/644969.sHtML
http://www.blog.cmcvrr.cn/Article/details/38126.sHtML
http://www.blog.cmcvrr.cn/Article/details/3918692.sHtML
http://www.blog.cmcvrr.cn/Article/details/53381.sHtML
http://www.blog.cmcvrr.cn/Article/details/0874376.sHtML
http://www.blog.cmcvrr.cn/Article/details/4088.sHtML
http://www.blog.cmcvrr.cn/Article/details/0242319.sHtML
http://www.blog.cmcvrr.cn/Article/details/0627239.sHtML
http://www.blog.cmcvrr.cn/Article/details/00280.sHtML
http://www.blog.cmcvrr.cn/Article/details/8401.sHtML
http://www.blog.cmcvrr.cn/Article/details/6841820.sHtML
http://www.blog.cmcvrr.cn/Article/details/053630.sHtML
http://www.blog.cmcvrr.cn/Article/details/814199.sHtML
http://www.blog.cmcvrr.cn/Article/details/1197.sHtML
http://www.blog.cmcvrr.cn/Article/details/45787.sHtML
http://www.blog.cmcvrr.cn/Article/details/12566.sHtML
http://www.blog.cmcvrr.cn/Article/details/1788380.sHtML
http://www.blog.cmcvrr.cn/Article/details/2423.sHtML
http://www.blog.cmcvrr.cn/Article/details/00152.sHtML
http://www.blog.cmcvrr.cn/Article/details/873218.sHtML
http://www.blog.cmcvrr.cn/Article/details/11874.sHtML
http://www.blog.cmcvrr.cn/Article/details/62611.sHtML
http://www.blog.cmcvrr.cn/Article/details/5849074.sHtML
http://www.blog.cmcvrr.cn/Article/details/4629.sHtML
http://www.blog.cmcvrr.cn/Article/details/6975.sHtML
http://www.blog.cmcvrr.cn/Article/details/28596.sHtML
http://www.blog.cmcvrr.cn/Article/details/4502096.sHtML
http://www.blog.cmcvrr.cn/Article/details/593509.sHtML
http://www.blog.cmcvrr.cn/Article/details/9536736.sHtML
http://www.blog.cmcvrr.cn/Article/details/510103.sHtML
http://www.blog.cmcvrr.cn/Article/details/7535123.sHtML
http://www.blog.cmcvrr.cn/Article/details/85083.sHtML
http://www.blog.cmcvrr.cn/Article/details/9651156.sHtML
http://www.blog.cmcvrr.cn/Article/details/4820.sHtML
http://www.blog.cmcvrr.cn/Article/details/99264.sHtML
http://www.blog.cmcvrr.cn/Article/details/0107.sHtML
http://www.blog.cmcvrr.cn/Article/details/9776033.sHtML
http://www.blog.cmcvrr.cn/Article/details/57087.sHtML
http://www.blog.cmcvrr.cn/Article/details/0667831.sHtML
http://www.blog.cmcvrr.cn/Article/details/38823.sHtML
http://www.blog.cmcvrr.cn/Article/details/6145326.sHtML
http://www.blog.cmcvrr.cn/Article/details/1781.sHtML
http://www.blog.cmcvrr.cn/Article/details/7925.sHtML
http://www.blog.cmcvrr.cn/Article/details/061293.sHtML
http://www.blog.cmcvrr.cn/Article/details/16460.sHtML
http://www.blog.cmcvrr.cn/Article/details/8360548.sHtML
http://www.blog.cmcvrr.cn/Article/details/5503937.sHtML
http://www.blog.cmcvrr.cn/Article/details/458717.sHtML
http://www.blog.cmcvrr.cn/Article/details/3406891.sHtML
http://www.blog.cmcvrr.cn/Article/details/7248334.sHtML
http://www.blog.cmcvrr.cn/Article/details/8469502.sHtML
http://www.blog.cmcvrr.cn/Article/details/167918.sHtML
http://www.blog.cmcvrr.cn/Article/details/9929664.sHtML
http://www.blog.cmcvrr.cn/Article/details/530489.sHtML
http://www.blog.cmcvrr.cn/Article/details/88376.sHtML
http://www.blog.cmcvrr.cn/Article/details/760326.sHtML
http://www.blog.cmcvrr.cn/Article/details/7723377.sHtML
http://www.blog.cmcvrr.cn/Article/details/7085.sHtML
http://www.blog.cmcvrr.cn/Article/details/271505.sHtML
http://www.blog.cmcvrr.cn/Article/details/777039.sHtML
http://www.blog.cmcvrr.cn/Article/details/4030.sHtML
http://www.blog.cmcvrr.cn/Article/details/7678.sHtML
http://www.blog.cmcvrr.cn/Article/details/0631742.sHtML
http://www.blog.cmcvrr.cn/Article/details/04996.sHtML
http://www.blog.cmcvrr.cn/Article/details/6922223.sHtML
http://www.blog.cmcvrr.cn/Article/details/0449.sHtML
http://www.blog.cmcvrr.cn/Article/details/8079156.sHtML
http://www.blog.cmcvrr.cn/Article/details/2874387.sHtML
http://www.blog.cmcvrr.cn/Article/details/00385.sHtML
http://www.blog.cmcvrr.cn/Article/details/96604.sHtML
http://www.blog.cmcvrr.cn/Article/details/39661.sHtML
http://www.blog.cmcvrr.cn/Article/details/03898.sHtML
http://www.blog.cmcvrr.cn/Article/details/1423671.sHtML
http://www.blog.cmcvrr.cn/Article/details/3979.sHtML
http://www.blog.cmcvrr.cn/Article/details/9746929.sHtML
http://www.blog.cmcvrr.cn/Article/details/676860.sHtML
http://www.blog.cmcvrr.cn/Article/details/6869.sHtML
http://www.blog.cmcvrr.cn/Article/details/56040.sHtML
http://www.blog.cmcvrr.cn/Article/details/8869.sHtML
http://www.blog.cmcvrr.cn/Article/details/36016.sHtML
http://www.blog.cmcvrr.cn/Article/details/98424.sHtML
http://www.blog.cmcvrr.cn/Article/details/968204.sHtML
http://www.blog.cmcvrr.cn/Article/details/653879.sHtML
http://www.blog.cmcvrr.cn/Article/details/5333945.sHtML
http://www.blog.cmcvrr.cn/Article/details/7174717.sHtML
http://www.blog.cmcvrr.cn/Article/details/26467.sHtML
http://www.blog.cmcvrr.cn/Article/details/380607.sHtML
http://www.blog.cmcvrr.cn/Article/details/3133711.sHtML
http://www.blog.cmcvrr.cn/Article/details/7100.sHtML
http://www.blog.cmcvrr.cn/Article/details/71386.sHtML
http://www.blog.cmcvrr.cn/Article/details/0831.sHtML
http://www.blog.cmcvrr.cn/Article/details/3569.sHtML
http://www.blog.cmcvrr.cn/Article/details/0498327.sHtML
http://www.blog.cmcvrr.cn/Article/details/34021.sHtML
http://www.blog.cmcvrr.cn/Article/details/104407.sHtML
http://www.blog.cmcvrr.cn/Article/details/654032.sHtML
http://www.blog.cmcvrr.cn/Article/details/546623.sHtML
http://www.blog.cmcvrr.cn/Article/details/129976.sHtML
http://www.blog.cmcvrr.cn/Article/details/1936234.sHtML
http://www.blog.cmcvrr.cn/Article/details/3435.sHtML
http://www.blog.cmcvrr.cn/Article/details/0473.sHtML
http://www.blog.cmcvrr.cn/Article/details/06958.sHtML
http://www.blog.cmcvrr.cn/Article/details/392399.sHtML
http://www.blog.cmcvrr.cn/Article/details/06807.sHtML
http://www.blog.cmcvrr.cn/Article/details/1102148.sHtML
http://www.blog.cmcvrr.cn/Article/details/661403.sHtML
http://www.blog.cmcvrr.cn/Article/details/8352.sHtML
http://www.blog.cmcvrr.cn/Article/details/9721.sHtML

## 项目结构

```
blog-cmcvrr-gateway/
├── gateway/                          # 项目主配置目录
│   ├── settings/                     # 多环境配置拆分
│   │   ├── base.py                   # 基础配置，适用于所有环境
│   │   ├── development.py            # 开发环境配置，开启调试和本地缓存
│   │   └── production.py             # 生产环境配置，关闭调试启用优化
│   ├── urls.py                       # 根路由配置，映射到各子应用
│   └── wsgi.py                       # WSGI 入口，供 gunicorn 调用
├── apps/                             # 所有 Django 子应用
│   ├── articles/                     # 文章核心应用：模型、视图、索引
│   │   ├── models.py                 # Article, Category, Tag 数据模型
│   │   ├── indexer.py                # 倒排索引构建和查询逻辑
│   │   └── management/               # 自定义命令行工具，含导入导出
│   ├── accounts/                     # 用户认证和个人资料管理
│   ├── bookmarks/                    # 收藏和阅读列表功能
│   ├── analytics/                    # 访问日志采集和统计报表
│   └── external/                     # 外部链接健康检查和代理
├── static/                           # 前端静态资源
│   ├── css/                          # Sass 源文件和编译后的样式
│   ├── js/                           # 原生 JavaScript 模块，含检索交互
│   └── images/                       # 图标和默认占位图
├── templates/                        # Django 模板文件
│   ├── layout/                       # 基础布局和导航组件
│   └── articles/                     # 文章列表、详情、搜索结果页
├── tests/                            # 单元测试和集成测试
│   ├── test_models.py                # 模型层测试用例
│   ├── test_indexer.py               # 索引引擎性能与正确性测试
│   └── test_api.py                   # API 端点功能测试
├── scripts/                          # 运维脚本和定时任务
│   ├── health_check.py               # 链接可达性批量检测
│   └── import_articles.py            # 从外部数据源批量导入
├── deploy/                           # 部署相关配置
│   ├── nginx.conf                    # Nginx 站点配置模板
│   ├── gunicorn.conf.py              # Gunicorn 进程参数配置
│   └── supervisor.conf               # Supervisor 进程守护配置
├── requirements.txt                  # Python 依赖清单，含版本锁定
├── manage.py                         # Django 管理命令行入口
└── README.md                         # 本文档
```

## 贡献指南

1. 阅读项目行为准则（CODE_OF_CONDUCT.md）和贡献规范（CONTRIBUTING.md），确认遵守社区约定。所有贡献者需签署开发者原产地证书（DCO）。

2. 在 GitHub Issue 列表中查找未被认领的任务或提交新 Issue 描述你发现的问题或建议的新功能，等待维护者反馈后再开始编码。

3. Fork 本仓库到个人账号，创建以功能或修复命名的特性分支（如 feature/enhance-search-sorting），提交代码时遵循 Conventional Commits 格式（type(scope): subject）。

4. 编写或更新相应的单元测试，确保测试覆盖率达到现有水平以上，所有测试用例在本地通过后再发起 Pull Request。

5. 向 main 分支发起 Pull Request，在描述中关联对应的 Issue 编号，维护者会在 3 个工作日内进行 Code Review 并提出修改意见。

## 常见问题

**Q: 部署后访问文章详情页出现 404 错误，但文章列表显示正常，是什么原因？**

A: 请检查 `gateway/settings/base.py` 中 `ALLOWED_HOSTS` 配置是否包含当前访问域名。同时确认数据库中的文章记录确实存在且 `is_published` 字段为 True。若使用 PostgreSQL，可执行 `python manage.py shell` 进入交互环境，通过 `Article.objects.filter(id=xxx).values('title', 'is_published')` 检查目标文章状态。另外需确保 URL 中的文章 ID 与数据库主键一致，若使用了自定义 slug 字段，请检查 `urls.py` 中的路由捕获方式。

**Q: 全文检索返回结果速度较慢，如何优化？**

A: 首先确认是否正确配置并启动了 Elasticsearch 服务，Django 的数据库 LIKE 查询不适合生产环境。检查 `settings/base.py` 中 `HAYSTACK_CONNECTIONS` 配置的 `TIMEOUT` 和 `MAX_RETRIES` 参数。若数据量超过 10 万条，建议为 Elasticsearch 分配至少 2GB 堆内存（修改 `ES_JAVA_OPTS`）。还可启用 Redis 缓存检索结果，在 `CACHES` 配置中添加 `'OPTIONS': {'MAX_ENTRIES': 10000}` 限制缓存条目数量。

**Q: 如何将本系统迁移到已有的 Django 项目中作为子模块？**

A: 将 `apps/` 目录下的各应用复制到目标项目的应用目录，在目标项目的 `INSTALLED_APPS` 中添加对应条目。复制 `gateway/settings/base.py` 中的数据库表定义和索引配置到目标项目的 `settings.py`。运行 `python manage.py makemigrations articles bookmarks analytics` 生成迁移文件。需注意本系统依赖 Django 4.2 的 `db.models.JSONField`，若目标项目使用较低版本，需额外安装 `django-jsonfield-backport` 兼容层。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 16:28:07
