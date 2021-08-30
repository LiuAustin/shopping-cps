# 电商导购CPS

https://mp.weixin.qq.com/s/vpy_wksG4A34FveyyjS-yg

![Image text](https://img-blog.csdnimg.cn/900992371fbe4ed0ab5bb4632900cca7.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5oKf56m656CB5a2X,size_20,color_FFFFFF,t_70,g_se,x_16)

#### 介绍
电商导购CPS就是接入全网最大的几家电商联盟平台，包括淘宝、京东、拼多多、唯品会、苏宁易购，美团，饿了么，集成商品和外卖，自购省钱，分享赚钱。主要业务功能模块有tab管理、通知公告、微信管理、电商导购、外卖物料、分销管理、用户管理、订单管理、提现管理，更多功能请自身体验。

#### 概述
前段时间写了个外卖cps小程序，并开源了代码，源码在这里 零基础，搞外卖CPS小程序副业，附源码(https://mp.weixin.qq.com/s/QfOvmMzriy6y1IVcZINkSQ) ，有需要的小伙伴自取，可以结合这篇文章 外卖CPS小程序部署指南，个人获取美团外卖小程序跳转链接(https://mp.weixin.qq.com/s/R_G5r7iNIkVd4CFWVQxnNQ) 部署 。

你猜的没错，今天聊的还是cps，不过是电商导购cps，就是淘宝，京东，拼多多，唯品会，苏宁易购这些电商联盟平台。这些购物平台也有隐藏的优惠券，给推广者佣金奖励，平时你直接从APP进去是看不到这些优惠券的，自然也无法享受到这些优惠。

![Image text](https://img-blog.csdnimg.cn/1f97faf477a946c59b870843d0330821.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5oKf56m656CB5a2X,size_20,color_FFFFFF,t_70,g_se,x_16)

我们要做的就是写代码接入这些平台的商品，用户从我们这里购物，我们就是推广者，当用户收货成功后，联盟平台会结算佣金给我们，每个商品佣金比例不同，高低不一。联盟平台有活跃用户，用户有优惠券可以用，推广者有佣金可以拿，可以说是三赢的局面。

![Image text](https://img-blog.csdnimg.cn/39f899838c114d95a8d4c6b4f53f9e58.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5oKf56m656CB5a2X,size_20,color_FFFFFF,t_70,g_se,x_16)

开发过程挺繁杂，熬了多个夜，要研究多个开放平台的接口调用，特别是商品价格、优惠券、佣金比例等字段。还要数据库设计，服务器环境搭建，其实这些都是项目搞起的基础，也不必多说。

![Image text](https://img-blog.csdnimg.cn/4fd2ccbbb8e245bb856f78d64e661881.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5oKf56m656CB5a2X,size_20,color_FFFFFF,t_70,g_se,x_16)

如果想把项目搞起来，那自然少不了分销的模块，那分给用户的 💰 从哪里出，当然是联盟平台给我们的佣金。要实现这个功能我们就需要知道这个订单是哪个用户下的，也就是行业常说的跟单。其他平台想实现跟单并不难，复杂的是淘宝联盟和拼多多联盟，这个以后专门的文章来详细介绍吧。

![Image text](https://img-blog.csdnimg.cn/9e3b07ff9aa147cd8c3dd8c71ba307c7.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5oKf56m656CB5a2X,size_20,color_FFFFFF,t_70,g_se,x_16)

这次也把外卖cps的两个角色嵌进来了，不过功能更丰富了，包括饿了么外卖、果蔬部分，美团外卖、闪购、优选、酒店部分。外卖cps有一个特点就是由于确认收货的周期短，所以结算比较快，不像电商购物，还有物流的过程，更容易推广些。

![Image text](https://img-blog.csdnimg.cn/26674bc1268c4cef8aef812d6a7d2cf5.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5oKf56m656CB5a2X,size_20,color_FFFFFF,t_70,g_se,x_16)

项目用户端是公众号H5，你问我为什么不做成小程序，先说下前端是基于uniapp框架开发。江湖传言，uniapp打包一套代码，多个环境（微信、抖音、支付宝、百度）多种形式（APP、H5、小程序）运行，自然也可以打包成小程序，但是不建议做成小程序（这里说的是微信小程序），至于为啥子，小伙伴不妨展开想象的翅膀，自由思考吧。

做公众号有个明显的好处就是各种通知不需要短信，可以用公众号发模板消息，比如注册成功通知、验证码通知、用户登录通知、订单通知、提现通知等等，别看这些通知，也可以省很多银子的哈。

![Image text](https://img-blog.csdnimg.cn/6cce424fe2f34ff88c6228f73b062c5a.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5oKf56m656CB5a2X,size_20,color_FFFFFF,t_70,g_se,x_16)

更多功能还在迭代中，敬请期待。

如果你也同在电商导购cps，有问题有想法可以互相交流。

用户端体验：

![Image text](https://img-blog.csdnimg.cn/8ba10fd11a9c4aefa8fd8737e9a3255f.png)

管理端体验：

公众号后台回复【电商导购CPS】获取整个项目体验地址。

![Image text](https://img-blog.csdnimg.cn/101a73ed0228494786544af811382ace.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5oKf56m656CB5a2X,size_14,color_FFFFFF,t_70,g_se,x_16)
