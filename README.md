# DEMO
demo
#依次运行以下命令，安装jd_v4_bot和面板。


1、安装v4_bot(amd64) 一键命令（1）

  (提前在宿主机新建文件夹jd_v4_bot，下面再新建config,log,own,diy,scripts五个文件夹。如要自行修改路径，记得为绝对路径。)
  
  docker run -dit \
   -v /jd_v4_bot/config:/jd/config \
   -v /jd_v4_bot/log:/jd/log \
   -v /jd_v4_bot/own:/jd/own \
   -v /jd_v4_bot/diy:/jd/jbot/diy \
   -v /jd_v4_bot/scripts:/jd/scripts \
   -p 5678:5678 \
   -e ENABLE_HANGUP=true \
   -e ENABLE_WEB_PANEL=true \
   -e ENABLE_WEB_TTYD=true \
   --name jd_v4_bot \
   --hostname jd_v4_bot \
   --restart always \
   annyooo/jd:v4_bot



1.1、安装v4_bot(amd64) 一键命令（2）

    wget -q https://raw.githubusercontent.com/Annyoo2021/jd_v4_bot/main/jd-docker.sh -O jd-docker.sh && chmod +x jd-docker.sh && ./jd-docker.sh


   
2、进入容器，默认容器名jd_v4_bot，如做了修改，按实际修改命令。

    docker exec -it jd_v4_bot bash 


 
3、安装面板。执行以下命令后，请访问5678端口进行配置，如果你做了映射，请使用实际映射的端口进行访问，默认用户名admin，密码adminadmin。
 
    wget -q https://raw.githubusercontent.com/Annyoo2021/jd_v4_bot/main/v4mb.sh -O v4mb.sh && chmod +x v4mb.sh && ./v4mb.sh
 
 

3.1、更新或者重装装面板执行以下命令后，请使用旧密码进行访问面板。

    wget -q https://raw.githubusercontent.com/Annyoo2021/jd_v4_bot/main/v4mb_up.sh -O v4mb_up.sh && chmod +x v4mb_up.sh && ./v4mb_up.sh



4、下载库里的：scripts.tar.gz，解压至scripts文件夹。


5、如不操作第4条，或想用其他库的脚本，当脚本报错缺少依赖时，依次执行以下3条命令，默认容器名jd_v4_bot，如做了修改，按实际修改命令。

  (前提scripts文件夹里得有package.json和package-lock.json，没有就去scripts.tar.gz里找)

    docker exec -it jd_v4_bot bash
    cd scripts
    npm install
