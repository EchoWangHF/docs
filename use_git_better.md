# Git 使用备忘录

### 1 初始化git账号
git config --global user.name "自定义用户名"

git config --global user.email "邮箱"

### 2 生成git ssh public key
ssh-keygen -t rsa -C "yourmail@xxx.com"

cat .ssh/id_rsa.pub 

### 3 将多个提交合并成一个提交
比如将前3个提交合并成1个提交： `git rebase -i HEAD~3`

将除第一个以外的提交的`pick`改为`fixup`

然后 `:wq` 退出保存即可。

### 4 如何将fork过来的仓库同步到原仓库
1 `cd` 到本地仓库的目录

2 `git remote -v` 查看你的仓库有没有上游分支 `upstream`, 如果没有 `git remote add upstream xxxx upstream ssh/http地址xxxx.git `

3 `git fetch upstream` 抓取  `upstream` 的更新

4 `git checkout master` 切到你自己的仓库的master当中，`git merge upstream/master` 合并你的分支和上游分支。

5 `git push` 到远程即可