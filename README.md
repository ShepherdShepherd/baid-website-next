# BAID Website @ Next

## 项目结构

- `src` - 源码

  - `assets` - 页面内使用的素材，会被随机重命名
    - `styles` - 全局样式
      - `desktop.css`
      - `mobile.css`
    - `fonts` - 字体
    - `images` - 图片，只在一个页面中用到的图片请放入文件夹内
    - `videos` - 视频，命名方式与图片类似

  - `components` - 全部**非页面组件**放到这里，命名一律为**多词 CamelCase**

    如果是仅限于某个 view 内使用的组件，请将其放在一个文件夹内，文件夹名称类似 `DesktopAboutUs`

  - `layouts` - 基础布局

    - `DesktopLayout.vue` - 桌面端的默认布局
    - `MobileLayout.vue` - 移动端的默认布局

  - `views` - 全部**页面组件**，每个页面都需要有桌面端的和移动端的，两个组件名称需**相同**
    - `desktop` - 桌面端页面组件
    - `mobile` - 移动端页面组件

  - `main.js` - 入口
  - `App.vue` - 根组件
  - `messages.json` - 全部字符串+翻译
  - `router.js` - SPA 路由部分
  - `i18n.js` - 国际化部分

## 开发时可能要用到的命令

注意，目前`pnpm`已经不再推荐，请使用`yarn`或`npm`。

- `yarn` - 安装依赖
- `yarn dev` - 打开开发服务器（Vite）
- `yarn test` - 检查代码有无任何不规范
- `yarn build` - 生成静态构建

## 开发时可能要用到的资料

- UnoCSS 参考：<https://uno.antfu.me/>
- WindiCSS 参考（与 UnoCSS 完全兼容）：<https://windicss.org/>
- Vue3 API 参考：<https://v3.cn.vuejs.org/api/>
- Vue Router API 参考：<https://router.vuejs.org/api/>
- Popmotion 参考：<https://popmotion.io/>
- Vue motion 参考：<https://motion.vueuse.org/introduction.html>

## 推荐启用的 VSCode 拓展

- Volar (不要使用 Vetur)
- Prettier ESLint (已配置开箱即用)
- UnoCSS
