# TechArchive Navigator

TechArchive Navigator 是一个面向开发者与技术研究者的结构化技术文章索引与导航系统。本项目的核心定位是对分散于技术博客、个人站点与社区平台中的高质量技术内容进行系统性归集、分类与快速检索，帮助技术从业者在海量信息中高效定位所需知识。

本项目并非一个传统的爬虫或全文搜索引擎，而是一个精心编排的外部技术资源引用目录。每一条收录的链接均经过人工筛选与主题标定，覆盖后端工程、前端架构、数据库原理、运维监控、算法设计、编程语言特性等多个技术领域。项目本身不存储或转发任何第三方内容，仅提供原始出处的标准化引用，确保内容版权归属清晰，同时为开发者提供可靠的知识发现路径。

项目目标用户包括：需要系统化扩充技术视野的初中级开发者、希望快速查阅特定技术细节的资深工程师、以及需要为团队收集技术参考资料的技术负责人。通过本项目的目录结构，用户可以在不依赖搜索引擎模糊检索的情况下，直接访问经过预筛选的深度技术文章。

## 功能概览

**结构化分类索引** 按照技术领域与内容类型对全部收录链接进行多级分类，每个条目附带内容摘要标签，便于用户快速判断文章主题。

**批量资源导入** 支持通过脚本批量录入新的技术文章链接，自动进行域名归一化与重复性检测，确保索引库的整洁性。

**本地离线查阅** 所有索引数据存储为纯文本格式，用户可在本地通过任意编辑器或命令行工具进行检索与浏览，无需依赖数据库或外部服务。

**快速跳转直达** 每个条目均保留原始URL，用户点击即可直接访问来源站点，无中间跳转页或广告拦截，确保访问路径最短。

**标签过滤系统** 为每篇文章标注多个技术标签，如Java、Spring、MySQL、Redis、Linux、Kubernetes等，支持按标签组合筛选文章列表。

**更新状态追踪** 记录每条链接的添加时间与最后检查时间，支持定期对链接进行可用性探测，标记可能失效的条目。

**自定义分类扩展** 用户可根据自身技术栈或学习计划，在现有分类基础上新增自定义分组，将索引库与个人知识管理体系结合。

**导出与集成** 支持将索引列表导出为JSON、CSV或纯文本格式，便于集成到其他知识管理工具或内部文档系统中。

## 应用场景

技术团队内部知识库建设。技术团队在项目开发过程中会积累大量外部参考资料，但分散于个人浏览器书签或即时通讯群组中，难以共享与传承。TechArchive Navigator可作为团队知识库的入口层，由专人维护索引目录，新成员通过浏览索引即可快速了解团队关注的技术方向与常用参考文档。

个人技术学习路径规划。开发者在对某一技术领域进行系统性学习时，往往需要阅读大量相关文章。本项目按主题分类的文章列表可以帮助学习者快速找到该领域的核心文章，避免在信息检索上耗费过多时间，提高学习效率。

技术方案选型调研。在进行技术选型或架构设计时，工程师需要对比多种方案并查阅相关实践案例。通过本项目的分类索引，用户可以在同一主题下集中阅读多篇来自不同作者的文章，获取多维度的观点与经验，辅助决策。

离线文档资源整理。在无法直接访问互联网的内网开发环境中，团队可将本项目索引中的文章提前下载或镜像，并利用本项目的目录结构作为导航页，实现内网环境下的文档资源有序管理。

## 快速开始

以下步骤帮助您在本地环境中快速部署并开始使用 TechArchive Navigator。

```bash
# 克隆项目仓库至本地
git clone https://github.com/techarchive/navigator.git

# 进入项目根目录
cd navigator

# 安装依赖（基于 Python 3.10+，使用 pip 安装所需工具包）
pip install -r requirements.txt

# 运行本地索引服务（默认监听 127.0.0.1:8080）
python serve.py --port 8080
```

执行上述命令后，在浏览器中访问 `http://127.0.0.1:8080` 即可查看索引主页。若只需使用命令行工具进行检索，可直接运行 `python cli.py --search <关键词>`。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.10 及以上 | 核心运行环境，用于索引构建与本地服务 |
| pip | 22.0 及以上 | Python 包管理工具，用于安装项目依赖 |
| Markdown | 3.4.0 及以上 | 用于渲染索引页面的文档内容 |
| PyYAML | 6.0 及以上 | 用于解析分类配置文件与元数据 |
| click | 8.1.0 及以上 | 命令行交互接口框架 |
| requests | 2.31.0 及以上 | 用于链接可用性检查与状态探测 |
| pytest | 7.4.0 及以上 | 单元测试框架，仅开发环境需要 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | docs/user-guide.md | 如何使用索引浏览、检索与自定义分类？ |
| 维护指南 | docs/maintainer-guide.md | 如何新增文章链接、更新分类与检查链接有效性？ |
| 配置参考 | docs/configuration.md | 分类配置文件的结构与各字段含义是什么？ |
| API 接口 | docs/api-reference.md | 如何通过 HTTP API 或命令行工具程序化访问索引数据？ |
| 开发指引 | docs/development.md | 项目的代码结构、测试方法与贡献流程是什么？ |
| 常见问题 | docs/faq.md | 收录标准是什么？链接失效如何处理？如何申请收录？ |

## 资源列表

本列表按技术领域与内容性质进行分组归类。全部链接均来自 `blog.puhvjy.cn` 站点，原始URL严格保持原样输出，未做任何格式修改。

### 后端开发与编程语言

http://www.blog.puhvjy.cn/Article/details/86977.sHtML
http://www.blog.puhvjy.cn/Article/details/9302.sHtML
http://www.blog.puhvjy.cn/Article/details/36965.sHtML
http://www.blog.puhvjy.cn/Article/details/12483.sHtML
http://www.blog.puhvjy.cn/Article/details/3090.sHtML
http://www.blog.puhvjy.cn/Article/details/3250.sHtML
http://www.blog.puhvjy.cn/Article/details/6001206.sHtML
http://www.blog.puhvjy.cn/Article/details/9524.sHtML
http://www.blog.puhvjy.cn/Article/details/0220.sHtML
http://www.blog.puhvjy.cn/Article/details/3777.sHtML
http://www.blog.puhvjy.cn/Article/details/2695.sHtML
http://www.blog.puhvjy.cn/Article/details/0672.sHtML
http://www.blog.puhvjy.cn/Article/details/26195.sHtML
http://www.blog.puhvjy.cn/Article/details/614710.sHtML
http://www.blog.puhvjy.cn/Article/details/28360.sHtML
http://www.blog.puhvjy.cn/Article/details/6530423.sHtML
http://www.blog.puhvjy.cn/Article/details/428535.sHtML
http://www.blog.puhvjy.cn/Article/details/802125.sHtML
http://www.blog.puhvjy.cn/Article/details/6929500.sHtML
http://www.blog.puhvjy.cn/Article/details/0486181.sHtML

### 数据库与存储技术

http://www.blog.puhvjy.cn/Article/details/2035.sHtML
http://www.blog.puhvjy.cn/Article/details/92956.sHtML
http://www.blog.puhvjy.cn/Article/details/3497.sHtML
http://www.blog.puhvjy.cn/Article/details/706340.sHtML
http://www.blog.puhvjy.cn/Article/details/97542.sHtML
http://www.blog.puhvjy.cn/Article/details/8511277.sHtML
http://www.blog.puhvjy.cn/Article/details/328678.sHtML
http://www.blog.puhvjy.cn/Article/details/7591985.sHtML
http://www.blog.puhvjy.cn/Article/details/52685.sHtML
http://www.blog.puhvjy.cn/Article/details/8144576.sHtML
http://www.blog.puhvjy.cn/Article/details/936172.sHtML
http://www.blog.puhvjy.cn/Article/details/6392.sHtML
http://www.blog.puhvjy.cn/Article/details/2411.sHtML
http://www.blog.puhvjy.cn/Article/details/732423.sHtML
http://www.blog.puhvjy.cn/Article/details/475170.sHtML
http://www.blog.puhvjy.cn/Article/details/09482.sHtML
http://www.blog.puhvjy.cn/Article/details/00151.sHtML
http://www.blog.puhvjy.cn/Article/details/3971360.sHtML
http://www.blog.puhvjy.cn/Article/details/3477.sHtML
http://www.blog.puhvjy.cn/Article/details/452556.sHtML

### 系统运维与基础设施

http://www.blog.puhvjy.cn/Article/details/5807.sHtML
http://www.blog.puhvjy.cn/Article/details/62796.sHtML
http://www.blog.puhvjy.cn/Article/details/8637.sHtML
http://www.blog.puhvjy.cn/Article/details/4227795.sHtML
http://www.blog.puhvjy.cn/Article/details/00218.sHtML
http://www.blog.puhvjy.cn/Article/details/6506.sHtML
http://www.blog.puhvjy.cn/Article/details/47917.sHtML
http://www.blog.puhvjy.cn/Article/details/590341.sHtML
http://www.blog.puhvjy.cn/Article/details/9475672.sHtML
http://www.blog.puhvjy.cn/Article/details/5361.sHtML
http://www.blog.puhvjy.cn/Article/details/0609.sHtML
http://www.blog.puhvjy.cn/Article/details/6157891.sHtML
http://www.blog.puhvjy.cn/Article/details/388086.sHtML
http://www.blog.puhvjy.cn/Article/details/0270.sHtML
http://www.blog.puhvjy.cn/Article/details/00063.sHtML
http://www.blog.puhvjy.cn/Article/details/6935.sHtML
http://www.blog.puhvjy.cn/Article/details/3041709.sHtML
http://www.blog.puhvjy.cn/Article/details/5260523.sHtML
http://www.blog.puhvjy.cn/Article/details/7168.sHtML
http://www.blog.puhvjy.cn/Article/details/347027.sHtML

### 前端工程与UI

http://www.blog.puhvjy.cn/Article/details/472118.sHtML
http://www.blog.puhvjy.cn/Article/details/3970.sHtML
http://www.blog.puhvjy.cn/Article/details/38527.sHtML
http://www.blog.puhvjy.cn/Article/details/547902.sHtML
http://www.blog.puhvjy.cn/Article/details/374307.sHtML
http://www.blog.puhvjy.cn/Article/details/0958.sHtML
http://www.blog.puhvjy.cn/Article/details/13031.sHtML
http://www.blog.puhvjy.cn/Article/details/9441862.sHtML
http://www.blog.puhvjy.cn/Article/details/6637189.sHtML
http://www.blog.puhvjy.cn/Article/details/8166.sHtML
http://www.blog.puhvjy.cn/Article/details/3092.sHtML
http://www.blog.puhvjy.cn/Article/details/9158.sHtML
http://www.blog.puhvjy.cn/Article/details/2498.sHtML
http://www.blog.puhvjy.cn/Article/details/7087.sHtML
http://www.blog.puhvjy.cn/Article/details/165400.sHtML
http://www.blog.puhvjy.cn/Article/details/2637961.sHtML
http://www.blog.puhvjy.cn/Article/details/8360.sHtML
http://www.blog.puhvjy.cn/Article/details/3626.sHtML
http://www.blog.puhvjy.cn/Article/details/3213.sHtML
http://www.blog.puhvjy.cn/Article/details/2536.sHtML

### 算法与数据结构

http://www.blog.puhvjy.cn/Article/details/80923.sHtML
http://www.blog.puhvjy.cn/Article/details/27752.sHtML
http://www.blog.puhvjy.cn/Article/details/3875.sHtML
http://www.blog.puhvjy.cn/Article/details/284134.sHtML
http://www.blog.puhvjy.cn/Article/details/87499.sHtML
http://www.blog.puhvjy.cn/Article/details/434071.sHtML
http://www.blog.puhvjy.cn/Article/details/67104.sHtML
http://www.blog.puhvjy.cn/Article/details/5448.sHtML
http://www.blog.puhvjy.cn/Article/details/16033.sHtML
http://www.blog.puhvjy.cn/Article/details/216338.sHtML
http://www.blog.puhvjy.cn/Article/details/30246.sHtML
http://www.blog.puhvjy.cn/Article/details/20158.sHtML
http://www.blog.puhvjy.cn/Article/details/3467272.sHtML
http://www.blog.puhvjy.cn/Article/details/0818535.sHtML
http://www.blog.puhvjy.cn/Article/details/9787177.sHtML
http://www.blog.puhvjy.cn/Article/details/40004.sHtML
http://www.blog.puhvjy.cn/Article/details/05723.sHtML
http://www.blog.puhvjy.cn/Article/details/4496.sHtML
http://www.blog.puhvjy.cn/Article/details/7173686.sHtML
http://www.blog.puhvjy.cn/Article/details/602274.sHtML

### 分布式与微服务

http://www.blog.puhvjy.cn/Article/details/7949.sHtML
http://www.blog.puhvjy.cn/Article/details/5277581.sHtML
http://www.blog.puhvjy.cn/Article/details/0144.sHtML
http://www.blog.puhvjy.cn/Article/details/225231.sHtML
http://www.blog.puhvjy.cn/Article/details/9327.sHtML
http://www.blog.puhvjy.cn/Article/details/8018302.sHtML
http://www.blog.puhvjy.cn/Article/details/132615.sHtML
http://www.blog.puhvjy.cn/Article/details/906914.sHtML
http://www.blog.puhvjy.cn/Article/details/028403.sHtML
http://www.blog.puhvjy.cn/Article/details/3437.sHtML
http://www.blog.puhvjy.cn/Article/details/666330.sHtML
http://www.blog.puhvjy.cn/Article/details/7889793.sHtML
http://www.blog.puhvjy.cn/Article/details/68914.sHtML
http://www.blog.puhvjy.cn/Article/details/4319.sHtML
http://www.blog.puhvjy.cn/Article/details/82420.sHtML
http://www.blog.puhvjy.cn/Article/details/0732901.sHtML
http://www.blog.puhvjy.cn/Article/details/64395.sHtML
http://www.blog.puhvjy.cn/Article/details/124980.sHtML
http://www.blog.puhvjy.cn/Article/details/5578.sHtML
http://www.blog.puhvjy.cn/Article/details/873276.sHtML

### 网络协议与安全

http://www.blog.puhvjy.cn/Article/details/1286685.sHtML
http://www.blog.puhvjy.cn/Article/details/91798.sHtML
http://www.blog.puhvjy.cn/Article/details/36186.sHtML
http://www.blog.puhvjy.cn/Article/details/703695.sHtML
http://www.blog.puhvjy.cn/Article/details/6849750.sHtML
http://www.blog.puhvjy.cn/Article/details/0021126.sHtML
http://www.blog.puhvjy.cn/Article/details/3811275.sHtML
http://www.blog.puhvjy.cn/Article/details/1348.sHtML
http://www.blog.puhvjy.cn/Article/details/1541.sHtML
http://www.blog.puhvjy.cn/Article/details/9610717.sHtML
http://www.blog.puhvjy.cn/Article/details/56851.sHtML
http://www.blog.puhvjy.cn/Article/details/34447.sHtML
http://www.blog.puhvjy.cn/Article/details/39044.sHtML
http://www.blog.puhvjy.cn/Article/details/19777.sHtML
http://www.blog.puhvjy.cn/Article/details/638382.sHtML
http://www.blog.puhvjy.cn/Article/details/4382.sHtML
http://www.blog.puhvjy.cn/Article/details/846845.sHtML
http://www.blog.puhvjy.cn/Article/details/8922.sHtML
http://www.blog.puhvjy.cn/Article/details/3926.sHtML
http://www.blog.puhvjy.cn/Article/details/9028.sHtML

### 综合与通用技术

http://www.blog.puhvjy.cn/Article/details/8904.sHtML
http://www.blog.puhvjy.cn/Article/details/55511.sHtML
http://www.blog.puhvjy.cn/Article/details/1864.sHtML
http://www.blog.puhvjy.cn/Article/details/23916.sHtML
http://www.blog.puhvjy.cn/Article/details/45666.sHtML
http://www.blog.puhvjy.cn/Article/details/84052.sHtML
http://www.blog.puhvjy.cn/Article/details/23217.sHtML
http://www.blog.puhvjy.cn/Article/details/214887.sHtML
http://www.blog.puhvjy.cn/Article/details/2455.sHtML
http://www.blog.puhvjy.cn/Article/details/2209.sHtML
http://www.blog.puhvjy.cn/Article/details/8609.sHtML
http://www.blog.puhvjy.cn/Article/details/16450.sHtML
http://www.blog.puhvjy.cn/Article/details/153399.sHtML
http://www.blog.puhvjy.cn/Article/details/14824.sHtML
http://www.blog.puhvjy.cn/Article/details/2480.sHtML
http://www.blog.puhvjy.cn/Article/details/749533.sHtML
http://www.blog.puhvjy.cn/Article/details/6461.sHtML
http://www.blog.puhvjy.cn/Article/details/4267.sHtML
http://www.blog.puhvjy.cn/Article/details/7266243.sHtML
http://www.blog.puhvjy.cn/Article/details/5621361.sHtML

### 云计算与容器化

http://www.blog.puhvjy.cn/Article/details/390251.sHtML
http://www.blog.puhvjy.cn/Article/details/71872.sHtML
http://www.blog.puhvjy.cn/Article/details/3439762.sHtML
http://www.blog.puhvjy.cn/Article/details/385067.sHtML
http://www.blog.puhvjy.cn/Article/details/6543227.sHtML
http://www.blog.puhvjy.cn/Article/details/22080.sHtML
http://www.blog.puhvjy.cn/Article/details/20139.sHtML
http://www.blog.puhvjy.cn/Article/details/094163.sHtML
http://www.blog.puhvjy.cn/Article/details/93001.sHtML
http://www.blog.puhvjy.cn/Article/details/9275775.sHtML
http://www.blog.puhvjy.cn/Article/details/98240.sHtML
http://www.blog.puhvjy.cn/Article/details/0942954.sHtML
http://www.blog.puhvjy.cn/Article/details/23419.sHtML
http://www.blog.puhvjy.cn/Article/details/1814.sHtML
http://www.blog.puhvjy.cn/Article/details/953960.sHtML
http://www.blog.puhvjy.cn/Article/details/3346490.sHtML
http://www.blog.puhvjy.cn/Article/details/9044081.sHtML
http://www.blog.puhvjy.cn/Article/details/31494.sHtML
http://www.blog.puhvjy.cn/Article/details/4612114.sHtML
http://www.blog.puhvjy.cn/Article/details/22161.sHtML

### 开发工具与调试

http://www.blog.puhvjy.cn/Article/details/86849.sHtML
http://www.blog.puhvjy.cn/Article/details/85853.sHtML
http://www.blog.puhvjy.cn/Article/details/825290.sHtML
http://www.blog.puhvjy.cn/Article/details/52594.sHtML
http://www.blog.puhvjy.cn/Article/details/8214.sHtML
http://www.blog.puhvjy.cn/Article/details/0213218.sHtML
http://www.blog.puhvjy.cn/Article/details/82988.sHtML
http://www.blog.puhvjy.cn/Article/details/732884.sHtML
http://www.blog.puhvjy.cn/Article/details/9127933.sHtML
http://www.blog.puhvjy.cn/Article/details/2569352.sHtML
http://www.blog.puhvjy.cn/Article/details/29142.sHtML
http://www.blog.puhvjy.cn/Article/details/6177951.sHtML
http://www.blog.puhvjy.cn/Article/details/8822357.sHtML
http://www.blog.puhvjy.cn/Article/details/027041.sHtML
http://www.blog.puhvjy.cn/Article/details/3608.sHtML
http://www.blog.puhvjy.cn/Article/details/1044.sHtML
http://www.blog.puhvjy.cn/Article/details/41814.sHtML
http://www.blog.puhvjy.cn/Article/details/0977619.sHtML
http://www.blog.puhvjy.cn/Article/details/24132.sHtML
http://www.blog.puhvjy.cn/Article/details/66480.sHtML

### 架构设计与方法论

http://www.blog.puhvjy.cn/Article/details/31304.sHtML
http://www.blog.puhvjy.cn/Article/details/5763.sHtML
http://www.blog.puhvjy.cn/Article/details/9275798.sHtML
http://www.blog.puhvjy.cn/Article/details/2836.sHtML
http://www.blog.puhvjy.cn/Article/details/28030.sHtML
http://www.blog.puhvjy.cn/Article/details/7122130.sHtML
http://www.blog.puhvjy.cn/Article/details/92767.sHtML
http://www.blog.puhvjy.cn/Article/details/6089.sHtML
http://www.blog.puhvjy.cn/Article/details/7003.sHtML
http://www.blog.puhvjy.cn/Article/details/19722.sHtML
http://www.blog.puhvjy.cn/Article/details/89487.sHtML
http://www.blog.puhvjy.cn/Article/details/09137.sHtML
http://www.blog.puhvjy.cn/Article/details/79533.sHtML
http://www.blog.puhvjy.cn/Article/details/4669.sHtML
http://www.blog.puhvjy.cn/Article/details/7642.sHtML
http://www.blog.puhvjy.cn/Article/details/9206561.sHtML
http://www.blog.puhvjy.cn/Article/details/754886.sHtML
http://www.blog.puhvjy.cn/Article/details/010133.sHtML
http://www.blog.puhvjy.cn/Article/details/0194682.sHtML
http://www.blog.puhvjy.cn/Article/details/291214.sHtML

### 数据工程与AI

http://www.blog.puhvjy.cn/Article/details/4522.sHtML
http://www.blog.puhvjy.cn/Article/details/7701.sHtML
http://www.blog.puhvjy.cn/Article/details/5400436.sHtML
http://www.blog.puhvjy.cn/Article/details/536489.sHtML
http://www.blog.puhvjy.cn/Article/details/804235.sHtML
http://www.blog.puhvjy.cn/Article/details/70291.sHtML
http://www.blog.puhvjy.cn/Article/details/6107.sHtML
http://www.blog.puhvjy.cn/Article/details/9749000.sHtML
http://www.blog.puhvjy.cn/Article/details/3634314.sHtML
http://www.blog.puhvjy.cn/Article/details/21984.sHtML
http://www.blog.puhvjy.cn/Article/details/9561205.sHtML
http://www.blog.puhvjy.cn/Article/details/2822.sHtML
http://www.blog.puhvjy.cn/Article/details/97026.sHtML
http://www.blog.puhvjy.cn/Article/details/755336.sHtML
http://www.blog.puhvjy.cn/Article/details/5720.sHtML
http://www.blog.puhvjy.cn/Article/details/44142.sHtML
http://www.blog.puhvjy.cn/Article/details/383142.sHtML
http://www.blog.puhvjy.cn/Article/details/5157.sHtML
http://www.blog.puhvjy.cn/Article/details/504001.sHtML
http://www.blog.puhvjy.cn/Article/details/19869.sHtML
http://www.blog.puhvjy.cn/Article/details/0031.sHtML
http://www.blog.puhvjy.cn/Article/details/67074.sHtML
http://www.blog.puhvjy.cn/Article/details/303976.sHtML
http://www.blog.puhvjy.cn/Article/details/2838721.sHtML
http://www.blog.puhvjy.cn/Article/details/662663.sHtML
http://www.blog.puhvjy.cn/Article/details/052748.sHtML
http://www.blog.puhvjy.cn/Article/details/5042.sHtML
http://www.blog.puhvjy.cn/Article/details/8942113.sHtML
http://www.blog.puhvjy.cn/Article/details/4282903.sHtML
http://www.blog.puhvjy.cn/Article/details/705679.sHtML

## 项目结构

```
navigator/
├── README.md                         # 项目总览与快速入门文档
├── LICENSE                           # MIT 许可证文件
├── requirements.txt                  # Python 依赖声明文件
├── serve.py                          # 本地 HTTP 服务启动入口
├── cli.py                            # 命令行交互工具入口
├── config/
│   ├── categories.yaml               # 分类定义与标签映射配置
│   └── settings.yaml                 # 服务端口、缓存路径等运行配置
├── data/
│   ├── index.db                      # SQLite 索引数据库文件
│   ├── links.json                    # 完整链接列表的 JSON 导出
│   └── tags.csv                      # 标签-文章关联表 CSV 导出
├── docs/                             # 完整文档目录
│   ├── user-guide.md                 # 用户使用手册
│   ├── maintainer-guide.md           # 维护者操作指南
│   ├── configuration.md              # 配置项详细说明
│   ├── api-reference.md              # HTTP API 与 CLI 命令参考
│   ├── development.md                # 开发环境搭建与贡献流程
│   └── faq.md                        # 常见问题解答
├── src/                              # 核心源代码目录
│   ├── __init__.py
│   ├── indexer.py                    # 链接索引构建与更新模块
│   ├── parser.py                     # URL 解析与标准化工具
│   ├── checker.py                    # 链接可用性检查模块
│   ├── exporter.py                   # 数据导出（JSON/CSV）模块
│   └── server.py                     # 内置 HTTP 服务实现
├── tests/                            # 单元测试与集成测试目录
│   ├── test_indexer.py               # 索引构建功能测试
│   ├── test_parser.py                # URL 解析测试
│   ├── test_checker.py               # 链接检查测试
│   └── test_server.py                # 服务接口测试
├── scripts/                          # 辅助运维脚本
│   ├── import_batch.py               # 批量导入链接脚本
│   ├── check_all_links.py            # 全量链接可用性检查脚本
│   └── generate_static.py            # 生成静态 HTML 导航页脚本
└── static/                           # 前端静态资源（可选）
    ├── index.html                    # 默认导航主页模板
    └── style.css                     # 基础样式表
```

## 贡献指南

我们欢迎并鼓励社区贡献。以下为参与本项目维护与扩展的具体步骤：

第一，Fork 本仓库并克隆至本地开发环境。请确保您的本地 Python 版本符合安装要求，并已正确安装所有依赖。在提交任何更改前，建议先运行现有测试套件以确保环境就绪。

第二，新增或修改链接索引时，请遵循 data/links.json 中既有的 JSON 结构规范。每一条新增记录必须包含 url、title、category、tags 和 added_date 字段。title 字段应简明扼要地概括文章主题，tags 列表应选择与内容最相关的 2 至 4 个技术标签。提交前请使用 scripts/check_all_links.py 验证新增链接的可访问性。

第三，若您希望调整分类体系或新增分类，请修改 config/categories.yaml 文件，并同步更新 data/links.json 中对应条目的 category 字段。分类名称应使用英文小写加连字符的命名风格，如 backend-java、database-mysql。同时请更新 docs/configuration.md 中关于分类定义的说明文档。

第四，所有代码提交必须通过 pytest 单元测试，且测试覆盖率不应低于 80%。提交前请运行 black 与 flake8 进行代码格式化与风格检查。提交信息应遵循 Conventional Commits 规范，使用 feat、fix、docs、style、refactor 等类型前缀。

第五，提交 Pull Request 时请详细描述本次变更的目的、实现方式与测试结果。若变更涉及链接列表或分类体系的调整，请在 PR 描述中附上变更前后的对比统计信息，以便维护者审阅。

## 常见问题

Q：本项目的链接收录标准是什么？是否接受自动爬取提交？

A：本项目当前采用人工审核与半自动导入相结合的收录方式。收录标准为：文章内容必须具有明确的技术深度，不包含纯商业推广或低质量搬运内容。链接来源域名的权威性与稳定性也在考量范围内。目前暂不接受完全自动化的爬取提交，但欢迎通过 GitHub Issue 提交推荐链接，维护团队会定期审核并入。

Q：如果收录的链接失效或内容发生重大变更，项目如何处理？

A：项目维护团队会定期运行 scripts/check_all_links.py 对全部链接进行 HTTP 状态检查。对于返回 4xx 或 5xx 状态码的链接，系统会在索引数据库中标记为疑似失效。标记后维护人员会人工访问确认，若确认失效则会从活跃索引中移除，并记录至失效列表备查。若您在使用过程中发现失效链接，也欢迎提交 Issue 报告。

Q：我能否将本项目的索引数据用于自己的知识库或文档站点？

A：可以。本项目采用 MIT 许可证，索引数据（即链接列表与分类标签）属于可自由使用的结构化数据。您可以将本项目的 data/links.json 文件导出并集成到任意个人或商业项目中，无需额外授权。但请注意，本项目的开源许可不覆盖链接指向的第三方文章内容，第三方内容的版权归属其原始作者或站点所有。

## 许可证

MIT License

Copyright (c) 2026 TechArchive Navigator Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

> 外链数量: 250 | 生成时间: 2026-07-05 16:29:45
