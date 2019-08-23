# 12306-ticket
这是一个 12306 全自动购票系统，该系统为 Spring Boot 编写的后端服务，就不需要天天盯着 12306 官网查询余票了。

功能介绍
自动识别验证码
多账号同步购票
定时刷新监控余票
设置多座位优先抢票
自动下单
下单成功短息通知
基础环境
JDK8
maven
python3
python 依赖安装
Mac 或者 Linux 用户使用虚拟环境：

cd ticket/python

python3 -m venv venv

source venv/bin/activate

sudo pip install -r requirements.txt
Windows 用户使用本地当前环境：

cd ticket/python

sudo pip install -r requirements.txt
如果上面依赖下载太慢，可以使用 pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple 下载。

验证码识别测试
Mac 或者 Linux 用户使用虚拟环境：

cd ticket/python

source venv/bin/activate

python3 main.py ../temp/index.jpg
Windows 用户使用本地当前环境：

cd ticket/python


python main.py ../temp/index.jpg
配置说明
短信配置
短信使用的是阿里云短信服务，这个很便宜，申请一个就好了：点击申请
修改配置文件：application-sms.yml

notice:
  accessKeyId: "阿里云获取"
  accessSecret: "阿里云获取"
  templateCode: "阿里云获取"
  signName: "阿里云获取"
默认用户配置
默认用户是指在项目启动的时候，直接开始抢购对应的配置购票信息。
配置文件：application-user.yml

在线接口文档
项目集成了 swagger ，可以在线直接调用接口使用。
项目启动成功后，输入地址：

http://localhost:9998/swagger-ui.html
