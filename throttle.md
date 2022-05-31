# 点击防抖
## throttle.js
    let flag;
    /**
     * 在一定时间内，只能触发一次
     * @param {Object} parame 传参
     * @return null
     */
    function throttle(func,parame) {
      if (!flag) {
       flag = true;
       typeof func === 'function' && func(parame);
       setTimeout(() => {
        flag = false;
       }, 600);//每600毫秒执行一次
      }

    }
    export default throttle
## main.js引入
    //引入throttle.js文件
    import throttle from "@/config/throttle.js";

    //引入全局方法
    Vue.prototype.$throttle = throttle;
## 使用方法
    //html使用
    @click="$throttle(function, parame)"
    
    //js使用
    this.$throttle(function, parame)
