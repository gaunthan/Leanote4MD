title: Leanote导入导出MD工具
date: 2015/04/01 15:43:41
updated: 2017/02/01 16:46:15
categories:
- 代码
tags:
- Python
- Leanote

---

# 说明
基于原项目对export功能做了部分修改：

- 修复tags导出功能
- 笔记根据笔记本导出到相应目录中，若目录不存在则自动删除
- 移除图片导出功能

# leanote导入导出MD工具
- 可以把你储存在[Leanote](http://leanote.com)上的笔记、文章都导出成Markdown文件、文本文件
- 也可以把你储存在硬盘的Markdown文件、文本文件都导入到[Leanote](http://leanote.com)上去
- 目前支持导入导出含YAML格式的meta信息的文件，参照 [hexo](http://hexo.io/docs/front-matter.html)  的文件格式，也就是说文件头部可以有`title` `tags` `date` `categoris`等meta信息
- 兼容官方网站，以及自建的服务器（基于beta4，以及API 0.1版本）

# 如何使用
- 首先安装Python2版本
- 确保机器已经安装 `requests` `Pillow` `PyYaml` `requests_toolbelt` 等模块，如果没装请 `pip install`
- 然后在命令行执行`python leanote4MD.py`
  - 如果报错，应该是你的 python 路径问题，或者缺少某些python module
- 根据提示输入域名（默认是http://leanote.com）、用户邮箱、密码
  - 域名不要忘记加`http://`
  - 如果是自建服务器，请保证版本不低于 beta4
  - 记得用邮箱，而不是用户名
- 一般导入的错误都是文件没有严格按照YAML格式（多余空格等）造成的解析错误


# 功能

- [x] 从Leanote导入、导出笔记本/子笔记本到MD或txt文本文件
- [x] 保存为兼容 hexo front matter 的tag、category、date、title等
  - 由于0.1版本API限制，导入时暂时无法设置 保存时间、修改时间
- [x] 只导入、导出不在垃圾箱的笔记
- [x] 数不尽的bug
- [ ] 根据是否为已发布的blog，生成post或者draft属性
- [x] 导出时保存图片到本地
- [ ] 导入时提交图片到服务器
