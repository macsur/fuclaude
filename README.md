# Fuclaude
[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/mPax7h5UhOw/0.jpg)](https://www.youtube.com/watch?v=mPax7h5UhOw)

Docker搭建claude网站-原潘多拉作者新作

这是最新claude镜像网站作品，完美使用Claude 3.5 Sonnet欢迎体验。

Claude 3.5 Sonnet 是我们迄今为止最强大的视觉模型，在标准视觉基准上超越了 Claude 3 Opus。这些重大改进对于需要视觉推理的任务最为明显，例如解释图表和图形。Claude 3.5 Sonnet 还可以准确地从不完美的图像中转录文本 - 这是零售、物流和金融服务的核心功能，在这些服务中，AI 可以从图像、图形或插图中获得比仅从文本中更多的见解。

demo 
https://claude.itellyou.cf/
登录自己的claude账号使用
本demo网站密码：www.ywsj365.com

demo 2:
https://claude.zttz.eu.org
https://clai.zttz.eu.org
登录自己的claude账号使用
本demo 2 网站密码：zttz.eu.org

准备条件
1）一台服务器
需要便宜VPS的可以参考这个《RackNerd》|《vultr》|《莱卡云》|《lightnode》

2）本项目的github
https://github.com/wozulong/fuclaude

3）本项目claude官网
https://claude.ai/login

接收验证码可以使用这个平台
https://sms-activate.io/cn
一、Docker环境部署
在vps安装docker和docker-compose
Docker官方安装文档（英文）
https://duan.yyzq.eu.org/docker-001
Docker-Compose官方安装文档（英文)
https://duan.yyzq.eu.org/docker-002
Centos安装Docker和Docker-compose（中文）
https://duan.yyzq.eu.org//03
Ubuntu安装Docker和Docker-compose（中文）
https://duan.yyzq.eu.org//04

或者直接用一键脚本
bash <(curl -sSL https://cdn.jsdelivr.net/gh/SuperManito/LinuxMirrors@main/DockerInstallation.sh)
docker-compose安装脚本
curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && chmod +x /usr/local/bin/docker-compose

二、创建docker-compose.yml文件
mkdir fuclaude;cd fuclaude  #创建一个目录，并进入此目录
vim docker-compose.yml
version: '3'

services:
  fuclaude:
    image: pengzhile/fuclaude
    ports:
      - "8181:8181"
    environment:
      - TZ=Asia/Shanghai
      - FUCLAUDE_BIND=0.0.0.0:8181
      - FUCLAUDE_TIMEOUT=600
      - FUCLAUDE_PROXY_URL=
      - FUCLAUDE_REAL_LOGOUT=false
      - FUCLAUDE_SITE_PASSWORD=               #网站密码
      - FUCLAUDE_COOKIE_SECRET=1234567890abcdefghijklmnopqrstuv
      - FUCLAUDE_OPENAI_BASE_URL=https://api.openai.com/v1
      - FUCLAUDE_OPENAI_API_KEY=sk-xxx
      - FUCLAUDE_MODERATION_ENABLED=true
      - FUCLAUDE_SIGNUP_ENABLED=true
      - FUCLAUDE_SHOW_SESSION_KEY=true
    restart: always  
三、执行容器运行命令
docker-compose up -d #运行容器
docker-compose ps  #查看是否开启成功

四、打开web页面使用
http://ip:8181  #打开自己VPS的端口加ip进入web页面

claude官网的sessionKey获取方法
如下图所示
[![2024-08-06_103141.png](http://pic1.gitme.us.kg/i/2024/08/06/66b193463f2c3.png)](http://pic1.gitme.us.kg/i/2024/08/06/66b193463f2c3.png)
![2024-08-06_103141.png](http://pic1.gitme.us.kg/i/2024/08/06/66b193463f2c3.png)

五、绑定域名
绑定域名可以参考
NginxProxyManager
https://duan.yyzq.eu.org//npm-ch
绑定完域名就可以用域名来访问了


