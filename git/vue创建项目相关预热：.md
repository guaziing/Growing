### 创建项目预热：

> 创建仓库 生成/添加公匙 克隆到本地
创建项目：<br/>
vue init webpack 项目名称（set up unit tests(No) Setup e2e tests with Nightwatch? (n)）<br/>
test （no）<br/>
cd 项目名称<br/>
npm run dev(让项目跑起来)<br/>

> 关于git上传代码：<br/>
git init <br/>
git commit -am '相关信息'<br/>
git remote add origin 地址<br/>
git pull origin master<br/>
git push -u origin master  (如果当前分支与多个主机存在追踪关系，则可以使用-u选项指定一个默认主机，这样后面就可以不加任何参数使用Git push。)<br/>

> 代码上传：(记住必须是在有git灰色文件的文件夹执行)<br/>
git add .（放在本地缓冲区）<br/>
git commit -m '描述内容'（内容放进到本地仓库）<br/>
git push origin master<br/>

> 从另一个存储库或本地分支获取并集成(整合)<br/>
git pull [options] [<repository> [<refspec>…]]（https://www.yiibai.com/git/git_pull.html）<br/>
将本地服务器转换到index-swiper下：<br/>
git checkout index-swiper<br/>

> 线上创建分支后<br/>
git pull （将创建的分支拉过来）<br/>
git checkout index-icons（将本地转换到index-icons进行开发）<br/>

> git  add  .<br/>
git commit -m "change"<br/>
git push<br/>
将该分支的内容合并到master分支上面：<br/>
git checkout master(切换到maser分支上)<br/>
 git merge origin/index-swiper（再将线上的index-swiper分支上新增的内容合并到master分支上）<br/>
git push（将master内容传上去）<br/>


> git status(可以查看详情，包括有没有没有上传的代码。现在在哪个分支下面)<br/>
git branch(查看有哪些分支，以及现在在哪个分支下面)<br/>


> 创建本地分支<br/>：
git branch 分支名字<br/>
git checkout 分支名字<br/>
git branch --set-upstream-to master(建立本地仓库对于远程仓库的追踪)<br/>
git push origin 分支名字:分支名字（将本地分支传到上面去）<br/>

https://blog.csdn.net/boysky0015/article/details/78185879<br/>
> git add .<br/>
git commit <br/>
git push -u origin 分支的名字<br/>
git checout master<br/>
git pull origin master<br/>
git merge 分支的名字<br/>
git status<br/>

> git add .<br/>
git commit --m（必须加上注释）<br/>
git push origin 分支名字<br/>

> 删除vue的node_modle<br/>
rm -f /node_modules<br/>
rimraf node_modules<br/>


