## 介绍

&#160;&#160;&#160;&#160;**自动为hexo中的图片映射绝对路径 | Automatically maps absolute paths to images in hexo**
添加使用jsdelivr加速`图片`和`视频`配置。

## 开始使用

```bash
npm i https://github.com/YyItRoad/hexo-filter-image.git --save
```
> 由于本身Hexo带有缓存会导致插件第一次使用可能会出现无效果，请使用```hexo clean```清除缓存后即可正常使用

------------

## 配置(可选)
> 请向Hexo的 `_config.yml` 文件或主题的 `_config.yml` 文件中添加配置.

```yaml
filter_image:
  # 日志是否启用
  log: true
  # 是否使用jsdelivr加速
  jsdelivr: null
```

jsdelivr参数:
   - null => 不使用jsdelivr加速。一般本地调试使用。
   - :path => 加速地址一般为`https://cdn.jsdelivr.net/gh/:user/:repo`,user为用户名称，repo为项目名称
 
 eg:   
 ```
 jsdelivr: https://cdn.jsdelivr.net/gh/yyitroad/yyitroad.github.io/
 ```

# Example

&#160;&#160;&#160;&#160;当Hexo配置文件的属性```root```值变化时，无需改变Markdown内容的图片地址，此插件会自动将图片映射成绝对路径

> 文章内容示例

```bash
![](/img/test.jpg)
```

> Hexo配置文件

```yaml
root: /testPath/
jsdelivr: https://cdn.jsdelivr.net/gh/yyitroad/yyitroad.github.io/
```

> jsdelivr为`null`生成后的图片路径为`/testPath/img/test.jpg`

> 使用CDN加速后的图片路径为`https://cdn.jsdelivr.net/gh/yyitroad/yyitroad.github.io/testPath/img/test.jpg`

## LICENSE

[![LICENSE](https://img.shields.io/github/license/JoeyBling/hexo-filter-image "LICENSE")](./LICENSE "LICENSE")
