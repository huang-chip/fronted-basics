# HTML 多媒体与响应式

> 学习HTML多媒体元素的使用以及响应式图片处理方案。

## 🎯 学习目标
- 掌握多媒体元素的使用方法和属性
- 理解响应式图片的实现方式
- 学会处理不同设备和屏幕尺寸下的媒体显示

## 📚 核心知识点

### 1. 图片相关
- 基础图片
  - **`<img>` - 基本图片元素**
    - **`src` - 图片源**
    - **`alt` - 替代文本**
    - **`width/height` - 尺寸属性**
    - `loading` - 加载策略
      - `eager` - 立即加载
      - **`lazy` - 延迟加载**
    - `decoding` - 解码策略
      - `sync` - 同步解码
      - `async` - 异步解码
      - `auto` - 自动选择

- 响应式图片
  - **`srcset` 属性 - 不同分辨率图片集**
    - 格式: `图片地址 宽度描述符w`
    - 示例: `image-320.jpg 320w, image-480.jpg 480w`
  - **`sizes` 属性 - 响应式尺寸设置**
    - 格式: `媒体条件 尺寸`
    - 示例: `(max-width: 320px) 280px, (max-width: 480px) 440px`
  - **`<picture>` 元素**
    - **`<source>` - 不同媒体源**
    - **`media` 属性 - 媒体查询**
    - **`type` 属性 - 图片格式**
      - `image/webp`
      - `image/jpeg`
      - `image/png`
      - `image/avif`

### 2. 音频/视频
- 音频 **`<audio>`**
  - 主要属性
    - **`src` - 音频源**
    - **`controls` - 控制面板**
    - `autoplay` - 自动播放
    - `loop` - 循环播放
    - `muted` - 静音
    - `preload` - 预加载策略
      - `none` - 不预加载
      - `metadata` - 仅元数据
      - `auto` - 自动预加载
  - 多源支持
    ```html
    <audio controls>
      <source src="audio.mp3" type="audio/mpeg">
      <source src="audio.ogg" type="audio/ogg">
      您的浏览器不支持音频播放。
    </audio>
    ```

- 视频 **`<video>`**
  - 主要属性
    - **`src` - 视频源**
    - **`poster` - 封面图**
    - **`controls` - 控制面板**
    - **`width/height` - 尺寸**
    - `autoplay` - 自动播放
    - `loop` - 循环播放
    - `muted` - 静音
    - `playsinline` - 行内播放
    - `preload` - 预加载策略
      - `none` - 不预加载
      - `metadata` - 仅元数据
      - `auto` - 自动预加载
  - 多源支持
    ```html
    <video controls width="600" poster="cover.jpg">
      <source src="video.webm" type="video/webm">
      <source src="video.mp4" type="video/mp4">
      <track kind="subtitles" src="captions.vtt" srclang="zh">
      您的浏览器不支持视频播放。
    </video>
    ```

### 3. 嵌入内容
- **`<iframe>` - 内联框架**
  - 安全属性
    - **`sandbox` - 安全限制**
      - `allow-same-origin`
      - `allow-scripts`
      - `allow-forms`
      - `allow-popups`
    - **`allow` - 功能许可**
      - `fullscreen`
      - `camera`
      - `microphone`
  - 常用属性
    - **`src` - 内容源**
    - **`width/height` - 尺寸**
    - `loading` - 加载策略
      - `eager`
      - `lazy`
    - `referrerpolicy` - 引用策略

### 4. 响应式设计基础
- **视口设置**
  ```html
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  ```

- **响应式图片最佳实践**
  ```html
  <!-- 基于设备像素比的响应式图片 -->
  <img srcset="image-1x.png 1x,
               image-2x.png 2x,
               image-3x.png 3x"
       src="image-1x.png"
       alt="响应式图片">

  <!-- 基于视口宽度的响应式图片 -->
  <img srcset="small.jpg 300w,
               medium.jpg 600w,
               large.jpg 900w"
       sizes="(max-width: 320px) 280px,
              (max-width: 640px) 580px,
              800px"
       src="fallback.jpg"
       alt="响应式图片">

  <!-- 使用picture元素的艺术指导 -->
  <picture>
    <source media="(min-width: 800px)"
            srcset="hero.jpg"
            type="image/jpeg">
    <source media="(min-width: 400px)"
            srcset="cropped-hero.jpg"
            type="image/jpeg">
    <img src="mobile-hero.jpg" alt="响应式图片">
  </picture>
  ```

## 🌟 最佳实践
1. **图片优化**
   - 始终提供有意义的alt文本
   - 使用适当的图片格式（WebP优先）
   - 实现延迟加载
   - 提供响应式图片
   - 指定图片尺寸避免布局偏移

2. **音视频优化**
   - 提供多格式源文件
   - 添加字幕和描述
   - 避免自动播放
   - 设置合适的预加载策略
   - 提供后备内容

3. **iframe安全**
   - 使用sandbox限制权限
   - 配置CSP策略
   - 使用allow控制特性
   - 实现延迟加载
   - 设置正确的尺寸

## 📝 注意事项
- 移动端优先考虑性能和带宽
- 注意媒体内容的版权问题
- 确保可访问性
- 提供降级方案
- 考虑不同浏览器的兼容性
