# scss公共样式
## App.vue引入
    @import "@/index.scss";
## index.scss
    .main-color {
        color: $main-color;
    } //主背景色
    .main-font-color {
        color: $main-font-color;
    } //找回密码颜色
    .main-ff75 {
        color: $main-ff75;
    } //辅助色
    .main-6666 {
        color: $main-6666;
    } //辅助色
    .main-9999 {
        color: $main-9999;
    } //辅助色
    .main-cccc {
        color: $main-cccc;
    } //辅助色
    .main-tpis {
        color: $main-tpis;
    } //辅助色
    .main-f3f3 {
        color: $main-f3f3;
    } 
    .color-ffff{
        color: #ffffff;
    }
    .min-h{
        min-height: 100%;
    }
    /* 定义字体(rpx)单位 */
    @for $i from 0 through 80 {
        .font-#{$i} {
            font-size: $i +2+ rpx;
        }
    }   
    /* flex 横向 */
    .flex {
        /* #ifndef APP-NVUE */
        display: flex;
        /* #endif */
        flex-direction: row;
        align-items: center;
    }
    /* flex 纵向 */
    .flex-col {
        /* #ifndef APP-NVUE */
        display: flex;
        /* #endif */
        flex-direction: column;
    }
    /* flex不换行 */
    .flex-wrap {
        flex-wrap: wrap;
    }
    /* 垂直居中 */
    .flex-nowrap {
        flex-wrap: nowrap;
    }   
    /* 垂直居中 */
    .col-center {
        align-items: center;
    }   
    /* 顶部对齐 */
    .col-top {
        align-items: flex-start;
    }   
    /* 底部对齐 */
    .col-bottom {
        align-items: flex-end;
    }   
    /* 左边对齐 */
    .row-left {
        justify-content: flex-start;
    }   
    /* 水平居中 */
    .row-center {
        justify-content: center;
    }   
    /* 右边对齐 */
    .row-right {
        justify-content: flex-end;
    }   
    /* 水平两端对齐，项目之间的间隔都相等 */
    .row-between {
        justify-content: space-between;
    }   
    /* 水平每个项目两侧的间隔相等，所以项目之间的间隔比项目与父元素两边的间隔大 倍 */
    .row-around {
        justify-content: space-around;
    }   
    /* 文字左对齐 */
    .text-left {
        text-align: left;
    }   
    /* 文字居中对齐 */
    .text-center {
        text-align: center;
    }   
    /* 文字右对齐 */
    .text-right {
        text-align: right;
    }   
    /* 定义flex等分 */
    @for $i from 0 through 12 {
        .flex-#{$i} {
            flex: $i;
        }
    }   
    // 定义内外边距，历遍1-200
    @for $i from 0 through 200 {
        // 得出：u-margin-30或者u-m-30
        .margin-#{$i},
        .m-#{$i} {
            margin: $i + rpx !important;
        }   
        // 得出：u-padding-30或者u-p-30
        .padding-#{$i},
        .p-#{$i} {
            padding: $i + rpx !important;
        }   
        @each $short, $long in l left, t top, r right, b bottom {
            // 缩写版，结果如： u-m-l-30
            // 定义外边距
            .m-#{$short}-#{$i} {
                margin-#{$long}: $i + rpx !important;
            }   
            // 定义内边距
            .p-#{$short}-#{$i} {
                padding-#{$long}: $i + rpx !important;
            }   
            // 完整版，结果如：u-margin-left-30
            // 定义外边距
            .margin-#{$long}-#{$i} {
                margin-#{$long}: $i + rpx !important;
            }   
            // 定义内边距
            .padding-#{$long}-#{$i} {
                padding-#{$long}: $i + rpx !important;
            }
        }
    }
    // 相对定位
    .relative {
        position: relative;
    }
    // 绝对定位
    .absolute {
        position: absolute;
    }
    .fixed {
        position: fixed;
    }
    // 绝对定位边距
    @for $i from 0 through 200 {
        .left-#{$i} {
            left: $i + rpx !important;
        }   
        .top-#{$i} {
            top: $i + rpx !important;
        }   
        .right-#{$i} {
            right: $i + rpx !important;
        }   
        .bottom-#{$i} {
            bottom: $i + rpx !important;
        }
    }
    // 行高
    @for $i from 0 through 200 {
        .l-height-#{$i} {
            line-height: $i + rpx !important;
        }
    }   
    .h {
        height: 100%;
    }
    .vh {
        height: 100vh;
    }
    .w {
        width: 100%;
    }
    .bgw {
        background-color: #ffffff;
    }
    //边框
    .border {
        border: 1px solid #000000;
    }
    .border-r {
        border-radius: 99999px;
    }
    .border-r-16 {
        border-radius: 20rpx;
    }
    .font-color {
        color: $main-font-color !important;
    }
    .font-bold{
        font-weight: bold;
    }
    //吸顶
    .sticky{
        position: sticky;
        top: 0;
        z-index: 99;
    }
    // 按钮
    .button {
        background-color: $main-color;
        color: #ffffff;
        font-size: 26rpx;
        padding: 4rpx;
    }
    .u-page {
        &__code-text {
            color: $main-color;
            font-size: 28rpx;
        }
    }
    /*需给父元素设置height:100%*/
    .page-warp {
        height: 100%;
        display: flex;
        flex-direction: column;
    }
    /* 下 */
    .center-warp {
        flex: 1;
        min-width: 0;
        min-height: 0; /* 需给flex:1的元素加上最小高,否则内容超过会溢出容器 (如:小程    序Android真机) */
    
    }
