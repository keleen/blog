# 创意市场交接文档

## 简介

  创意市场是依附于穿云箭平台的一个子系统，主要用于广告主发布创意需求和创意者制作创意的平台。


### 原型
See [地址](http://product.altamob.com/CMC/creativemarket20190905/start.html).

## 仓库地址
```
git@gitlab.chumob.com:synative/creative-center.git
```

## 项目设置
```
npm install
```

### 开发启动
```
npm run serve
```

### 构建
```
npm run build
```

### 执行 eslint
```
npm run lint
```

## 环境地址
```
测试环境：http://qa-cmc.synative.cn/
正式环境：http://drama.tyrise.com/
```
## 项目接口文档
```
http://doc.codex.com/showdoc/index.php?s=/34&page_id=649
```
## 代码发布
  > 正式环境请找项目后端负责人进行发布，测试环境参考下面命令。前端需要本地构建后访问发布接口即可发布（浏览器也可以）。
```
 $ cd front && npm run build 
 $ curl http://qa-cmc.synative.cn/backend/public/sync.php
```

## 项目目录

```
├── README.md
├── babel.config.js
├── package-lock.json
├── package.json
├── public
│   ├── doc
│   ├── favicon.ico
│   └── index.html
├── src
│   ├── App.vue
│   ├── assets # css img 
│   │   ├── css
│   │   │   ├── common.css
│   │   │   └── reset.css
│   │   ├── icons
│   │   │   ├── iconfont.js
│   │   │   └── index.js
│   │   ├── img
│   │   │   ├── banner.png
│   │   │   ├── btn_close.png
│   │   │   ├── btn_play.png
│   │   │   ├── icon_ok.png
│   │   │   ├── new.png
│   │   │   ├── new2.png
│   │   │   └── register-bg.png
│   │   └── logo.png
│   ├── components # 所有不涉及路由的组件
│   │   ├── ad # 广告主
│   │   │   └── BtnAction.vue # 不同订单状态展示不同的按钮
│   │   ├── admin # 运营人员相关
│   │   │   ├── AuditOrderDetailItem.vue # 运营人员订单审核页面详情
│   │   │   ├── BdOrderDetailItem.vue # 运营人员订单审核页面详情
│   │   │   └── PlatformOrderAttach.vue # 运营平台订单详情中上传附件详情
│   │   ├── base # 基本组件
│   │   │   ├── BaseArea.vue # 地区查询级联租金
│   │   │   ├── BasePage.vue # 分页租金
│   │   │   ├── BaseStrSlice.vue # 字符串过长切割成... 组件
│   │   │   └── BaseUpload.vue # 上传附件组件
│   │   ├── commons # 公共组件
│   │   │   ├── ElSearch.vue # 好像没有用
│   │   │   ├── MessageList.vue # 消息列表
│   │   │   ├── icon.vue # 图标
│   │   │   └── index.js
│   │   ├── creator # 创意者
│   │   │   ├── BtnAction.vue # 不同订单状态展示不同的按钮
│   │   │   └── OrderDetailItem.vue # 创意者订单详情
│   │   ├── layout # 布局相关
│   │   │   ├── BaseHeader.vue
│   │   │   ├── BaseLayout.vue
│   │   │   └── BaseMenu.vue
│   │   ├── order # 订单相关
│   │   │   ├── OrderAttach.vue # 订单详情附件
│   │   │   ├── OrderAuthor.vue # 订单详情创意者
│   │   │   ├── OrderChannel.vue # 订单详情-下拉菜单-渠道
│   │   │   ├── OrderDetailItem.vue # 订单详情
│   │   │   ├── OrderIndustry.vue # 订单详情-下拉菜单-行业
│   │   │   ├── OrderMessage.vue # 无用（可删除）
│   │   │   ├── OrderRatio.vue # 订单详情-下拉菜单-视频比例
│   │   │   ├── OrderSetMeal.vue # 订单详情-下拉菜单-套餐
│   │   │   ├── OrderStatus.vue # 订单详情-下拉菜单-订单状态
│   │   │   ├── OrderStep.vue # 订单详情-下拉菜单-视频比例
│   │   │   ├── OrderTimer.vue # 订单详情-根据秒数倒计时
│   │   │   ├── OrderTitle.vue # 订单详情-流程图标题
│   │   │   └── SetMeal.vue # 套餐
│   │   └── other # 其他
│   │       ├── AttachDownload.vue # 附件下载相关
│   │       ├── SelectAuthor.vue # 选择创意者
│   │       └── VideoCover.vue # 自动绘制视频封面
│   ├── config  # 配置相关
│   │   ├── config.js # 全局配置包括登录页地址、上次文件、上次视频地址
│   │   ├── dict.js # 字典配置
│   │   ├── menu.js # 全局 vue router 和登录后的左侧菜单统一设置
│   │   └── rules.js # 全局表单校验相关规则配置
│   ├── filters
│   │   └── index.js # vue 过滤器：包括日期、字典、切割字符串等相关操作
│   ├── main.js # 主入口
│   ├── mixins
│   │   └── source.js # 注入到全局页面，包括字典、全局配置、表单校验规则
│   ├── pages # 所有涉及路由的组件
│   │   ├── admin # 运营角色相关页面
│   │   │   ├── AuditComplaint.vue  # 素材投诉审核
│   │   │   ├── AuditCreativity.vue # 创意（订单）审核
│   │   │   ├── AuditCreator.vue  # 创意者审核
│   │   │   ├── BdOrderDetail.vue # 创意者的订单详情
│   │   │   ├── ComplaintDetail.vue # 素材投诉详情
│   │   │   ├── CreativityDetail.vue  # 订单详情
│   │   │   ├── CreatorDetail.vue # 创意者（审核）详情
│   │   │   ├── OrderGrabList.vue # 已抢订单列表
│   │   │   ├── OrderInvalidList.vue # 失效订单
│   │   │   ├── OrderNoGrabList.vue # 未抢订单
│   │   │   ├── ReportAd.vue # 广告主报表列表
│   │   │   ├── ReportCreator.vue # 创意者报表列表
│   │   │   ├── ReportCustomer.vue # 
│   │   │   ├── ReportDetail.vue # 广告主和创意者报表详情
│   │   │   ├── ReportPlatform.vue # 平台报表列表
│   │   │   ├── ReportPlatformDetail.vue # 平台报表详情
│   │   │   ├── ToolAdPay.vue # 广告主比例比例
│   │   │   ├── ToolCreator.vue # 创意者口
│   │   │   └── ToolSetmealMgr.vue # 套餐管理
│   │   ├── creator # 创意者订单相关
│   │   │   ├── CreateorOrderDetail.vue # 创意者订单详情入口
│   │   │   ├── CreatorNoHandOrderList.vue # 创意者未接订单列表
│   │   │   ├── CreatorOrderList.vue  # 创意者订单列表
│   │   │   └── CreatorOwnerOrderList.vue # 创意者专属订单列表
│   │   ├── finance # 广告主和创意者财务管理
│   │   │   ├── FinanceDetail.vue # 财务详情
│   │   │   └── FinanceList.vue # 财务列表
│   │   ├── index.js  # page 所有的 components 都需要在 index.js 导出
│   │   ├── message # 消息列表
│   │   │   └── list.vue
│   │   ├── order # 广告主订单相关
│   │   │   ├── OrderDetail.vue # 广告主订单详情
│   │   │   ├── OrderEdit.vue # 广告主发布需求和编辑需求
│   │   │   ├── OrderList.vue # 广告主需求列表
│   │   │   └── OrderPersonCenter.vue # 无用可删掉
│   │   ├── personal  # 个人中心
│   │   │   └── PersonalCenter.vue  # 个人中心
│   │   └── public  # 广告主、创意者公共页面的文件夹
│   │       ├── ComplaintAdd.vue # 素材投诉的新增
│   │       ├── ComplaintList.vue # 素材投诉的列表
│   │       ├── PageBiu.vue # 穿云箭的平台传送到我们自己的测试平台的页面
│   │       ├── PageHelp.vue  # 帮助中心
│   │       ├── PageRegister.vue  # 注册页面
│   │       └── template  # 帮助中心的问答
│   │           ├── question.vue
│   │           └── standard.vue
│   ├── plugins # 引用 elementUI
│   │   └── element.js
│   ├── router # 路由配置
│   │   └── index.js
│   ├── store # vuex 
│   │   ├── actions.js
│   │   ├── getter.js
│   │   ├── index.js
│   │   ├── mutations.js
│   │   └── state.js
│   └── tools # 工具
│       ├── common.js # 公共 JS 
│       ├── http.js # 基于 axios 的封装
│       └── validator.js  # 表单字段验证器
└── vue.config.js # 配置代理，cookie 相关

```

## 注意事项

### 1. 项目启动是需要从线上环境获取 cookie 
> 由于开发用到线上的接口 `qa-cmc.synative.cn`，这个接口有相关的鉴权逻辑，所以要获取同账户的 `cookie`,然后修改 `vue.config.js` 中的代理配置的信息。切记：获取线上的 cookie 的域名一定要和代理的域名保持一直。

### 2. 加载流程（示例）
1. 浏览器访问调用链接 `http://qa-cmc.synative.cn/backend/public/index.php/login?token=24045757-acfc-4f84-a979-fac1f76a34e1&expires_in=9999999`,（token 是穿云箭跳转到我们系统必带参数）进行后端登录
2. 后端根据 `token` 从穿云箭拿到用户信息和角色信息后重定向到 `http://qa-cmc.synative.cn/dist/?token=24045757-acfc-4f84-a979-fac1f76a34e1`（前端页面）
3. 前端初始化进入 app.vue 执行逻辑
    * 保存 token 到 vuex 中
    * 调用接口 `/baseinfo` 查询用户信息
    * 根据不同角色初始化不同的页面路由（请阅读 menu.js 配置）
    * 进入该角色配置路由的默认页面
### menu.js 功能
1. vue router 、页面菜单、角色级别权限控制集一身的配置
2. 属性 `component` 的值源于 `pages/index.js`的组件

### 如何登录测试环境
> 执行一下步骤的前提是，正式环境和测试环境有相同的账户。

1. 登录正式环境然后进入创意市场，比如登录后：`http://drama.tyrise.com/dist/?#/app/creator/order/list`
2. 修改 url 中 `#` 后面的路由：`http://drama.tyrise.com/dist/?#/biu`
3. 点击图片会自动调整到测试环境
