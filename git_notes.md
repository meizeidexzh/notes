![image](https://pic2.zhimg.com/v2-3bc9d5f2c49a713c776e69676d7d56c5_r.jpg)


## git基础
**基础概念**
- Workspace：工作区
- Index / Stage：暂存区
- Repository：仓库区（或本地仓库）
- Remote：远程仓库

**1. 初始化**

- git init

**2. 配置**
- git config --list 查看所有配置
- git config --global user.email "xxx@xx.xx"
- git config --global user.name "xxx"


**3. 添加和提交**
- git add/rm
- git commit
    - `-a` 将所有已跟踪的发生改变的文件提交到本地仓库
    - `-m` 添加描述
- git status


## 提交树上移动
**改变HEAD的指向**
- 查看HEAD指向:`cat .git/HEAD`
- HEAD除了可以指向分支，还能指向提交记录点
- 提交树上的每个记录用一个40位的哈希值来标识
- git checkout 

**相对引用**
- 使用`^`向前1步
- 使用`~N`向前N步

**撤销变更**
- git reset
- git revert 

**整理式提交记录**
- git rebase -i HEAD~3
- git cherry-pick c2 c3 c5



## 协同开发
#### ssh-keygen使用方法

ssh-key用于生成密钥，选项如下：

```
-b: 指定密钥长度；
-e：读取openssh的私钥或者公钥文件；
-C：添加注释；
-f：指定用来保存密钥的文件名；
-i：读取未加密的ssh-v2兼容的私钥/公钥文件，然后在标准输出设备上显示openssh兼容的私钥/公钥；
-l：显示公钥文件的指纹数据；
-N：提供一个新密语；
-P：提供（旧）密语；
-q：静默模式；
-t：指定要创建的密钥类型。

样例：
使用-t指定密钥类型，-b指定字节长度
ssh-keygen -t rsa -C "Fan@outlook.com" -b 2048

使用-f指定生成的文件
ssh-keygen -t rsa -C "your_secondemail@email.com" -f ~/.ssh/second-rsa
```

#### 远程仓库



## 推荐阅读
[知乎：Git使用教程](https://zhuanlan.zhihu.com/p/30044692)

[git小游戏](https://learngitbranching.js.org/?NODEMO=&locale=zh_CN)

