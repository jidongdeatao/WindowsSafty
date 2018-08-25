# WindowsSafty

Windows系统提权基础命令：
  1.获取IP地址信息 ipconfig/all
  2.获取端口信息 netstat -an
  3.获取服务信息和进程信息
    服务：net start 查看系统开启的所有服务
         net stop  servicename 停止某一服务
         net start servicename 开启某一服务
    进程：命令:tasklist/svc 获取运行的进程名称、服务和ID
         使用msinfo32命令来获取进程更加详细的信息（包括获取环境变量、程序组信息、启动程序相关信息）
            start /wait msinfo32 /report c:\windows\temp\Startup.txt /categories....
         进程结束：有两种方式
          1）taskkill /im imagename /F
            或 taskkill /pid /pocessid /F
          2) pskill 进程好（或名字）
  4.用户管理
    添加temp为管理员
      步骤：1）net user temp T@#地址 /add
              net Localgroup Administrators temp /add
           2）查看当前系统管理员用户
              net localgroup Administrators
           3）加入远程桌面用户组
              net localgroup "Remote Desktop Users" temp /add
           4）查看指定用户信息
              net user temp
    激活guest用户：
        net user guest /active:yes
        
        
 渗透Windows系统：
  1.Windows提权信息的收集
  2.使用MSF平台搜索可利用的POC
  3.本地检查Windows漏洞——使用脚本工具：Windows-exploit-suggester
  4.低权限进程集服务提权
    主要是通过发现某用户对系统服务所具备的写权限
    然后修改服务，反弹Shell获取服务器权限
  5.Windows口令扫描及3389口令暴力破解
    通过收集IP段，配置用户名、密码字典，工具扫描
  6.利用特定工具获取远程登录系统密码
  7.域服务器（内网）渗透
  8.主机特定漏洞利用
  9.Web应用漏洞利用
       
Windows下渗透测试工具：
扫描工具
日志清理工具
远程控制工具（冰河木马）
网页木马生成工具（小僧网马生成器）
逆向分析工具
加壳解壳工具
缓冲区溢出攻击工具；流光、Snake IIS
ADSL密码破解工具

