无刷新页面切换实现：

思路一：

借助于html5新增的history.pushState、history.replaceState方法、window.onpopstate事件实现；

思路二：

值助于页面url的hash值，及window.onhashchange事件实现

原理：

当调用pusthState方法，或者直接改变hash值时，会生成新的历史记录，页面url地址发生相应变化，但不会刷新浏览器。

一致性实现：

统一切换时，url地址变化的部分是改变的是url的hash值。两种方式同时使用时，也方便向后兼容


pushstate、onpopstate兼容性问题：

1、新api存在某些低版本浏览器的未实现，
2、当手动改变url的hash值时，onpopstate事件中取不到history.state的值，返回null; 解决方案使用hash值替代。

onhashchange实现上不存在兼容性问题，可放心使用


 
