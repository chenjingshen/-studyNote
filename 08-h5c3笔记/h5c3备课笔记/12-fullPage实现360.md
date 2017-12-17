## fullPage

### fupage的实现步骤
1. 导入css `jquery.fullpage.min.css`, 注意路径
2. 设置html结构, 注意每一屏的class都需要设为`section`
```html
<div id="heima">
    <div class="section">Some section1</div>
    <div class="section">Some section2</div>
    <div class="section">Some section3</div>
    <div class="section">Some section4</div>
</div>
```
3. 导入jquery `jquery-1.12.4.min.js` 注意路径
4. 导入fullPage插件的js文件 `jquery.fullpage.min.js` 注意路径
5. 调用fullPage插件
```js
<script type="text/javascript">
    // $(document).ready(function () {
    $(function () {
        $('#heima').fullpage();
    });
</script>
```

### 示代代码
```html
<!DOCTYPE html>
<html lang="zh-CN">

<head>
    <meta charset="UTF-8">
    <title>title</title>
    <!-- 1. 导入 css -->
    <link rel="stylesheet" type="text/css" href="lib/jquery.fullpage.min.css" />
    
    <style>
        /* final 最后根据需求去添加样式即可 */
        .section:nth-child(1) {
            background-color: skyblue;
        }

        .section:nth-child(2) {
            background-color: gray;
        }

        .section:nth-child(3) {
            background-color: gold;
        }

        .section:nth-child(4) {
            background-color: black;
        }
    </style>
</head>

<body>
    <!-- 2.设置html结构 -->
    <div id="heima">
        <div class="section">Some section1</div>
        <div class="section">Some section2</div>
        <div class="section">Some section3</div>
        <div class="section">Some section4</div>
    </div>
</body>

</html>
<!-- 3.导入 jQuery -->
<script type="text/javascript" src="lib/jquery-1.12.4.min.js"></script>
<!-- 4.导入fullpage插件 -->
<script type="text/javascript" src="lib/jquery.fullpage.min.js"></script>

<!-- 5.调用 fullpage插件 -->
<script type="text/javascript">
    $(function () {
        $('#heima').fullpage();
    });
</script>