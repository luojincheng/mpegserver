# mpegserver

#### 介绍
   1. mpegserver是基于ffmpeg api开发的一款收取流（大华、海康等摄像头或rtsp视频源）完成hls直播、回看web软件       
   2. 本软件支持两种数据库h2/mysql(h2不需安装数据库启动运行即可)                                     
   3. 传统视频媒体服务器利用ffmepg.exe完成收流,而MPEGSERVER是利用api与自己软件完美结合完成收流                
   4. 免费版终身使用,但视频打印开发者水印                                                      
   5. 本软件提供window和linux  两个版本(64位)                                            
   6. 二次开发API（av_ffhls_Api、av_ffplay_Api库文件）及相关文档
   （见：api文档: https://gitee.com/luo-jincheng/av_api_example）                    
   7. 特殊合作开发可以提供源代码                                                           
   8. 本软件支持二次合作开发，联系方式：微/电13190082295 
   9. 视频教程：https://www.bilibili.com/video/BV16U4y1P7xu/

#### 软件架构特点
   1.软件web端采用 spring boot开发 (java)                       
   2.视频流处理采用ffmpeg api 处理 (c)                            
   3.数据库支持h2单机免安装 和mysql两个版本                             
   4. 软件使用极其简单                                           
   5. 多视频源收流，每一路一个线程收流（更好控制业务流程）                         
   6. 视频直播、回看web端免安装插件(支持google chrome浏览器,firefox火狐浏览器)  


#### 安装教程
   1.安装jdk1.8或以上版本(见：下载地址4、5)                                                                                                                        
   2.下载 linux64_version/win64_version                                                                                                                   
   3. 运行 startup.bat 或 startup.sh                                                                                                     
     或直接运行                                                                                                                                  
     java -Dspring.profiles.active=h2  -Dspring.config.location=./application.yml    -jar ./springboot_single_mpeg_server-1.0-SNAPSHOT.jar   

#### 下载地址
   1.本软件下载地址1：https://gitee.com/luo-jincheng/mpegserver 

   2.本软件下载地址2： 链接：https://pan.baidu.com/s/1v6se4LBE8ASisEsShy10tA     提取码：1111  

   3.测试环境搭建(vcl)：链接：https://pan.baidu.com/s/1dlyr7tUic1Be8tPprggonQ	提取码：1111 
    
   4.jdk 1.8（window） 下载：

       网盘下载：https://pan.baidu.com/s/1v6se4LBE8ASisEsShy10tA  提取码：1111   
       官网下载:https://www.oracle.com/cn/java/technologies/javase/javase-jdk8-downloads.html

   5.jdk 1.8（centos） 下载：yum install java-1.8.0-openjdk
   

    
#### 使用文档
               
  1.web拉流服务启动默认端口8085（见：参数配置)

  2.登录初始账号：admin 密码：123456

  3.视频直播列表

       (1)添加视频源（例如：摄像头等）填写名称，视频源rtsp地址，选择tcp/udp通讯（注意：建议用tcp，udp可能丢包花屏）

       (2)如果视频源正常可立即拉取并保存，默认保存位置：d:/temp/video/rtsp(win) 或 /temp/video/rtsp(linux)（见：参数配置）

       (3)可以停止拉流、修改、删除视频源

  4.视频回看列表：说明每天0点自动生成回看。


#### 参数配置  

 说明：就是对application.yml 参数修改。

  1.配置及使用视频：【需补】

  2.修改web管理端口

    server:
       port: 8080

  3.修改web日志保存路径

     file:
        path: d:/temp/springboot_single_mpeg_server/logs

  4.选择数据库类型

     spring:
       profiles:
         active: h2

  5.视频保存路径
    myconfig:
       hlspath:
            - tsurl
            - d:/temp/video/rtsp #m3u8/ts文件保存位置

   6.正版序列号配置
        hlsSN: "135b5d73d2166b07a82746b5d444c56236746ce222dba1e0f17dd26824a352396ec996fbe9b38f9890efcbaea1c370ecc46b5d70407187a3a46e585520ec7f0d43c2d8750cfd21948b1b5ad5c4986569ae1c470363998b0ed3153e70442771e79b9d9e81b574b069f6249cd3343406e322245a3fb11dd444c43cbf961aed83ee"

#### 正式版与免费版区别 
                                
    1.正式版视频不带水印,免费版视频带开发者水印。
                
    2.正式版支持mysql数据库,免费版只支持h2数据库。
            
    3.正式版与免费版都终身免费。
                         
    4.正式版获得方式： 微/电13190082295               
                                            




