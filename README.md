# 七牛云图床

![七牛logo](http://oe8r161mt.bkt.clouddn.com/others/qiniuLogo.png?imageView/2/w/400/q/100)

## 简要使用步骤

1. 注册[七牛云](https://www.qiniu.com/)账户
  > 1. 创建属于你的账号并完善相关信息，在个人中心获取	`AccessKey/SecretKey`。
  > 1. 添加对象存储空间`bucket`，对于没有绑定过自己域名（需要备案）的账号，七牛云会提供一个测试域名，后续图片访问也是基于该域名的。

1. 配置`conf.json`
  ```json
  {
      "src": "Local directory to upload",
      "dest": "qiniu:access_key=[Please apply your access key here]&secret_key=[Dont send your secret key to anyone]&bucket=[Bucket name on qiniu resource storage]",
      "debug_level": 1
  }
```

1. 使用命令同步文件
 <br>在命令行运行`qrsync conf.json`即可提交文件。
 ```
_> qrsync conf.json
  2017/05/12 14:15:02.185127 [INFO] qbox.us/qrsync/v3/qrsync/qrsync.go:50: Syncing E:\blogImg => jq-blog
  2017/05/12 14:15:02.218215 [INFO] qbox.us/qrsync/v3/sync/sync.go:172: Putting others/qiniuLogo.png
  2017/05/12 14:15:02.623598 [INFO] qbox.us/qrsync/v3/sync/sync.go:146: Put E:\blogImg/others/qiniuLogo.png => jq-blog:others/qiniuLogo.png
  Sync done!
 ```
 成功上传！

 图片地址为：
  `http://[域名][图片路径]`，如：<br>
 *http://oe8r161mt.bkt.clouddn.com/others/qiniuLogo.png*，

1. chrome插件
 <br>chrome 上安装[**qiniu upload files**](https://chrome.google.com/webstore/detail/qiniu-upload-files/emmfkgdgapbjphdolealbojmcmnphdcc?utm_source=chrome-app-launcher-info-dialog)方便管理和查看。


## 小tips

  如果需要不同大小的图片，可在图片URL后添加查询参数如：`?imageView/2/w/400/q/100`来定义图片大小和质量。

  详情参考七牛[图片基本处理](https://developer.qiniu.com/dora/manual/1279/basic-processing-images-imageview2)开发者中心文档。

## 参考

[qrsync 命令行同步工具 ](http://docs.qiniu.com/tools/v6/qrsync.html)
