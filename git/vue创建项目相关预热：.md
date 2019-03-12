### 创建项目预热：

创建仓库 生成/添加公匙 克隆到本地
创建项目：
vue init webpack 项目名称（set up unit tests(No) Setup e2e tests with Nightwatch? (n)）
test （no）
cd 项目名称
npm run dev(让项目跑起来)

关于git上传代码：
git init 
git commit -am '相关信息'
git remote add origin 地址
git pull origin master
git push -u origin master

代码上传：(记住必须是在有git灰色文件的文件夹执行)
git add .（放在本地缓冲区）
git commit -m '描述内容'（内容放进到本地仓库）
git push origin master

从另一个存储库或本地分支获取并集成(整合)
git pull [options] [<repository> [<refspec>…]]（https://www.yiibai.com/git/git_pull.html）
将本地服务器转换到index-swiper下：
git checkout index-swiper

线上创建分支后
git pull （将创建的分支拉过来）
git checkout index-icons（将本地转换到index-icons进行开发）

git  add  .
git commit -m "change"
git push
将该分支的内容合并到master分支上面：
git checkout master(切换到maser分支上)
 git merge origin/index-swiper（再将线上的index-swiper分支上新增的内容合并到master分支上）
git push（将master内容传上去）


git status(可以查看详情，包括有没有没有上传的代码。现在在哪个分支下面)
git branch(查看有哪些分支，以及现在在哪个分支下面)


创建本地分支：
git branch 分支名字
git checkout 分支名字
git branch --set-upstream-to master(建立本地仓库对于远程仓库的追踪)
git push origin 分支名字:分支名字（将本地分支传到上面去）

https://blog.csdn.net/boysky0015/article/details/78185879
git add .
git commit 
git push -u origin 分支的名字
git checout master
git pull origin master
git merge 分支的名字
git status

git add .
git commit --m（必须加上注释）
git push origin 分支名字

删除vue的node_modle
rm -f /node_modules
rimraf node_modules


