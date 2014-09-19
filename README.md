mmRouter
=============

avalon的三柱臣之一（ 路由，动画，AJAX）


<h3>路由器的相关API</h3>
http://rubylouvre.github.io/mvvm/avalon.router.html

<h3>路由器与多个VM的协作（每个VM定义在不同的JS文件中）</h3>
```javascript

//aaa.js
define("aaa", function(){
   return  avalon.define("aaa", function(vm){
        vm.path = "/aaa"
  
   })

})

//bbb.js
define("bbb", function(){
   return avalon.define("bbb", function(vm){
       
 
   })
})

//ccc.js
define("ccc", function(){
    return avalon.define("ccc", function(vm){
     
   })
})

//页面
require(["mmRouter", "aaa", "bbb", "ccc"], function(avalon, av, bv, cv){
    avalon.router.get("/aaa", function(a) {
       av.path = a
    })
    avalon.router.get("/bbb", function(a) {
        bv
    })
    avalon.router.get("/ccc", function(a) {
       cv
    })
   
    avalon.history.start({
    basepath: "/mvvm"
    })
    avalon.router.navigate("/aaa")
    avalon.scan()

})
```
thanks to  sammy， jquery-address， backbone.js，angular.js
以后要学习一下 director
