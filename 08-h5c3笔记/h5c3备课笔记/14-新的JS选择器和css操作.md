## 新的js选择器和css操作方法

### 新增的js选择器
* document.QuerySelector();
    * 传id `#test`
    * 传class `.text`
    * 传tagname `.li`
    * 返回的是满足条件的第一个元素
* document.QuerySelectorAll();
    * 传id `#test`
    * 传class `.text`
    * 传tagname `.li`
    * 返回的是满足条件的伪数组，即便只有一个，也可能使用数组

### 新增的css操作方法
* 早期我们要操纵类名 需要使用
    * dom.className = "abc" 来修改 由于返回的是字符串 操作起来并不方便
    * $("body").addClass
    * $("body").removeClass
    * $("body").toggleClass
    * $("body").hasClass
* h5提供的新添加类的方法
    * 添加类
        * document.body.classList.add('black');
    * 删除类 
        * document.body.classList.remove('black');
    * 切换类 
        * document.body.classList.toggle('black');
    * 判断是否包括类名
        * document.body.classList.contain('black');