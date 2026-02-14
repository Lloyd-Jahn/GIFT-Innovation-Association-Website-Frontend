# Week2

后端返回数据格式:

| 字段 | 数据类型 | 含义 | 备注     |
| :--- |:--- |:---|:-------|
| code | 整型 | HTTP状态码 |        |
| message | 字符串型 | 数据错误原因 | 成功时不会带 |
| data | 字典 | 前端所需数据 | 需要时才会带 |

## WorkShop

1. 留下访问后端审核状态相关数据的接口
2. 完善前后端交互逻辑

## 具体需求

### index.html

这是交互的主页面，要求是

1. 页面简洁，不要那么多的动画效果，简单的变色即可
2. CSS和HTML文件必须分文件书写
3. 写\<a href\>之类的链接语句时不要写链接到html文件，而是链接到一个URL
4. 保留以下和后端交互的接口

- 前端向`/api/workshop/works`发送`GET`请求，返回包含`data`字段，

`data`信息: 

```json
{
  "works": [
    "img_src1", "img_src2" 
  ]
}
```
，包含了一个数组，含返回的图片URL

- 前端向`/api/news/links`发送`GET`请求，返回包含`data`字段，

`data`信息: 

```json
{
    "links": [
        "news_link1", "news_link2" 
    ],
    "titles": [
        "title1", "title2"
    ],
    "briefs": [
        "brief1", "brief2"
    ]
}
```
包含了几个数组，含返回的新闻URL以及标题，简介等数据

- 前端保留对`3D打印工坊`，`用户登录`，`关于界面`的访问链接

### login.html

1. 使用表单提交数据，已在模板`user/login.html`中作出交互示例
2. 保留对注册界面的导航
3. 头部内容适当保留，主要保留icons即可
4. 成功后导航到主页面

### register.html

1. 使用表单提交数据，已在模板`user/register.html`中作出交互示例
2. 保留对登录界面的导航
3. 头部内容适当保留，主要保留icons即可
4. 成功后导航到主页面

### workshop.html

1. 使用表单向`/workshop/index`发出POST请求提交所有数据
2. 要求表单提交数据格式如下: 

```json
{
    "print-file": "(file)",
    "material": "material_name",
    "model": "型号信息",
    "color": "颜色信息",
    "allowed_time": {
        "Monday": ["morning", "afternoon", "evening", "night"],
        "Tuesday": ["morning"]
    }
}
```

### user.html

1. 查看个人基本信息，包括学号，邮箱，姓名等
2. 查看自己提交过的3D打印申请
3. 提供接口访问3D打印申请（用占位符代替）
4. 查看自己的3D打印作品(用占位符代替)
