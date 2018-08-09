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
          "title": "test",//图集标题
          "atlas_desc": "test...desc"//图集描述
          "type": 1 //图集类型
          "cover_img_id":10000,//封面图片id
          "is_on": "test",//是否有效
          "img_url": "http://xxxx"//封面图片地址
        }，
        {
          "atlas_id":10000,//图集id
          "title": "test",//图集标题
          "atlas_desc": "test...desc"//图集描述
          "type": 1 //图集类型
          "cover_img_id":10000,//封面图片id
          "is_on": "test",//是否有效
          "img_url": "http://xxxx"//封面图片地址
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
          "atlas_id":10000,//图集id
          "title": "test",//图集标题
          "atlas_desc": "test...desc"//图集描述
          "type": 1 //图集类型
          "cover_img_id":10000,//封面图片id
          "is_on": "test",//是否有效
          "img_url": "http://xxxx"//封面图片地址
        }
    }，
     "pay": {
         {
          "atlas_id":10000,//图集id
          "title": "test",//图集标题
          "atlas_desc": "test...desc"//图集描述
          "type": 1 //图集类型
          "cover_img_id":10000,//封面图片id
          "is_on": "test",//是否有效
          "img_url": "http://xxxx"//封面图片地址
        }
      }，
     "month": {
        {
          "atlas_id":10000,//图集id
          "title": "test",//图集标题
          "atlas_desc": "test...desc"//图集描述
          "type": 1 //图集类型
          "cover_img_id":10000,//封面图片id
          "is_on": "test",//是否有效
          "img_url": "http://xxxx"//封面图片地址
        }
     }，
     "special": {
        {
         "atlas_id":10000,//图集id
          "title": "test",//图集标题
          "atlas_desc": "test...desc"//图集描述
          "type": 1 //图集类型
          "cover_img_id":10000,//封面图片id
          "is_on": "test",//是否有效
          "img_url": "http://xxxx"//封面图片地址
       }
	 }，
    }
  }
  
```

### 图集列表和首页图集换一换接口
* 请求URL：

```
http://video001.guduokeji.com/api/picture/get_atlas

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
           "atlas_id":10000,//图集id
          "title": "test",//图集标题
          "atlas_desc": "test...desc"//图集描述
          "type": 1 //图集类型
          "cover_img_id":10000,//封面图片id
          "is_on": "test",//是否有效
          "img_url": "http://xxxx"//封面图片地址
      }
   }
 }
  
```

### 图集详情接口
* 请求URL：

```
http://video001.guduokeji.com/api/picture/atlas_detail

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
      "atlas_id":10000,//图集id
      "title": "test",//图集标题
      "atlas_desc": "test...desc"//图集描述
      "type": 1 //图集类型
      "cover_img_id":10000,//封面图片id
      "is_on": "test",//是否有效
      "img_url": "http://xxxx"//封面图片地址
      "pictures_list": {
	        {
	          "picture_id":10000,
	          "img_url": "http://XXXXX",
	        }，
      }
    }
  }
  
```

### 图集搜索接口
* 请求URL：

```
http://video001.guduokeji.com/api/picture/search_pictures

```

* 请求方式：POST
* 有token的话一定要带上

| 参数名 | 必选 | 类型 |说明 |
| :--- | :----: | ----: |----: |
| slug | true | int |查询关键字 |


#####返回示例


```
 {
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
	   {
	   	    "atlas_id":10000,//图集id
      		"title": "test",//图集标题
          "atlas_desc": "test...desc"//图集描述
          "type": 1 //图集类型
          "cover_img_id":10000,//封面图片id
          "is_on": "test",//是否有效
          "img_url": "http://xxxx"//封面图片地址   
      }
    }
  }
  
```


### 图集搜索历史接口
* 请求URL：

```
http://video001.guduokeji.com/api/picture/picture_search_history

```

* 请求方式：GET
* 注意：接口需要带上登录接口返回的token这个参数，后端会进行校验登录态（所有类型都是字符串）。

#####返回示例


```
 {
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
	   {
	   	    "atlas_id":10000,//图集id
      		"title": "test",//图集标题
          "atlas_desc": "test...desc"//图集描述
          "type": 1 //图集类型
          "cover_img_id":10000,//封面图片id
          "is_on": "test",//是否有效
          "img_url": "http://xxxx"//封面图片地址   
      }
    }
  }
  
```

### 图集评论信息接口
* 请求URL：

```
http://video001.guduokeji.com/api/picture/picture_comment

```

* 请求方式：GET


#####返回示例


```
 {
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": {
	   {
	   	    "comment_id":10000,//评论id
      		"comment": "test",//评论内容
          "user_id": "test...desc"//用户id
          "picture_id": 1 //图片id
          "user_name":10000,//用户名
          "nick_name": "test",//用户昵称
          "head_url": "http://xxxx"//头像图片地址   
      }
    }
  }
  
```

### 图集添加评论信息接口
* 请求URL：

```
http://video001.guduokeji.com/api/picture/add_picture_comment

```

* 请求方式：POST
* 注意：接口需要带上登录接口返回的token这个参数，后端会进行校验登录态（所有类型都是字符串）。

| 参数名 | 必选 | 类型 |说明 |
| :--- | :----: | ----: |----: |
| picture_id | true | int |图片 |
| comment | true | string |评论内容 |



#####返回示例


```
 {
    "errno": 0,
    "errmsg": "SUCCESS",
    "data": []
  }
  
```