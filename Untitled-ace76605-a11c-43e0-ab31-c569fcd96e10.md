# 选择器优先级

Reviewed: No
Status: Css
频率: ⭐⭐

# 什么是选择器优先级（Specificity）？

浏览器通过优先级来判断哪一些属性值与哪一个元素最为相关，从而在该元素上应用这些属性值。优先级是基于不同种类选择器组成的匹配规则。

## 优先级的计算

> 内联 > ID选择器 >类选择器 > 标签选择器

浏览器的优先级算法：

> **A specificity is determined by plugging numbers into (a, b, c, d):**
1. If the styles are applied via the style ttribute, a=1; otherwise, a=0.
2. b is equal to the number of ID selectors present.
3. c is equal to the number of class selectors, attribute selectors, and pseudoclasses present.
4. d is equal to the number of type selectors and pseudoelements present.

翻译之后：

优先级是由 `A` 、`B`、`C`、`D` 的值来决定的，其中它们的值计算规则如下：

1. 如果存在内联样式，那么 `A = 1`, 否则 `A = 0`;
2. `B` 的值等于 `ID选择器` 出现的次数;
3. `C` 的值等于 `类选择器` 和 `属性选择器` 和 `伪类` 出现的总次数;
4. `D` 的值等于 `标签选择器` 和 `伪元素` 出现的总次数 。

**比较规则是:A,B,C,D 从左往右依次进行比较 ，较大者胜出，如果相等，则继续往右移动一位进行比较 。如果4位全部相等，则后面的会覆盖前面的。**

## 特殊情况

内联样式是优先级最高的，但是在外部样式里加上！inportant就可以覆盖内联样式。

[!important提升指定样式的优先级](./important-33e3c4dd-7897-4ee6-8129-afb1930a98e4.md)