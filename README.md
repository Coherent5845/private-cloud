# 私有云+远程下载

一键搭建支持远程下载的私人网盘...

- 远程下载：cloud torrent
- 私有网盘：nextcloud


## 功能

- nextcloud可以用来存储个人文件，照片等，HTTPS加密，有各大平台客户端，支持WebDav
- cloud torrent 有web界面，远程添加种子，下载好之后，可以通过nextcloud拉到本地，视频文件也可以直接网页播放

## 使用方式

1. 安装docker-compose [安装方式](https://docs.docker.com/compose/install/)
2. git clone 
3. 在docker-compose.yml 文件中配置以下参数

    - MYSQL_ROOT_PASSWORD：mysql的root密码
    - VIRTUAL_HOST：你的域名 如 example.com  需要域名的DNS记录指向你的服务器
    - LETSENCRYPT_HOST：同上
    - LETSENCRYPT_EMAIL：邮箱地址
    
    然后在 db.env中配置以下参数
    
    - MYSQL_PASSWORD：mysql密码
4. sudo docker-compose up -d 
5. 访问你的域名，初始化nextcloud，然后在nextcloud中启用外部存储支持，添加本地目录 /downloads
6. 远程下载服务在3000端口，还不支持HTTPS

### 有问题请提Issus