我尝试了以下方法：
  #### 1.使用https协议上传代码
    开始报错 致命错误：无法访问 'https://github.com/168Ai/JavaLearn.git/'：The requested URL returned error: 403
    原因是 你的账号 没有权限 push 这个仓库， 是token 生成的时候，没有选择 push 权限。Select scopes： ✅ 一定要勾上 repo（第一个）
    我重新生成了一个token，上传的时候卡住不动了。最后懒得试了。就用ssh协议上传代码。

  #### 2.使用ssh协议上传代码
    通过豆包的提示，都是错误的，最后其实是网络问题，我需要关闭防火墙，才能连接到github的服务器443端口。

   ```
    ssh -T git@github.com
    kex_exchange_identification: read: Connection reset by peer
    Connection reset by 20.205.243.160 port 443
    
    这个错误是由于github的服务器端口443被重置了，导致连接失败。
   ```

公司的网络是关闭了443端口的，所以导致连接失败。我最后通过热点连接，成功上传了代码。


