# 直播相关


## 接口


### 获取推流url
* 请求URL：

```
http://video001.guduokeji.com/api/live/post_url
```

* 请求方式：GET
* 注意：接口需要带上登录接口返回的token这个参数，后端会进行校验登录态（所有类型都是字符串）。



#####返回示例

```
 {
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
        "uid":10000,//用户id
        "push_ur":"rtmp://24116.livepush.myqcloud.com/live/24116_aec62ff298?bizid=24116&txSecret=65984879e0b0effe5cb5f815b6731bd1&txTime=5B68707F",//推流url
        "expire_time":"2018-11-12 12:00:00",//推流url过期时间，一般为获得url的时间+24小时

    }
}
```

### 获取播放url接口
* 请求URL：

```
http://video001.guduokeji.com/api/live/play_url
```

* 请求方式：POST

* | 参数名 | 必选 | 类型 |说明 |
| :--- | :----: | ----: |----: |
| anchor_id | true | int | 主播id |


#####返回示例


```
 ```
 {
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
        "uid":10000,//用户id
        "anchor_id":10001,//主播id
        "push_ur":{"rtmp://24116.livepush.myqcloud.com/live/24116_aec62ff298?bizid=24116&txSecret=65984879e0b0effe5cb5f815b6731bd1&txTime=5B68707F",
        "http://24116.liveplay.myqcloud.com/live/24116_aec62ff298.flv",
        "http://24116.liveplay.myqcloud.com/live/24116_aec62ff298.m3u8"}//推流url
 	}
}
```

### 关注主播接口
* 请求URL：

```
http://video001.guduokeji.com/api/live/attention
```

* 请求方式：POST
* 参数

| 参数名 | 必选 | 类型 |说明 |
| :--- | :----: | ----: |----: |
| anchor_id | true | int |主播id |
| uid    | true      | int | 用户id|

* 注意：接口需要带上登录接口返回的token这个参数，后端会进行校验登录态（所有类型都是字符串）。


#####返回示例


```
{
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
    }
}
```


### 搜寻主页面列表接口
* 请求URL：

```
http://video001.guduokeji.com/api/live/search_index
```

* 请求方式：GET


* 注意：接口需要带上登录接口返回的token这个参数，后端会进行校验登录态（所有类型都是字符串）。


#####返回示例


```
{
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
    	"10000": {
         "anchor_id": 10000;
         "user_name": "源源";
         "nick_name": "源源";
         "head_url": "http://..."; //头像url
         "is_live": 1; //是否正在直播 1:直播 0:没有直播
         "foreshow": "下午一点直播"; //直播预告 is_live=1时有效
         "foreshow_time": 18387788484; //预告直播时间戳 is_live=1时有效
         "room_id": 189;
         "viewing_num": 776; //正在观看直播的人数
        }，
      "10001": {
         ......
        }
	}
}
```

### 主播搜索接口
* 请求URL：

```
http://video001.guduokeji.com/api/live/search
```

* 请求方式：GET



* 注意：接口需要带上登录接口返回的token这个参数，后端会进行校验登录态（所有类型都是字符串）。


#####返回示例


```
{
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
    	"10000": {
         "anchor_id": 10000;
         "user_name": "源源";
         "nick_name": "源源";
         "head_url": "http://..."; //头像url
         "is_live": 1; //是否正在直播 1:直播 0:没有直播
         "foreshow": "下午一点直播"; //直播预告 is_live=1时有效
         "foreshow_time": 18387788484; //预告直播时间戳 is_live=1时有效
         "room_id": 189;
         "viewing_num": 776; //正在观看直播的人数
        }
    }
}
```



### 搜寻历史接口
* 请求URL：

```
http://video001.guduokeji.com/api/live/search_history
```

* 请求方式：GET


* 注意：接口需要带上登录接口返回的token这个参数，后端会进行校验登录态（所有类型都是字符串）。


#####返回示例



```
{
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
    	"10000": {
         "anchor_id": 10000;
         "user_name": "源源";
         "nick_name": "源源";
         "head_url": "http://..."; //头像url
         "is_live": 1; //是否正在直播 1:直播 0:没有直播
         "foreshow": "下午一点直播"; //直播预告 is_live=1时有效
         "foreshow_time": 18387788484; //预告直播时间戳 is_live=1时有效
         "room_id": 189;
         "viewing_num": 776; //正在观看直播的人数
        }，
      "10001": {
         ......
        }
	}
}
```

### 房间页接口
* 请求URL：

```
http://video001.guduokeji.com/api/live/room_info
```

* 请求方式：POST

 | 参数名 | 必选 | 类型 |说明 |
| :--- | :----: | ----: |----: |
| anchor_id | true | int |主播id |


* 注意：接口需要带上登录接口返回的token这个参数，后端会进行校验登录态（所有类型都是字符串）。


#####返回示例



```
{
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
    	"10000": {
         "anchor_id": 10000;
         "user_name": "源源";
         "nick_name": "源源";
         "head_url": "http://..."; //头像url
         "is_live": 1; //是否正在直播 1:直播 0:没有直播
         "foreshow":"下午一点直播"; //直播预告 is_live=1时有效
         "foreshow_time": 18387788484; //预告直播时间戳 is_live=1时有效
         "room_id": 189;
         "viewing_num": 776; //正在观看直播的人数
        }
	}
}
```

### 直播录屏的视频接口
* 请求URL：

```
http://video001.guduokeji.com/api/live/live_video_list
```

* 请求方式：POST

 | 参数名 | 必选 | 类型 |说明 |
| :--- | :----: | ----: |----: |
| anchor_id | true | int |主播id |
| start | false | int |默认0 |
| num | false | int |默认10 |





#####返回示例
```
{
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
    	  {
	         "anchor_id": 10000;
	         "video_id": 193999; //腾讯video id 播放器根据这个播放视频
	         "movie_address": "https://...."; //视频下载地址
	         "start_time": 17719919; //录像的直播开始时间 时间戳
	         "end_time": 17719999; //录像的直播结束时间 时间戳
	         "is_free":0; //是否免费
	         "is_on": 1; //是否有效
	         "total_time": 189; //视频时长 s
	         "origin_price": 776; //原有价格 代币
	         "now_price": 776; //现在价格 代币
        }
	}
}
```




 





