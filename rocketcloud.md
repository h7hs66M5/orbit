# LinkVault 技术资源聚合平台

LinkVault 是一个面向开发者、技术研究人员与内容创作者的轻量级技术文章与资源外链聚合系统。该项目定位于对分散于各类技术博客、教程站点与文档库中的优质外链进行结构化整理、分类归档与全文元数据索引，帮助用户以可复用的方式管理和检索技术阅读列表。

项目不提供全文爬取与存储服务，而是作为外链元数据登记与导航中枢，适用于个人知识管理、团队技术文档索引、开源项目外部参考资料归档等场景。通过统一的条目模板与标签体系，用户可快速录入新链接、按主题筛选已有资源，并生成静态导航页面供内部或公开使用。


## 功能概览

**多源外链统一登记**：支持手工录入与批量导入，每条记录自动提取域名、路径、扩展名与查询参数，生成标准化条目。

**分层标签与分类体系**：内置技术栈、难度等级、内容类型（教程、案例、参考手册、视频）等多维度标签，支持自定义扩展。

**全文元数据检索**：基于标题、描述、标签与路径关键词的轻量级倒排索引，支持布尔运算符与通配符查询。

**链接可用性检查**：定期对已登记外链发起 HEAD 请求，标记失效链接并生成报告，辅助维护清理。

**静态导航站点生成**：根据标签与分类筛选条件，输出纯 HTML/CSS 的响应式导航页面，可直接部署至 Web 服务器或 CDN。

**导入导出互操作**：支持 JSON、CSV 与 OPML 格式的批量导入导出，便于与其他书签工具或 RSS 阅读器协同工作。


## 应用场景

**个人技术阅读工作流管理**：开发者可将日常浏览发现的优质技术文章、官方文档与视频教程快速录入 LinkVault，按学习路线打标，替代浏览器书签的混乱文件夹结构，实现基于标签的动态筛选与检索。

**团队共享技术文档索引**：技术团队可将项目依赖的第三方库文档、内部设计文档链接、运维手册地址等统一登记至 LinkVault，生成团队内部导航页，新成员入职时可快速访问全部核心参考资料。

**开源项目外部参考归档**：开源维护者可将项目依赖的论文、标准规范、相关项目地址等外链集中管理，作为项目 README 或 Wiki 的补充资料库，便于贡献者追溯设计依据。

**技术内容策展与 Newsletter 素材库**：技术博主或内容策展人可使用 LinkVault 分类存储候选选题素材，按主题或时间范围快速导出链接列表，用于周报、月刊或专题推荐。


## 快速开始

以下命令适用于 Linux 与 macOS 环境，Windows 用户建议使用 WSL2 或 Git Bash。

```bash
# 克隆项目仓库
git clone https://github.com/your-org/linkvault.git

# 进入项目目录
cd linkvault

# 安装依赖（基于 Python 3.10+）
pip install -r requirements.txt

# 初始化本地数据库与配置文件
python linkvault.py init

# 运行内置 Web 服务（开发模式，默认端口 8080）
python linkvault.py serve --port 8080
```

启动后访问 `http://127.0.0.1:8080` 即可进入本地导航界面。生产环境部署建议使用 Gunicorn 或 uWSGI 配合 Nginx 反向代理。


## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---------|---------|------|
| Python | 3.10 及以上 | 核心运行时，用于后端 API 与 CLI 工具 |
| SQLite | 3.35 及以上 | 本地元数据存储引擎，支持 JSON 函数与全文检索 |
| pip | 21.0 及以上 | Python 包依赖管理工具 |
| Git | 2.25 及以上 | 用于克隆仓库与版本管理，非运行必需 |
| requests | 2.28.0 | HTTP 客户端库，用于链接可用性检查 |
| markdown | 3.4.0 | 用于将条目描述渲染为 HTML 摘要 |
| jinja2 | 3.1.0 | 模板引擎，用于静态导航页面生成 |
| pytest | 7.0.0（可选） | 单元测试框架，仅开发与贡献时使用 |


## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|-----------|
| 用户手册 | docs/user-guide.md | 如何录入链接、打标签、筛选检索、生成导航页 |
| 配置参考 | docs/configuration.md | 环境变量、配置文件字段说明、自定义标签方案 |
| 开发指南 | docs/development.md | 项目架构、插件扩展机制、API 接口设计 |
| 部署运维 | docs/deployment.md | 生产环境部署方案、性能调优、备份与恢复策略 |


## 资源列表

以下为项目第 249/280 批次收录的外部技术资源链接，按类别分组展示。所有 URL 均保持用户提供的原始格式一字不差输出。

技术文章与教程类

http://www.blog.puhvjy.cn/Article/details/28295.sHtML
http://www.blog.puhvjy.cn/Article/details/2016059.sHtML
http://www.blog.puhvjy.cn/Article/details/141705.sHtML
http://www.blog.puhvjy.cn/Article/details/2687135.sHtML
http://www.blog.puhvjy.cn/Article/details/3082.sHtML
http://www.blog.puhvjy.cn/Article/details/195181.sHtML
http://www.blog.puhvjy.cn/Article/details/1083604.sHtML
http://www.blog.puhvjy.cn/Article/details/822361.sHtML
http://www.blog.puhvjy.cn/Article/details/488833.sHtML
http://www.blog.puhvjy.cn/Article/details/0712.sHtML
http://www.blog.puhvjy.cn/Article/details/5162897.sHtML
http://www.blog.puhvjy.cn/Article/details/6524.sHtML
http://www.blog.puhvjy.cn/Article/details/966043.sHtML
http://www.blog.puhvjy.cn/Article/details/399887.sHtML
http://www.blog.puhvjy.cn/Article/details/847695.sHtML
http://www.blog.puhvjy.cn/Article/details/8081674.sHtML
http://www.blog.puhvjy.cn/Article/details/0862482.sHtML
http://www.blog.puhvjy.cn/Article/details/44631.sHtML
http://www.blog.puhvjy.cn/Article/details/1283.sHtML
http://www.blog.puhvjy.cn/Article/details/516887.sHtML
http://www.blog.puhvjy.cn/Article/details/4866063.sHtML
http://www.blog.puhvjy.cn/Article/details/75906.sHtML
http://www.blog.puhvjy.cn/Article/details/72236.sHtML
http://www.blog.puhvjy.cn/Article/details/795294.sHtML
http://www.blog.puhvjy.cn/Article/details/772278.sHtML
http://www.blog.puhvjy.cn/Article/details/7140.sHtML
http://www.blog.puhvjy.cn/Article/details/87710.sHtML
http://www.blog.puhvjy.cn/Article/details/512026.sHtML
http://www.blog.puhvjy.cn/Article/details/86833.sHtML
http://www.blog.puhvjy.cn/Article/details/8930494.sHtML
http://www.blog.puhvjy.cn/Article/details/957708.sHtML
http://www.blog.puhvjy.cn/Article/details/372650.sHtML
http://www.blog.puhvjy.cn/Article/details/03145.sHtML
http://www.blog.puhvjy.cn/Article/details/48567.sHtML
http://www.blog.puhvjy.cn/Article/details/3712381.sHtML
http://www.blog.puhvjy.cn/Article/details/561039.sHtML
http://www.blog.puhvjy.cn/Article/details/02298.sHtML
http://www.blog.puhvjy.cn/Article/details/4258.sHtML
http://www.blog.puhvjy.cn/Article/details/1208.sHtML
http://www.blog.puhvjy.cn/Article/details/8794.sHtML
http://www.blog.puhvjy.cn/Article/details/8305.sHtML
http://www.blog.puhvjy.cn/Article/details/3355204.sHtML
http://www.blog.puhvjy.cn/Article/details/6970917.sHtML
http://www.blog.puhvjy.cn/Article/details/7276.sHtML
http://www.blog.puhvjy.cn/Article/details/9685641.sHtML
http://www.blog.puhvjy.cn/Article/details/57947.sHtML
http://www.blog.puhvjy.cn/Article/details/23523.sHtML
http://www.blog.puhvjy.cn/Article/details/470257.sHtML
http://www.blog.puhvjy.cn/Article/details/3407395.sHtML
http://www.blog.puhvjy.cn/Article/details/7849.sHtML
http://www.blog.puhvjy.cn/Article/details/1396.sHtML
http://www.blog.puhvjy.cn/Article/details/0636496.sHtML
http://www.blog.puhvjy.cn/Article/details/54653.sHtML
http://www.blog.puhvjy.cn/Article/details/50233.sHtML
http://www.blog.puhvjy.cn/Article/details/335798.sHtML
http://www.blog.puhvjy.cn/Article/details/9513410.sHtML
http://www.blog.puhvjy.cn/Article/details/6088.sHtML
http://www.blog.puhvjy.cn/Article/details/764973.sHtML
http://www.blog.puhvjy.cn/Article/details/0936.sHtML
http://www.blog.puhvjy.cn/Article/details/5916837.sHtML
http://www.blog.puhvjy.cn/Article/details/6215.sHtML
http://www.blog.puhvjy.cn/Article/details/1082933.sHtML
http://www.blog.puhvjy.cn/Article/details/845709.sHtML
http://www.blog.puhvjy.cn/Article/details/11174.sHtML
http://www.blog.puhvjy.cn/Article/details/7129.sHtML
http://www.blog.puhvjy.cn/Article/details/995271.sHtML
http://www.blog.puhvjy.cn/Article/details/687760.sHtML
http://www.blog.puhvjy.cn/Article/details/13814.sHtML
http://www.blog.puhvjy.cn/Article/details/84985.sHtML
http://www.blog.puhvjy.cn/Article/details/74856.sHtML
http://www.blog.puhvjy.cn/Article/details/8795877.sHtML
http://www.blog.puhvjy.cn/Article/details/0217838.sHtML
http://www.blog.puhvjy.cn/Article/details/5864671.sHtML
http://www.blog.puhvjy.cn/Article/details/6001.sHtML
http://www.blog.puhvjy.cn/Article/details/411726.sHtML
http://www.blog.puhvjy.cn/Article/details/4912.sHtML
http://www.blog.puhvjy.cn/Article/details/865666.sHtML
http://www.blog.puhvjy.cn/Article/details/8437911.sHtML
http://www.blog.puhvjy.cn/Article/details/7826.sHtML
http://www.blog.puhvjy.cn/Article/details/2438892.sHtML
http://www.blog.puhvjy.cn/Article/details/3541266.sHtML
http://www.blog.puhvjy.cn/Article/details/6273.sHtML
http://www.blog.puhvjy.cn/Article/details/9691169.sHtML
http://www.blog.puhvjy.cn/Article/details/5358784.sHtML
http://www.blog.puhvjy.cn/Article/details/4938.sHtML
http://www.blog.puhvjy.cn/Article/details/8066.sHtML
http://www.blog.puhvjy.cn/Article/details/747406.sHtML
http://www.blog.puhvjy.cn/Article/details/58183.sHtML
http://www.blog.puhvjy.cn/Article/details/01885.sHtML
http://www.blog.puhvjy.cn/Article/details/2635138.sHtML
http://www.blog.puhvjy.cn/Article/details/8820.sHtML
http://www.blog.puhvjy.cn/Article/details/5090671.sHtML
http://www.blog.puhvjy.cn/Article/details/06651.sHtML
http://www.blog.puhvjy.cn/Article/details/809174.sHtML
http://www.blog.puhvjy.cn/Article/details/37136.sHtML
http://www.blog.puhvjy.cn/Article/details/4446966.sHtML
http://www.blog.puhvjy.cn/Article/details/8056117.sHtML
http://www.blog.puhvjy.cn/Article/details/655310.sHtML
http://www.blog.puhvjy.cn/Article/details/6220.sHtML
http://www.blog.puhvjy.cn/Article/details/5893.sHtML
http://www.blog.puhvjy.cn/Article/details/9613180.sHtML
http://www.blog.puhvjy.cn/Article/details/9745313.sHtML
http://www.blog.puhvjy.cn/Article/details/30332.sHtML
http://www.blog.puhvjy.cn/Article/details/7425.sHtML
http://www.blog.puhvjy.cn/Article/details/0533.sHtML
http://www.blog.puhvjy.cn/Article/details/0007558.sHtML
http://www.blog.puhvjy.cn/Article/details/5334.sHtML
http://www.blog.puhvjy.cn/Article/details/5465076.sHtML
http://www.blog.puhvjy.cn/Article/details/7735.sHtML
http://www.blog.puhvjy.cn/Article/details/9157105.sHtML
http://www.blog.puhvjy.cn/Article/details/47376.sHtML
http://www.blog.puhvjy.cn/Article/details/317014.sHtML
http://www.blog.puhvjy.cn/Article/details/2972.sHtML
http://www.blog.puhvjy.cn/Article/details/8811.sHtML
http://www.blog.puhvjy.cn/Article/details/090065.sHtML
http://www.blog.puhvjy.cn/Article/details/7494.sHtML
http://www.blog.puhvjy.cn/Article/details/79010.sHtML
http://www.blog.puhvjy.cn/Article/details/40216.sHtML
http://www.blog.puhvjy.cn/Article/details/9403785.sHtML
http://www.blog.puhvjy.cn/Article/details/144576.sHtML
http://www.blog.puhvjy.cn/Article/details/3024996.sHtML
http://www.blog.puhvjy.cn/Article/details/5092.sHtML
http://www.blog.puhvjy.cn/Article/details/5009628.sHtML
http://www.blog.puhvjy.cn/Article/details/136197.sHtML
http://www.blog.puhvjy.cn/Article/details/69263.sHtML
http://www.blog.puhvjy.cn/Article/details/72996.sHtML
http://www.blog.puhvjy.cn/Article/details/1983.sHtML
http://www.blog.puhvjy.cn/Article/details/01136.sHtML
http://www.blog.puhvjy.cn/Article/details/6859.sHtML
http://www.blog.puhvjy.cn/Article/details/44025.sHtML
http://www.blog.puhvjy.cn/Article/details/49656.sHtML
http://www.blog.puhvjy.cn/Article/details/788634.sHtML
http://www.blog.puhvjy.cn/Article/details/12606.sHtML
http://www.blog.puhvjy.cn/Article/details/5899.sHtML
http://www.blog.puhvjy.cn/Article/details/609366.sHtML
http://www.blog.puhvjy.cn/Article/details/205071.sHtML
http://www.blog.puhvjy.cn/Article/details/93488.sHtML
http://www.blog.puhvjy.cn/Article/details/4358.sHtML
http://www.blog.puhvjy.cn/Article/details/14065.sHtML
http://www.blog.puhvjy.cn/Article/details/6216532.sHtML
http://www.blog.puhvjy.cn/Article/details/580466.sHtML
http://www.blog.puhvjy.cn/Article/details/9928.sHtML
http://www.blog.puhvjy.cn/Article/details/9669369.sHtML
http://www.blog.puhvjy.cn/Article/details/47046.sHtML
http://www.blog.puhvjy.cn/Article/details/8623.sHtML
http://www.blog.puhvjy.cn/Article/details/915415.sHtML
http://www.blog.puhvjy.cn/Article/details/4931.sHtML
http://www.blog.puhvjy.cn/Article/details/2911071.sHtML
http://www.blog.puhvjy.cn/Article/details/87502.sHtML
http://www.blog.puhvjy.cn/Article/details/681433.sHtML
http://www.blog.puhvjy.cn/Article/details/0996.sHtML
http://www.blog.puhvjy.cn/Article/details/497729.sHtML
http://www.blog.puhvjy.cn/Article/details/0317336.sHtML
http://www.blog.puhvjy.cn/Article/details/50873.sHtML
http://www.blog.puhvjy.cn/Article/details/88978.sHtML
http://www.blog.puhvjy.cn/Article/details/71870.sHtML
http://www.blog.puhvjy.cn/Article/details/2229074.sHtML
http://www.blog.puhvjy.cn/Article/details/5222450.sHtML
http://www.blog.puhvjy.cn/Article/details/498941.sHtML
http://www.blog.puhvjy.cn/Article/details/3023117.sHtML
http://www.blog.puhvjy.cn/Article/details/4919420.sHtML
http://www.blog.puhvjy.cn/Article/details/126612.sHtML
http://www.blog.puhvjy.cn/Article/details/401936.sHtML
http://www.blog.puhvjy.cn/Article/details/588422.sHtML
http://www.blog.puhvjy.cn/Article/details/20243.sHtML
http://www.blog.puhvjy.cn/Article/details/08729.sHtML
http://www.blog.puhvjy.cn/Article/details/98316.sHtML
http://www.blog.puhvjy.cn/Article/details/29231.sHtML
http://www.blog.puhvjy.cn/Article/details/51457.sHtML
http://www.blog.puhvjy.cn/Article/details/4210.sHtML
http://www.blog.puhvjy.cn/Article/details/6208784.sHtML
http://www.blog.puhvjy.cn/Article/details/95588.sHtML
http://www.blog.puhvjy.cn/Article/details/72348.sHtML
http://www.blog.puhvjy.cn/Article/details/51246.sHtML
http://www.blog.puhvjy.cn/Article/details/36412.sHtML
http://www.blog.puhvjy.cn/Article/details/939478.sHtML
http://www.blog.puhvjy.cn/Article/details/6921138.sHtML
http://www.blog.puhvjy.cn/Article/details/4696.sHtML
http://www.blog.puhvjy.cn/Article/details/9886.sHtML
http://www.blog.puhvjy.cn/Article/details/0267097.sHtML
http://www.blog.puhvjy.cn/Article/details/0683734.sHtML
http://www.blog.puhvjy.cn/Article/details/341877.sHtML
http://www.blog.puhvjy.cn/Article/details/2704.sHtML
http://www.blog.puhvjy.cn/Article/details/003912.sHtML
http://www.blog.puhvjy.cn/Article/details/250154.sHtML
http://www.blog.puhvjy.cn/Article/details/8196457.sHtML
http://www.blog.puhvjy.cn/Article/details/575018.sHtML
http://www.blog.puhvjy.cn/Article/details/69424.sHtML
http://www.blog.puhvjy.cn/Article/details/622191.sHtML
http://www.blog.puhvjy.cn/Article/details/7248359.sHtML
http://www.blog.puhvjy.cn/Article/details/319404.sHtML
http://www.blog.puhvjy.cn/Article/details/90657.sHtML
http://www.blog.puhvjy.cn/Article/details/125169.sHtML
http://www.blog.puhvjy.cn/Article/details/042207.sHtML
http://www.blog.puhvjy.cn/Article/details/2984877.sHtML
http://www.blog.puhvjy.cn/Article/details/108873.sHtML
http://www.blog.puhvjy.cn/Article/details/89722.sHtML
http://www.blog.puhvjy.cn/Article/details/0015.sHtML
http://www.blog.puhvjy.cn/Article/details/07843.sHtML
http://www.blog.puhvjy.cn/Article/details/5274.sHtML
http://www.blog.puhvjy.cn/Article/details/7849941.sHtML
http://www.blog.puhvjy.cn/Article/details/4748583.sHtML
http://www.blog.puhvjy.cn/Article/details/957462.sHtML
http://www.blog.puhvjy.cn/Article/details/86430.sHtML
http://www.blog.puhvjy.cn/Article/details/489009.sHtML
http://www.blog.puhvjy.cn/Article/details/13285.sHtML
http://www.blog.puhvjy.cn/Article/details/4019.sHtML
http://www.blog.puhvjy.cn/Article/details/857517.sHtML
http://www.blog.puhvjy.cn/Article/details/70992.sHtML
http://www.blog.puhvjy.cn/Article/details/7128.sHtML
http://www.blog.puhvjy.cn/Article/details/64857.sHtML
http://www.blog.puhvjy.cn/Article/details/0876560.sHtML
http://www.blog.puhvjy.cn/Article/details/4277221.sHtML
http://www.blog.puhvjy.cn/Article/details/1857793.sHtML
http://www.blog.puhvjy.cn/Article/details/8485.sHtML
http://www.blog.puhvjy.cn/Article/details/734300.sHtML
http://www.blog.puhvjy.cn/Article/details/6733359.sHtML
http://www.blog.puhvjy.cn/Article/details/4070859.sHtML
http://www.blog.puhvjy.cn/Article/details/05947.sHtML
http://www.blog.puhvjy.cn/Article/details/819774.sHtML
http://www.blog.puhvjy.cn/Article/details/0445144.sHtML
http://www.blog.puhvjy.cn/Article/details/858883.sHtML
http://www.blog.puhvjy.cn/Article/details/27741.sHtML
http://www.blog.puhvjy.cn/Article/details/737404.sHtML
http://www.blog.puhvjy.cn/Article/details/3858396.sHtML
http://www.blog.puhvjy.cn/Article/details/07042.sHtML
http://www.blog.puhvjy.cn/Article/details/12414.sHtML
http://www.blog.puhvjy.cn/Article/details/40359.sHtML
http://www.blog.puhvjy.cn/Article/details/436701.sHtML
http://www.blog.puhvjy.cn/Article/details/7795.sHtML
http://www.blog.puhvjy.cn/Article/details/7088.sHtML
http://www.blog.puhvjy.cn/Article/details/1223255.sHtML
http://www.blog.puhvjy.cn/Article/details/8312490.sHtML
http://www.blog.puhvjy.cn/Article/details/640382.sHtML
http://www.blog.puhvjy.cn/Article/details/2414537.sHtML
http://www.blog.puhvjy.cn/Article/details/4054404.sHtML
http://www.blog.puhvjy.cn/Article/details/18282.sHtML
http://www.blog.puhvjy.cn/Article/details/341453.sHtML
http://www.blog.puhvjy.cn/Article/details/856562.sHtML
http://www.blog.puhvjy.cn/Article/details/4707.sHtML
http://www.blog.puhvjy.cn/Article/details/7646.sHtML
http://www.blog.puhvjy.cn/Article/details/081136.sHtML
http://www.blog.puhvjy.cn/Article/details/817897.sHtML
http://www.blog.puhvjy.cn/Article/details/150955.sHtML
http://www.blog.puhvjy.cn/Article/details/204965.sHtML
http://www.blog.puhvjy.cn/Article/details/3179.sHtML
http://www.blog.puhvjy.cn/Article/details/9436939.sHtML
http://www.blog.puhvjy.cn/Article/details/8875.sHtML
http://www.blog.puhvjy.cn/Article/details/70463.sHtML
http://www.blog.puhvjy.cn/Article/details/306610.sHtML


## 项目结构

```
linkvault/
├── linkvault.py               # 主入口 CLI 程序，整合 init/serve/check/export 子命令
├── requirements.txt           # Python 依赖声明文件，锁定主要库版本
├── config.yaml                # 用户配置文件，包含数据库路径、端口、标签方案等
├── README.md                  # 项目说明文档（本文件）
├── LICENSE                    # MIT 许可证全文
│
├── core/                      # 核心业务逻辑模块
│   ├── __init__.py
│   ├── entry.py               # 外链条目数据模型与校验逻辑
│   ├── indexer.py             # 倒排索引构建与检索实现
│   ├── checker.py             # 链接可用性异步检查器
│   └── exporter.py            # JSON/CSV/OPML 格式导出器
│
├── storage/                   # 数据持久化层
│   ├── __init__.py
│   ├── database.py            # SQLite 连接池与表结构初始化
│   ├── repository.py          # CRUD 操作封装
│   └── migrations/            # 数据库版本迁移脚本
│       ├── v001_initial.sql
│       └── v002_add_tags.sql
│
├── web/                       # Web 界面与静态站点生成
│   ├── __init__.py
│   ├── app.py                 # Flask/FastAPI 应用工厂
│   ├── routes/                # 路由处理器
│   │   ├── api.py             # RESTful API 端点
│   │   └── pages.py           # 页面渲染路由
│   ├── templates/             # Jinja2 模板文件
│   │   ├── base.html
│   │   ├── index.html
│   │   └── detail.html
│   └── static/                # 构建输出的静态资源目录
│       ├── css/
│       └── js/
│
├── tests/                     # 单元测试与集成测试
│   ├── test_entry.py
│   ├── test_indexer.py
│   └── test_checker.py
│
├── scripts/                   # 运维辅助脚本
│   ├── backup_db.sh           # 数据库定时备份脚本
│   └── import_bookmarks.py    # 从浏览器书签 HTML 导入的转换脚本
│
└── docs/                      # 完整文档手册
    ├── user-guide.md
    ├── configuration.md
    ├── development.md
    └── deployment.md
```


## 贡献指南

1. 在 GitHub Issues 中查阅现有待办事项或提出新功能建议，确认无重复工作后 fork 项目仓库到个人账户。

2. 创建以 feature/ 或 fix/ 为前缀的分支，遵循项目现有代码风格（PEP 8 规范，函数与类需包含 docstring），并确保所有单元测试通过。

3. 提交 Pull Request 时填写模板中的变更摘要、测试覆盖情况与相关 Issue 编号，维护者将在 7 个工作日内进行代码审查。

4. 若涉及新增外部依赖或修改数据库表结构，需同步更新 docs/ 下对应文档章节以及 migrations/ 中的迁移脚本。

5. 文档类贡献（包括修正拼写错误、补充使用示例）同样欢迎，直接提交 PR 即可，无需预先创建 Issue。


## 常见问题

**Q：LinkVault 是否会爬取并存储所收录链接的页面内容？**

不会。LinkVault 仅存储用户主动录入的 URL、标题、描述与标签等元数据，不对目标页面进行全文爬取或内容缓存。链接可用性检查仅发送 HEAD 请求验证 HTTP 状态码，不下载响应体。用户需自行遵守目标网站的 robots.txt 与访问条款。

**Q：如何从浏览器书签或 Pinboard 等第三方服务迁移数据？**

项目提供 scripts/import_bookmarks.py 脚本，支持 Netscape HTML 书签导出格式（所有主流浏览器均支持）以及 Pinboard 的 JSON 导出格式。执行 `python scripts/import_bookmarks.py --input bookmarks.html --format netscape` 即可导入。对于其他服务，可先导出为 CSV 或 JSON 再通过 `linkvault.py import` 命令映射字段。

**Q：静态生成的导航页面能否部署到 GitHub Pages 或 Vercel 等平台？**

可以。执行 `linkvault.py build --output ./dist` 会在指定目录生成完整的静态 HTML、CSS 与 JavaScript 文件，无需后端服务即可运行。将 dist 目录内容推送至 GitHub Pages 仓库或 Vercel 项目即可完成部署，所有链接跳转均在前端完成。


## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 16:29:43
