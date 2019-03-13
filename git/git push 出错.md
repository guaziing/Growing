### git push 出错
failed to push some refs to 'https://github.com/guaziing/Growing.git'


**原因：** github中的README.md文件不在本地代码目录中
**解决方案：** 
1. git pull --rebase origin master （在文件中出现了READ.md文件）
2. git push -u origin master
