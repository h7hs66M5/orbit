# LinkVault

LinkVault 是一个面向技术研究者、开发者和内容创作者的轻量级外链资源聚合与导航工具。该项目并非传统意义上的爬虫或采集系统，而是一个结构化的外链元数据管理仓库，旨在解决个人知识管理过程中外部优质链接易丢失、难分类、不便检索的痛点。LinkVault 通过统一的条目格式、标签化分类和可定制的呈现模板，帮助用户将分散在浏览器书签、笔记软件或即时通讯记录中的海量 URL 转化为可长期维护、可团队共享、可快速检索的本地化知识资产。

LinkVault 适用于需要频繁引用外部技术资料、文档、博客或开源仓库的开发者，也适用于需要构建团队内部技术雷达或学习路径的架构师与技术负责人。项目本身不依赖任何外部数据库或云服务，所有数据以纯文本 Markdown 和 YAML Front Matter 形式存储，保证数据完全由用户控制，且与 Git 工作流天然兼容，便于版本追踪与协作审阅。

## 功能概览

**批量导入与去重**：支持从浏览器书签 HTML 导出文件、CSV 列表或纯文本 URL 清单中批量导入链接，自动检测并移除重复条目，保留最早添加的记录。

**层级化标签系统**：每个链接条目可关联多个标签，支持无限层级嵌套（如 `lang/python/framework`、`devops/ci/cd`），并提供标签使用频率统计与未使用标签清理建议。

**全文元数据检索**：基于链接标题、描述、标签、来源域名和添加日期构建本地倒排索引，支持布尔运算符（AND、OR、NOT）与通配符查询，检索结果可按相关性或时间排序。

**自定义导出模板**：内置 HTML、JSON、CSV 和纯文本四种导出格式，用户可基于 Jinja2 模板引擎自定义输出样式，便于将链接列表嵌入个人博客、Wiki 或项目文档。

**定期健康检查**：通过可配置的定时任务（默认每周一次）对库内链接发起 HEAD 请求，自动标记响应码非 200 的链接为“失效”，并生成失效报告供用户批量清理或更新。

**协作审阅工作流**：支持基于 Git 分支的链接增删改提案机制，每个变更可附带变更说明（Change Note），便于团队内部进行链接质量审核与合并讨论。

## 应用场景

**技术团队内部知识库构建**：团队可将日常开发中遇到的优秀博客、API 参考文档、开源项目地址统一录入 LinkVault，并按照业务模块或技术栈打上标签。新成员入职时，可通过导出的技术栈标签列表快速获取必读资料，大幅缩短上手周期。

**个人学习路径规划与跟踪**：学习者可将待读文章、在线课程页面、官方教程入口按学习阶段（基础、进阶、实战）和主题分类管理，配合健康检查功能自动提醒已失效的课程链接，避免因链接失效打断学习节奏。

**开源项目文档外链管理**：开源项目维护者可在仓库 `docs` 目录下维护一个 LinkVault 实例，集中存放所有外部引用（如依赖库主页、协议解读、性能对比报告），确保 README 和设计文档中的外链统一可追溯，减少多处维护导致的链接不一致问题。

**技术资讯周报自动化生成**：内容创作者可将每日阅读的优质资讯链接录入 LinkVault，利用标签筛选（如 `week/2026-w27`）和自定义导出模板，一键生成带摘要和分类的周报 HTML 文件，直接粘贴至博客或邮件客户端发布。

## 快速开始

以下命令将在当前目录下克隆 LinkVault 仓库，安装依赖并启动本地 Web 管理界面（默认监听 `127.0.0.1:8080`）。

```bash
git clone https://github.com/linkvault/linkvault.git
cd linkvault
pip install -r requirements.txt
python linkvault.py serve --port 8080
```

首次启动时会自动创建 `data/` 目录和初始配置文件 `config.yaml`。若需从现有书签文件导入，可使用 `import` 子命令：

```bash
python linkvault.py import --from bookmarks.html --format html
```

所有操作均会在 `data/audit.log` 中记录时间戳和操作类型，便于事后回溯。

## 安装要求

| 依赖 | 必需 | 说明 |
|------|------|------|
| Python 3.9 及以上 | 是 | 核心运行环境，低于 3.9 版本将无法解析类型注解 |
| pip 21.0 及以上 | 是 | 用于安装 requirements.txt 中列出的第三方库 |
| Git 2.25 及以上 | 是 | 仅在使用协作审阅工作流或克隆仓库时需要 |
| requests 2.28.0 及以上 | 是 | 用于健康检查功能中的 HTTP 请求发送 |
| PyYAML 6.0 及以上 | 是 | 用于解析和写入 `config.yaml` 及条目元数据 |
| Jinja2 3.1.0 及以上 | 否 | 仅在需要使用自定义导出模板功能时安装，未安装时回退至内置简约模板 |
| pytest 7.0 及以上 | 否 | 仅开发测试时需要，生产环境可不安装 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|------------|
| 入门指南 | `docs/getting-started.md` | 如何安装、初始化数据目录、添加第一条链接并进行首次检索 |
| 配置手册 | `docs/configuration.md` | 所有可用的 `config.yaml` 字段说明，包括检查间隔、标签别名、导出默认格式等 |
| 模板开发 | `docs/template-guide.md` | 自定义导出模板的语法、可用变量列表以及内置过滤器示例 |
| API 参考 | `docs/api-reference.md` | 核心模块（`core.py`、`indexer.py`、`checker.py`）的类与方法文档，供二次开发使用 |

## 资源列表

本项目第 16/280 批外链资源收录清单如下。所有条目均来自 `http://www.blog.fuvxie.cn/Article/` 下的技术文章存档，按文章编号升序排列，保留原始 URL 大小写与扩展名格式。

技术教程与开发笔记

http://www.blog.fuvxie.cn/Article/details/0007.sHtML
http://www.blog.fuvxie.cn/Article/details/0032.sHtML
http://www.blog.fuvxie.cn/Article/details/008418.sHtML
http://www.blog.fuvxie.cn/Article/details/015745.sHtML
http://www.blog.fuvxie.cn/Article/details/018348.sHtML
http://www.blog.fuvxie.cn/Article/details/01959.sHtML
http://www.blog.fuvxie.cn/Article/details/020188.sHtML
http://www.blog.fuvxie.cn/Article/details/021343.sHtML
http://www.blog.fuvxie.cn/Article/details/025642.sHtML
http://www.blog.fuvxie.cn/Article/details/02607.sHtML
http://www.blog.fuvxie.cn/Article/details/02755.sHtML
http://www.blog.fuvxie.cn/Article/details/04090.sHtML
http://www.blog.fuvxie.cn/Article/details/04164.sHtML
http://www.blog.fuvxie.cn/Article/details/0417.sHtML
http://www.blog.fuvxie.cn/Article/details/0447828.sHtML
http://www.blog.fuvxie.cn/Article/details/045252.sHtML
http://www.blog.fuvxie.cn/Article/details/050866.sHtML
http://www.blog.fuvxie.cn/Article/details/05383.sHtML
http://www.blog.fuvxie.cn/Article/details/0543008.sHtML
http://www.blog.fuvxie.cn/Article/details/05602.sHtML
http://www.blog.fuvxie.cn/Article/details/057181.sHtML
http://www.blog.fuvxie.cn/Article/details/0667113.sHtML
http://www.blog.fuvxie.cn/Article/details/06727.sHtML
http://www.blog.fuvxie.cn/Article/details/0697.sHtML
http://www.blog.fuvxie.cn/Article/details/075645.sHtML
http://www.blog.fuvxie.cn/Article/details/077018.sHtML
http://www.blog.fuvxie.cn/Article/details/0771.sHtML
http://www.blog.fuvxie.cn/Article/details/078560.sHtML
http://www.blog.fuvxie.cn/Article/details/0071610.sHtML
http://www.blog.fuvxie.cn/Article/details/08885.sHtML
http://www.blog.fuvxie.cn/Article/details/0890.sHtML
http://www.blog.fuvxie.cn/Article/details/089163.sHtML

架构设计与性能优化

http://www.blog.fuvxie.cn/Article/details/10350.sHtML
http://www.blog.fuvxie.cn/Article/details/104901.sHtML
http://www.blog.fuvxie.cn/Article/details/117712.sHtML
http://www.blog.fuvxie.cn/Article/details/1191856.sHtML
http://www.blog.fuvxie.cn/Article/details/121928.sHtML
http://www.blog.fuvxie.cn/Article/details/12289.sHtML
http://www.blog.fuvxie.cn/Article/details/12431.sHtML
http://www.blog.fuvxie.cn/Article/details/1289.sHtML
http://www.blog.fuvxie.cn/Article/details/129272.sHtML
http://www.blog.fuvxie.cn/Article/details/1430279.sHtML
http://www.blog.fuvxie.cn/Article/details/1438054.sHtML
http://www.blog.fuvxie.cn/Article/details/1452.sHtML
http://www.blog.fuvxie.cn/Article/details/1451925.sHtML
http://www.blog.fuvxie.cn/Article/details/1506732.sHtML
http://www.blog.fuvxie.cn/Article/details/15954.sHtML
http://www.blog.fuvxie.cn/Article/details/1665657.sHtML
http://www.blog.fuvxie.cn/Article/details/17038.sHtML
http://www.blog.fuvxie.cn/Article/details/17156.sHtML
http://www.blog.fuvxie.cn/Article/details/174267.sHtML
http://www.blog.fuvxie.cn/Article/details/194310.sHtML
http://www.blog.fuvxie.cn/Article/details/19454.sHtML

编程语言与框架专题

http://www.blog.fuvxie.cn/Article/details/20559.sHtML
http://www.blog.fuvxie.cn/Article/details/20888.sHtML
http://www.blog.fuvxie.cn/Article/details/2104.sHtML
http://www.blog.fuvxie.cn/Article/details/214437.sHtML
http://www.blog.fuvxie.cn/Article/details/226344.sHtML
http://www.blog.fuvxie.cn/Article/details/22656.sHtML
http://www.blog.fuvxie.cn/Article/details/2272.sHtML
http://www.blog.fuvxie.cn/Article/details/22873.sHtML
http://www.blog.fuvxie.cn/Article/details/235924.sHtML
http://www.blog.fuvxie.cn/Article/details/2449184.sHtML
http://www.blog.fuvxie.cn/Article/details/247541.sHtML
http://www.blog.fuvxie.cn/Article/details/2621372.sHtML
http://www.blog.fuvxie.cn/Article/details/26454.sHtML
http://www.blog.fuvxie.cn/Article/details/26978.sHtML
http://www.blog.fuvxie.cn/Article/details/2723.sHtML
http://www.blog.fuvxie.cn/Article/details/2755.sHtML
http://www.blog.fuvxie.cn/Article/details/286402.sHtML
http://www.blog.fuvxie.cn/Article/details/2868.sHtML
http://www.blog.fuvxie.cn/Article/details/29063.sHtML
http://www.blog.fuvxie.cn/Article/details/293185.sHtML
http://www.blog.fuvxie.cn/Article/details/2977.sHtML
http://www.blog.fuvxie.cn/Article/details/2997.sHtML

数据库与中间件

http://www.blog.fuvxie.cn/Article/details/3013035.sHtML
http://www.blog.fuvxie.cn/Article/details/3023.sHtML
http://www.blog.fuvxie.cn/Article/details/3095018.sHtML
http://www.blog.fuvxie.cn/Article/details/3108714.sHtML
http://www.blog.fuvxie.cn/Article/details/32874.sHtML
http://www.blog.fuvxie.cn/Article/details/33468.sHtML
http://www.blog.fuvxie.cn/Article/details/3407.sHtML
http://www.blog.fuvxie.cn/Article/details/3443034.sHtML
http://www.blog.fuvxie.cn/Article/details/349308.sHtML
http://www.blog.fuvxie.cn/Article/details/350880.sHtML
http://www.blog.fuvxie.cn/Article/details/3530213.sHtML
http://www.blog.fuvxie.cn/Article/details/3534869.sHtML
http://www.blog.fuvxie.cn/Article/details/357046.sHtML
http://www.blog.fuvxie.cn/Article/details/3616.sHtML
http://www.blog.fuvxie.cn/Article/details/3721.sHtML
http://www.blog.fuvxie.cn/Article/details/3887414.sHtML
http://www.blog.fuvxie.cn/Article/details/3890718.sHtML
http://www.blog.fuvxie.cn/Article/details/3947.sHtML
http://www.blog.fuvxie.cn/Article/details/39717.sHtML
http://www.blog.fuvxie.cn/Article/details/40321.sHtML
http://www.blog.fuvxie.cn/Article/details/404663.sHtML
http://www.blog.fuvxie.cn/Article/details/4170.sHtML
http://www.blog.fuvxie.cn/Article/details/4185.sHtML
http://www.blog.fuvxie.cn/Article/details/423484.sHtML
http://www.blog.fuvxie.cn/Article/details/4249702.sHtML
http://www.blog.fuvxie.cn/Article/details/4264558.sHtML
http://www.blog.fuvxie.cn/Article/details/4321404.sHtML
http://www.blog.fuvxie.cn/Article/details/4334454.sHtML
http://www.blog.fuvxie.cn/Article/details/4356316.sHtML
http://www.blog.fuvxie.cn/Article/details/437526.sHtML
http://www.blog.fuvxie.cn/Article/details/43964.sHtML

运维、监控与持续集成

http://www.blog.fuvxie.cn/Article/details/4469.sHtML
http://www.blog.fuvxie.cn/Article/details/449809.sHtML
http://www.blog.fuvxie.cn/Article/details/451685.sHtML
http://www.blog.fuvxie.cn/Article/details/4529.sHtML
http://www.blog.fuvxie.cn/Article/details/45310.sHtML
http://www.blog.fuvxie.cn/Article/details/4545318.sHtML
http://www.blog.fuvxie.cn/Article/details/45915.sHtML
http://www.blog.fuvxie.cn/Article/details/4634243.sHtML
http://www.blog.fuvxie.cn/Article/details/4651.sHtML
http://www.blog.fuvxie.cn/Article/details/47096.sHtML
http://www.blog.fuvxie.cn/Article/details/4720.sHtML
http://www.blog.fuvxie.cn/Article/details/47392.sHtML
http://www.blog.fuvxie.cn/Article/details/4745.sHtML
http://www.blog.fuvxie.cn/Article/details/4794.sHtML
http://www.blog.fuvxie.cn/Article/details/500077.sHtML
http://www.blog.fuvxie.cn/Article/details/5042.sHtML
http://www.blog.fuvxie.cn/Article/details/5061.sHtML
http://www.blog.fuvxie.cn/Article/details/509365.sHtML
http://www.blog.fuvxie.cn/Article/details/5168.sHtML
http://www.blog.fuvxie.cn/Article/details/5226.sHtML
http://www.blog.fuvxie.cn/Article/details/53530.sHtML
http://www.blog.fuvxie.cn/Article/details/538755.sHtML
http://www.blog.fuvxie.cn/Article/details/5448383.sHtML
http://www.blog.fuvxie.cn/Article/details/557274.sHtML
http://www.blog.fuvxie.cn/Article/details/56166.sHtML
http://www.blog.fuvxie.cn/Article/details/56667.sHtML
http://www.blog.fuvxie.cn/Article/details/56725.sHtML
http://www.blog.fuvxie.cn/Article/details/5817265.sHtML
http://www.blog.fuvxie.cn/Article/details/5862.sHtML
http://www.blog.fuvxie.cn/Article/details/58702.sHtML
http://www.blog.fuvxie.cn/Article/details/601973.sHtML
http://www.blog.fuvxie.cn/Article/details/6033.sHtML
http://www.blog.fuvxie.cn/Article/details/6121314.sHtML
http://www.blog.fuvxie.cn/Article/details/615952.sHtML
http://www.blog.fuvxie.cn/Article/details/61718.sHtML
http://www.blog.fuvxie.cn/Article/details/617928.sHtML
http://www.blog.fuvxie.cn/Article/details/6192.sHtML
http://www.blog.fuvxie.cn/Article/details/621837.sHtML
http://www.blog.fuvxie.cn/Article/details/6235331.sHtML
http://www.blog.fuvxie.cn/Article/details/62682.sHtML
http://www.blog.fuvxie.cn/Article/details/6285766.sHtML
http://www.blog.fuvxie.cn/Article/details/628755.sHtML
http://www.blog.fuvxie.cn/Article/details/6347575.sHtML
http://www.blog.fuvxie.cn/Article/details/6362725.sHtML
http://www.blog.fuvxie.cn/Article/details/6367114.sHtML
http://www.blog.fuvxie.cn/Article/details/6369713.sHtML
http://www.blog.fuvxie.cn/Article/details/6388.sHtML
http://www.blog.fuvxie.cn/Article/details/649091.sHtML
http://www.blog.fuvxie.cn/Article/details/652146.sHtML
http://www.blog.fuvxie.cn/Article/details/653512.sHtML
http://www.blog.fuvxie.cn/Article/details/6560939.sHtML
http://www.blog.fuvxie.cn/Article/details/6610.sHtML
http://www.blog.fuvxie.cn/Article/details/66539.sHtML
http://www.blog.fuvxie.cn/Article/details/670979.sHtML
http://www.blog.fuvxie.cn/Article/details/672330.sHtML
http://www.blog.fuvxie.cn/Article/details/6774701.sHtML
http://www.blog.fuvxie.cn/Article/details/6800.sHtML
http://www.blog.fuvxie.cn/Article/details/681481.sHtML
http://www.blog.fuvxie.cn/Article/details/68479.sHtML
http://www.blog.fuvxie.cn/Article/details/68560.sHtML
http://www.blog.fuvxie.cn/Article/details/6942293.sHtML
http://www.blog.fuvxie.cn/Article/details/7006587.sHtML
http://www.blog.fuvxie.cn/Article/details/70377.sHtML
http://www.blog.fuvxie.cn/Article/details/7044157.sHtML
http://www.blog.fuvxie.cn/Article/details/7079742.sHtML
http://www.blog.fuvxie.cn/Article/details/710155.sHtML
http://www.blog.fuvxie.cn/Article/details/71047.sHtML
http://www.blog.fuvxie.cn/Article/details/714177.sHtML
http://www.blog.fuvxie.cn/Article/details/715374.sHtML
http://www.blog.fuvxie.cn/Article/details/7225761.sHtML
http://www.blog.fuvxie.cn/Article/details/73251.sHtML
http://www.blog.fuvxie.cn/Article/details/737385.sHtML
http://www.blog.fuvxie.cn/Article/details/738178.sHtML
http://www.blog.fuvxie.cn/Article/details/73841.sHtML
http://www.blog.fuvxie.cn/Article/details/7407.sHtML
http://www.blog.fuvxie.cn/Article/details/74074.sHtML
http://www.blog.fuvxie.cn/Article/details/744777.sHtML
http://www.blog.fuvxie.cn/Article/details/7448.sHtML
http://www.blog.fuvxie.cn/Article/details/748522.sHtML
http://www.blog.fuvxie.cn/Article/details/7492787.sHtML
http://www.blog.fuvxie.cn/Article/details/755517.sHtML
http://www.blog.fuvxie.cn/Article/details/77016.sHtML
http://www.blog.fuvxie.cn/Article/details/780263.sHtML
http://www.blog.fuvxie.cn/Article/details/7806501.sHtML
http://www.blog.fuvxie.cn/Article/details/783684.sHtML
http://www.blog.fuvxie.cn/Article/details/78865.sHtML
http://www.blog.fuvxie.cn/Article/details/7934.sHtML
http://www.blog.fuvxie.cn/Article/details/7959269.sHtML
http://www.blog.fuvxie.cn/Article/details/80384.sHtML
http://www.blog.fuvxie.cn/Article/details/80851.sHtML
http://www.blog.fuvxie.cn/Article/details/8103.sHtML
http://www.blog.fuvxie.cn/Article/details/8175.sHtML
http://www.blog.fuvxie.cn/Article/details/8183.sHtML
http://www.blog.fuvxie.cn/Article/details/83072.sHtML
http://www.blog.fuvxie.cn/Article/details/830940.sHtML
http://www.blog.fuvxie.cn/Article/details/8457531.sHtML
http://www.blog.fuvxie.cn/Article/details/8458.sHtML
http://www.blog.fuvxie.cn/Article/details/8471887.sHtML
http://www.blog.fuvxie.cn/Article/details/84785.sHtML
http://www.blog.fuvxie.cn/Article/details/849206.sHtML
http://www.blog.fuvxie.cn/Article/details/8541.sHtML
http://www.blog.fuvxie.cn/Article/details/8543.sHtML
http://www.blog.fuvxie.cn/Article/details/854872.sHtML
http://www.blog.fuvxie.cn/Article/details/8564.sHtML
http://www.blog.fuvxie.cn/Article/details/8583475.sHtML
http://www.blog.fuvxie.cn/Article/details/85876.sHtML
http://www.blog.fuvxie.cn/Article/details/86429.sHtML
http://www.blog.fuvxie.cn/Article/details/8652.sHtML
http://www.blog.fuvxie.cn/Article/details/8712460.sHtML
http://www.blog.fuvxie.cn/Article/details/8737.sHtML
http://www.blog.fuvxie.cn/Article/details/8744300.sHtML
http://www.blog.fuvxie.cn/Article/details/875315.sHtML
http://www.blog.fuvxie.cn/Article/details/875329.sHtML
http://www.blog.fuvxie.cn/Article/details/876621.sHtML
http://www.blog.fuvxie.cn/Article/details/8815.sHtML
http://www.blog.fuvxie.cn/Article/details/88227.sHtML
http://www.blog.fuvxie.cn/Article/details/88763.sHtML
http://www.blog.fuvxie.cn/Article/details/89333.sHtML
http://www.blog.fuvxie.cn/Article/details/89449.sHtML
http://www.blog.fuvxie.cn/Article/details/90075.sHtML
http://www.blog.fuvxie.cn/Article/details/90334.sHtML
http://www.blog.fuvxie.cn/Article/details/9044.sHtML
http://www.blog.fuvxie.cn/Article/details/9052.sHtML
http://www.blog.fuvxie.cn/Article/details/90637.sHtML
http://www.blog.fuvxie.cn/Article/details/9071024.sHtML
http://www.blog.fuvxie.cn/Article/details/91453.sHtML
http://www.blog.fuvxie.cn/Article/details/922255.sHtML
http://www.blog.fuvxie.cn/Article/details/9256490.sHtML
http://www.blog.fuvxie.cn/Article/details/934920.sHtML
http://www.blog.fuvxie.cn/Article/details/938815.sHtML
http://www.blog.fuvxie.cn/Article/details/9397100.sHtML
http://www.blog.fuvxie.cn/Article/details/94497.sHtML
http://www.blog.fuvxie.cn/Article/details/9461.sHtML
http://www.blog.fuvxie.cn/Article/details/966251.sHtML
http://www.blog.fuvxie.cn/Article/details/97369.sHtML
http://www.blog.fuvxie.cn/Article/details/974096.sHtML
http://www.blog.fuvxie.cn/Article/details/9818661.sHtML
http://www.blog.fuvxie.cn/Article/details/98241.sHtML
http://www.blog.fuvxie.cn/Article/details/9827254.sHtML
http://www.blog.fuvxie.cn/Article/details/98705.sHtML
http://www.blog.fuvxie.cn/Article/details/98841.sHtML
http://www.blog.fuvxie.cn/Article/details/99338.sHtML
http://www.blog.fuvxie.cn/Article/details/9939058.sHtML
http://www.blog.fuvxie.cn/Article/details/99737.sHtML

## 项目结构

LinkVault 采用模块化分层设计，核心逻辑与数据存储严格分离，便于单元测试和未来扩展。

```
linkvault/
├── linkvault.py                # CLI 入口，负责子命令路由与参数解析
├── config.yaml                 # 用户配置文件（自动生成），包含检查间隔、标签别名、默认导出格式
├── requirements.txt            # 生产环境依赖列表（requests、pyyaml、jinja2 可选）
├── core/
│   ├── __init__.py
│   ├── models.py               # 定义 LinkEntry、Tag、CheckResult 等数据类（Pydantic 模型）
│   ├── storage.py              # 基于 YAML 文件的 CRUD 操作，负责读写 data/ 目录下的条目
│   ├── indexer.py              # 倒排索引构建与布尔查询执行器（基于 Python dict 和 set）
│   └── checker.py              # 异步 HTTP 健康检查调度器，使用 asyncio 和 aiohttp
├── web/
│   ├── __init__.py
│   ├── server.py               # 内置 Flask 应用，提供 /list、/search、/export 等路由
│   ├── templates/              # 默认 Jinja2 模板目录
│   │   ├── base.html
│   │   ├── list.html
│   │   └── report.html
│   └── static/                 # 内置 CSS 与 JavaScript（仅用于本地调试）
├── cli/
│   ├── __init__.py
│   ├── import_cmd.py           # 处理 --from 和 --format 参数的导入逻辑
│   ├── export_cmd.py           # 处理 --output 和 --template 参数的导出逻辑
│   └── check_cmd.py            # 手动触发健康检查子命令
├── data/                       # 用户数据目录（Git 忽略，但保留 .gitkeep）
│   ├── entries/                # 每个链接条目单独保存为一个 .yaml 文件，以 URL 的 MD5 命名
│   ├── tags/                   # 标签索引文件，记录每个标签下的条目 ID 列表
│   ├── index.pickle            # 倒排索引序列化文件（用于加速重启后首次检索）
│   ├── audit.log               # 操作审计日志（追加写入，含时间戳和操作人）
│   └── .gitkeep
├── tests/                      # 单元测试目录（pytest 框架）
│   ├── test_models.py
│   ├── test_storage.py
│   ├── test_indexer.py
│   └── conftest.py
└── docs/                       # 项目文档
    ├── getting-started.md
    ├── configuration.md
    ├── template-guide.md
    └── api-reference.md
```

## 贡献指南

LinkVault 遵循 GitHub Flow 协作模型，所有贡献均通过 Pull Request 进行。欢迎提交新功能、性能优化、文档改进或问题修复。

1. 从 `main` 分支创建新的功能分支，分支命名采用 `feat/`、`fix/` 或 `docs/` 前缀加简要描述，例如 `feat/import-from-pocket`。确保分支与上游仓库保持同步。

2. 编写代码时请遵循 PEP 8 风格规范，并为新增或修改的函数添加完整的 docstring（Google 风格）。所有对外暴露的 API 变动需同步更新 `docs/api-reference.md` 中的对应章节。

3. 提交前运行完整的测试套件（`pytest tests/`），确保所有现有测试通过。新增功能需附带对应的单元测试，测试覆盖率不应低于 85%。

4. 提交 Pull Request 时，请在描述中清晰说明变更动机、实现方案以及影响范围。若修复了已记录的 Issue，请使用 `Closes #ISSUE_NUMBER` 进行关联。

5. 项目维护者会在 3 个工作日内进行 Review，必要时会提出修改意见。合并后 CI 流水线将自动构建并发布新的 Docker 镜像（如有）和 PyPI 包。

## 常见问题

**Q：LinkVault 与传统的浏览器书签管理器有什么本质区别？**

A：浏览器书签管理器侧重于快速保存和访问，但缺乏对链接的元数据描述、标签层级、批量检索和健康状态追踪等深度管理能力。LinkVault 将链接视为可长期维护的知识资产，提供结构化的字段（如描述、标签、添加原因、过期时间）和基于本地索引的查询语法，更适合管理成百上千的技术参考链接。此外，所有数据以纯文本文件存储，便于与 Git 仓库结合实现版本控制和团队协同。

**Q：健康检查功能会频繁请求外部站点，是否会被目标服务器封禁？**

A：LinkVault 的健康检查采用保守策略：默认并发数不超过 5，每个请求超时时间为 10 秒，且会在请求头中设置 `User-Agent: LinkVault-HealthCheck/1.0` 以表明身份。用户可在 `config.yaml` 中调整 `check_interval` 和 `max_concurrent` 参数。若目标站点有明确的 `robots.txt` 禁止抓取策略，建议用户将该域名加入 `check_whitelist` 或直接禁用对该域名的检查。项目不鼓励也不支持高频率或隐蔽性探测行为。

**Q：能否将 LinkVault 部署为团队共用的 Web 服务？**

A：可以。LinkVault 内置的 Flask 服务器支持 `--host 0.0.0.0` 参数，可绑定至非本地地址。但需要注意：当前版本未内置身份验证和权限管理模块，因此不建议直接暴露在公网。团队共用场景下，推荐的做法是将 LinkVault 仓库托管在内网 Git 服务器上，各成员通过 Git 同步数据变更，使用本地 Web 界面或 CLI 进行查询和导出操作。若需要中心化服务，建议在反向代理层（如 nginx）配置基础认证（Basic Auth）或 OAuth2 Proxy。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 16:26:27
