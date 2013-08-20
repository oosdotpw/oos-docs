###/api/post/new (发新消息)

INPUT: 

    {
       "content" : <消息内容(HTML)>
    }

OUTPUT: 

    {
       "id" : <新消息的ID>
    }

错误：

* `bad_contect`: 消息内容不符合要求

###/api/post/reply (回复消息)

INPUT: 

    {
       "content" : <回复内容(MD格式)>, 
       "reply_post" : <回复的消息的消息ID>, 
    }

OUTPUT: 

    {
       "id" : <回复的ID>
    }

错误：

* `bad_contect` : 回复内容不符合要求
* `bad_reply_post` : 消息ID错误

###/api/post/get_post (获取一个消息的详情)

INPUT: 

    {
       "id": <消息ID>
    }

OUTPUT: 

    {
         "content": <消息内容(HTML)>, 
         "time": <发表时间>, 
         "replys": <评论数>, 
         "author":{
             "id": <用户ID>, 
             "username": <用户名>, 
             "avatar": <用户头像>
         }
    }

错误：

* `bad_reply_post` : 消息ID错误

### /api/post/get_replys  (获取一个消息下的评论)  
INPUT: 

    {
         "id" : <消息ID>
    }  

OUTPUT: 

    {
        "result": [{
            "content": <评论内容(HTML)>, 
            "time": <发表时间>, 
            "author":{
                "id": <用户ID>, 
                "username": <用户名>, 
                "avatar": <用户头像>
            }
          }, <更多评论>
        ]
    }

错误：

* `bad_reply_post` : 消息ID错误