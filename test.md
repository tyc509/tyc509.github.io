# docker容器热迁移问题  
实验环境：虚拟机ubuntu 16.04，内核版本4.15，docker17.03 
## 1.docker pull镜像：docker: Get https://registry-1.docker.io/v2/: net/http: request canceled  
答案：网络连接问题，1.使用镜像源；2.虚拟机使用代理；3.手动下载.tar文件，然后加载  
目前可用https://docker.aityp.com/image/docker.io/library/busybox:latest

## 2.docker-pull missing-signature-key
答案：docker版本https://forums.docker.com/t/error-message-from-daemon-missing-signature-key/143124/2

## 3. custom checkpointdir is not supported
答案：docker版本https://stackoverflow.com/questions/42487859/docker-container-migration

## 4.虚拟机ping不通
答案：使用桥接模式，https://fast.v2ex.com/t/1055272

## 5.开启桥接模式无效
答案：在windows防火墙设置虚拟机监控（回显请求），检查Serivce的Virtuabox选项是否开启
https://www.cnblogs.com/vipally/p/14733003.html

说明：ubuntu 18.04似乎不行

参考
```
https://blog.csdn.net/qq_37076942/article/details/111571322
https://github.com/ZhuangweiKang/Docker-CRIU-Live-Migration
https://zhuanlan.zhihu.com/p/269552404

https://blog.csdn.net/alwaysbefine/article/details/111409904
```
