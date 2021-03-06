## 架构
出于尝试新技术的目的，这次打算做到前后端彻底分离，仅通过下文制定的JSON API进行沟通。

### 前端
1. 旧版使用 Ruby 进行开发，Web框架使用 Sinatra ，前端与后端使用 HTTP/HTTPS 进行通信，End-User 不能访问后端服务器。部署使用nginx + thin 模式。
2. 新版本使用 AngularJS进行纯静态开发。
### 后端
使用 Go 开发，主要使用 MongoDB 做数据库，使用 memcahe 进行缓存。

## API 约定
* 所有 API 均使用 POST 方式请求
* POST 请求使用 `x-www-form-urlencoded` 格式，返回信息为 `application/json` 格式
* API 返回信息中不会有语言相关的信息，以便今后国际化
* API 中的时间均为 Unix 时间戳

### 请求地址
API 请求地址分两个部分，模块名和 API 名，类似这样：

    /api/account/signup

### 请求格式

大部分请求都有的字段：

    {
        "token": <账户令牌>
    }

* 所有用户都通过用户名(而不是ID)表示

### 返回格式

成功：

    {
        "error": false,
        "data": {<实际的返回数据>}
    }

失败：

    {
        "error": true,
        "error_msg": <错误ID>, 
        "data" {<有关错误的详细信息>}
    }

两种情况下，如果没有数据，就可能没有 `data` 一项。

### 通用错误ID

* missing_token: 应当提供 Token 的请求没有提供
* invalid_token: Token 失效
