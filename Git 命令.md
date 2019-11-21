Git 操作指南：
1. Git branch -D branch ：删除分支删除本地分支
2. Git branch -m old_branch new_branch 修改本地分支名
3. git branch | grep 分支名      搜索本地分支
4. git branch -r | grep 分支名           搜索远程分支（先fetch）
5. Git branch -D <BranchName>  ：删除本地分支
6. Git branch -m oldbranchname newbranchname 修改本地分支名
7. Git branch -vv        查看当前详细分支信息（可看到当前分支与对应的远程追踪分支）
8. Git branch -r         查看远程分支
9. Git branch -a        查看所有分支
10. Git show stash@{1} ： 展示指定版本号的修改
11. Git stash apply stash@{0} ：把指定版本号的数据取出来
12. Git rest --hard HEAD~3:将最近3次的提交回滚本地新建和远程分支对应的新分支
13. Git checkout -b newBranchName origin/remoteBranchName: 本地新建和远程分支对应的新分支
14. Git reset - -hard commit-id:会滚到commit-id, 将commit-id之后提交的commit都去除
15. Git push origin feature-branch:feature-branch  //推送本地的feature-branch(冒号前面的)分支到远程origin的feature-branch(冒号后面的)分支(没有会自动创建)
16. Git merge master : 合并分支
17. Git checkout <filename>         撤销文件的修改
18. Git remote -vv        查看当前远程仓库信息 
19. Git push origin --delete <BranchName>            删除远程分支
20. Git  push origin :Roger : 删除远程分支Roger
21. Git config user.name   查看用户名
22. Git config user.eamil    查看邮箱
23. Git config --global user.name “username”   修改用户名
24. Git config --global user.email “email”  修改用户名
25. Git log -p filename  查看某个单一文件的修改历史
26. git diff branch1 branch2  --stat       查看两个分支之间改动的文件
27. git cherry-pick --abort.          舍弃cherry-pick过来的内容
28. git tag -a tagName -m “tag描述”       在当前分支打tag       
29. git push origin tagName                把tag推送到远程分支
30. git log --grep=comment注释的关键词        通过注视查看commit        git log  —grep=‘关键词’
31. git log oneline  只显示提交的SHA1值和提交信息，SHA1值还是缩短显示前几位





1.从远程拉取分支到本地（切换远程分支）
	git checkout -b MX_BJBANK_MERGE_6.6.1 origin/MX_BJBANK_MERGE_6.6.1

2.推送分支到远程
	git push origin 5.3.8_MX_SZCCB

3.打tag，上传tag
	切换到准备打tag的分支
    1. git tag -a tagName -m "" f52c633
    2. git push origin tagName
4.查看远程分支
	git remote -v
	输出：
	origin git@git.dehuinet.com:wangxb/mxclient_android.git (fetch)
	origin git@git.dehuinet.com:wangxb/mxclient_android.git (push)


5.把符合相关规则的tag列出来
	git tag -l v6.8.2.*

6.查看过滤相关分支
	git branch -r | grep "BJBANK_MERGE_6.6.1"

7.查看过滤相关tag
	git tag | grep "MX_BJBANK"

8.根据tag打tag
	git tag new_tag old_tag

9.根据commit打tag
	git tag tag_name commit_id

10.修改分支名字
	git branch -m oldbranchname newbranchname

11.不小心stage了，现在想退回去
	git reset HEAD  <file>...

12.删除tag
git tag -d tag_name　　　　　　　　//本地删除tag
git push origin :refs/tags/tag_name　　　　//本地tag删除了，再执行该句，删除线上tag

13.qwe
git checkout . #本地所有修改的。没有的提交的，都返回到原来的状态
git stash #把所有没有提交的修改暂存到stash里面。可用git stash pop回复。
git reset --hard HASH #返回到某个节点，不保留修改。
git reset --soft HASH #返回到某个节点。保留修改



GIt代码提交流程

     Git status 查看本地修改的文件
     Git diff 查看所有修改的具体内容
     Git stash 压栈本地修改的代码
     Git pull 拉取远程代码
     Git stash pop 把本地修改的代码，从栈中取出
     (这个时候可能会有冲突，要先解决冲突)
     (git add <filename> 把冲突的文件提交，准备推送到远程）
     Git commit -a -m “描述提交的内容”  提交本地修改
     Git push    把代码推送到远程 

Gradle文件目录

    .gradle/wrapper/dists/                   gradle版本目录


Linux 操作指南

    1. rm -fr 文件名      删除文件（rm -fr gradle-2.*   删除gradle-2.开头的文件）
    2. du -h                   查看当前目录的大小

