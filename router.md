# uni-app 路由跳转封装
## router.js
    // 路由跳转
    export function toPath(url, isLogin = true) {
      if (!url) {
        return;
      }
      let delay = 500;
      let timer = null;
      if (timer) {
        return;
      }
      if (isLogin && !uni.getStorageSync("token")) {
        uni.$u.route("pages/login/login");
      } else {
        uni.$u.route(url);
      }
      timer = setTimeout(() => {
        timer = null;
      }, delay);
    }
## main.js引入
    //引入router.js文件
    import { toPath } from '@/config/router.js'

    //引入全局方法
    Vue.prototype.$toPath = toPath
## 使用方法
    //html使用
    @click="$toPath('/pages/index/index')"
    
    //js使用
    this.$toPath('/pages/index/index')
