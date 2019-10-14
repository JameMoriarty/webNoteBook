# isArray()方法，isArray(ary.prototype) //false

Reviewed: No
Status: JavaScript
频率: ⭐⭐

# 数组检测方法

    var array=[1,2,3];

## 方法1：instanceof

    //方法1
    if(array instanceof Array){
    
    }
    //返回true

## 方法2：Array.isArray();

    //方法二 ES5
    if(Array.isArray(array)){
    
    }
    //返回true

## 方法3：isArray()的原理

    Object.prototype.toString.apply(ary);
    //返回'[object Array]'

    Object.prototype.toString.call(ary);
    //返回'[object Array]'