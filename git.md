### git
> git:工具，版本控制
> github:网站，社交平台，开源项目，远程仓库

- svn与git区别:
    - 集成式
    - 分布式

- git的三个区：
    - 工作区
    - 暂存区
        - 作为过渡层
        - 避免误操作
        - 保护工作区和版本区
        - 分支处理
    - 版本区（库）


- github官网:https://github.com

- git工具:不同系统，方式不同




- 建立一个库:
    ```
        git init
        git  clone  [url]
    ```

- 设置开发者：
    - name
    - email
    ```
    git config --local  user.name
    git config --global user.email
    ```

- 查看所有配置项：
    ```
    git config --list
    ```

- 查看状态：
    ```
    git status
    ```

- 添加文件到暂存区：
    ```
    git add
            name
            .
    ```

- 暂存区提交到版本库：
    ```
    git commit
            -m
            -a -m    是add和commit合并，后面再加一个注释
    ```

- 对比：
    ```
    git diff           比较暂存区和工作区
    git diff --cached(--staged)   比较暂存区和版本区
    git diff master    比较工作区和版本区
    ```

- 撤销:
    ```
    git reset HEAD <file.name>    撤销暂存区回到工作区
    git checkout -- <file.name>   撤销工作区的代码回到上一个版本
    git commit --amend   代码跟上一个版本合并
    ```

- 删除：
    ```
    git rm <file.name>  删除工作区和暂存区
    git rm -f <file.name> 删除工作区和暂存区
    git rm --cached <file.name> 删除暂存区的文件
    ```

- 恢复：
    ```
    git checkout commit_id <file.name> 
    git reset --hard commit_id
                HEAD^
                HEAD~<num>
    git reflog
    ```

- 同步到远程仓库：
    ```
    git remote
            -v
            origin
    git push origin master
    ```

- 多人协作解决冲突：
    ```
    git fetch
    git diff master origin/master
    git merge  orgin/master
    git pull
    ```

- 开源项目协作：
    ```
    fork
    pull request
    ```



- Git分支：
    ```
    git branch             查看分支
    git branch name        新建分支, 在哪个分支上新建分支，该分支当前的版本会拷贝新分支上。
            -d           删除合并过的分支
            -D        强制删除分支（合并和未合并都删除）
            --merged        查看合并过的分支
            --no-merged     查看未合并过的分支
    git checkout name          切换分支(切换分支前需要将本分支的代码先提交)
                            切换分支后工作区和缓存区会跟当前分支版本区一样
             -b name            创建并切换分支
    git merge          合并分支
    ```

- github上的分支
    ```
    提交本地分支到远程，远程没有该分支
    git push --set-upstream origin develop 
    拉取远程的分支，本地没有该分支
    git fetch
    git checkout -b js origin/js
    提交分支代码
    git push origin js

    git push 
    
    github上直接创建
    ```

- github上的标签
    ```
    git tag
    github上直接创建
    ```
