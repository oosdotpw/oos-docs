## account
该模块处理与帐号和令牌相关的逻辑。

### /api/account/signup (注册帐号)

请求：

    {
        "username": <用户名>,
        "email": <邮箱>, 
        "passwd": <密码>
    }

错误：

* bad_username: 用户名格式不符合要求
* bad_email: 邮箱地址格式不符合要求
* bad_passwd: 密码格式不符合要求
* username_exits: 用户名已存在

该请求不需要 Token.

### /api/account/login (登录并获取 Token) 

请求：

    {
        "username": <用户名>,
        "passwd": <密码>
    }

返回：

    {
        "token": <账户令牌>
    }


该请求不需要 Token.

### /api/account/logout (注销 Token)

### /api/account/session_info (获取会话信息)

返回：

    {
        "expired": <过期时间>
    }