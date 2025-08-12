# project1

- **dependent environments**

1. MySQL

```cmd
#cmd(Administrator)
net start mysql
net -u root -p(cmd:123456)
```

2. zookeeper

```cmd
cd D:\environmentpro\zookeeper\zookeeper-3.4.11\bin
zkServer.cmd
```

3. nacos

```cmd
cd D:\environmentpro\nacos\bin
startup.cmd -m standalone
```

4. rocketmq

```cmd
#1.start NameServer
cd D:\environmentpro\rocketmq-4.4\rocketmq-all-4.4.0-bin-release\bin
start mqnamesrv.cmd

#2.start Broker
start mqbroker.cmd -n localhost:9876 -c ..\conf\broker.conf
# if the port is occupied,
netstat -ano | findstr 10911 #find PID
taskkill /PID 1234 /F
start mqbroker.cmd -n localhost:9876 -c ..\conf\broker.conf
# test result
C:\Windows\system32>netstat -ano | findstr 10911
  TCP    10.20.6.211:10911      113.240.72.102:443     CLOSE_WAIT      13676

C:\Windows\system32>tasklist /FI "PID eq 13676"

映像名称                       PID 会话名              会话#       内存使用
========================= ======== ================ =========== ============
qmbrowser.exe                13676 Console                    1    154,884 K

C:\Windows\system32>taskkill /PID 13676 /F
成功: 已终止 PID 为 13676 的进程。
```

5. Seata

```cmd
cd D:\environmentpro\seata-server-1.3.0\seata\bin
seata-server.bat
```

6. Canal

```cmd
cd D:\environmentpro\canal.deployer-1.1.4\bin
startup.bat
```



# git

1. create remote github repository--HTTPS![image-20250812161101734](C:\Users\vikinea\AppData\Roaming\Typora\typora-user-images\image-20250812161101734.png)

2. Upload the local project to GitHub

```bash
#first upload
cd ..
git init 
git add .
git config --global user.name "parajoo"
git config --global user.email "minz523334@gmail.com"
git commit -m "first commit"
git remote add origin https://github.com/parajoo/project0812.git
git branch -M main   # 把分支名改成 main（如果还没改过）
git push -u origin main
#further uploaded
git add .
git commit -m "更新说明"
git push

```

