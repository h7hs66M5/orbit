# TechRef Navigator

TechRef Navigator 是一个面向技术研发与工程实践人员的结构化外链资源导航系统。项目定位于技术文档、开发教程、架构案例与运维笔记的集中式收录与索引平台，解决开发者在海量技术博客与碎片化知识中难以快速定位有效信息的问题。本项目不对原始内容做二次加工，仅提供清晰分类、稳定引用与快速检索能力，适用于个人知识管理、团队技术栈梳理以及开源社区文档共建等场景。

本项目属于第 265/280 批次资源整合计划，当前收录有效外链共计 250 条，全部来源于技术博客域 blog.puhvjy.cn。所有链接均保持原始协议、域名、路径与大小写格式，确保引用精确性与可追溯性。

## 功能概览

**结构化资源索引**：按照文章主题、技术领域与内容形态对收录链接进行多维度分类，提供清晰查找路径。

**原始链接保真收录**：所有 URL 严格保留来源格式，不额外添加协议头、www 前缀或尾部斜杠，杜绝引用偏差。

**轻量化本地预览**：支持通过本地克隆与静态服务快速启动导航面板，无需依赖外部数据库或容器环境。

**全文检索辅助**：内置基于标题与分类关键词的简单匹配逻辑，便于在大量链接中执行定向筛选。

**可扩展分类体系**：采用 YAML 配置文件管理分类规则，用户可自行增删分类节点与标签，适应个性化需求。

**开源共建机制**：提供标准化的链接提交、分类建议与文档修正流程，鼓励社区参与者完善资源图谱。

## 应用场景

**技术选型调研**：架构师或技术负责人可通过本导航系统快速查阅特定领域（如微服务、消息队列、云原生）的实践文章与案例笔记，辅助决策。

**新员工技术栈熟悉**：团队可基于本系统整理内部推荐阅读清单，新成员通过浏览分类资源快速了解团队所涉及的技术生态与工程规范。

**离线文档镜像准备**：运维人员可将本导航所收录的链接批量导入离线下载工具，结合企业内网缓存服务，构建内部技术文档镜像站。

**技术写作素材收集**：技术博主或文档撰写者可利用本系统的分类链接作为参考资料池，快速定位权威或典型的技术分析文章。

## 快速开始

以下命令适用于 Linux / macOS / Windows WSL 环境，要求已安装 Git 与 Node.js 18 以上版本。

```bash
# 克隆仓库至本地
git clone https://github.com/techref-navigator/navigator.git
cd navigator

# 安装项目依赖
npm install

# 以开发模式启动本地导航服务
npm run dev
```

执行完成后，访问控制台输出的本地地址（通常为 http://127.0.0.1:3000）即可查看导航页面。生产环境部署可使用 `npm run build` 构建静态文件，并将 `dist` 目录托管至任意 HTTP 服务器。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Node.js | 18.x 或 20.x LTS | 运行时环境，用于执行构建与开发服务器 |
| npm | 9.x 或 10.x | 包管理器，用于安装项目依赖 |
| Git | 2.30 以上 | 版本控制工具，用于克隆仓库与提交贡献 |
| 现代浏览器 | Chrome 100+ / Firefox 100+ / Edge 100+ | 用于浏览导航界面，支持 ES2022 语法 |
| 磁盘空间 | 200 MB 以上 | 存放源代码、依赖包及构建产物 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户指南 | docs/user-guide.md | 如何使用导航面板进行检索、分类筛选与链接跳转 |
| 维护者手册 | docs/maintainer-guide.md | 如何新增、更新或废弃链接，如何管理分类标签 |
| 贡献规范 | docs/contributing.md | 提交链接的格式要求、分类规则与审核流程 |
| 架构说明 | docs/architecture.md | 项目的前端架构、数据流与扩展点设计 |

## 资源列表

### 技术文章类

http://www.blog.puhvjy.cn/Article/details/704277.sHtML
http://www.blog.puhvjy.cn/Article/details/6575.sHtML
http://www.blog.puhvjy.cn/Article/details/4750.sHtML
http://www.blog.puhvjy.cn/Article/details/379620.sHtML
http://www.blog.puhvjy.cn/Article/details/56611.sHtML
http://www.blog.puhvjy.cn/Article/details/5998.sHtML
http://www.blog.puhvjy.cn/Article/details/117039.sHtML
http://www.blog.puhvjy.cn/Article/details/070819.sHtML
http://www.blog.puhvjy.cn/Article/details/46336.sHtML
http://www.blog.puhvjy.cn/Article/details/593993.sHtML
http://www.blog.puhvjy.cn/Article/details/57800.sHtML
http://www.blog.puhvjy.cn/Article/details/8863064.sHtML
http://www.blog.puhvjy.cn/Article/details/6044.sHtML
http://www.blog.puhvjy.cn/Article/details/97674.sHtML
http://www.blog.puhvjy.cn/Article/details/906357.sHtML
http://www.blog.puhvjy.cn/Article/details/0806.sHtML
http://www.blog.puhvjy.cn/Article/details/517196.sHtML
http://www.blog.puhvjy.cn/Article/details/23819.sHtML
http://www.blog.puhvjy.cn/Article/details/7265.sHtML
http://www.blog.puhvjy.cn/Article/details/57393.sHtML
http://www.blog.puhvjy.cn/Article/details/2361.sHtML
http://www.blog.puhvjy.cn/Article/details/6058339.sHtML
http://www.blog.puhvjy.cn/Article/details/294684.sHtML
http://www.blog.puhvjy.cn/Article/details/5379992.sHtML
http://www.blog.puhvjy.cn/Article/details/8342.sHtML
http://www.blog.puhvjy.cn/Article/details/460510.sHtML
http://www.blog.puhvjy.cn/Article/details/3901.sHtML
http://www.blog.puhvjy.cn/Article/details/5076706.sHtML
http://www.blog.puhvjy.cn/Article/details/620090.sHtML
http://www.blog.puhvjy.cn/Article/details/76362.sHtML
http://www.blog.puhvjy.cn/Article/details/2715203.sHtML
http://www.blog.puhvjy.cn/Article/details/89210.sHtML
http://www.blog.puhvjy.cn/Article/details/2171929.sHtML
http://www.blog.puhvjy.cn/Article/details/5760.sHtML
http://www.blog.puhvjy.cn/Article/details/70798.sHtML
http://www.blog.puhvjy.cn/Article/details/5443.sHtML
http://www.blog.puhvjy.cn/Article/details/136226.sHtML
http://www.blog.puhvjy.cn/Article/details/12139.sHtML
http://www.blog.puhvjy.cn/Article/details/951778.sHtML
http://www.blog.puhvjy.cn/Article/details/03457.sHtML
http://www.blog.puhvjy.cn/Article/details/91888.sHtML
http://www.blog.puhvjy.cn/Article/details/9211667.sHtML
http://www.blog.puhvjy.cn/Article/details/586363.sHtML
http://www.blog.puhvjy.cn/Article/details/673254.sHtML
http://www.blog.puhvjy.cn/Article/details/821026.sHtML
http://www.blog.puhvjy.cn/Article/details/20218.sHtML
http://www.blog.puhvjy.cn/Article/details/9404139.sHtML
http://www.blog.puhvjy.cn/Article/details/062755.sHtML
http://www.blog.puhvjy.cn/Article/details/0734696.sHtML
http://www.blog.puhvjy.cn/Article/details/6704466.sHtML
http://www.blog.puhvjy.cn/Article/details/988969.sHtML
http://www.blog.puhvjy.cn/Article/details/7137446.sHtML
http://www.blog.puhvjy.cn/Article/details/308698.sHtML
http://www.blog.puhvjy.cn/Article/details/239611.sHtML
http://www.blog.puhvjy.cn/Article/details/17758.sHtML
http://www.blog.puhvjy.cn/Article/details/277183.sHtML
http://www.blog.puhvjy.cn/Article/details/8947238.sHtML
http://www.blog.puhvjy.cn/Article/details/3768468.sHtML
http://www.blog.puhvjy.cn/Article/details/15869.sHtML
http://www.blog.puhvjy.cn/Article/details/41942.sHtML
http://www.blog.puhvjy.cn/Article/details/2382469.sHtML
http://www.blog.puhvjy.cn/Article/details/6295.sHtML
http://www.blog.puhvjy.cn/Article/details/3280731.sHtML
http://www.blog.puhvjy.cn/Article/details/132491.sHtML
http://www.blog.puhvjy.cn/Article/details/4693.sHtML
http://www.blog.puhvjy.cn/Article/details/39388.sHtML
http://www.blog.puhvjy.cn/Article/details/1885.sHtML
http://www.blog.puhvjy.cn/Article/details/64463.sHtML
http://www.blog.puhvjy.cn/Article/details/4164621.sHtML
http://www.blog.puhvjy.cn/Article/details/29151.sHtML
http://www.blog.puhvjy.cn/Article/details/2772889.sHtML
http://www.blog.puhvjy.cn/Article/details/3552694.sHtML
http://www.blog.puhvjy.cn/Article/details/301841.sHtML
http://www.blog.puhvjy.cn/Article/details/900814.sHtML
http://www.blog.puhvjy.cn/Article/details/2017885.sHtML
http://www.blog.puhvjy.cn/Article/details/7228870.sHtML
http://www.blog.puhvjy.cn/Article/details/633226.sHtML
http://www.blog.puhvjy.cn/Article/details/508532.sHtML
http://www.blog.puhvjy.cn/Article/details/7468000.sHtML
http://www.blog.puhvjy.cn/Article/details/1408.sHtML
http://www.blog.puhvjy.cn/Article/details/7109286.sHtML
http://www.blog.puhvjy.cn/Article/details/094640.sHtML
http://www.blog.puhvjy.cn/Article/details/3386.sHtML
http://www.blog.puhvjy.cn/Article/details/4193.sHtML
http://www.blog.puhvjy.cn/Article/details/9832866.sHtML
http://www.blog.puhvjy.cn/Article/details/7084.sHtML
http://www.blog.puhvjy.cn/Article/details/7058.sHtML
http://www.blog.puhvjy.cn/Article/details/21639.sHtML
http://www.blog.puhvjy.cn/Article/details/9584217.sHtML
http://www.blog.puhvjy.cn/Article/details/4057.sHtML
http://www.blog.puhvjy.cn/Article/details/1784.sHtML
http://www.blog.puhvjy.cn/Article/details/934050.sHtML
http://www.blog.puhvjy.cn/Article/details/221142.sHtML
http://www.blog.puhvjy.cn/Article/details/7891.sHtML
http://www.blog.puhvjy.cn/Article/details/7786.sHtML
http://www.blog.puhvjy.cn/Article/details/088803.sHtML
http://www.blog.puhvjy.cn/Article/details/5797.sHtML
http://www.blog.puhvjy.cn/Article/details/8755.sHtML
http://www.blog.puhvjy.cn/Article/details/336039.sHtML
http://www.blog.puhvjy.cn/Article/details/986163.sHtML
http://www.blog.puhvjy.cn/Article/details/150823.sHtML
http://www.blog.puhvjy.cn/Article/details/94064.sHtML
http://www.blog.puhvjy.cn/Article/details/574001.sHtML
http://www.blog.puhvjy.cn/Article/details/4614.sHtML
http://www.blog.puhvjy.cn/Article/details/005123.sHtML
http://www.blog.puhvjy.cn/Article/details/359805.sHtML
http://www.blog.puhvjy.cn/Article/details/7121.sHtML
http://www.blog.puhvjy.cn/Article/details/274272.sHtML
http://www.blog.puhvjy.cn/Article/details/824572.sHtML
http://www.blog.puhvjy.cn/Article/details/933008.sHtML
http://www.blog.puhvjy.cn/Article/details/56510.sHtML
http://www.blog.puhvjy.cn/Article/details/2410988.sHtML
http://www.blog.puhvjy.cn/Article/details/079067.sHtML
http://www.blog.puhvjy.cn/Article/details/1162866.sHtML
http://www.blog.puhvjy.cn/Article/details/695689.sHtML
http://www.blog.puhvjy.cn/Article/details/91730.sHtML
http://www.blog.puhvjy.cn/Article/details/6225341.sHtML
http://www.blog.puhvjy.cn/Article/details/20646.sHtML
http://www.blog.puhvjy.cn/Article/details/4779922.sHtML
http://www.blog.puhvjy.cn/Article/details/784082.sHtML
http://www.blog.puhvjy.cn/Article/details/42649.sHtML
http://www.blog.puhvjy.cn/Article/details/0893090.sHtML
http://www.blog.puhvjy.cn/Article/details/0018.sHtML
http://www.blog.puhvjy.cn/Article/details/3858935.sHtML
http://www.blog.puhvjy.cn/Article/details/3067297.sHtML
http://www.blog.puhvjy.cn/Article/details/4266037.sHtML
http://www.blog.puhvjy.cn/Article/details/8668.sHtML
http://www.blog.puhvjy.cn/Article/details/59059.sHtML
http://www.blog.puhvjy.cn/Article/details/7730685.sHtML
http://www.blog.puhvjy.cn/Article/details/0578104.sHtML
http://www.blog.puhvjy.cn/Article/details/2276263.sHtML
http://www.blog.puhvjy.cn/Article/details/9106249.sHtML
http://www.blog.puhvjy.cn/Article/details/7453.sHtML
http://www.blog.puhvjy.cn/Article/details/466046.sHtML
http://www.blog.puhvjy.cn/Article/details/49390.sHtML
http://www.blog.puhvjy.cn/Article/details/88826.sHtML
http://www.blog.puhvjy.cn/Article/details/8933.sHtML
http://www.blog.puhvjy.cn/Article/details/8336956.sHtML
http://www.blog.puhvjy.cn/Article/details/150557.sHtML
http://www.blog.puhvjy.cn/Article/details/924363.sHtML
http://www.blog.puhvjy.cn/Article/details/9486600.sHtML
http://www.blog.puhvjy.cn/Article/details/6779294.sHtML
http://www.blog.puhvjy.cn/Article/details/128252.sHtML
http://www.blog.puhvjy.cn/Article/details/6676048.sHtML
http://www.blog.puhvjy.cn/Article/details/4830.sHtML
http://www.blog.puhvjy.cn/Article/details/843950.sHtML
http://www.blog.puhvjy.cn/Article/details/75739.sHtML
http://www.blog.puhvjy.cn/Article/details/420198.sHtML
http://www.blog.puhvjy.cn/Article/details/515346.sHtML
http://www.blog.puhvjy.cn/Article/details/8851225.sHtML
http://www.blog.puhvjy.cn/Article/details/486217.sHtML
http://www.blog.puhvjy.cn/Article/details/2478366.sHtML
http://www.blog.puhvjy.cn/Article/details/821656.sHtML
http://www.blog.puhvjy.cn/Article/details/8182.sHtML
http://www.blog.puhvjy.cn/Article/details/360750.sHtML
http://www.blog.puhvjy.cn/Article/details/4111.sHtML
http://www.blog.puhvjy.cn/Article/details/8975318.sHtML
http://www.blog.puhvjy.cn/Article/details/7399142.sHtML
http://www.blog.puhvjy.cn/Article/details/9025.sHtML
http://www.blog.puhvjy.cn/Article/details/0312.sHtML
http://www.blog.puhvjy.cn/Article/details/426190.sHtML
http://www.blog.puhvjy.cn/Article/details/12574.sHtML
http://www.blog.puhvjy.cn/Article/details/32496.sHtML
http://www.blog.puhvjy.cn/Article/details/0001151.sHtML
http://www.blog.puhvjy.cn/Article/details/653799.sHtML
http://www.blog.puhvjy.cn/Article/details/903836.sHtML
http://www.blog.puhvjy.cn/Article/details/10797.sHtML
http://www.blog.puhvjy.cn/Article/details/997851.sHtML
http://www.blog.puhvjy.cn/Article/details/7447.sHtML
http://www.blog.puhvjy.cn/Article/details/920724.sHtML
http://www.blog.puhvjy.cn/Article/details/16200.sHtML
http://www.blog.puhvjy.cn/Article/details/4441.sHtML
http://www.blog.puhvjy.cn/Article/details/24322.sHtML
http://www.blog.puhvjy.cn/Article/details/0300.sHtML
http://www.blog.puhvjy.cn/Article/details/23949.sHtML
http://www.blog.puhvjy.cn/Article/details/3519.sHtML
http://www.blog.puhvjy.cn/Article/details/35767.sHtML
http://www.blog.puhvjy.cn/Article/details/1000.sHtML
http://www.blog.puhvjy.cn/Article/details/817588.sHtML
http://www.blog.puhvjy.cn/Article/details/707203.sHtML
http://www.blog.puhvjy.cn/Article/details/5345684.sHtML
http://www.blog.puhvjy.cn/Article/details/88024.sHtML
http://www.blog.puhvjy.cn/Article/details/681641.sHtML
http://www.blog.puhvjy.cn/Article/details/21529.sHtML
http://www.blog.puhvjy.cn/Article/details/942885.sHtML
http://www.blog.puhvjy.cn/Article/details/8903.sHtML
http://www.blog.puhvjy.cn/Article/details/5696.sHtML
http://www.blog.puhvjy.cn/Article/details/62320.sHtML
http://www.blog.puhvjy.cn/Article/details/6733.sHtML
http://www.blog.puhvjy.cn/Article/details/048504.sHtML
http://www.blog.puhvjy.cn/Article/details/35597.sHtML
http://www.blog.puhvjy.cn/Article/details/67537.sHtML
http://www.blog.puhvjy.cn/Article/details/3423334.sHtML
http://www.blog.puhvjy.cn/Article/details/8761.sHtML
http://www.blog.puhvjy.cn/Article/details/05936.sHtML
http://www.blog.puhvjy.cn/Article/details/6035138.sHtML
http://www.blog.puhvjy.cn/Article/details/590283.sHtML
http://www.blog.puhvjy.cn/Article/details/3070070.sHtML
http://www.blog.puhvjy.cn/Article/details/30474.sHtML
http://www.blog.puhvjy.cn/Article/details/239619.sHtML
http://www.blog.puhvjy.cn/Article/details/1253088.sHtML
http://www.blog.puhvjy.cn/Article/details/777407.sHtML
http://www.blog.puhvjy.cn/Article/details/3572.sHtML
http://www.blog.puhvjy.cn/Article/details/3591.sHtML
http://www.blog.puhvjy.cn/Article/details/776809.sHtML
http://www.blog.puhvjy.cn/Article/details/38941.sHtML
http://www.blog.puhvjy.cn/Article/details/765604.sHtML
http://www.blog.puhvjy.cn/Article/details/82369.sHtML
http://www.blog.puhvjy.cn/Article/details/55028.sHtML
http://www.blog.puhvjy.cn/Article/details/02577.sHtML
http://www.blog.puhvjy.cn/Article/details/655755.sHtML
http://www.blog.puhvjy.cn/Article/details/00216.sHtML
http://www.blog.puhvjy.cn/Article/details/3480733.sHtML
http://www.blog.puhvjy.cn/Article/details/171221.sHtML
http://www.blog.puhvjy.cn/Article/details/3151483.sHtML
http://www.blog.puhvjy.cn/Article/details/5703.sHtML
http://www.blog.puhvjy.cn/Article/details/79403.sHtML
http://www.blog.puhvjy.cn/Article/details/01592.sHtML
http://www.blog.puhvjy.cn/Article/details/158267.sHtML
http://www.blog.puhvjy.cn/Article/details/155793.sHtML
http://www.blog.puhvjy.cn/Article/details/39616.sHtML
http://www.blog.puhvjy.cn/Article/details/8796504.sHtML
http://www.blog.puhvjy.cn/Article/details/94128.sHtML
http://www.blog.puhvjy.cn/Article/details/2620.sHtML
http://www.blog.puhvjy.cn/Article/details/35024.sHtML
http://www.blog.puhvjy.cn/Article/details/3388255.sHtML
http://www.blog.puhvjy.cn/Article/details/0136.sHtML
http://www.blog.puhvjy.cn/Article/details/991920.sHtML
http://www.blog.puhvjy.cn/Article/details/948270.sHtML
http://www.blog.puhvjy.cn/Article/details/4388356.sHtML
http://www.blog.puhvjy.cn/Article/details/1113049.sHtML
http://www.blog.puhvjy.cn/Article/details/50667.sHtML
http://www.blog.puhvjy.cn/Article/details/8246991.sHtML
http://www.blog.puhvjy.cn/Article/details/7802668.sHtML
http://www.blog.puhvjy.cn/Article/details/793939.sHtML
http://www.blog.puhvjy.cn/Article/details/866641.sHtML
http://www.blog.puhvjy.cn/Article/details/314376.sHtML
http://www.blog.puhvjy.cn/Article/details/12690.sHtML
http://www.blog.puhvjy.cn/Article/details/054110.sHtML
http://www.blog.puhvjy.cn/Article/details/4930.sHtML
http://www.blog.puhvjy.cn/Article/details/37092.sHtML
http://www.blog.puhvjy.cn/Article/details/62332.sHtML
http://www.blog.puhvjy.cn/Article/details/58827.sHtML
http://www.blog.puhvjy.cn/Article/details/2439807.sHtML
http://www.blog.puhvjy.cn/Article/details/572180.sHtML
http://www.blog.puhvjy.cn/Article/details/67659.sHtML
http://www.blog.puhvjy.cn/Article/details/85548.sHtML
http://www.blog.puhvjy.cn/Article/details/263895.sHtML
http://www.blog.puhvjy.cn/Article/details/9683987.sHtML
http://www.blog.puhvjy.cn/Article/details/222139.sHtML

## 项目结构

```
navigator/
├── src/                            # 源代码主目录
│   ├── core/                       # 核心索引与解析模块
│   │   ├── linkRegistry.js         # 链接注册表维护逻辑
│   │   └── categoryMatcher.js      # 基于关键词的分类匹配引擎
│   ├── ui/                         # 用户界面组件
│   │   ├── NavPanel.vue            # 导航主面板组件
│   │   ├── SearchBar.vue           # 检索过滤条组件
│   │   └── CategoryFilter.vue      # 分类筛选侧栏组件
│   ├── assets/                     # 静态资源文件
│   │   ├── defaultCategories.yaml  # 默认分类体系定义
│   │   └── logo.svg                # 项目标识图形
│   └── main.js                     # 应用入口文件
├── public/                         # 公开静态目录，不经过构建处理
│   └── favicon.ico                 # 站点图标
├── docs/                           # 项目文档目录
│   ├── user-guide.md               # 用户使用手册
│   ├── maintainer-guide.md         # 维护者操作指南
│   ├── contributing.md             # 贡献规范说明
│   └── architecture.md             # 系统架构设计文档
├── scripts/                        # 工具脚本目录
│   ├── validateLinks.js            # 链接可用性校验脚本
│   └── generateSitemap.js          # 站点地图生成脚本
├── tests/                          # 单元测试与集成测试目录
│   ├── registry.test.js            # 链接注册表单元测试
│   └── category.test.js            # 分类匹配逻辑测试
├── .gitignore                      # Git 忽略规则文件
├── package.json                    # 项目依赖与脚本定义
├── vite.config.js                  # 构建工具 Vite 配置文件
└── README.md                       # 项目说明文档（本文件）
```

## 贡献指南

1. 复刻本仓库至个人账户，在本地新建功能分支，分支命名遵循 `feat/描述` 或 `fix/描述` 格式。

2. 如需新增链接，请编辑 `src/assets/defaultCategories.yaml` 文件，按照既有分类结构添加条目，必须包含原始 URL、文章标题梗概与建议分类标签。链接 URL 必须保持原样，不得添加协议或前缀。

3. 提交前运行 `npm run test` 确保所有单元测试通过，并执行 `npm run validate` 校验新增链接的格式与可访问性。

4. 向主仓库发起 Pull Request，描述中需明确说明本次新增或修改的链接数量与分类调整依据。PR 至少需要一名项目维护者审核通过方可合并。

5. 若发现已有链接失效或分类不当，请通过 Issue 系统提交问题报告，包含失效链接的原始 URL 与建议处理方式。

## 常见问题

**问：收录链接是否会定期校验可用性？**

答：项目维护者会每季度执行一次全量链接可用性扫描，使用 `scripts/validateLinks.js` 脚本检查 HTTP 状态码。对于返回 4xx 或 5xx 的链接，将在导航面板中标记为待确认，并在连续两次校验失败后予以移除。用户也可主动触发本地校验。

**问：是否可以提交来源于其他域名的链接？**

答：可以。本项目定位为通用技术资源导航，不限制来源域名。但提交者需确保链接内容为技术相关文章、文档或工具页面，且不涉及侵权或违规内容。新增链接需在 `defaultCategories.yaml` 中明确标注来源域名与分类。

**问：导航面板的检索功能是否支持模糊匹配？**

答：支持。当前检索逻辑基于标题关键词与分类标签进行子串匹配，不区分大小写。未来版本计划引入基于简单 TF-IDF 的排序增强，但不会引入外部搜索引擎或云服务，确保本地部署的独立性。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 16:29:48
