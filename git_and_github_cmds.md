# git 和 github常用指令（老年人备忘录）

- ## github相关

  ### 从github创建仓库，然后克隆到本地

  1. github创建repository, initialize with README

  2. 克隆到本地

     ```shell
     git clone git@github.com:HxxAddoil/repository_name.git
     cd repository_name
     ```

  3. 对项目进行修改

  4. 查看仓库状态

     ```shell
     git status
     ```

  5. add和commit

     ```shell
     git add file
     git commit -m <message>
     ```

  6. push到远程仓库github

     ```shell
     git push -u origin master
     ```

  ### 创建本地仓库再添加到远程库

  你已经在本地创建了一个Git仓库后，又想在GitHub创建一个Git仓库，并且让这两个仓库进行远程同步，这样，GitHub上的仓库既可以作为备份，又可以让其他人通过该仓库来协作，真是一举多得。

  1. github创建repository, initialize with README

  2. 本地库关联远程库

     ```shell
     git remote add origin git@github.com:HxxAddoil/repository_name.git
     ```

  3. push

     

- ## git指令相关

  1.保存
  
  ```shell
  git stash save "message"
  git stash list
  git stash apply
  git stash pop
  git stash drop
  git stash clear
  ```
  
  2.变基和reset
  
  ```shell
  git rebase -i HEAD~3
  git reset --hard HEAD^
  ```
  
  3.add delete文件
  
  ```shell
  git add delete-file -A
  ```
  
  4.修补式提交
  
  ```shell
  git commit --amend
  ```
  
  

