# git操作之ssh与https互换  
来源https://blog.csdn.net/yym836659673/article/details/77504430

ssh换为https
步骤：
+ 修改远程仓库地址
方法有三种：

1.修改命令
```
git remote set-url origin [url]
```
使用 git remote set-url origin [url]命令，直接修改远程仓库为https的地址

2.先删后加
```
git remote rm origin
git remote add origin [url]
```

3.直接修改config文件

+ 以上进行git操作的时候，每次都需要密码，所以可以配置免密
1）新建文件并保存密码
```
$ touch ~/.git-credentials
$ vim ~/.git-credentials
```
2）添加内容
``https://{username}:{passwd}@github.com``
3）添加git配置
``$ git config --global credential.helper store``


---------------------


如果想切回ssh,直接修改远程仓库的地址即可
例如：git remote set-url origin [ssh的url]
