基本路径表示：  
~ 用户目录  
./ 当前文件夹  
../ 上一级文件夹  
  
  
基本终端命令：  
cd 切换目录  
mkdir 新建文件夹  
ls 列出文件列表  
touch 新建文件(Linux)  
New-Item -Path "路径" -ItemType 文件、文件夹或符号链接 新建文件(Windows)  
echo 将输入字符串送往标准输出(Linux/Windows)  
输入重定向  
\> 覆盖 >> 追加  
Windows文本编辑器应用  
notepad  
Ubuntu文本编辑器应用  
nano, vim, gedit  
  
  
查看Git应用版本：  
git --version  
  
  
配置git全局用户名、用户邮箱：  
``` git
git config --global user.name "胡伯融"  
git config --global user.email "hu1203362986@vip.qq.com"  
```
（Git全局配置gitconfig路径：(磁盘或根目录)\\Users\\user\\.gitconfig)  


本地练习：  
1.新建Git项目文件夹，执行基本终端命令进入项目文件夹。  
2.执行git init构建仓库(输出.git文件夹)。  
3.项目文件夹目录新建文件，执行git status查看新建文件跟踪状态。  
->文件存在，没有受到跟踪。  
Git仓库范围文件存在受跟踪(Tracked)和不受跟踪(Untracked)状态。  
空仓库首次添加文件，文件不受跟踪。  
Git管理文件需要仓储文件，git add作用.git文件夹文件，标记.git文件夹之外不受跟踪文件作为受跟踪文件。  
4.git add --all  
添加项目文件夹仓库所在目录所有文件。 
-> 覆盖“增、删、改”操作记录。(可使用 -A 替换 --all)  
5.git commit -m "附加信息"  
提交跟踪状态仓库文件，commit 类比新建项目存档。  
6.git status --short 查看简单版本文件状态。  
（标记含义：?? 不受跟踪的文件 A 处于仓储状态的文件 M 经过修改的文件 D 删除的文件）  
（颜色含义：绿色 已仓储，待提交 红色 未仓储）  
7.git log查看提交日志。  
8.git (command) --help查看特定命令帮助。  
9.git help --all查看所有可执行命令。  
输入SHIFT + G跳转到达页面末尾，输入q退出阅览。  
10.git branch (branch_name)创建版本分支。  
11.git branch查看现有分支和当前分支。  
12.git checkout (branch_name)  
切换分支，切换到(branch_name)分支最新提交状态。  
13.git merge (branch_name)合并目标分支到当前分支。  
（无冲突采用"Fast forward"模式，冲突可在确认、修改冲突文件之后后再次仓储、提交）  
14.git branch -d (branch-name)删除分支。  
15..gitignore划定忽略文件。  
  
  
获取云仓库写入权限：  
1.生成密钥对，复制公钥。  
终端应用输入 ssh-keygen -t ed25519 -C "SSH Key"  
单击回车，连续单击三次回车。  
执行cd ~/.ssh/，执行cat id_ed25519.pub，复制SSH Key和空格左侧部分公钥文本。  
2.上传公钥至网站页面个人公钥选项。  
悬停Gitee页面右上角圆圈和三角，右键单击设置，单击在新标签页中打开链接，单击SSH公钥。  
  
  
互联练习：  
1.新建空白云仓库，git remote add origin (URL)关联本地仓库、云仓库URL链接。  
(origin作为云仓库链接本地命名，git_bus作为云仓库命名)  
2.git push --set-upstream origin master  
上传origin本地master分支，关联origin作为本地master分支默认云分支。  
(--set-upstream 可替换为 -u)  
3.git fetch origin下载origin链接对应云分支。  
4.git diff (origin/master)查看当前所在本地分支(master)与云仓库分支(origin/master)差异。  
5.git pull (云仓库链接本地命名或云仓库链接)同步云仓库内容更新，等效顺序合并执行fetch命令与merge命令。  
6.git branch -a查看所有本地分支与云分支。  
7.git branch -r查看所有云分支。  
8.git remote show origin显示origin对应云仓库仓库详细信息。  
9.git remote -v查看云仓库链接。  
10.git remote add (name) (url)增添云仓库链接。  
规范所属仓库命名origin-(name)，其它账号仓库命名upstream-(name)。  
11.git fetch --prune根据云仓库分支裁剪本地仓库分支。  
12.git clone (URL)下载云仓库。  
13.git clone (URL) (folder_path)下载云仓库到路径对应文件夹。  
  
  
建立合作工作流：  
1.创建分支。  
2.编辑文件，commit附言变更。  
3.测试部署 → 合并主分支和测试分支。  
  
  
云仓库按钮：  
Watch订阅改动。  
Star收藏仓库。  
Fork拷贝其它账号仓库作为所属账号仓库。  
