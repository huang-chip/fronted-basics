# HTML 基本结构

> 掌握HTML文档的基本结构和必要元素

## 核心要点

### 1. HTML5文档声明
```html
<!DOCTYPE html>
```

### 2. 基本骨架
```html
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>页面标题</title>
</head>
<body>
    <!-- 页面内容 -->
</body>
</html>
```

### 3. 必要的meta标签
```html
<!-- 字符编码 -->
<meta charset="UTF-8">

<!-- 视口设置 -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- SEO相关 -->
<meta name="description" content="页面描述">
<meta name="keywords" content="关键词1,关键词2">

<!-- JavaScript引入 -->
<script src="script.js"></script>                           <!-- 普通加载 -->
<script src="script.js" defer></script>                     <!-- DOM解析完成后执行 -->
<script src="script.js" async></script>                     <!-- 异步加载并执行 -->


<!-- 社交媒体元数据 -->
<meta property="og:title" content="页面标题">
<meta property="og:description" content="页面描述">
<meta property="og:image" content="share-image.jpg">
```

### 4. 常用头部元素
```html
<!-- 外部CSS -->
<link rel="stylesheet" href="styles.css">

<!-- 外部JavaScript -->
<script src="script.js"></script>

<!-- 网站图标 -->
<link rel="icon" href="favicon.ico">
```

## 实践检查清单
- [ ] DOCTYPE声明正确
- [ ] HTML语言属性设置
- [ ] 字符编码声明
- [ ] 视口设置完整
- [ ] 页面标题有意义
- [ ] 必要的meta标签齐全

## 注意事项
1. DOCTYPE必须是文档第一行
2. 字符编码声明应放在head的最前面
3. 视口设置对移动端适配必要
4. 建议使用语义化标签构建页面结构

## 相关练习
1. 创建一个基本的HTML5页面结构
2. 添加必要的meta标签和外部资源链接
3. 确保页面通过HTML验证器检查


