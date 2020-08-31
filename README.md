# 腾讯云对象存储插件

## 1.插件介绍
> OpenWRT COS插件是一款腾讯云研发的，提供给Lean编译的系统的官方插件。实现在软路由上挂载COSFS，并开启。

| 标题       | 名称                                                         |
| ---------- | ------------------------------------------------------------ |
| 中文名称   | 腾讯云对象存储（COS）插件                                    |
| 英文名称   | luci-app-tencentcloud-cos                                    |
| 最新版本   | 1.0.0 (2020.08.03)                                           |
| 适用平台   | [Lean OpenWRT](https://github.com/coolsnowwolf/lede)         |
| 适用产品   | [腾讯云对象存储（COS）](https://cloud.tencent.com/product/cos) |
| GitHub项目 | tencentcloud-openwrt-plugin-cos                              |
| 主创团队   | 腾讯云中小企业产品中心（SMB Product Center of Tencent Cloud） |

## 2.功能特性

- 支持在软路由上挂载COSFS

- 支持FTP形式访问COSFS挂载目录

## 3.安装指引

- 登录openwrt路由器

- 进入系统→软件包页面，将下方软件包的地址放入从网络安装的输入框中，点击确认完成安装

## 4.使用指引

### 4.1.名词解释
- **EnableCos**：是否开启COS挂载

- **SecretId**：在腾讯云云平台API密钥上申请的标识身份的 SecretId。详情参考[腾讯云文档](https://cloud.tencent.com/document/product)
- **SecretKey**：在腾讯云云平台API密钥上申请的标识身份的SecretId对应的SecretKey。详情参考[腾讯云文档](https://cloud.tencent.com/document/product)
- **Region**：在腾讯云服务器所在地域。详情参考[腾讯云文档](https://cloud.tencent.com/document/product/457/44232)
- **BucketName**：COS服务中存储桶的名称。详情参考[腾讯云文档](https://cloud.tencent.com/document/product/436/41153)
- **Folder**：COS挂载的文件夹名称，默认路径在`/home/ftp/cos`

## 5.获取入口
- ipk [下载地址](https://openapp.qq.com/openwrt/luci-app-tencentcloud-cos_1.0-1_x86_64.ipk)

## 6.版本迭代记录

### 6.1 tencentcloud-openwrt-plugin-cos v1.0.0
- 支持在软路由上挂载COSFS
- 支持FTP形式访问COSFS挂载目录

### 7.注意事项

- openwrt cos 插件实现原理为通过在 /home/ftp/cos 目录挂载 cosfs 实现上传，cosfs 挂载上传文件时受 openwrt /tmp 目录 900M 大小的限制，超出此大小会上传失败
- 如出现安装包依赖安装失败时，但本地已经有了相应的低版本依赖，可以使用命令opkg --nodeps install 安装