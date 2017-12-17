## transition过渡

### 1. 过渡是怎么回事
* 假如某个css属性 P，它有一个初始值a，再设一个初始值b。指定P属性是可以过渡显示的，那么当P从a变到b时，会有一个动画的效果。
* 注意： 伪类的过渡会还原，非伪类元素动画执行完成后，会保存动画完成时的状态

* transtion的几个属性： 
    * transition-property: 就是上面那个P，比如说你指定width发生变化， 就填width;
    * transition-duration: 动画的时间 多少秒 比如 1s
    * transition-timing-function: 动画执行的速度效果
    * transition-delay: 延迟几秒执行

### 2. 过渡的复合写法
1. 某一个属性发生变化时，执行动画
    * transition: width 1s linear 2s;
    * width: 指定元素的width发生变化时，发生动画
    * 1s: 指定动画时长为1s
    * linear: 指定动画为匀速
    * 2s: 指定延时两秒执行

2.  所有属性变化时， 都执行动画
    * transition: all 1s linear;
    * all代表所有属性，只要发生变化都执行动画，时长都是1秒
    * 但如果各个属性执行动画的时长不一样呢?

3. 几个属性变化时，各自执行动画
    * transition: width 1s linear, height 1s ease 1s;
    * 代表width和height都会动画，但各自有自己的动画的参数;

4. 多个属性动画，分开写（如果参数相同，可以合并）
    * 可以多个属性分开写
        ```css
        transition-property: width, height;
        transition-duration: 1s; /*代表都是执行一秒，合并了*/
        transition-timing-function: ease, ease-in;
        transition-delay: 2s;
        ```

### 3. transtion支持的属性
* transition-property是用来指定当元素其中一个属性改变时执行transition效果: 所支持的属性类型如下：
    * color: 通过红、绿、蓝和透明度组件变换（每个数值处理）如：background-color,border-color,color,outline-color等css属性；
    * length: 真实的数  * 字 如：word-spacing,width,vertical-align,top,right,bottom,left,padding,outline-width,margin,min-width,min-height,max-width,max-height,line-height,height,border-width,border-spacing,background-position等属性；
    * percentage:真实的数字 如：word-spacing,width,vertical-align,top,right,bottom,left,padding,outline-width,margin,min-width,min-height,max-width,max-height,line-height,height,border-width,border-spacing,background-position等属性；
    * integer离散步骤（整个数字），在真实的数字空间，以及使用floor()转换为整数时发生 如：outline-offset,z-index等属性；
    * number真实的（浮点型）数值，如：zoom,opacity,font-weight,等属性；
    * transform list
    * rectangle:通过x, y, width 和 height（转为数值）变换，如：crop
    * visibility: 离散步骤，在0到1数字范围之内，0表示“隐藏”，1表示完全“显示”,如：visibility
    * shadow: 作用于color, x, y 和 blur（模糊）属性,如：text-shadow
    * gradient: 通过每次停止时的位置和颜色进行变化。它们必须有相同的类型（放射状的或是线性的）和相同的停止数值以便执行动画,如：background-image
    * paint server (SVG): 只支持下面的情况：从gradient到gradient以及color到color，然后工作与上面类似space-separated list of above:如果列表有相同的项目数值，则列表每一项按照上面的规则进行变化，否则无变化
    * a shorthand property: 如果缩写的所有部分都可以实现动画，则会像所有单个属性变化一样变化

### 3. 附录：动画速度样式详解
* linear： 线性过渡。等同于贝塞尔曲线(0.0, 0.0, 1.0, 1.0) 
* ease： 平滑过渡。等同于贝塞尔曲线(0.25, 0.1, 0.25, 1.0) 
* ease-in： 由慢到快。等同于贝塞尔曲线(0.42, 0, 1.0, 1.0) 
* ease-out： 由快到慢。等同于贝塞尔曲线(0, 0, 0.58, 1.0) 
* ease-in-out： 由慢到快再到慢。等同于贝塞尔曲线(0.42, 0, 0.58, 1.0) 
* step-start： 等同于 steps(1, start) 
* step-end： 等同于 steps(1, end) 
* steps(integer)： 分多少步完成
* <img src="./image/动画.png" width=600>
