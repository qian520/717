## **项目名称：717食品安全商城**
#### **主要用到的技术：vue axios locastro 

##项目结构
一:1首页
    轮播（展现出该产品的亮点）
    导航（对一些产品进行分类，让用户一目了然）
    搜索（可以对自己想要的产品进行搜索，比较方便）
2分类
    商品列表（有各类商品的展示详情介绍）

3购物车
    统计用户所选中的产品，进行计算，然后购买
4我的
    有关产品的一个物流情况以及关于产品质量和售后服务方面的承诺
二:2、用到的库，框架和第三方插件，工具Es6、vue、mock、vuex、router-loader、swiper、vue-router、axios、github

##项目思路
用vue脚手架进行搭建，利用vue-router以及vue中的组件开发对整体页面结构进行搭建，在首页用html5中的swiper做banner图的轮播效果，利用icon图标做图标列表，减少浏览器的请求速度，使用vuex中的store进行数据存储，对列表中的每个产品进行组件化封装，利用axios拦截器请求数据，进行参数匹配、数据渲染，实现产品列表效果，之后利用路由传参进行跳转详情页，以及数据渲染，购物车页面的实现，将vuex中store下的state设置为默认的初始状态，以及对页面进行渲染，效果搭建好之后，运用store里面的mutation,actions进行总价计算。之后用actions和dispatch进行异步操作实现购物车的效果。
在我的模块中有一些相对应的小模块，可以利用路由跳转进行搭建以及网页设计。在登录页，用户名和密码利用了正则判断以及进行localStorage本地存储，将请求到的数据直接存储到本地，给用户很好的体验。

##项目亮点
1.利用官方提供的vue-cli脚手架搭建工具，可以一键部署开发环境，省去很多麻烦。
2.项目的导航、产品列表、产品详情、购物车等内容都是利用vue组件化开发，方便重复模块的使用，减少了开发的效率。
用到了localStorage本地存储，减少网络流量，快速显示数据，给用良好的用户体验。

## 框架结构
    1-1.使用了vue脚手架搭建基本目录结构，整个项目包含四个主要内容，首页、分类、购物车和我的。每块内容由vue-router搭建出一个单独的路由
    2.在首页顶部有商品搜索功能，通过路由跳转到搜索页，可以实现搜索商品的功能，同时也通过localstorage记录了搜索历史。banner部分使用swiper实现轮播。
    3.分类导航是请求数据的渲染，并添加路由跳转，通过携带不同参数，跳转到对应的分类里。
    4.商品部分，将商品封装成组件，通过请求后台数据，得到商品数据，再遍历数据传递给商品组件不同的值，完成渲染。
    2-1.分类
    在钩子内设置一个路由拦截，并请求后台接口，数据请求完成后，根据数据渲染分类菜单，点击每个分类，改变当前的路由参数，处理路由参数，渲染对应分类里的商品
    3-1.购物车
    进入购物车页面，首先进行判断，如果当前状态为登录状态，则获取cookie中的登录信息，作为请求参数，向后台发送请求，后台通过登录信息，获取本地存储中相关数据并返回。如果没有登录则显示购物车为空。
    4-1我的
    每次进入路由前通过获取cookie信息判断是否为登录状态，若已登录，则直接进入，否则先进入登录页面
    点击登录，首先验证登录信息是否填写正确，不正确则提醒用户，正确则向后台发送请求，将登录信息发送
    用户注册时，首先验证信息填写是否正确，正确则发送后台请求，将注册信息发送，否则提示用户信息错误
    后台将注册信息保存到本地存储中，用于登录时的验证
    在我的页面中，点击地址管理，跳转路由到地址管理，并在进入前进行请求，判断当前账号下是否有相关的地址信息
    点击删除，取到要删除的地址对应的 id ，在本地存储中删除对应的地址
    点击编辑，携带对应的地址id跳转,进入新增地址是，判断是否带有参数，若有参数则为编辑，向后台请求相关信息，渲染页面
    同时请求城市信息,保存地址时首先判断信息是否填写完整，完整则向后台发送请求，将地址信息保存到当前登录用户名下，并保存到本地存储中

