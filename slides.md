---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
monaco: true # 默认为 "dev"
download: true
exportFilename: 'slidev-exported'
routerMode: hash
info: |
  ## 更多关于UniApp的内容
  请访问：[https://xuebin.me](https://lxb.notion.site/uni-app-fe5673cefc2a46dca7c0fb43e2c68f91)

  # 相关链接
  - [UniApp](https://uniapp.dcloud.io)
  - [slidev](https://cn.sli.dev)
  - [UnoCSS](https://uno.antfu.me)
  - [icon](https://icones.js.org)

drawings:
  persist: false
css: unocss
title: uni-app和火山小程序前端实践
---

# uni-app和火山小程序前端实践

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    创新产品组 - 柳学斌
  </span>
</div>

---
layout: section
---
# 背景
---

# Uni-APP

| uni-app 是一个使用 Vue.js 开发所有前端应用的框架，开发者编写一套代码，可发布到iOS、Android、Web（响应式）、以及各种小程序（微信/支付宝/百度/头条/QQ/快手/钉钉/淘宝）、快应用等多个平台。

<!-- ![功能框架图](https://vkceyugu.cdn.bspapp.com/VKCEYUGU-f184e7c3-1912-41b2-b81f-435d1b37c7b4/29448a55-2785-4296-9248-913dbda9de7f.png) -->
<img src="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-f184e7c3-1912-41b2-b81f-435d1b37c7b4/29448a55-2785-4296-9248-913dbda9de7f.png" class="h-90 m-auto rounded shadow" />

---

# 跨端开发框架

- [uni-app](https://github.com/dcloudio/uni-app) 👍
  
  > Vue

- [taro](https://www.npmjs.com/package/@tarojs/taro)
  
  > React


[跨端开发框架深度横评之2020版](https://juejin.cn/post/6844904118901817351)

---

# uni-app 特色

- [easycom](https://uniapp.dcloud.net.cn/collocation/pages?id=easycom) 
  
  > 符合components/组件名称/组件名称.vue目录结构。就可以不用引用、注册，直接在页面中使用。

- [uni_modules](https://uniapp.dcloud.io/plugin/uni_modules.html)

  > 对一组js sdk、组件、页面、uniCloud云函数、公共模块等的封装，用于嵌入到uni-app项目中使用，也支持直接封装为项目模板。

- [条件编译](https://uniapp.dcloud.io/tutorial/platform.html)

  > #ifdef、#ifndef

---
layout: section
---
# 开始
---

# 创建工程

<div grid="~ cols-2 gap-4" m="t-2">
<div>

# HBuilderX

![](/assets/hbuilderx_create_app.png)

</div>
<div>

# Cli

-  Vue2

```ts {1}
npm install -g @vue/cli@4
vue create -p dcloudio/uni-preset-vue my-project
```

- Vue3

```ts {5}
// javascript
npx degit dcloudio/uni-preset-vue#vite my-vue3-project

// typescript
npx degit dcloudio/uni-preset-vue#vite-ts my-vue3-project
```

</div>
</div>

---

# HBuilderX 工程目录

> https://uniapp.dcloud.io/tutorial/project.html#%E7%9B%AE%E5%BD%95%E7%BB%93%E6%9E%84


```ts {16-20|7-11|2,3-4}
┌─uniCloud              云空间目录，阿里云为uniCloud-aliyun,腾讯云为uniCloud-tcb（详见uniCloud）
├─uni_modules           存放[uni_module](/uni_modules)。
│─components            符合vue组件规范的uni-app组件目录
│  └─comp-a.vue         可复用的a组件
├─hybrid                App端存放本地html文件的目录，详见
├─platforms             存放各平台专用页面的目录，详见
├─pages                 业务页面文件存放的目录
│  ├─index
│  │  └─index.vue       index页面
│  └─list
│     └─list.vue        list页面
├─static                存放应用引用的本地静态资源（如图片、视频等）的目录，注意：静态资源只能存放于此
├─wxcomponents          存放小程序组件的目录，详见
├─nativeplugins         App原生插件 详见
├─unpackage             非工程代码，一般存放运行或发行的编译结果
├─main.js               Vue初始化入口文件
├─App.vue               应用配置，用来配置App全局样式以及监听 应用生命周期
├─manifest.json         配置应用名称、appid、logo、版本等打包信息，详见
├─pages.json            配置页面路由、导航条、选项卡等页面类信息，详见
└─uni.scss              这里是uni-app内置的常用样式变量 
```

---

# HBuilderX 运行前准备 - 配置开发工具路径

![](/assets/hbuilderx_config.png)

<arrow x1="105" y1="215" x2="180" y2="400" color="#f00" width="5" arrowSize="1" />

---

# 启动项目

![](/assets/hbuilderx_run.png)

---

# 小程序模拟器配置

<img src="/assets/weixin_devtools.png" h="100%">

<arrow x1="565" y1="135" x2="530" y2="380" color="#f00" width="5" arrowSize="1" />

---

# 火山小程序模拟器

> 和字节小程序客户端不是一个，不要走错了~

<div class="py-4">
  <a href="https://www.volcengine.com/docs/6505/92634" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    火山小程序开发者工具下载地址 <carbon:arrow-right class="inline"/>
  </a>
</div>

<img src="/assets/mars_login.png" h="100%" />

<arrow x1="900" y1="50" x2="690" y2="200" color="#f00" width="5" arrowSize="1" />

---

# 各小程序 request 网络请求的 Referer

- [微信开放文档 (qq.com)](https://developers.weixin.qq.com/miniprogram/dev/framework/ability/network.html#%E4%BD%BF%E7%94%A8%E9%99%90%E5%88%B6)
    
    > https://servicewechat.com/{appid}/{version}/page-frame.html

- [支付宝文档中心 (alipay.com)](https://opendocs.alipay.com/mini/api/owycmh#referer%20%E8%AF%B4%E6%98%8E)
    
    > https://{appid}.hybrid.alipay-eco.com/{appid}/{version}/index.html#pages/index

- [字节小程序 (bytedance.com)](https://microapp.bytedance.com/docs/zh-CN/mini-app/develop/api/network/http/tt-request/#header-%E8%AF%B4%E6%98%8E)
    
    > https://tmaservice.developer.toutiao.com/?appid=madab9772ccfc01a73&version=1.0.0

    > /?appid=madab9772ccfc01a73&version=1.0.0

---
layout: section
---
# 折腾
---

# 我的工程目录

<div grid="~ cols-3 gap-4">
<div>

![](/assets/mp-inno-uni-zhuan-1.png)

</div>
<div>

![](/assets/mp-inno-uni-zhuan-2.png)

</div>
<div>

> git submodule 引入 HBuilderX 工程


![](/assets/mp-inno-uni-zhuan-3.png)

<arrow x1="650" y1="400" x2="305" y2="325" color="#f00" width="5" arrowSize="1" />

</div>
</div>

---

# cli scripts

> https://gitlab.dev.zhaopin.com/innovation/mp-innovation-uni/-/blob/master/package.json

```jsonc {all|4-5}
{
  //...
  "scripts": {
    "serve": "cross-env NODE_ENV=development node_modules/.bin/zx script/dev.mjs",
    "build": "cross-env NODE_ENV=production node_modules/.bin/zx script/build.mjs",
    "------------------------------------------------------------------------------------------------------------------------------------------------------------": "",
    "build:app-plus": "cross-env NODE_ENV=production UNI_PLATFORM=app-plus vue-cli-service uni-build",
    "build:custom": "cross-env NODE_ENV=production uniapp-cli custom",
    "build:h5": "cross-env NODE_ENV=production UNI_PLATFORM=h5 vue-cli-service uni-build",
    "build:mp-360": "cross-env NODE_ENV=production UNI_PLATFORM=mp-360 vue-cli-service uni-build",
    "build:mp-alipay": "cross-env NODE_ENV=production UNI_PLATFORM=mp-alipay vue-cli-service uni-build",
    "build:mp-baidu": "cross-env NODE_ENV=production UNI_PLATFORM=mp-baidu vue-cli-service uni-build",
    "build:mp-jd": "cross-env NODE_ENV=production UNI_PLATFORM=mp-jd vue-cli-service uni-build",
    "build:mp-kuaishou": "cross-env NODE_ENV=production UNI_PLATFORM=mp-kuaishou vue-cli-service uni-build",
    "build:mp-lark": "cross-env NODE_ENV=production UNI_PLATFORM=mp-lark vue-cli-service uni-build",
    "build:mp-qq": "cross-env NODE_ENV=production UNI_PLATFORM=mp-qq vue-cli-service uni-build",
    "build:mp-toutiao": "cross-env NODE_ENV=production UNI_PLATFORM=mp-toutiao vue-cli-service uni-build",
    "build:mp-weixin": "cross-env NODE_ENV=production UNI_PLATFORM=mp-weixin vue-cli-service uni-build",
    "build:mp-xhs": "cross-env NODE_ENV=production UNI_PLATFORM=mp-xhs vue-cli-service uni-build",
    "build:quickapp-native": "cross-env NODE_ENV=production UNI_PLATFORM=quickapp-native vue-cli-service uni-build",
    "build:quickapp-webview": "cross-env NODE_ENV=production UNI_PLATFORM=quickapp-webview vue-cli-service uni-build",
    "build:quickapp-webview-huawei": "cross-env NODE_ENV=production UNI_PLATFORM=quickapp-webview-huawei vue-cli-service uni-build",
    "build:quickapp-webview-union": "cross-env NODE_ENV=production UNI_PLATFORM=quickapp-webview-union vue-cli-service uni-build",
    "dev:app-plus": "cross-env NODE_ENV=development UNI_PLATFORM=app-plus vue-cli-service uni-build --watch",
    "dev:custom": "cross-env NODE_ENV=development uniapp-cli custom",
    "dev:h5": "cross-env NODE_ENV=development UNI_PLATFORM=h5 vue-cli-service uni-serve",
    "dev:mp-360": "cross-env NODE_ENV=development UNI_PLATFORM=mp-360 vue-cli-service uni-build --watch",
    "dev:mp-alipay": "cross-env NODE_ENV=development UNI_PLATFORM=mp-alipay vue-cli-service uni-build --watch",
    "dev:mp-baidu": "cross-env NODE_ENV=development UNI_PLATFORM=mp-baidu vue-cli-service uni-build --watch",
    "dev:mp-jd": "cross-env NODE_ENV=development UNI_PLATFORM=mp-jd vue-cli-service uni-build --watch",
    "dev:mp-kuaishou": "cross-env NODE_ENV=development UNI_PLATFORM=mp-kuaishou vue-cli-service uni-build --watch",
    "dev:mp-lark": "cross-env NODE_ENV=development UNI_PLATFORM=mp-lark vue-cli-service uni-build --watch",
    "dev:mp-qq": "cross-env NODE_ENV=development UNI_PLATFORM=mp-qq vue-cli-service uni-build --watch",
    "dev:mp-toutiao": "cross-env NODE_ENV=development UNI_PLATFORM=mp-toutiao vue-cli-service uni-build --watch",
    "dev:mp-weixin": "cross-env NODE_ENV=development UNI_PLATFORM=mp-weixin vue-cli-service uni-build --watch",
    "dev:mp-xhs": "cross-env NODE_ENV=development UNI_PLATFORM=mp-xhs vue-cli-service uni-build --watch",
    "dev:quickapp-native": "cross-env NODE_ENV=development UNI_PLATFORM=quickapp-native vue-cli-service uni-build --watch",
    "dev:quickapp-webview": "cross-env NODE_ENV=development UNI_PLATFORM=quickapp-webview vue-cli-service uni-build --watch",
    "dev:quickapp-webview-huawei": "cross-env NODE_ENV=development UNI_PLATFORM=quickapp-webview-huawei vue-cli-service uni-build --watch",
    "dev:quickapp-webview-union": "cross-env NODE_ENV=development UNI_PLATFORM=quickapp-webview-union vue-cli-service uni-build --watch",
    "info": "node node_modules/@dcloudio/vue-cli-plugin-uni/commands/info.js",
    "serve:quickapp-native": "node node_modules/@dcloudio/uni-quickapp-native/bin/serve.js",
    "test:android": "cross-env UNI_PLATFORM=app-plus UNI_OS_NAME=android jest -i",
    "test:h5": "cross-env UNI_PLATFORM=h5 jest -i",
    "test:ios": "cross-env UNI_PLATFORM=app-plus UNI_OS_NAME=ios jest -i",
    "test:mp-baidu": "cross-env UNI_PLATFORM=mp-baidu jest -i",
    "test:mp-weixin": "cross-env UNI_PLATFORM=mp-weixin jest -i",
  },
  //...
}
```

---

# 自定义运行 - 获取各端小程序的命令行工具

> https://gitlab.dev.zhaopin.com/innovation/mp-innovation-uni/-/tree/master/script

<!-- {monaco} {height:'calc(100% - 30px)'} -->
```ts {all|3,6|9,12,15}
export const cli = {
  /** [HBuilderX cli命令行工具](https://hx.dcloud.net.cn/cli/README) */
  hb: `/Applications/HBuilderX.app/Contents/MacOS/cli`,
  
  /** [Weixin cli命令行工具](https://developers.weixin.qq.com/miniprogram/dev/devtools/cli.html) */
  weixin: `/Applications/wechatwebdevtools.app/Contents/MacOS/cli`,
  
  /** [Weixin ci工具](https://developers.weixin.qq.com/miniprogram/dev/devtools/ci.html) */
  'weixin-ci': `node_modules/.bin/miniprogram-ci`,
  
  /** [Alipay cli命令行工具](https://opendocs.alipay.com/mini/02q17h) */
  alipay: `node_modules/.bin/minidev`,
  
  /** [Mars火山小程序 cli命令行工具](https://www.volcengine.com/docs/6505/116886) */
  toutiao: `node_modules/.bin/mars-mp`,
}
```

---

# 自定义运行命令 - 编写运行IDE命令

> https://gitlab.dev.zhaopin.com/innovation/mp-innovation-uni/-/tree/master/script

```ts
#! /usr/bin/env zx

import { cli } from 'config.mjs'

const dist = (mp) => path.join(__dirname, `../../dist/dev/mp-${mp}`)

export const open = {
  weixin: () => $`${cli.weixin} open --project ${dist('weixin')}`,
  alipay: () => $`${cli.alipay} ide --project ${dist('alipay')}`,
  toutiao: () => $`${cli.toutiao} open ${dist('toutiao')}`,
}
```

---

# 自定义运行命令 - 编写获取预览二维码命令
> https://gitlab.dev.zhaopin.com/innovation/mp-innovation-uni/-/tree/master/script

```ts
#! /usr/bin/env zx

import { cli } from 'config.mjs'

const dist = (mp) => path.join(__dirname, `../../dist/dev/mp-${mp}`)

export const preview = {
  weixin: async () => $`${cli.weixin} preview --project ${dist('weixin')}`.nothrow(),
  alipay: async () => {
    if(await fs.readJson(`${os.homedir()}/.minidev/config.json`)?.alipay?.authentication){
      await within(() => $`${cli.alipay} login`)
    }
    return await $`${cli.alipay} preview --project ${dist('alipay')} --app-id ${appid.alipay}`.nothrow()
  },
  toutiao: async () => {
    await $`${cli.toutiao} login-d ${toutiao.ak} ${toutiao.sk}`.quiet()
    return await $`${cli.toutiao} preview ${dist('toutiao')} -s`.nothrow()
  },
}
```

---

# 自定义运行命令

> https://gitlab.dev.zhaopin.com/innovation/mp-innovation-uni/-/tree/master/script

```ts
#! /usr/bin/env zx

import { cli } from 'config.mjs'

const dist = (mp) => path.join(__dirname, `../../dist/dev/mp-${mp}`)

let result = []
Object.keys(open).forEach(async (mp) => {
  const p = $`npm run dev:mp-${mp}`.nothrow()
  for await (const chunk of p.stdout) {
    if (`${chunk}`.includes('complete')) {
        result.push(mp)
        if (result.length % runMps.length === 0) {
          if (result.length < runMps.length + 1) {
            await openIde()
          }
          await getPreviewCode()
        }
      }
  }
})
```

---
layout: section
---
# 优化
---

# VSCode 开发体验优化

<div grid="~ cols-3 gap-4">
<div>

## Vue 相关
- [volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar)
- [vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur)
- [vue-vscode-snippets](https://marketplace.visualstudio.com/items?itemName=sdras.vue-vscode-snippets)

</div><div>

## 代码美化
- [vscode-eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [prettier-vscode](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [vscode-scss](https://marketplace.visualstudio.com/items?itemName=mrmlnc.vscode-scss)

</div><div>

## uni-app 代码提示
- [bond.better-comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments)
- [create-uniapp-view](https://marketplace.visualstudio.com/items?itemName=mrmaoddxxaa.create-uniapp-view)
- [vscode-uni-helper](https://marketplace.visualstudio.com/items?itemName=ModyQyW.vscode-uni-helper)

</div>
</div>

---

# VScode 插件推荐

> .vscode/extensions.json

```json
{
  "recommendations": [
    "Vue.volar",
    "octref.vetur",
    "sdras.vue-vscode-snippets",

    "dbaeumer.vscode-eslint",
    "esbenp.prettier-vscode",
    "mrmlnc.vscode-scss",

    "aaron-bond.better-comments",
    "mrmaoddxxaa.create-uniapp-view",
    "modyqyw.vscode-uni-helper",
  ]
}
```

---

# 更全面的 uni-app 语法提示

- 补充d.ts

    ```shell
    npm i @types/uni-app @types/html5plus -D
    ```

- 安装组件语法提示

    ```shell
    npm i @dcloudio/uni-helper-json
    ```

- 导入 HBuilderX 自带的代码块

    > 从 github 下载 uni-app 代码块，放到项目目录下的 .vscode 目录即可拥有和 HBuilderX 一样的代码块。

    ```shell
    rm -rf .vscode/uni-snippets
    git clone https://github.com/zhetengbiji/uniapp-snippets-vscode.git .vscode/uni-snippets
    mv .vscode/uni-snippets/* .vscode
    rm -rf .vscode/uni-snippets .vscode/.git
    ```

---
layout: section
---
# 建议
---

# UI 组件库

<div class="py-4">
  <a href="https://www.volcengine.com/docs/6505/92634" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    官方《关于uni-app的ui库、ui框架、ui组件》建议 <carbon:arrow-right class="inline"/>
  </a>
</div>

UI 推荐
- [uView](https://github.com/umicro/uView2.0) - <span c="#f00">仅支持Vue2</span>
- [uni-ui](https://github.com/dcloudio/uni-ui)
- [FirstUI](https://github.com/FirstUI/FirstUI)
- [tm-vuetify](https://tmui.design/)
- [ThorUI组件库](https://ext.dcloud.net.cn/plugin?id=556)

> 插件市场：[https://ext.dcloud.net.cn/](https://ext.dcloud.net.cn/)

---

# 流畅滚动

- Page
- [mescroll](https://www.mescroll.com/)

---

# 组件划分

<div grid="~ cols-2 gap-4">
<div>

小程序

- 数据交互区域封装成组件

- 避免组件层级过深

</div><div>

H5 / UniApp

</div>
</div>

---

# 静态资源

<div grid="~ cols-2 gap-4">
<div>

local

</div><div>

remote

</div>
</div>

---

# 数据使用

- 双向data数据 / freeze冻结数据 / globalData / Storage
- 分批加载

---
layout: section
---

# 提前规划分包

<div display="flex" justify="center">
<div my="auto" text="left">

* subPackages 开启分包优化
* preloadRule 配置分包预加载

</div>
</div>


---

# 配置全局分享

<div grid="~ cols-2 gap-4">
<div>

支付宝

> main.js

```tsx {all|3,9}
import globalShare from 'helper/globalShare.js'

const OriginPage = Page
Page = function (pageConfig) {
  const onShow = pageConfig['onShow']
  pageConfig['onShow'] = function (...args) {
    globalShare()
    if(typeof onShow === 'function'){
      return onShow.apply(this, args)
    }
  }
  OriginPage(pageConfig)
}
```

</div><div>

微信

> App.vue

```tsx {all|5-7}
<script>
import globalShare from 'helper/globalShare.js'
export default {
  onLaunch() {
    // #ifdef MP-WEIXIN
    wx.onAppRoute(() => globalShare())
    // #endif
  },
  onShareAppMessage() {
    const pages = getCurrentPages() || []
    const page = pages[pages.length - 1] //获取当前页面的对象
    return {
      title: '智联赚赚',
      path: page?.$page?.fullPath,
    }
  },
}
</script>
```

</div>
</div>
---

```tsx {all|18-20}
import _ from 'lodash'

export default function() {
  try {
    const pages = getCurrentPages() || [] //获取加载的页面
    const page = pages[pages.length - 1] //获取当前页面的对象
    if (page) {
      const options = {
        title: '智联赚赚',
        path: (page.$page || {}).fullPath || [
          page.route,
          _.reduce(page.options || {}, (result, value, key) => ([...result, `${key}=${value}`]), []).join('&')
        ].join('?')
      }
      console.log(`%c[路由发生变化] → ${options.path}`, 'background-color: #5ba7da', page)
      const data = page.data || {} // 若想给个别页面做特殊处理 可以给特殊页面加isOverShare为true 就不会重写了
      if (!data.isOverShare) {
        page.onShareAppMessage = () => (options)
        page.onShareTimeline = () => (options)
        uni.showShareMenu(options)
      }
    }
  } catch (e) {
    console.error('[globalShare] ->', e)
  }
}
```

---
layout: section
---

# CSS优化

推荐集成 [tailwindcss](https://tailwindcss.com/)，减少重复css

---
layout: section
---

# 你可能不需要 es6 转 es5

上传小程序时，如果使用了 es6 转 es5 、css 对齐的功能，可能会增大代码体积

---
layout: section
---

# 避免滥用外部js插件

有官方API的就不要额外引用js插件增加项目体积，必要的轮子该造还是要造

---
layout: section
download: true
---

<!-- 创新产品组 - 柳学斌 -->

<div class="pt-12">
  <a href="https://lxb.notion.site/uni-app-fe5673cefc2a46dca7c0fb43e2c68f91" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    lxb.notion.site <carbon:arrow-right class="inline"/>
  </a>
</div>


<div class="pt-12">
  <a href="https://gitlab.dev.zhaopin.com/innovation/mp-innovation-uni/" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    GitLab: mp-innovation-uni <carbon:arrow-right class="inline"/>
  </a>
</div>
