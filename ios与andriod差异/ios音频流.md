ios音频无法自动播放

1. 业务场景

> 参加活动需要自动播放音频

2. 业务问题

> 安卓大部分机型没有问题, ios由于安全策略的限制(个人觉得 流量，用户体验方面的考虑)，无法自动播放音频。

3. 解决方案（api 可以参考微信api）

> 由客户端来播放音频（客户端提供jsapi）

4. 代码

```js
  /**
  主流支持格式 Ogg Vorbis 和 AAC 
  */
  <audio id="audio">
      <source src="sound.AAC" type="audio/mpeg" />
      <source src="sound.ogg" type="audio/ogg" />
      <source src="sound.mp4" type="audio/ogg" />
  </audio>

  var audio = document.getElementById('audio');
  audio.load(); // 部分手机需要load 
  audio.play(); // ios 不会自动播放
```

5. ios h5音频无法自动播放 折中解决方案

> 通过用户的触摸 点击 等用户主动操作来触发视屏播放

```js
  var onClick = function() {
      audio.play(); // audio will load and then play
  };
   
  button.addEventListener('click', onClick, false);
```

6. 不适用的业务场景

> 多段视屏组合播放，摇一摇

7. 注意点

> ios 手机摇动事件（http）

8. http与https协议对音频的影响

>  http协议下 ios音频无法播放（用户手动触发也无法播放）

>  http协议下 手机摇动事件不支持

```js
  window.addEventListener('devicemotion', function(event) {
    // 设备运动
  });

  window.addEventListener("deviceorientation", function(event) {
    // 设备方向
  }, true);
```