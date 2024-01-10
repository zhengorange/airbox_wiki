### 启动 api 服务
`python api.py` 
    
    该服务依赖于whisper命令。在使用该服务之前，请成功安装whisper。

### upload task 接口
- url `/upload_task`
- method `post`
- form parameter `{'file': audio file}`
- response `{'task_id': task_id}`
- description `在表单中上传一个音频文件，键名为'file'。系统会将请求的文件添加到任务队列，并同时返回一个task_id。`

### download result file 接口
- url `check_task`
- method `post`
- json parameter `{'task_id': task_id}`
- response `{"state": task state}` or `.zip result file`
- description `检查task_id是否已完成。如果已完成，返回结果文件；如果未完成，返回任务状态。 `