## 圆角内凹
```
background: radial-gradient(circle at bottom right, #FFFFFF 0, #FFFFFF 0) bottom right

例子：（上下两部分，中间有虚线和内凹圆角）
<!--index.wxml-->
<view class="container">
 <view class="top"></view>
 <view class="bottom"></view>
</view>
<!--index.wxss-->
.container{
  background: skyblue;
}
.top{
  height: 205rpx;
  width: 100%;
  background-color: skyblue;
  background: radial-gradient(circle at bottom right, transparent 15rpx, #FFFFFF 0) bottom right,
    radial-gradient(circle at bottom left, transparent 15rpx, #FFFFFF 0) bottom left,
    radial-gradient(circle at top left, #FFFFFF 15rpx, #FFFFFF 0) top left,
    radial-gradient(circle at top right, #FFFFFF 15rpx, #FFFFFF 0) top right;
  background-size: 54% 54%;
  background-repeat: no-repeat;
  position: relative;
}
.top::after{
  position: absolute;
  content: '';
  width: 676rpx;
  height:0rpx; 
  background-color: skyblue;
  border: 1rpx dashed #B7BBC0;
  left: 22rpx;
  z-index: 1;
  bottom: 0;
}
.bottom{
  display: flex;
  align-items: center;
  width: 100%;
  height: 206rpx;
  background-color: skyblue;
  position: relative;
  background: radial-gradient(circle at bottom right, #FFFFFF 0, #FFFFFF 0) bottom right,
    radial-gradient(circle at bottom left, #FFFFFF 0, #FFFFFF 0) bottom left,
    radial-gradient(circle at top left, transparent 15rpx, #FFFFFF 0) top left,
    radial-gradient(circle at top right, transparent 15rpx, #FFFFFF 0) top right;
  background-size: 60% 60%;
  background-repeat: no-repeat;
}
```