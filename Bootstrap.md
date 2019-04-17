# Bootstrap 学习记录
记录一下Bootstrap3.3.7学习过程中的问题和解决方案。By kacoo@2019.04.17
## Gird System
1. 将屏幕均匀地分成12列
2. 媒体查询
通过`@media (min-width: 1200px)`适应不同的屏幕大小
3. 包含4种型号：xs、sm、md、lg，分别对应：  
.col-xs-n, <768px  
.col-sm-n, >=768px  
.col-md-n, >=992px  
.col-lg-n, >=1200px  
4. 偏移列`col-md-offset-3`
5. 嵌套列，在包含`row`中，继续使用网格分布
## 排版列
1. 重新定义了h1-h6标题样式
2. `.small`类，能得到一个字号更小的颜色更浅的文本，字体为父文本大小的 85%
3. `.lead`类，得到更大更粗、行高更高的文本
4. 提供了一些强调文本的类，如`small`、`strong`、`em`、`text-left`、`text-center`、`text-right`、`text-muted`、`text-promary`、`text-success`、`text-info`、`text-warning`、`text-danger`
5. 列表相关的类，`list-unstyled`（无样式）、`list-inline`（内联）
6. 表单相关的类，`sr-only`可以隐藏内联表单的标签
## 组件
1. 面包屑导航`首页 / 配置 / 密码`
2. 导航栏，胶囊型/默认
3. 按钮
4. 下拉菜单
5. 字体图标
6. 翻页Pagination
7. 徽章badge，可以用来当小tip显示消息数量
8. 缩略图thumbnail，适合排版类似的图片和文字说明
9. 进度条
10. 多媒体对象，如图片/视频的对齐
11. 面板，有点像便签