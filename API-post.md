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

* `bad\_contect`: 消息内容不符合要求

###/api/post/reply (回复消息)

INPUT: 

    {
       "content" : <回复内容(MD格式)>, 
       "reply\_post" : <回复的消息的消息ID>, 
    }

OUTPUT: 

    {
       "id" : <回复的ID>
    }

错误：

* `bad\_contect`: 回复内容不符合要求
* `bad\_reply\_post`: 消息ID错误