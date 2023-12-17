# 构建方式

> 引自：
>
> [笔记文档一把梭——MkDocs 快速上手指南 ｜ 少数派会员 π+Prime (sspai.com)](https://sspai.com/prime/story/mkdocs-primer)
>
> [How To Create STUNNING Code Documentation With MkDocs Material Theme (youtube.com)](https://www.youtube.com/watch?v=Q-YA_dA8C20)

此网站基于[mkdocs-material](https://squidfunk.github.io/mkdocs-material/)构建。

## mkdocs

MkDocs（Markdown Documents）是一个快速、简单的静态网站生成器，用于将 Markdown 文档组织起来构建成有层次、美观的文档站点。

MkDocs 基于 Python 编写，也贯彻了 Python 里「简洁胜于复杂」的理念，与其他常见的静态网站生成器相比，无需繁琐的环境配置（如 Jekyll 涉及的 Bundler、Gems 等），所有配置都用只有简单的一个配置文件管理，并且当中配置项的内容也仅有一页文档。

## mkdocs.yml
mkdocs配置文件通过yml格式配置，主要配置如下（[全部配置](https://www.mkdocs.org/user-guide/configuration/)）：

- site_name：站点名称

- site_url：站点 URL 链接

- nav：MkDocs 提供了让使用者能够自由安排文档层级结构或目录编排的设置，这将决定最后文档在站点中的编排效果如何。这里主要是通过 nav 项来进行配置

## 扩展和主题
### Markdown 扩展
MkDocs 使用 Python-Markdown 库（Markdown 规范的 Python 实现）来渲染 Markdown 内容，因此 MkDocs 中对于 Markdown 内容渲染的扩展也是来自于此。我们可以在 Python-Markdown 的 官方文档 中浏览到目前所支持的 Markdown 扩展有哪些。

### 主题

https://github.com/mkdocs/mkdocs/wiki/MkDocs-Themes


## 站点部署
如果你只是临时用于离线浏览文档，那么使用 mkdocs serve 命令其实足矣；但如果你是打算作为个人站点或主页部署到云服务器，那么你就需要将整个文档项目编译打包，最后放到对应的服务器上部署。

这里 MkDocs 给我们提供了两个选项：一个是使用 mkdocs build 命令将项目打包之后，再由个人将打包文件上传至服务器对应的目录下进行部署；另外一个就是如果你有打算使用 Github Pages 来作为展示的站点（参见 GitHub Pages 搭建教程），那么我们就只需要使用 mkdocs gh-deploy 这一条命令就可以帮我们完成部署任务。

该命令的过程主要是先将编译打包好的相关资源文件（如 HTML 页面、样式、静态资源图片、用于交互的 JavaScript 等）上传至对应个人 Github 用户名的 Github Pages 仓库中，然后再利用 GitHub Actions 来保持站点活跃。

这样我们每次只需要在本地更新内容之后，通过该命令进行提交、部署，就可以实现文档内容的更新。

# 参考

[Mkdocs配置文件说明(mkdocs.yml)-CSDN博客](https://blog.csdn.net/m0_63203517/article/details/129765689)
