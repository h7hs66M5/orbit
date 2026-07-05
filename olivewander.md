# TechLink Navigator

TechLink Navigator 是一个面向开发者与技术研究者的技术资源外链汇总平台，专注于收录高质量的技术博客文章、开发教程与架构设计讨论。本项目不生产内容，而是通过人工筛选与自动化校验，将分散在互联网各处的优质技术文章按主题归档，帮助技术从业者在信息过载的环境中快速定位有价值的外链资源。

本项目定位为技术阅读辅助工具，适用于日常技术学习、面试准备、架构选型调研以及项目复盘等场景。当前收录资源覆盖后端开发、前端工程、运维监控、数据库调优、算法设计等多个技术领域，所有外链均保留原始出处，确保可追溯性。

## 功能概览

**按主题分类归档**：所有外链按技术领域与话题标签进行归类，支持按类别快速浏览。

**每日自动校验**：系统定时检测已收录链接的有效性，自动标记失效链接并生成报告。

**全文元数据提取**：对每条链接自动抓取标题、发布时间、作者等元信息，提升检索效率。

**用户收藏与标签**：允许注册用户对外链添加自定义标签与收藏，构建个人技术阅读清单。

**链接热度排序**：基于点击量与收藏数计算链接热度，展示当前活跃的技术讨论话题。

**批量导入导出**：支持通过 CSV 与 JSON 格式批量导入外部链接，也支持导出收藏夹。

**RSS 订阅源生成**：为每个分类生成独立的 RSS 订阅地址，方便集成至阅读器。

**搜索与筛选**：提供关键词搜索，并支持按时间、热度、分类等多维度筛选结果。

## 应用场景

**技术团队周报素材收集**：团队技术负责人可定期浏览本站收录的热门文章，筛选与当前项目相关的讨论，整理为周报素材分发给团队成员。

**个人技术阅读规划**：开发者可按自身技术栈订阅对应分类，每周批量阅读收录的外链文章，系统性补充知识体系。

**架构设计参考调研**：在进行技术选型或架构设计时，可通过搜索与分类筛选快速找到同类场景的实践经验与踩坑记录。

**面试题库准备**：求职者可针对目标岗位的技术要求，检索对应分类下的高频讨论话题与深度分析文章，整理面试问答素材。

**技术写作选题挖掘**：技术博主可通过热度排序发现当前社区关注度较高的方向，结合自身经验撰写更深入的专题文章。

## 快速开始

以下步骤指导您在本机部署 TechLink Navigator 开发环境。

```bash
# 克隆代码仓库
git clone https://github.com/techlink-navigator/techlink-navigator.git
cd techlink-navigator

# 安装项目依赖（使用 pip 与虚拟环境）
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# 初始化数据库并导入示例链接数据
python manage.py migrate
python manage.py loaddata fixtures/initial_links.json

# 启动本地开发服务器
python manage.py runserver 0.0.0.0:8000
```

访问 http://127.0.0.1:8000 即可查看本地运行实例。管理员后台地址为 /admin，默认账号 admin 密码 admin123，请在生产环境前及时修改。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.9 至 3.11 | 核心运行环境，3.12 暂未完全兼容 |
| Django | 4.2.x LTS | Web 框架，提供 ORM 与 admin 界面 |
| PostgreSQL | 14.x 或 15.x | 生产环境推荐数据库，支持 JSONB 字段 |
| Redis | 7.0.x | 缓存与任务队列后端，用于链接状态缓存 |
| Celery | 5.3.x | 异步任务队列，处理链接校验与元数据抓取 |
| BeautifulSoup4 | 4.12.x | HTML 解析库，用于提取外链页面元信息 |
| Requests | 2.31.x | HTTP 客户端，执行链接可用性检测 |
| django-cors-headers | 4.3.x | 跨域资源共享中间件，供前端独立调用 |
| django-rest-framework | 3.14.x | API 接口框架，提供 RESTful 端点 |
| psycopg2-binary | 2.9.x | PostgreSQL 适配器，二进制版本便于安装 |
| gunicorn | 21.2.x | 生产级 WSGI 服务器，用于部署运行 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户指南 | /docs/user-guide/quick-start.md | 如何注册、收藏、搜索与订阅链接分类 |
| 管理员手册 | /docs/admin/link-management.md | 如何审核新链接、处理失效报告与分类维护 |
| 开发参考 | /docs/developer/api-endpoints.md | API 鉴权方式、请求限流策略与返回值结构 |
| 部署运维 | /docs/operations/deployment-checklist.md | 生产环境变量配置、日志轮转与备份策略 |
| 设计文档 | /docs/design/data-model.md | 数据库表关系、索引设计与缓存更新时机 |
| 测试规范 | /docs/testing/integration-test.md | 如何编写链接校验的单元测试与集成测试用例 |

## 资源列表

**技术文章外链（来自 www.blog.ityiqv.cn）**

http://www.blog.ityiqv.cn/Article/details/7267816.sHtML
http://www.blog.ityiqv.cn/Article/details/819006.sHtML
http://www.blog.ityiqv.cn/Article/details/5201824.sHtML
http://www.blog.ityiqv.cn/Article/details/4333834.sHtML
http://www.blog.ityiqv.cn/Article/details/00580.sHtML
http://www.blog.ityiqv.cn/Article/details/63307.sHtML
http://www.blog.ityiqv.cn/Article/details/1675384.sHtML
http://www.blog.ityiqv.cn/Article/details/2425953.sHtML
http://www.blog.ityiqv.cn/Article/details/0302.sHtML
http://www.blog.ityiqv.cn/Article/details/40314.sHtML
http://www.blog.ityiqv.cn/Article/details/2784.sHtML
http://www.blog.ityiqv.cn/Article/details/252371.sHtML
http://www.blog.ityiqv.cn/Article/details/8530373.sHtML
http://www.blog.ityiqv.cn/Article/details/4510.sHtML
http://www.blog.ityiqv.cn/Article/details/2503704.sHtML
http://www.blog.ityiqv.cn/Article/details/4978.sHtML
http://www.blog.ityiqv.cn/Article/details/451202.sHtML
http://www.blog.ityiqv.cn/Article/details/978142.sHtML
http://www.blog.ityiqv.cn/Article/details/2015418.sHtML
http://www.blog.ityiqv.cn/Article/details/244701.sHtML
http://www.blog.ityiqv.cn/Article/details/33567.sHtML
http://www.blog.ityiqv.cn/Article/details/8371311.sHtML
http://www.blog.ityiqv.cn/Article/details/5466309.sHtML
http://www.blog.ityiqv.cn/Article/details/7563771.sHtML
http://www.blog.ityiqv.cn/Article/details/0272.sHtML
http://www.blog.ityiqv.cn/Article/details/77569.sHtML
http://www.blog.ityiqv.cn/Article/details/772929.sHtML
http://www.blog.ityiqv.cn/Article/details/6630128.sHtML
http://www.blog.ityiqv.cn/Article/details/3759212.sHtML
http://www.blog.ityiqv.cn/Article/details/8879555.sHtML
http://www.blog.ityiqv.cn/Article/details/802517.sHtML
http://www.blog.ityiqv.cn/Article/details/58315.sHtML
http://www.blog.ityiqv.cn/Article/details/71347.sHtML
http://www.blog.ityiqv.cn/Article/details/9242.sHtML
http://www.blog.ityiqv.cn/Article/details/974824.sHtML
http://www.blog.ityiqv.cn/Article/details/609338.sHtML
http://www.blog.ityiqv.cn/Article/details/072795.sHtML
http://www.blog.ityiqv.cn/Article/details/9597894.sHtML
http://www.blog.ityiqv.cn/Article/details/470768.sHtML
http://www.blog.ityiqv.cn/Article/details/783265.sHtML
http://www.blog.ityiqv.cn/Article/details/9365.sHtML
http://www.blog.ityiqv.cn/Article/details/8262991.sHtML
http://www.blog.ityiqv.cn/Article/details/632067.sHtML
http://www.blog.ityiqv.cn/Article/details/4508534.sHtML
http://www.blog.ityiqv.cn/Article/details/918111.sHtML
http://www.blog.ityiqv.cn/Article/details/55899.sHtML
http://www.blog.ityiqv.cn/Article/details/9778.sHtML
http://www.blog.ityiqv.cn/Article/details/0495260.sHtML
http://www.blog.ityiqv.cn/Article/details/5437512.sHtML
http://www.blog.ityiqv.cn/Article/details/75249.sHtML
http://www.blog.ityiqv.cn/Article/details/349771.sHtML
http://www.blog.ityiqv.cn/Article/details/06584.sHtML
http://www.blog.ityiqv.cn/Article/details/3811.sHtML
http://www.blog.ityiqv.cn/Article/details/5914.sHtML
http://www.blog.ityiqv.cn/Article/details/0472.sHtML
http://www.blog.ityiqv.cn/Article/details/1521.sHtML
http://www.blog.ityiqv.cn/Article/details/7117009.sHtML
http://www.blog.ityiqv.cn/Article/details/654952.sHtML
http://www.blog.ityiqv.cn/Article/details/3903359.sHtML
http://www.blog.ityiqv.cn/Article/details/58063.sHtML
http://www.blog.ityiqv.cn/Article/details/09826.sHtML
http://www.blog.ityiqv.cn/Article/details/41587.sHtML
http://www.blog.ityiqv.cn/Article/details/914939.sHtML
http://www.blog.ityiqv.cn/Article/details/92140.sHtML
http://www.blog.ityiqv.cn/Article/details/153305.sHtML
http://www.blog.ityiqv.cn/Article/details/6896.sHtML
http://www.blog.ityiqv.cn/Article/details/7673.sHtML
http://www.blog.ityiqv.cn/Article/details/31075.sHtML
http://www.blog.ityiqv.cn/Article/details/108725.sHtML
http://www.blog.ityiqv.cn/Article/details/20560.sHtML
http://www.blog.ityiqv.cn/Article/details/91566.sHtML
http://www.blog.ityiqv.cn/Article/details/207834.sHtML
http://www.blog.ityiqv.cn/Article/details/18111.sHtML
http://www.blog.ityiqv.cn/Article/details/992570.sHtML
http://www.blog.ityiqv.cn/Article/details/487594.sHtML
http://www.blog.ityiqv.cn/Article/details/90582.sHtML
http://www.blog.ityiqv.cn/Article/details/3808.sHtML
http://www.blog.ityiqv.cn/Article/details/8663994.sHtML
http://www.blog.ityiqv.cn/Article/details/4767472.sHtML
http://www.blog.ityiqv.cn/Article/details/4017.sHtML
http://www.blog.ityiqv.cn/Article/details/2509.sHtML
http://www.blog.ityiqv.cn/Article/details/322702.sHtML
http://www.blog.ityiqv.cn/Article/details/4580.sHtML
http://www.blog.ityiqv.cn/Article/details/23220.sHtML
http://www.blog.ityiqv.cn/Article/details/8761.sHtML
http://www.blog.ityiqv.cn/Article/details/4698426.sHtML
http://www.blog.ityiqv.cn/Article/details/72984.sHtML
http://www.blog.ityiqv.cn/Article/details/0606.sHtML
http://www.blog.ityiqv.cn/Article/details/6029.sHtML
http://www.blog.ityiqv.cn/Article/details/4943608.sHtML
http://www.blog.ityiqv.cn/Article/details/288559.sHtML
http://www.blog.ityiqv.cn/Article/details/738280.sHtML
http://www.blog.ityiqv.cn/Article/details/29025.sHtML
http://www.blog.ityiqv.cn/Article/details/09030.sHtML
http://www.blog.ityiqv.cn/Article/details/61694.sHtML
http://www.blog.ityiqv.cn/Article/details/8957350.sHtML
http://www.blog.ityiqv.cn/Article/details/677133.sHtML
http://www.blog.ityiqv.cn/Article/details/671614.sHtML
http://www.blog.ityiqv.cn/Article/details/14954.sHtML
http://www.blog.ityiqv.cn/Article/details/470179.sHtML
http://www.blog.ityiqv.cn/Article/details/878622.sHtML
http://www.blog.ityiqv.cn/Article/details/683351.sHtML
http://www.blog.ityiqv.cn/Article/details/6651.sHtML
http://www.blog.ityiqv.cn/Article/details/9482.sHtML
http://www.blog.ityiqv.cn/Article/details/7799149.sHtML
http://www.blog.ityiqv.cn/Article/details/5069337.sHtML
http://www.blog.ityiqv.cn/Article/details/903329.sHtML
http://www.blog.ityiqv.cn/Article/details/163367.sHtML
http://www.blog.ityiqv.cn/Article/details/982141.sHtML
http://www.blog.ityiqv.cn/Article/details/88681.sHtML
http://www.blog.ityiqv.cn/Article/details/4450812.sHtML
http://www.blog.ityiqv.cn/Article/details/2592.sHtML
http://www.blog.ityiqv.cn/Article/details/47577.sHtML
http://www.blog.ityiqv.cn/Article/details/465396.sHtML
http://www.blog.ityiqv.cn/Article/details/5007218.sHtML
http://www.blog.ityiqv.cn/Article/details/55989.sHtML
http://www.blog.ityiqv.cn/Article/details/77854.sHtML
http://www.blog.ityiqv.cn/Article/details/0527422.sHtML
http://www.blog.ityiqv.cn/Article/details/052461.sHtML
http://www.blog.ityiqv.cn/Article/details/9040665.sHtML
http://www.blog.ityiqv.cn/Article/details/2119069.sHtML
http://www.blog.ityiqv.cn/Article/details/96959.sHtML
http://www.blog.ityiqv.cn/Article/details/5004815.sHtML
http://www.blog.ityiqv.cn/Article/details/145393.sHtML
http://www.blog.ityiqv.cn/Article/details/8197.sHtML
http://www.blog.ityiqv.cn/Article/details/3486497.sHtML
http://www.blog.ityiqv.cn/Article/details/9452987.sHtML
http://www.blog.ityiqv.cn/Article/details/10774.sHtML
http://www.blog.ityiqv.cn/Article/details/49680.sHtML
http://www.blog.ityiqv.cn/Article/details/8410529.sHtML
http://www.blog.ityiqv.cn/Article/details/86979.sHtML
http://www.blog.ityiqv.cn/Article/details/271645.sHtML
http://www.blog.ityiqv.cn/Article/details/6952.sHtML
http://www.blog.ityiqv.cn/Article/details/717201.sHtML
http://www.blog.ityiqv.cn/Article/details/769582.sHtML
http://www.blog.ityiqv.cn/Article/details/95468.sHtML
http://www.blog.ityiqv.cn/Article/details/0609.sHtML
http://www.blog.ityiqv.cn/Article/details/557498.sHtML
http://www.blog.ityiqv.cn/Article/details/7897.sHtML
http://www.blog.ityiqv.cn/Article/details/490828.sHtML
http://www.blog.ityiqv.cn/Article/details/1066.sHtML
http://www.blog.ityiqv.cn/Article/details/8273081.sHtML
http://www.blog.ityiqv.cn/Article/details/614412.sHtML
http://www.blog.ityiqv.cn/Article/details/86022.sHtML
http://www.blog.ityiqv.cn/Article/details/40564.sHtML
http://www.blog.ityiqv.cn/Article/details/11902.sHtML
http://www.blog.ityiqv.cn/Article/details/1465.sHtML
http://www.blog.ityiqv.cn/Article/details/58954.sHtML
http://www.blog.ityiqv.cn/Article/details/004221.sHtML
http://www.blog.ityiqv.cn/Article/details/276317.sHtML
http://www.blog.ityiqv.cn/Article/details/4219912.sHtML
http://www.blog.ityiqv.cn/Article/details/078879.sHtML
http://www.blog.ityiqv.cn/Article/details/454872.sHtML
http://www.blog.ityiqv.cn/Article/details/257216.sHtML
http://www.blog.ityiqv.cn/Article/details/4529048.sHtML
http://www.blog.ityiqv.cn/Article/details/3285547.sHtML
http://www.blog.ityiqv.cn/Article/details/239819.sHtML
http://www.blog.ityiqv.cn/Article/details/736803.sHtML
http://www.blog.ityiqv.cn/Article/details/5336.sHtML
http://www.blog.ityiqv.cn/Article/details/0264886.sHtML
http://www.blog.ityiqv.cn/Article/details/31407.sHtML
http://www.blog.ityiqv.cn/Article/details/84284.sHtML
http://www.blog.ityiqv.cn/Article/details/0357675.sHtML
http://www.blog.ityiqv.cn/Article/details/7894.sHtML
http://www.blog.ityiqv.cn/Article/details/4638104.sHtML
http://www.blog.ityiqv.cn/Article/details/522590.sHtML
http://www.blog.ityiqv.cn/Article/details/665978.sHtML
http://www.blog.ityiqv.cn/Article/details/72469.sHtML
http://www.blog.ityiqv.cn/Article/details/314165.sHtML
http://www.blog.ityiqv.cn/Article/details/287355.sHtML
http://www.blog.ityiqv.cn/Article/details/0739.sHtML
http://www.blog.ityiqv.cn/Article/details/8587.sHtML
http://www.blog.ityiqv.cn/Article/details/945045.sHtML
http://www.blog.ityiqv.cn/Article/details/513343.sHtML
http://www.blog.ityiqv.cn/Article/details/0784.sHtML
http://www.blog.ityiqv.cn/Article/details/14556.sHtML
http://www.blog.ityiqv.cn/Article/details/869760.sHtML
http://www.blog.ityiqv.cn/Article/details/25543.sHtML
http://www.blog.ityiqv.cn/Article/details/03686.sHtML
http://www.blog.ityiqv.cn/Article/details/9833122.sHtML
http://www.blog.ityiqv.cn/Article/details/03196.sHtML
http://www.blog.ityiqv.cn/Article/details/313599.sHtML
http://www.blog.ityiqv.cn/Article/details/0392457.sHtML
http://www.blog.ityiqv.cn/Article/details/950797.sHtML
http://www.blog.ityiqv.cn/Article/details/80497.sHtML
http://www.blog.ityiqv.cn/Article/details/888911.sHtML
http://www.blog.ityiqv.cn/Article/details/4926860.sHtML
http://www.blog.ityiqv.cn/Article/details/5610956.sHtML
http://www.blog.ityiqv.cn/Article/details/981487.sHtML
http://www.blog.ityiqv.cn/Article/details/9907.sHtML
http://www.blog.ityiqv.cn/Article/details/40825.sHtML
http://www.blog.ityiqv.cn/Article/details/02464.sHtML
http://www.blog.ityiqv.cn/Article/details/3267.sHtML
http://www.blog.ityiqv.cn/Article/details/1321980.sHtML
http://www.blog.ityiqv.cn/Article/details/2588.sHtML
http://www.blog.ityiqv.cn/Article/details/5721659.sHtML
http://www.blog.ityiqv.cn/Article/details/0199.sHtML
http://www.blog.ityiqv.cn/Article/details/448737.sHtML
http://www.blog.ityiqv.cn/Article/details/539658.sHtML
http://www.blog.ityiqv.cn/Article/details/5491.sHtML
http://www.blog.ityiqv.cn/Article/details/7928485.sHtML
http://www.blog.ityiqv.cn/Article/details/1970.sHtML
http://www.blog.ityiqv.cn/Article/details/0114563.sHtML
http://www.blog.ityiqv.cn/Article/details/8933.sHtML
http://www.blog.ityiqv.cn/Article/details/1970100.sHtML
http://www.blog.ityiqv.cn/Article/details/0160.sHtML
http://www.blog.ityiqv.cn/Article/details/65002.sHtML
http://www.blog.ityiqv.cn/Article/details/2477.sHtML
http://www.blog.ityiqv.cn/Article/details/595011.sHtML
http://www.blog.ityiqv.cn/Article/details/929504.sHtML
http://www.blog.ityiqv.cn/Article/details/890099.sHtML
http://www.blog.ityiqv.cn/Article/details/9343.sHtML
http://www.blog.ityiqv.cn/Article/details/84703.sHtML
http://www.blog.ityiqv.cn/Article/details/063839.sHtML
http://www.blog.ityiqv.cn/Article/details/3124682.sHtML
http://www.blog.ityiqv.cn/Article/details/11038.sHtML
http://www.blog.ityiqv.cn/Article/details/75077.sHtML
http://www.blog.ityiqv.cn/Article/details/84531.sHtML
http://www.blog.ityiqv.cn/Article/details/8367805.sHtML
http://www.blog.ityiqv.cn/Article/details/65396.sHtML
http://www.blog.ityiqv.cn/Article/details/1362593.sHtML
http://www.blog.ityiqv.cn/Article/details/37714.sHtML
http://www.blog.ityiqv.cn/Article/details/32938.sHtML
http://www.blog.ityiqv.cn/Article/details/272959.sHtML
http://www.blog.ityiqv.cn/Article/details/914024.sHtML
http://www.blog.ityiqv.cn/Article/details/7161134.sHtML
http://www.blog.ityiqv.cn/Article/details/6947.sHtML
http://www.blog.ityiqv.cn/Article/details/0536.sHtML
http://www.blog.ityiqv.cn/Article/details/5504.sHtML
http://www.blog.ityiqv.cn/Article/details/682139.sHtML
http://www.blog.ityiqv.cn/Article/details/4158.sHtML
http://www.blog.ityiqv.cn/Article/details/895687.sHtML
http://www.blog.ityiqv.cn/Article/details/3314069.sHtML
http://www.blog.ityiqv.cn/Article/details/40679.sHtML
http://www.blog.ityiqv.cn/Article/details/85712.sHtML
http://www.blog.ityiqv.cn/Article/details/6923.sHtML
http://www.blog.ityiqv.cn/Article/details/632420.sHtML
http://www.blog.ityiqv.cn/Article/details/81627.sHtML
http://www.blog.ityiqv.cn/Article/details/465550.sHtML
http://www.blog.ityiqv.cn/Article/details/7544868.sHtML
http://www.blog.ityiqv.cn/Article/details/7719.sHtML
http://www.blog.ityiqv.cn/Article/details/979107.sHtML
http://www.blog.ityiqv.cn/Article/details/47087.sHtML
http://www.blog.ityiqv.cn/Article/details/601389.sHtML
http://www.blog.ityiqv.cn/Article/details/0862.sHtML
http://www.blog.ityiqv.cn/Article/details/6804.sHtML
http://www.blog.ityiqv.cn/Article/details/1827.sHtML
http://www.blog.ityiqv.cn/Article/details/8940.sHtML
http://www.blog.ityiqv.cn/Article/details/9902.sHtML
http://www.blog.ityiqv.cn/Article/details/771106.sHtML

## 项目结构

```
techlink-navigator/
├── manage.py                         # Django 项目管理入口
├── requirements.txt                  # 生产环境依赖清单
├── requirements-dev.txt              # 开发调试额外依赖
├── .env.example                      # 环境变量配置模板
├── docker-compose.yml                # 本地容器编排（PostgreSQL + Redis）
│
├── application/                      # 核心应用主目录
│   ├── settings/                     # 分环境配置
│   │   ├── base.py                   # 基础配置（所有环境共用）
│   │   ├── development.py            # 开发环境配置（DEBUG=True）
│   │   └── production.py             # 生产环境配置（DEBUG=False）
│   ├── urls.py                       # 主路由分发
│   └── wsgi.py                       # WSGI 启动入口
│
├── apps/                             # 所有独立功能模块
│   ├── links/                        # 链接管理模块
│   │   ├── models.py                 # Link、Category、Tag 数据模型
│   │   ├── views.py                  # 链接列表、详情、搜索视图
│   │   ├── services.py               # 链接校验、元数据抓取业务逻辑
│   │   └── tasks.py                  # Celery 异步任务（每日校验）
│   ├── users/                        # 用户认证与个人中心
│   │   ├── models.py                 # 自定义用户模型与收藏关系
│   │   └── views.py                  # 注册、登录、收藏夹管理
│   ├── api/                          # RESTful API 接口
│   │   ├── serializers.py            # 链接与分类序列化器
│   │   └── endpoints.py              # /api/links, /api/categories 等端点
│   └── subscriptions/                # RSS 订阅与邮件通知
│       ├── feeds.py                  # 各分类 RSS 生成逻辑
│       └── notifiers.py              # 失效链接邮件告警
│
├── static/                           # 静态资源（CSS / JS / 图片）
│   ├── css/
│   └── js/
│
├── templates/                        # Django 模板文件
│   ├── base.html                     # 基础骨架模板
│   ├── links/                        # 链接列表与详情页模板
│   └── users/                        # 登录与注册页面模板
│
├── fixtures/                         # 初始数据种子
│   └── initial_links.json            # 预置外链数据（含本文收录链接）
│
├── scripts/                          # 运维与数据维护脚本
│   ├── import_csv.py                 # 从 CSV 批量导入链接
│   └── validate_all_links.py         # 手动触发全量链接校验
│
└── docs/                             # 完整文档目录
    ├── user-guide/
    ├── admin/
    ├── developer/
    ├── operations/
    ├── design/
    └── testing/
```

## 贡献指南

欢迎各类形式的贡献，包括但不限于新增外链收录、功能开发、文档改进与问题反馈。

**提交新链接收录请求**：在 GitHub Issues 中使用“链接推荐”模板，填写链接地址、所属分类与简短推荐理由。维护团队将在 3 个工作日内审核并决定是否收录。

**报告链接失效或内容变更**：若发现已收录链接无法访问或内容与描述严重不符，请在 Issues 中选择“链接失效报告”，附上链接地址与失效截图，便于快速处理。

**参与代码开发**：Fork 本仓库后，在 dev 分支进行开发。提交前请确保通过现有单元测试，并为新增功能编写对应测试用例。提交 Pull Request 时请参照 PR 模板填写改动说明。

**完善文档与翻译**：文档位于 /docs 目录，采用 Markdown 编写。欢迎修正错别字、补充示例或翻译为其他语言版本。提交时请单独针对文档改动发起 PR。

**参与讨论与答疑**：在 GitHub Discussions 中可提问、分享使用经验或提议新功能。活跃贡献者将被邀请加入协作团队。

## 常见问题

**Q：收录的链接出现 404 或连接超时，系统如何处理？**

A：系统通过 Celery 定时任务每 24 小时对所有链接执行一次 HEAD 请求校验。连续三次校验失败的链接会被自动标记为“失效”状态，并移出前端默认列表，同时管理员会收到邮件通知。用户仍可通过搜索找到失效链接并查看其历史记录，也可在页面上点击“报告失效”手动触发即时校验。

**Q：我想推荐链接但不想注册账号，是否可以？**

A：可以。本站提供匿名推荐入口，位于页面底部“推荐链接”表单。您只需填写链接地址、分类和简要说明即可提交。但匿名提交的链接需要经过人工审核，审核周期约 5 个工作日。注册用户提交的链接享有优先审核权，且可实时查看审核进度。

**Q：如何批量导出我的收藏夹？**

A：登录后进入个人中心“我的收藏”页面，点击“导出”按钮，可选择 CSV 或 JSON 格式。导出文件包含链接标题、原始地址、添加时间与自定义标签。导出操作不会删除收藏数据，后续可重新导入合并。

## 许可证

MIT License

Copyright (c) 2026 TechLink Navigator Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

> 外链数量: 250 | 生成时间: 2026-07-05 16:27:58
