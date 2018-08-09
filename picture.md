# 图集相关


## 接口


### 图集首页轮播图接口

* 请求URL：

```
http://video001.guduokeji.com/api/picture/pictures_rotation
```

* 请求方式：GET



#####返回示例

```
{
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
        {
          "atlas_id":10000,//图集id
          "cover_img_id": 10001,//封面图片id
          "cover_img_url": "http://xxx"10001//封面图片地址
		 }，
        {
           "atlas_id":10000,//图集id
          "cover_img_id": 10001,//封面图片id
          "cover_img_url": "http://xxx"10001//封面图片地址
        }
    }
```

### 图集首页列表接口
* 请求URL：

```
http://video001.guduokeji.com/api/picture/pictures_index
```

* 请求方式：GET



#####返回示例


```
 {
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
      "hot": {
          {
          "id":10000,
          "total_time":7200,
          "title": "测试图片",
          "desc": "测试图片",
          "img_url":"http://xxx",
          "type": "科幻",
          "scores": 1000 ,
          "play_nums": "100",
          "is_free": "1",//1,代表免费，0代表不免费
          "total_nums": "12",
        }
    }，
     "pay": {
          "0": {
          "id":10000,
          "total_time":7200,
          "title": "测试图片",
          "desc": "测试图片",
          "img_url":"http://xxx",
          "type": "科幻",
          "scores": 1000 ,
          "play_nums": "100",
          "is_free": "1",//1,代表免费，0代表不免费
          "total_nums": "12",
        }
      }，
     "month": {
          "0": {
          "id":10000,
          "total_time":7200,
          "title": "测试图片",
          "desc": "测试图片",
          "img_url":"http://xxx",
          "type": "科幻",
          "scores": 1000 ,
          "play_nums": "100",
          "is_free": "1",//1,代表免费，0代表不免费
          "total_nums": "12",
        }
     }，
     "special": {
          "0": {
         "id":10000,
          "total_time":7200,
          "title": "测试图片",
          "desc": "测试图片",
          "img_url":"http://xxx",
          "type": "科幻",
          "scores": 1000 ,
          "play_nums": "100",
          "is_free": "1",//1,代表免费，0代表不免费
          "total_nums": "12",
        }
	 }，
    }
  }
  
```

### 图集列表和首页图集换一换接口
* 请求URL：

```
http://video001.guduokeji.com/api/picture/get_pictures

```

* 请求方式：POST

| 参数名 | 必选 | 类型 |说明 |
| :--- | :----: | ----: |----: |
| type | false | int |类型，1：火热推荐，2：付费精品，3：包月精选，4：69特价 (默认为1) |
| from | false | int | 从第几条开始，默认为0（type为0时，无效）|
| num | false | int |展示的数量，默认为10 |

#####返回示例


```
 {
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
       {
          "id":10000,
          "total_time":7200,
          "title": "测试图片",
          "desc": "测试图片",
          "img_url":"http://xxx",
          "type": "科幻",
          "scores": 1000 ,
          "play_nums": "100",
          "is_free": "1",//1,代表免费，0代表不免费
          "total_nums": "12",
      }
   }
 }
  
```

### 图集详情接口
* 请求URL：

```
http://video001.guduokeji.com/api/picture/picture_detail

```

* 请求方式：POST

| 参数名 | 必选 | 类型 |说明 |
| :--- | :----: | ----: |----: |
| atlas_id | true | int |图集id |


#####返回示例


```
 {
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
      "id":10000,
      "total_time":7200,
      "title": "测试图片",
      "desc": "测试图片",
      "img_url":"http://xxx",
      "type": "科幻",
      "scores": 1000 ,
      "play_nums": "100",
      "is_free": "1",//1,代表免费，0代表不免费
      "total_nums": "12",
      "origin_price":10,
      "now_price"6,
      "is_free":"1",//1,代表免费，0代表不免费
      "has_collect":"1",//1,代表已收藏，0代表未收藏
      "has_buy":"1",//1,代表已购买，0代表未购买
      "guess_like": {
          "0": {
          "id":10000,
          "title": "头号玩家",
          "desc": "根据小说改编",
          "type": "科幻",
          "scores": 1000 ,
          "play_nums": "100",
          "origin_price":10,
          "now_price"6,
          "is_free": "1",//1,代表免费，0代表不免费
        }，
        "1": {
          "id":10000,
          "title": "头号玩家",
          "desc": "根据小说改编",
          "type": "科幻",
          "scores": 1000 ,
          "play_nums": "100",
          "origin_price":10,
          "now_price":6,
          "is_free": "1",//1,代表免费，0代表不免费
      }，
      "comments": {
          "0": {
              "id":1000,
              "user_nick": "test",
              "user_img": "http://xxxx.jpg",
              "content": "very good",
              "time": "2018-05-08 10:00:00" ,
              "likes": 50 ,
              "has_like":1,//1，代表已经点赞，0代表没有点赞
           },
         "1": {
              "id":1001,
              "user_nick": "test",
              "user_img": "http://xxxx.jpg",
              "content": "very good",
              "time": "2018-05-08 10:00:00" ,
              "likes": 50 ,
              "has_like":1,//1，代表已经点赞，0代表没有点赞
           },
      }
    }
  }
  
```