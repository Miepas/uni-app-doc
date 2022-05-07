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
      timer = setTimeout(() => {
        timer = null;
        if (isLogin && !uni.getStorageSync("token")) {
          uni.$u.route("pages/login/login");
        } else {
          uni.$u.route(url);
        }
      }, delay);
    }
## main.js引入
    //引入router.js文件
    import { toPath } from '@/config/router.js'

    //引入全局方法
    Vue.prototype.$testTo = toPath
