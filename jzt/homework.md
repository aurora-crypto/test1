一、将文件从暂存区中退回并恢复到前一版的方法：
1.使用git restore命令
    将文件恢复到最后一次提交的状态，可以使用命令git restore <文件名>
    将已上传从暂存区移除，可以使用命令git restore --staged <文件名>
    
   ![一.1](jzt/images/1(1）.png)

2.使用git reset命令配合git checkout或git restore
使用git reset命令可以将当前分支的提交历史重置到指定的提交点，再使用 git restore --staged --worktree<文件名> 来同时撤销工作目录和暂存区的修改，使其恢复文件状态。
![一.2](jzt/images/1(2）.png)
    
二、若已经提交了一个新版本，需要回退该版本的操作：
1.不修改历史
    使用git revert命令
       使用git log命令查看提交历史，找到要回退的版本的commit ID
       再使用git revert <commit ID> 命令撤销到指定的提交
    ![二.1](images/2(1).png)
2.修改历史
   使用git reset
    使用git log命令查看提交历史，找到要回退的版本的commit ID。
    使用git reset <commit ID> 命令将分支重置到指定的提交，将需要删除的提交前的pick 改为drop
    ![一.2](images/2(2).png)

三、不同的合并分支的方式 
    1、使用git cherry-pick命令: git cherry-pick <需要合并的分支中要提交的哈希名>
    ![三.1](images/3(1).png)
    2、使用git rebase命令变基合并分支：在目标分支上，使用git rebase <目标分支> 
  ![三.2](images/3(2).png)

