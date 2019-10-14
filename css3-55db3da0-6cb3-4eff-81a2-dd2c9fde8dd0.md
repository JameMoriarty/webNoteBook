# css3新特性

Class: css
Created: Sep 22, 2019 11:38 AM
Materials: http://css.cuishifeng.cn/animation.html
Reviewed: No
Status: css属性速查

# 边框

- border-radius 圆角边框
- box-shadow 阴影
    - 上偏移量
    - 左偏移量
    - 模糊半径
    - 阴影面积
    - 阴影颜色
    - inset 内阴影
- border-image 使用图形绘制边框
    - border-image-source 边框图片的路径
    - border-image-slice 边框向内偏移
    - border-image-width 图片边框的宽度
    - border-image-outset 图片超出边框的量
    - border-image-repeat 图像边框是否应平铺（repeated）、铺满（rounded）、拉伸（stretched）。

# 背景

- background-size 背景尺寸
- background-orgin 规定背景图片的定位区域， 可放在content-box、padding-box、border-box区域
- background-clip 背景的绘制区域

可以给body元素设置两幅背景图片。

# 文本效果

- text-shadow 文字阴影
    - h-shadow 水平阴影的位置
    - v-shadow 垂直阴影的位置
    - blur 模糊距离
    - color 阴影的颜色
- word-wrap 强制文本进行换行
    - normal 默认属性，只在允许的断字点换行
    - break-word 在长单词或url地址内部进行换行
- banging-punctuation 规定标点字符是否位于线框外
- punctation-trim 规定是否对标点字符进行修剪
- text-aligin-last 设置如何对齐最后一行或者紧挨着强制换行符之前的行
- text-emphasis 向元素的文本应用重点标记以及重点标记的前景色
- text-justify 水平对齐方法
- text-outlne 文本的轮廓
- text-overflow 当文本溢出包含元素时发生的事情
- text-wrap 规定文本的换行规则
- word-break 规定非中日韩文本的换行规则

# @font-face规则

    @font-face
    {
    font-family: myFirstFont;
    src: url('Sansation_Light.ttf'),
         url('Sansation_Light.eot'); /* IE9+ */
    }
    
    div
    {
    font-family:myFirstFont;
    }

使用@font-face定义要使用的字体，然后就可以在其他元素上使用这个字体了。
字体描述符

- font-family 必需 规定字体的名字
- src 必需 字体的url
- font-stretch 定义如何拉伸字体 默认normal，有动画性
    - normal 正常文字宽度
    - condensed 比正常文字宽度窄2个基数
    - ultra-condensed 比正常文字宽度窄4个基数
    - extra-condensed 比正常文字宽度窄3个基数
    - semi-condensed 比正常文字宽度窄1个基数
    - expanded	比正常文字宽度宽2个基数
    - semi-expanded 比正常文字宽度宽1个基数
    - extra-expanded 比正常文字宽度宽3个基数
    - ultra-expanded 比正常文字宽度宽4个基数
- font-style 文字样式
    - normal 正常
    - italic 斜体
    - oblique 倾斜的字体
- font-weight 文字粗细
    - normal
    - blod
    - bloder
    - lighter
    - 100 | 200 | 300 | 400 | 500 | 600 | 700 | 800 | 900

# 渐变

- linear-gradient（）线形渐变
    - 默认 从上到下
    - to left 从右到左
    - to right 从左到右
    - to bottom right 从左上角开始
    - to bottom left 从右上角开始
    - 角度
    - 颜色后面加百分数，实现条纹
- radial-gradient（）径向渐变
    - 颜色后面加百分数，实现不均匀分布的经向渐变
    - 形状：circle 圆形，ellipse 椭圆形
    - 渐变大小：
        - closest-side 指定径向渐变的半径长度为从圆心到离圆心最近的边
        - farthest-side 指定径向渐变的半径长度为从圆心到离圆心最远的边
        - closest-corner 指定径向渐变的半径长度为从圆心到离圆心最近的角
        - farthest-corner 指定径向渐变的半径长度为从圆心到离圆心最远的角

# transform

## 2D转换

- matrix（）六个参数的变换矩阵，相当于旋转、缩放、移动、倾斜于一体。
- translate（）平移。第一个参数对应x轴，第二个参数对应y轴，相对于左上角的坐标轴。
- rotate（）顺时针旋转，负值是逆时针
- skew（）倾斜。x轴和y轴倾斜的角度，为负数是反方向倾斜
- scale（）2D缩放。第一个参数是x轴，第二个是y轴，若第二个参数未提供，则取第一个参数的值。

## 3D转换

- matrix3d（）以一个4x4矩阵的形式指定一个3D变换。
- translate3d（）指定对象的3d位移。第一个参数是x轴，第二个参数是y轴，第三个参数是z轴。
- translatez（）指定对象z轴的平移。
- rotate3d()：指定对象的3D旋转角度，其中前3个参数分别表示旋转的方向x,y,z，第4个参数表示旋转的角度，参数不允许省略。
- rotatex()：指定对象在x轴上的旋转角度
- rotatey()：指定对象在y轴上的旋转角度
- rotatez()：指定对象在z轴上的旋转角度
- scale3d()：指定对象的3D缩放。第1个参数对应X轴，第2个参数对应Y轴，第3个参数对应Z轴，参数不允许省略
- scalez()：指定对象的z轴缩放
- perspective()：指定透视距离

# transition过渡

第一个参数是设置对象中参与过渡的属性，第二个持续时间，第三个是规定过渡效果的时间曲线，第四个是过渡效果的开始时间，若对所有属性都设置过渡，则使用all。

    <div></div>
    <style>
    div{
    	width:100px;
    	height:100px;
    	background:red;
    	transition:width 2s;
    }
    div:hover{
    	width:300px;
    }
    </style>

# 动画

## @keyframes

定义一个动画名称，和动画在每阶段的样式。
简单的动画使用from，to关键字。复杂的动画使用percentage设置某个时间段内的任意时间点的样式。

    /*简单的动画*/
    @keyframes changeColor{
    	from{
    		background:red;
    	}
    	to{
    		background:blue;
    	}
    }
    
    /*复杂的动画*/
    @keyframes changeMoreColor{
    	0%{
    		background:red;
    	}
    	25%{
    		background:yellow;
    	}
    	50%{
    		background:green;
    	}
    	75%{
    		background:blue;
    	}
    	100%{
    		background:white;
    	}
    }

## animation

第一个属性是动画名称，第二个属性是动画时长，第三个属性是检索或设置动画的过渡类型，第四个属性是延迟时间，第五个属性是魂环次数，第六个属性是在循环中是否反向运动，设置动画时间之外的状态。

尽可能不要使用伪元素来做动画，部分浏览器对伪元素动画支持的不够好。

# 多列

- column-count 列数
- column-width 列宽
- column-gap 列之间的间隙
- column-rule :
    - column-rule-width 列与列之间的边框厚度
    - column-rule-style 列与列之间的边框样式
    - column-rule-color 列与列之间的边框颜色
- column-span 指定元素跨多少列：
    - none 不跨列
    - all 跨所有列
- column-fill 指定元素每一列的高度是否自适应：
    - auto 高度自适应内容
    - balance 所有列的高度以其中最高的一列为准
- column-break-before 设置对象之前是否断行：
    - auto 即不强迫也不禁止在元素之前断行产生新列
    - always 总是在元素之前断行并产生新列
    - avoid 避免在元素之前断行并产生新列
- column-break-after 设置对象之后是否断行：
    - auto 既不强迫也不禁止在元素之后断行产生新列
    - always 总是在元素之后断行产生新列
    - avoid 避免在元素之后断行并产生新列
- column-break-inside 设置对象内部是否断行
    - auto 既不强迫也不禁止在元素内部断行并产生新列
    - avoid 避免在元素内部断行并产生新列

# 用户界面

## resize

设置对象的区域是否允许用户缩放，调节元素尺寸大小
* none 不允许用户调节元素大小
* both 用户可以调节元素的宽度和高度
* horizontal 用户可以调节元素的宽度
* vertical 用户可以调节元素的高度

此属性生效需配合overflow：auto

## box-sizing

设置对象的盒模型组成模式。
* content-box 标准模式下的盒模型。padding和border不被包含在定义的width和height之内
* border-box 怪异模式下的盒模型。padding和border被包含在定义的width和height之内。

## outline

设置对象外的线条轮廓。不占据布局空间，不影响元素尺寸。

- outline-width 指定轮廓边框的宽度
- outline-style 指定元素边框的样式
- outline-color 指定元素边框的颜色
- outline-offset 指定轮廓偏移量，允许为负值。以border边界作为参考点的。

## appearance

设置一个元素的外观像一个标准的用户界面元素。去除一个系统默认的样式，设置为none。

# 图片滤镜

- filter：
    - blur（）高斯模糊
    - brightness（%）线形乘法
    - contrast（%）对比度
    - drop-shadow（h-shadow v-shadow blur spread color）阴影
    - grayscale（）灰度图像
    - hue-rotate（deg）色相旋转
    - invert（%）反转输入
    - opacity（%）透明度
    - saturate（%）饱和度
    - sepia（%）深褐色
    - url（）接受一个xml文件，该文件设置了一个svg滤镜