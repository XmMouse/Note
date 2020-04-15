# vue-router
## 原理
***
```
const NotFound = { template: '<p>Page not found</p>' }
const Home = { template: '<p>home page</p>' }
const About = { template: '<p>about page</p>' }

const routes = {
  '/': Home,
  '/about': About
}

new Vue({
  el: '#app',
  data: {
    currentRoute: window.location.pathname
  },
  computed: {
    ViewComponent () {
      return routes[this.currentRoute] || NotFound
    }
  },
  render (h) { return h(this.ViewComponent) }
})
```
## 第三方路由
- page.js
- Director
- vue-router
## vue-router
### 本质
将组件 (components) 映射到路由 (routes)，然后告诉 Vue Router 在哪里渲染它们。  
遗留了连个问题  
1. 如何映射
2. 如何找到在哪里渲染
### 组成 
router-link 入口  
router-view 出口
3. 优先级- 定义顺序
## API
### 动态路由
#### 核心 path-to-regexp
1. 作用 - 把给定的url表达式解析成带有()的正则表达式
2. 用上面的正则表达式处理路径提取出实际表达式的对应的值
#### 动态路由匹配
1. 我们经常需要把某种模式匹配匹配到的所有路由，全都映射到同个组件
2. 当使用路由参数时，例如从 /user/foo 导航到 /user/bar，原来的组件实例会被复用。因为两个路由都渲染同个组件，比起销毁再创建，复用则显得更加高效。不过，这也意味着组件的生命周期钩子不会再被调用。
```
const User = {
  template: '...',
  watch: {
    '$route' (to, from) {
      // 对路由变化作出响应...
    }
  }
}
```
```
const User = {
  template: '...',
  beforeRouteUpdate (to, from, next) {
    // react to route changes...
    // don't forget to call next()
  }
}
```
### 嵌套路由
```
const router = new VueRouter({
  routes: [
    { path: '/user/:id', component: User,
      children: [
        {
          // 当 /user/:id/profile 匹配成功，
          // UserProfile 会被渲染在 User 的 <router-view> 中
          path: 'profile',
          component: UserProfile
        },
        {
          // 当 /user/:id/posts 匹配成功
          // UserPosts 会被渲染在 User 的 <router-view> 中
          path: 'posts',
          component: UserPosts
        }
      ]
    }
  ]
})
```
### 命名路由
1. router-link
2. router.push
3. routes.push
### 命名视图
1. router-view
### 重定向
> 当用户访问 /a时，URL 将会被替换成 /b，然后匹配路由为 /b
### 别名
> /a 的别名是 /b，意味着，当用户访问 /b 时，URL 会保持为 /b，但是路由匹配则为 /a，就像用户访问 /a 一样
### 路由传参
#### 方式一
使用$route
### 方式二
```
const User = {
  props: ['id'],
  template: '<div>User {{ id }}</div>'
}
const router = new VueRouter({
  routes: [
    { path: '/user/:id', component: User, props: true },

    // 对于包含命名视图的路由，你必须分别为每个命名视图添加 `props` 选项：
    {
      path: '/user/:id',
      components: { default: User, sidebar: Sidebar },
      props: { default: true, sidebar: false }
    }
  ]
})
```
##### props 的值
1. 布尔 route.params写入组件属性
2. Object 原样被写入 
3. () => {return {}}
## 导航守卫
### 全局守卫
1. router.afterEach((to, from)
2. router.beforeEach((to, from, next)
### 路由独享的守卫
```
const router = new VueRouter({
  routes: [
    {
      path: '/foo',
      component: Foo,
      beforeEnter: (to, from, next) => {
        // ...
      }
    }
  ]
})
```
### 组件内的守卫
```
const Foo = {
  template: `...`,
  beforeRouteEnter (to, from, next) {
    // 在渲染该组件的对应路由被 confirm 前调用
    // 不！能！获取组件实例 `this`
    // 因为当守卫执行前，组件实例还没被创建
  },
  beforeRouteUpdate (to, from, next) {
    // 在当前路由改变，但是该组件被复用时调用
    // 举例来说，对于一个带有动态参数的路径 /foo/:id，在 /foo/1 和 /foo/2 之间跳转的时候，
    // 由于会渲染同样的 Foo 组件，因此组件实例会被复用。而这个钩子就会在这个情况下被调用。
    // 可以访问组件实例 `this`
  },
  beforeRouteLeave (to, from, next) {
    // 导航离开该组件的对应路由时调用
    // 可以访问组件实例 `this`
  }
}
```
### 调用顺序
1. 导航被触发。
2. 在失活的组件里调用离开守卫。
3. 调用全局的 beforeEach 守卫。
4. 在重用的组件里调用 beforeRouteUpdate 守卫 (2.2+)。
5. 在路由配置里调用 beforeEnter。
6. 解析异步路由组件。
7. 在被激活的组件里调用 beforeRouteEnter。
8. 调用全局的 beforeResolve 守卫 (2.5+)。
9. 导航被确认。
10. 调用全局的 afterEach 钩子。
11. 触发 DOM 更新。
12. 用创建好的实例调用 beforeRouteEnter 守卫中传给 next 的回调函数。
## 路由元信息
1. 位置 $route.matched
## 过渡动画效果
```
<transition>
  <router-view></router-view>
</transition>
```
### 基于路由变化的动画效果
### 单个的动画效果
## 获取数据
尽量用这个 beforeRouteUpdate
## 滚动行为
```
const router = new VueRouter({
  routes: [...],
  scrollBehavior (to, from, savedPosition) {
    // return 期望滚动到哪个的位置
  }
})
```
## 路由懒加载
1. syntax-dynamic-import - const Foo = () => import('./Foo.vue')
2. resolve => require([URL], resolve)
## 源码分析
```
1. routes -> records
2. records -> route
```