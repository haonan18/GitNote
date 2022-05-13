# GitNote

> Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency. 
> 分布式项目版本管理系统 
> 记录每次版本更新并可以回溯
> 多人联合远程工作

 ## Common Command

 ### TRACEBACK

 查看日志
 ```
 git log (--pretty=oneline)
 ```
 查看命令日志
 ```
 git reflog
 ```
 版本回溯
 > 上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100
 ```
 git reset --hard HEAD^
 git reset --hard <commit_id>
 ```
 
 ## Work as Master
 
 ### Create a new repository
 
 版本库初始化
 ```
 git init
 ```
 添加文件
 > 每一次添加新的文件或修改文件后，都需执行此命令
 ```
 git add <filenames>
 ```
 添加提交
 > 每一次执行上述命令后，都需执行此命令
 ```
 git commit -m "commit_text"
 ```
 
 ### Create a new remote repository
 > 远端GIT服务器：　github.com gitlab.com
 
 关联远端版本库
 ```
 git remote add origin <https_url>
 ```
 推送
 ```
 git push
 ```
 获取
 ```
 git pull
 ```
 
 ## Work with Others
 > 和他人合作时，只能在个人分支上做修改并推送个人分支到远端版本库，然后请求合并
 
 ### Clone from remote
 
 登录服务器
 ```
 git config --global user.name "name"
 git config --global user.email "email"
 ```
 克隆
 ```
 git clone <https_url>
 ```
 
 ### Branch management
 
 创建分支
 ```
 git branch <branch_name>
 ```
 创建分支并切换
 ```
 git checkout -b <branch_name>
 ```
 所有分支
 ```
 git branch
 ```
 切换分支
 ```
 git checkout <branch_name>
 ```
 合并分支
 > 合并分支到当前分支上。如果你不是版本库所有者，不要轻易合并其他分支到master分支上。
 ```
 git merge <branch_name>
 ```
 删除分支
 >  因为创建、合并和删除分支非常快，所以Git鼓励你使用分支完成某个任务，合并后再删掉分支，这和直接在master分支上工作效果是一样的，但过程更安全。
 ```
 git branch -d <branch_name>
 ```
 推送分支
 > 如果已关联远端版本库，此命令可自动在远端创建对应分支
 ```
 git push origin <branch_name>
 ```
 
 ## Author
  - Haonan Yin - *Initial work* - haonan18
