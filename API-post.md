###/api/post/new (发新消息)

INPUT: 

    {
       `content` : <消息内容(HTML)>
    }

OUTPUT: 

    {
       `id` : <新消息的ID>
    }

###/api/post/reply (回复消息)

INPUT: 

    {
       `content` : <回复内容(MD格式)>, 
       `reply\_post` : <回复的消息的消息ID>, 
    }

OUTPUT: 

    {
       `id` : <回复的ID>
    }