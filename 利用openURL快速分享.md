
#利用openURL快速分享

#1.QQ

>`Tips` URL Scheme  QQ + 十六进制新AppId，不足八位在首部补0。（如 appid=222222 则 scheme=QQ0003640E）

`OPENURL`
```
mqqapi://share/to_fri
```
支持分享到：
* QQ好友、QQ空间

支持类型：
* 文字、图片、链接、音频、视频
* 图片、音频、视频文件采用`UIPasteBoard`来传递数据


#####参数解析:
```
cflag // 0 qq, 1 qzone, 2
file_type // text, img, news(链接), audio, video
sdkv // sdk版本
thirdAppDisplayName // 发起分享的app名字 base64编码字符串
version // 1
callback_type // scheme
callback_name // 注册的QQ URLScheme (QQ + 十六进制新AppId)
objectlocation // pasterboard
src_type // app
```


#2.微信

`OPENURL`
```
weixin://app/app注册的微信URLScheme/sendreq/?
```
支持分享到：
* 微信好友、微信朋友圈

支持类型：
* 文字、图片、链接、音频、视频、文稿文件、app
* 微信分享数据传递全部采用`UIPasteBoard`,具体参见demo


#####参数解析:
```
command // 1010 文字， 1020 其它
sdkver // sdk版本
scene // 0 微信好友， 1 微信朋友圈
fileExt // 文件后缀名 ex: .gif、.pdf...
extInfo // 分享app时的附加参数，微信回调时会传回这个值
```
```
objectType
typedef NS_ENUM(NSInteger, WXObjectType) {
    kWXObjectTypeImage = 2,
    kWXObjectTypeAudio,
    kWXObjectTypeVideo,
    kWXObjectTypeNews,
    kWXObjectTypeFile,
    kWXObjectTypeApp,
    kWXObjectTypeGif,
};
```

#3.新浪微博

`OPENURL`
```
weibosdk://request?id=设备uuid&sdkversion=003013000
```
支持类型：
* 文字、图片、链接
* 采用`UIPasteBoard`来传递数据
* 详情参见demo


