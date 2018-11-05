Git is a version control system.
Git is free software.

初始化一个Git仓库：
	进入所需目录，使用git init命令。

添加文件到Git仓库，分两步：
	使用命令git add <file>，注意，可反复多次使用，添加多个文件；
	使用命令git commit -m <message>，完成。

要随时掌握工作区的状态，使用git status命令。

如果git status告诉你有文件被修改过，用git diff可以查看修改内容。

HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。
	上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100。

穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。

要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。


工作区（Working Directory）
就是你在电脑里能看到的目录，比如我的learngit文件夹就是一个工作区

工作区有一个隐藏目录.git，这个不算工作区，而是Git的版本库。

Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD。


Git是如何跟踪修改的，每次修改，如果不用git add到暂存区，那就不会加入到commit中。

提交后，用git diff HEAD -- readme.txt命令可以查看工作区和版本库里面最新版本的区别：