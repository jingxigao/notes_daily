## 判断一个变量是否是数组

    var a = []; 
    // 1.基于instanceof 
    a instanceof Array; 
    // 2.基于constructor 
    a.constructor === Array; 
    // 3.基于Object.prototype.isPrototypeOf 
    Array.prototype.isPrototypeOf(a); 
    // 4.基于getPrototypeOf 
    Object.getPrototypeOf(a) === Array.prototype; 
    // 5.基于Object.prototype.toString 
    Object.prototype.toString.apply(a) === '[object Array]';
    // 6.Array.isArray
    Array.isArray([]); // true