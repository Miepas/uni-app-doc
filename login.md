## uni-app 微信登录方法
    // 登录
    async login() {
      const code = await this.code();
      const that = this;
      uni.showModal({
        title: '提示',
        content: '授权微信登录后才能正常使用小程序功能',
        success(res) {
          // 如果用户点击了确定按钮
          if (res.confirm) {
            uni.getUserProfile({
              desc: '获取你的昵称、头像',
              success: (rest) => {
                uni.$u.http
                  .post('/login', {
                    login_code: code,
                    nickname: rest.userInfo.nickName,
                    avatar: rest.userInfo.avatarUrl,
                  })
                  .then((ress) => {
                    uni.setStorageSync('access_token', `Bearer ${ressdata.access_token}`);
                    that.$store.commit('setUserInfo');
                  });
              },
              fail: () => {
                // 拒绝授权
                that.$u.toast('您拒绝了请求,不能正常使用小程序');
              },
            });
          } else if (res.cancel) {
            // 如果用户点击了取消按钮
            that.$u.toast('您拒绝了请求,不能正常使用小程序');
          }
        },
      });
    },
    // 获取code
    async code() {
      return new Promise((resolve) => {
        uni.login({
          provider: 'weixin',
          success: (res) => {
            resolve(res.code);
          },
        });
      });
    },
