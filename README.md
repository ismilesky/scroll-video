# scroll-video
 微信小程序视频上下滑动播放方案

### 视频滑动播放的两种方案：

1.  Swiper + Video ，使用Swiper嵌套Video进行视频播放， 小程序v2.4.0 起 Video组件支持同层渲染，大体思路是 保证一个视频组件, 记录Swiper的 current，
      并且对 swiper-item的下标做比对，来对比当前index和current是否一致，
      一致则展示Video组件。
      - 滑动效果比较好，还有优化的，怎么预加载， 怎么放置3个Video组件进行预加载的问题。
  
2.   平移动画，模拟上下滚动的效果。大体思路是固定一个视频组件,  把封面图平铺在视频组件上，根据手势滑动的范围，确定上滑或者下滑，通过改变translateY，切换视频源播放。   
       - 滑动效果不是很好，无法做到手指跟随。
   
### Vide组件加载视频黑屏慢的可能解决方案

video组件在播放视频的时候会黑屏，或者loading时间长，这有几种方案仅供参考，排除网络问题。

- 视频编码格式的问题，将视频转码，需要有转码平台,可能需要付费，阿里云或者腾讯云都有
- OSS + CDN , 视频资源放在OSS上存储，不占用服务器带宽，CDN解决了资源加载慢的问题, 如果阿里云CDN出现了卡顿之类的现象， 可以看这篇https://developers.weixin.qq.com/community/develop/doc/0002c2279402f0c1f538a74215b800
- 增加服务器的带宽


### 相关链接参考

https://www.hansuku.com/archives/155

https://developers.weixin.qq.com/community/develop/doc/00086ae98f4a00b0338aa717e5b000?_at=1597887924129

https://developers.weixin.qq.com/community/develop/doc/0002c2279402f0c1f538a74215b800

 
 

