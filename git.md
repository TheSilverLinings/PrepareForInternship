# Git Command

## 一、安装git

- Ubuntu Linux：

  - ```shell
    sudo apt-get install git
    ```

## 二、创建版本库

- 文件夹：

  - ```shell
    # 1. 创建
    mkdir mygit
    
    # 2. 进入
    cd mygit
    ```

- 创建git管理:

  - ```shell
    git init
    ```
    

## 三、添加文件

- 添加：

  - ```shell
    git add readme.md
    ```
  

## 四、提交到仓库

- 提交：

  - ```shell
    # -m 描述 本次提交的改动
    git commit -m "The meaning of this commit"
    ```

## 五、查看状态

- 查看：

  - ```shell
    # 仓库的状态
    git status
    
    
    # 文件被修改的具体内容
    git diff readme.md
    
    # 仓库修改的历史过程
    git log (--pretty=oneline)
    ```

## 六、穿越版本库

- 回退到  以往版本：

  - ```shell
    # 退回上一个版本
    git reset --hard HEAD^
    
    # 退回上两个版本
    git reset --hard HEAD^^
    
    # 退回上100个版本
    git reset --hard HEAD~100
    
    # 回退后无法再通过 git log 看到回退之前的版本号
    ```

- 前进到  回退之前的版本：

  - ```shell
    # --hard 指定需要前进回去的版本号，但是需要知道相应的版本号，知道前几位即可，git可以检索
    $ git reset --hard 1094a  
    
    # 获取相应的版本号，从终端中的历史信息获取，或者使用下面命令，记录了操作git的历史记录
    git reflog
    ```

## 七、简单理解git分区

- git分区：

  - ```shell
                             git add                  git commit
    |      工作区       |  ----------->    暂存区     ------------->    分支
    |--看得到得 folder--|                  |------------ .git -------------|
    ```

## 八、撤销修改

- 撤销：

  - ```shell
    # 撤销工作区 
    git checkout -- readme.md     # 注意 -- 是必须的
    
    # 撤销暂存区
    git reset HEAD readme.md 
    
    # 撤销分支 --> 参考 六、穿越版本库
    ```

## 九、删除文件

- 删除：

  - ```shell
    # 删除过程
    rm readme.md
    git rm readme.md
    git commit -m "remove the readme.md"
    
    # 复原
    git checkout -- readme.md
    
    # 注意：从来没有被添加到版本库就被删除的文件，是无法恢复的！
    ```

## 十、远程仓库

- 添加远程仓库:

  - ```shell
    # 使用ssh传输加密
    1. 生成本机ssh文件 (id_rsa, id_rsa.pub)
    2. 在github的settings，找到添加ssh的地方，添加进去即可
    ```

  - 