---
title: 模板
date: 2023-07-19 06:32:52
categories:
    - 建站
tags:
---

## 插入多媒体

### 插入视频

{% tabs 插入视频 %}
<!-- tab 插入本地视频 -->
```html
<video src='视频名称' type='video/mp4' controls='controls'  width='100%' height='100%'/>
```
<!-- endtab -->
<!-- tab 插入B站视频 -->
```html
<div style="position: relative; padding: 30% 45%;">
    <iframe 
    style="position: absolute; width: 60%; height: 60%; left: 0; top: 0;" 
    src="url" >
    </iframe>
</div>
```
| key | 说明 |
| --- | --- |
| aid | 视频ID就是B站的 avxxxx 后面的数字 |
| cid | 应该是客户端id, clientId 的缩写(推测的, 不一定准确)经过测试, 这个字段不填也没关系 |
|page|第几个视频, 起始下标为 1 (默认值也是为1)就是B站视频, 选集里的, 第几个视频|
|as_wide|是否宽屏1: 宽屏, 0: 小屏|
|high_quality|是否高清1: 高清, 0: 最低视频质量(默认)如视频有 360p 720p 1080p 三种, 默认或者 high_quality=0 是最低 360p high_quality=1 是最高1080p|
|danmaku|是否开启弹幕1: 开启(默认), 0: 关闭|
|autoplay|是否自动播放|
<!-- endtab -->
{% endtabs %}


