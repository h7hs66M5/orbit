# LinkVault Resource Aggregator

LinkVault is a curated technical resource aggregation system designed for developers, researchers, and technical writers who need to organize, categorize, and retrieve large volumes of web-based reference materials. The project addresses the common problem of scattered bookmarks, lost reference links, and inefficient manual organization of technical articles by providing a structured indexing framework with automated metadata extraction and search capabilities.

Target users include open-source maintainers building documentation hubs, technical bloggers managing reference collections, and engineering teams maintaining internal knowledge bases. The system processes URL lists in batch mode, extracts article metadata including titles, categories, and timestamps, and generates searchable indexes that integrate with static site generators or API-based retrieval systems.

## 功能概览

**批量URL导入** - 支持从文本文件、CSV或直接粘贴导入大量URL列表进行批量处理。

**元数据自动提取** - 从目标页面自动提取标题、发布时间、文章分类、关键词等元数据信息。

**分类标签管理** - 支持自定义分类体系，对资源进行多级标签标注和分类检索。

**全文检索索引** - 基于提取的元数据和页面内容构建轻量级全文检索索引。

**导出格式转换** - 支持将资源列表导出为Markdown、JSON、CSV或HTML格式。

**增量更新机制** - 支持定期检查URL有效性，自动标记失效链接并更新元数据变更。

**API查询接口** - 提供RESTful API接口，支持按分类、标签、关键词进行程序化查询。

**静态站点生成** - 内置模板引擎，可一键生成资源导航静态网站。

## 应用场景

技术文档团队维护外部参考链接库。团队在撰写技术方案时需引用大量外部规范、论文或博客文章，通过LinkVault建立分类索引，成员可快速查找并引用经过验证的参考链接。

开源项目构建社区资源导航页。项目维护者收集社区教程、插件生态、相关工具等链接，使用LinkVault生成结构化的资源导航页面，方便新用户快速了解项目生态。

个人开发者整理技术书签。开发者将日常积累的技术文章按编程语言、框架、算法等维度分类，配合全文检索功能，可在需要时快速定位特定主题的参考资料。

企业内部知识库外部资源整合。企业将员工分享的外部技术文章、行业报告、会议视频等链接统一入库，建立可共享的部门级技术资源库。

## 快速开始

```bash
# 克隆仓库
git clone https://github.com/your-org/linkvault.git
cd linkvault

# 安装依赖
pip install -r requirements.txt

# 初始化数据库并运行服务
python manage.py init
python manage.py runserver --port 8080
```

## 安装要求

| 依赖 | 必需版本 | 说明 |
|------|----------|------|
| Python | 3.9+ | 核心运行时环境 |
| SQLite | 3.35+ | 默认元数据存储引擎 |
| requests | 2.28+ | HTTP请求与页面抓取 |
| beautifulsoup4 | 4.11+ | HTML解析与元数据提取 |
| lxml | 4.9+ | XML/HTML解析器后端 |
| whoosh | 2.7+ | 全文检索索引库 |
| jinja2 | 3.1+ | 静态站点模板引擎 |
| click | 8.1+ | 命令行界面框架 |
| pytest | 7.2+ | 单元测试框架（开发依赖） |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|------------|
| 入门指南 | docs/quickstart.md | 如何安装部署并完成第一次资源导入？ |
| 配置参考 | docs/configuration.md | 支持哪些配置选项？如何调整抓取间隔和超时？ |
| API文档 | docs/api.md | 查询接口的端点、参数和返回格式是什么？ |
| 模板开发 | docs/templating.md | 如何自定义静态站点的页面布局和样式？ |
| 数据迁移 | docs/migration.md | 如何从旧版本升级或迁移到其他数据库？ |
| 性能调优 | docs/performance.md | 批量处理大量URL时的内存和网络优化建议 |

## 资源列表

核心技术资源

http://www.blog.ityiqv.cn/Article/details/8885.sHtML
http://www.blog.ityiqv.cn/Article/details/9883602.sHtML
http://www.blog.ityiqv.cn/Article/details/9934154.sHtML
http://www.blog.ityiqv.cn/Article/details/769331.sHtML
http://www.blog.ityiqv.cn/Article/details/2731.sHtML
http://www.blog.ityiqv.cn/Article/details/385651.sHtML
http://www.blog.ityiqv.cn/Article/details/1254437.sHtML
http://www.blog.ityiqv.cn/Article/details/1742156.sHtML
http://www.blog.ityiqv.cn/Article/details/284261.sHtML
http://www.blog.ityiqv.cn/Article/details/357660.sHtML
http://www.blog.ityiqv.cn/Article/details/365351.sHtML
http://www.blog.ityiqv.cn/Article/details/48905.sHtML
http://www.blog.ityiqv.cn/Article/details/40395.sHtML
http://www.blog.ityiqv.cn/Article/details/30821.sHtML
http://www.blog.ityiqv.cn/Article/details/9566.sHtML
http://www.blog.ityiqv.cn/Article/details/8291.sHtML
http://www.blog.ityiqv.cn/Article/details/8210.sHtML
http://www.blog.ityiqv.cn/Article/details/02620.sHtML
http://www.blog.ityiqv.cn/Article/details/1089.sHtML
http://www.blog.ityiqv.cn/Article/details/9016354.sHtML
http://www.blog.ityiqv.cn/Article/details/36447.sHtML
http://www.blog.ityiqv.cn/Article/details/31730.sHtML
http://www.blog.ityiqv.cn/Article/details/966384.sHtML
http://www.blog.ityiqv.cn/Article/details/2103030.sHtML
http://www.blog.ityiqv.cn/Article/details/2556682.sHtML
http://www.blog.ityiqv.cn/Article/details/0548.sHtML
http://www.blog.ityiqv.cn/Article/details/9520.sHtML
http://www.blog.ityiqv.cn/Article/details/6364365.sHtML
http://www.blog.ityiqv.cn/Article/details/0378619.sHtML
http://www.blog.ityiqv.cn/Article/details/0142.sHtML
http://www.blog.ityiqv.cn/Article/details/8363598.sHtML
http://www.blog.ityiqv.cn/Article/details/74820.sHtML
http://www.blog.ityiqv.cn/Article/details/979110.sHtML
http://www.blog.ityiqv.cn/Article/details/692454.sHtML
http://www.blog.ityiqv.cn/Article/details/1749.sHtML
http://www.blog.ityiqv.cn/Article/details/677813.sHtML
http://www.blog.ityiqv.cn/Article/details/9565.sHtML
http://www.blog.ityiqv.cn/Article/details/8388437.sHtML
http://www.blog.ityiqv.cn/Article/details/6934.sHtML
http://www.blog.ityiqv.cn/Article/details/12727.sHtML
http://www.blog.ityiqv.cn/Article/details/68153.sHtML
http://www.blog.ityiqv.cn/Article/details/5972478.sHtML
http://www.blog.ityiqv.cn/Article/details/468684.sHtML
http://www.blog.ityiqv.cn/Article/details/797905.sHtML
http://www.blog.ityiqv.cn/Article/details/7413612.sHtML
http://www.blog.ityiqv.cn/Article/details/5247.sHtML
http://www.blog.ityiqv.cn/Article/details/0419351.sHtML
http://www.blog.ityiqv.cn/Article/details/5809.sHtML
http://www.blog.ityiqv.cn/Article/details/74204.sHtML
http://www.blog.ityiqv.cn/Article/details/052741.sHtML
http://www.blog.ityiqv.cn/Article/details/692587.sHtML
http://www.blog.ityiqv.cn/Article/details/315963.sHtML
http://www.blog.ityiqv.cn/Article/details/6447175.sHtML
http://www.blog.ityiqv.cn/Article/details/8207153.sHtML
http://www.blog.ityiqv.cn/Article/details/2969.sHtML
http://www.blog.ityiqv.cn/Article/details/916788.sHtML
http://www.blog.ityiqv.cn/Article/details/462503.sHtML
http://www.blog.ityiqv.cn/Article/details/5296.sHtML
http://www.blog.ityiqv.cn/Article/details/6318.sHtML
http://www.blog.ityiqv.cn/Article/details/4495331.sHtML
http://www.blog.ityiqv.cn/Article/details/8963.sHtML
http://www.blog.ityiqv.cn/Article/details/9599050.sHtML
http://www.blog.ityiqv.cn/Article/details/732701.sHtML
http://www.blog.ityiqv.cn/Article/details/3134600.sHtML
http://www.blog.ityiqv.cn/Article/details/52635.sHtML
http://www.blog.ityiqv.cn/Article/details/170952.sHtML
http://www.blog.ityiqv.cn/Article/details/7351.sHtML
http://www.blog.ityiqv.cn/Article/details/6161.sHtML
http://www.blog.ityiqv.cn/Article/details/57325.sHtML
http://www.blog.ityiqv.cn/Article/details/8590043.sHtML
http://www.blog.ityiqv.cn/Article/details/5582.sHtML
http://www.blog.ityiqv.cn/Article/details/93165.sHtML
http://www.blog.ityiqv.cn/Article/details/8502.sHtML
http://www.blog.ityiqv.cn/Article/details/22482.sHtML
http://www.blog.ityiqv.cn/Article/details/008738.sHtML
http://www.blog.ityiqv.cn/Article/details/187418.sHtML
http://www.blog.ityiqv.cn/Article/details/711783.sHtML
http://www.blog.ityiqv.cn/Article/details/1336.sHtML
http://www.blog.ityiqv.cn/Article/details/19904.sHtML
http://www.blog.ityiqv.cn/Article/details/62756.sHtML
http://www.blog.ityiqv.cn/Article/details/23922.sHtML
http://www.blog.ityiqv.cn/Article/details/9254013.sHtML
http://www.blog.ityiqv.cn/Article/details/953328.sHtML
http://www.blog.ityiqv.cn/Article/details/151324.sHtML
http://www.blog.ityiqv.cn/Article/details/731029.sHtML
http://www.blog.ityiqv.cn/Article/details/6151.sHtML
http://www.blog.ityiqv.cn/Article/details/866963.sHtML
http://www.blog.ityiqv.cn/Article/details/04468.sHtML
http://www.blog.ityiqv.cn/Article/details/5138423.sHtML
http://www.blog.ityiqv.cn/Article/details/637311.sHtML
http://www.blog.ityiqv.cn/Article/details/80042.sHtML
http://www.blog.ityiqv.cn/Article/details/7732.sHtML
http://www.blog.ityiqv.cn/Article/details/958077.sHtML
http://www.blog.ityiqv.cn/Article/details/73019.sHtML
http://www.blog.ityiqv.cn/Article/details/37874.sHtML
http://www.blog.ityiqv.cn/Article/details/9355556.sHtML
http://www.blog.ityiqv.cn/Article/details/7921.sHtML
http://www.blog.ityiqv.cn/Article/details/148188.sHtML
http://www.blog.ityiqv.cn/Article/details/889928.sHtML
http://www.blog.ityiqv.cn/Article/details/4740734.sHtML
http://www.blog.ityiqv.cn/Article/details/81614.sHtML
http://www.blog.ityiqv.cn/Article/details/21158.sHtML
http://www.blog.ityiqv.cn/Article/details/82757.sHtML
http://www.blog.ityiqv.cn/Article/details/234276.sHtML
http://www.blog.ityiqv.cn/Article/details/2132908.sHtML
http://www.blog.ityiqv.cn/Article/details/0932.sHtML
http://www.blog.ityiqv.cn/Article/details/5721.sHtML
http://www.blog.ityiqv.cn/Article/details/93258.sHtML
http://www.blog.ityiqv.cn/Article/details/991838.sHtML
http://www.blog.ityiqv.cn/Article/details/1303.sHtML
http://www.blog.ityiqv.cn/Article/details/2567.sHtML
http://www.blog.ityiqv.cn/Article/details/272423.sHtML
http://www.blog.ityiqv.cn/Article/details/7874940.sHtML
http://www.blog.ityiqv.cn/Article/details/86971.sHtML
http://www.blog.ityiqv.cn/Article/details/3974.sHtML
http://www.blog.ityiqv.cn/Article/details/5486.sHtML
http://www.blog.ityiqv.cn/Article/details/48170.sHtML
http://www.blog.ityiqv.cn/Article/details/55117.sHtML
http://www.blog.ityiqv.cn/Article/details/005832.sHtML
http://www.blog.ityiqv.cn/Article/details/3419025.sHtML
http://www.blog.ityiqv.cn/Article/details/19980.sHtML
http://www.blog.ityiqv.cn/Article/details/597587.sHtML
http://www.blog.ityiqv.cn/Article/details/876003.sHtML
http://www.blog.ityiqv.cn/Article/details/988325.sHtML
http://www.blog.ityiqv.cn/Article/details/15321.sHtML
http://www.blog.ityiqv.cn/Article/details/439094.sHtML
http://www.blog.ityiqv.cn/Article/details/9741.sHtML
http://www.blog.ityiqv.cn/Article/details/9758003.sHtML
http://www.blog.ityiqv.cn/Article/details/49927.sHtML
http://www.blog.ityiqv.cn/Article/details/098548.sHtML
http://www.blog.ityiqv.cn/Article/details/380877.sHtML
http://www.blog.ityiqv.cn/Article/details/4662.sHtML
http://www.blog.ityiqv.cn/Article/details/9671.sHtML
http://www.blog.ityiqv.cn/Article/details/4859659.sHtML
http://www.blog.ityiqv.cn/Article/details/8566.sHtML
http://www.blog.ityiqv.cn/Article/details/1579.sHtML
http://www.blog.ityiqv.cn/Article/details/4890.sHtML
http://www.blog.ityiqv.cn/Article/details/6730961.sHtML
http://www.blog.ityiqv.cn/Article/details/846961.sHtML
http://www.blog.ityiqv.cn/Article/details/07926.sHtML
http://www.blog.ityiqv.cn/Article/details/1682791.sHtML
http://www.blog.ityiqv.cn/Article/details/5210992.sHtML
http://www.blog.ityiqv.cn/Article/details/630879.sHtML
http://www.blog.ityiqv.cn/Article/details/945726.sHtML
http://www.blog.ityiqv.cn/Article/details/56084.sHtML
http://www.blog.ityiqv.cn/Article/details/9533021.sHtML
http://www.blog.ityiqv.cn/Article/details/8572.sHtML
http://www.blog.ityiqv.cn/Article/details/4297.sHtML
http://www.blog.ityiqv.cn/Article/details/5113.sHtML
http://www.blog.ityiqv.cn/Article/details/487536.sHtML
http://www.blog.ityiqv.cn/Article/details/050500.sHtML
http://www.blog.ityiqv.cn/Article/details/1059639.sHtML
http://www.blog.ityiqv.cn/Article/details/44976.sHtML
http://www.blog.ityiqv.cn/Article/details/24056.sHtML
http://www.blog.ityiqv.cn/Article/details/3942080.sHtML
http://www.blog.ityiqv.cn/Article/details/9250.sHtML
http://www.blog.ityiqv.cn/Article/details/549076.sHtML
http://www.blog.ityiqv.cn/Article/details/88474.sHtML
http://www.blog.ityiqv.cn/Article/details/6334610.sHtML
http://www.blog.ityiqv.cn/Article/details/590557.sHtML
http://www.blog.ityiqv.cn/Article/details/6700440.sHtML
http://www.blog.ityiqv.cn/Article/details/583658.sHtML
http://www.blog.ityiqv.cn/Article/details/481163.sHtML
http://www.blog.ityiqv.cn/Article/details/7061.sHtML
http://www.blog.ityiqv.cn/Article/details/64608.sHtML
http://www.blog.ityiqv.cn/Article/details/7250.sHtML
http://www.blog.ityiqv.cn/Article/details/996258.sHtML
http://www.blog.ityiqv.cn/Article/details/5750.sHtML
http://www.blog.ityiqv.cn/Article/details/6766687.sHtML
http://www.blog.ityiqv.cn/Article/details/63270.sHtML
http://www.blog.ityiqv.cn/Article/details/4919.sHtML
http://www.blog.ityiqv.cn/Article/details/2440897.sHtML
http://www.blog.ityiqv.cn/Article/details/07284.sHtML
http://www.blog.ityiqv.cn/Article/details/6280715.sHtML
http://www.blog.ityiqv.cn/Article/details/5095368.sHtML
http://www.blog.ityiqv.cn/Article/details/9364916.sHtML
http://www.blog.ityiqv.cn/Article/details/9439.sHtML
http://www.blog.ityiqv.cn/Article/details/509478.sHtML
http://www.blog.ityiqv.cn/Article/details/3108.sHtML
http://www.blog.ityiqv.cn/Article/details/9294423.sHtML
http://www.blog.ityiqv.cn/Article/details/0220.sHtML
http://www.blog.ityiqv.cn/Article/details/995137.sHtML
http://www.blog.ityiqv.cn/Article/details/665325.sHtML
http://www.blog.ityiqv.cn/Article/details/987888.sHtML
http://www.blog.ityiqv.cn/Article/details/9204.sHtML
http://www.blog.ityiqv.cn/Article/details/0832562.sHtML
http://www.blog.ityiqv.cn/Article/details/6668456.sHtML
http://www.blog.ityiqv.cn/Article/details/5717707.sHtML
http://www.blog.ityiqv.cn/Article/details/3269969.sHtML
http://www.blog.ityiqv.cn/Article/details/1436151.sHtML
http://www.blog.ityiqv.cn/Article/details/22487.sHtML
http://www.blog.ityiqv.cn/Article/details/6174136.sHtML
http://www.blog.ityiqv.cn/Article/details/496151.sHtML
http://www.blog.ityiqv.cn/Article/details/078625.sHtML
http://www.blog.ityiqv.cn/Article/details/2438559.sHtML
http://www.blog.ityiqv.cn/Article/details/5415347.sHtML
http://www.blog.ityiqv.cn/Article/details/958150.sHtML
http://www.blog.ityiqv.cn/Article/details/22840.sHtML
http://www.blog.ityiqv.cn/Article/details/5563.sHtML
http://www.blog.ityiqv.cn/Article/details/8130.sHtML
http://www.blog.ityiqv.cn/Article/details/6415970.sHtML
http://www.blog.ityiqv.cn/Article/details/4934624.sHtML
http://www.blog.ityiqv.cn/Article/details/8206.sHtML
http://www.blog.ityiqv.cn/Article/details/049686.sHtML
http://www.blog.ityiqv.cn/Article/details/48577.sHtML
http://www.blog.ityiqv.cn/Article/details/828151.sHtML
http://www.blog.ityiqv.cn/Article/details/13199.sHtML
http://www.blog.ityiqv.cn/Article/details/78641.sHtML
http://www.blog.ityiqv.cn/Article/details/5344510.sHtML
http://www.blog.ityiqv.cn/Article/details/42923.sHtML
http://www.blog.ityiqv.cn/Article/details/3982452.sHtML
http://www.blog.ityiqv.cn/Article/details/47322.sHtML
http://www.blog.ityiqv.cn/Article/details/12213.sHtML
http://www.blog.ityiqv.cn/Article/details/359042.sHtML
http://www.blog.ityiqv.cn/Article/details/3722.sHtML
http://www.blog.ityiqv.cn/Article/details/244430.sHtML
http://www.blog.ityiqv.cn/Article/details/3840441.sHtML
http://www.blog.ityiqv.cn/Article/details/889834.sHtML
http://www.blog.ityiqv.cn/Article/details/15603.sHtML
http://www.blog.ityiqv.cn/Article/details/4180.sHtML
http://www.blog.ityiqv.cn/Article/details/67289.sHtML
http://www.blog.ityiqv.cn/Article/details/93225.sHtML
http://www.blog.ityiqv.cn/Article/details/536408.sHtML
http://www.blog.ityiqv.cn/Article/details/865944.sHtML
http://www.blog.ityiqv.cn/Article/details/25931.sHtML
http://www.blog.ityiqv.cn/Article/details/1493.sHtML
http://www.blog.ityiqv.cn/Article/details/4825.sHtML
http://www.blog.ityiqv.cn/Article/details/0480.sHtML
http://www.blog.ityiqv.cn/Article/details/487339.sHtML
http://www.blog.ityiqv.cn/Article/details/6759.sHtML
http://www.blog.ityiqv.cn/Article/details/422197.sHtML
http://www.blog.ityiqv.cn/Article/details/1542216.sHtML
http://www.blog.ityiqv.cn/Article/details/1887983.sHtML
http://www.blog.ityiqv.cn/Article/details/737640.sHtML
http://www.blog.ityiqv.cn/Article/details/2398.sHtML
http://www.blog.ityiqv.cn/Article/details/0039.sHtML
http://www.blog.ityiqv.cn/Article/details/4528.sHtML
http://www.blog.ityiqv.cn/Article/details/4047.sHtML
http://www.blog.ityiqv.cn/Article/details/091183.sHtML
http://www.blog.ityiqv.cn/Article/details/379955.sHtML
http://www.blog.ityiqv.cn/Article/details/69660.sHtML
http://www.blog.ityiqv.cn/Article/details/0917982.sHtML
http://www.blog.ityiqv.cn/Article/details/51177.sHtML
http://www.blog.ityiqv.cn/Article/details/7730551.sHtML
http://www.blog.ityiqv.cn/Article/details/61250.sHtML
http://www.blog.ityiqv.cn/Article/details/3066.sHtML
http://www.blog.ityiqv.cn/Article/details/7819383.sHtML
http://www.blog.ityiqv.cn/Article/details/4504635.sHtML
http://www.blog.ityiqv.cn/Article/details/2013.sHtML
http://www.blog.ityiqv.cn/Article/details/909125.sHtML

## 项目结构

```
linkvault/
├── src/                              # 源代码主目录
│   ├── core/                         # 核心业务逻辑
│   │   ├── aggregator.py             # URL聚合与批量处理引擎
│   │   ├── metadata.py               # 元数据提取器（标题/分类/时间）
│   │   └── validator.py              # URL有效性验证与健康检查
│   ├── storage/                      # 存储层
│   │   ├── database.py               # SQLite数据库操作封装
│   │   ├── index.py                  # Whoosh全文索引管理
│   │   └── cache.py                  # LRU缓存实现（减少重复请求）
│   ├── api/                          # RESTful API服务
│   │   ├── routes.py                 # 路由定义与请求分发
│   │   ├── serializers.py            # 响应数据序列化
│   │   └── middlewares.py            # 请求日志与限流中间件
│   ├── exporter/                     # 导出模块
│   │   ├── markdown.py               # Markdown格式生成器
│   │   ├── json.py                   # JSON数据导出
│   │   └── static.py                 # 静态HTML站点生成器
│   └── cli/                          # 命令行工具
│       ├── main.py                   # CLI入口与子命令注册
│       ├── import_cmd.py             # 导入命令实现
│       └── export_cmd.py             # 导出命令实现
├── templates/                        # Jinja2模板文件
│   ├── base.html                     # 基础页面模板
│   ├── index.html                    # 资源列表首页模板
│   └── detail.html                   # 单条资源详情模板
├── tests/                            # 单元测试与集成测试
│   ├── test_metadata.py              # 元数据提取测试用例
│   ├── test_api.py                   # API端点测试
│   └── fixtures/                     # 测试数据与模拟页面
├── docs/                             # 文档目录（详见文档导航）
├── scripts/                          # 运维与辅助脚本
│   ├── batch_import.sh               # 批量导入shell脚本
│   └── health_check.sh               # 定期健康检查脚本
├── config.yaml                       # 主配置文件（含超时/并发/重试设置）
├── requirements.txt                  # Python依赖清单
├── setup.py                          # 打包安装配置
└── README.md                         # 项目说明文档（本文件）
```

## 贡献指南

1. 阅读项目文档和贡献者行为准则，了解开发流程和代码规范。在GitHub上fork仓库并创建功能分支，分支命名格式为feature/功能描述或fix/问题描述。

2. 编写或修改代码时确保通过所有现有单元测试，并为新增功能添加对应的测试用例。使用pytest运行测试套件，保证代码覆盖率不低于85%。

3. 提交代码前运行代码格式化工具black和静态检查flake8，确保代码风格一致。提交信息遵循约定式提交规范（Conventional Commits），格式为type(scope): description。

4. 创建Pull Request并详细描述变更内容、测试结果和影响范围，等待维护者审查。审查通过后由维护者合并至主分支。

## 常见问题

问：处理大量URL时如何避免被目标网站封禁IP？

答：系统内置了可配置的请求间隔（默认500毫秒）和随机User-Agent轮换机制。建议在生产环境中启用代理池支持，并在配置文件中调整concurrency参数控制并发数。

问：提取的元数据不准确如何手动修正？

答：支持通过API或命令行工具对单条记录进行手动编辑。使用命令`linkvault edit --id <article_id>`进入交互式编辑模式，可修改标题、分类、标签等字段。

问：如何将现有浏览器书签导入系统？

答：支持导入Chrome和Firefox导出的HTML书签文件，使用命令`linkvault import --browser chrome --file bookmarks.html`即可自动解析并入库。也支持直接导入CSV格式的URL列表。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 16:28:03
