#ubuntu安装nvm时报Failed to connect to raw.githubusercontent.com port 443 Operation timed out错误

##尝试安装

今天尝试在windows的子系统安装nvm以便我管理node和npm的版本，于是前往nvm官方查看安装方法：

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

以为很快就能安装完毕，但却报了一个错误：

```
Failed to connect to raw.githubusercontent.com port 443 Operation timed out
```

哎，连这个都要ban！

##解决方法

###方法一、修改host文件

添加199.232.28.133 raw.githubusercontent.com 保存

然后运行

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

###方法二、使用gitee镜像安装

```
git clone https://gitee.com/mirrors/nvm.git ~/.nvm && cd ~/.nvm && git checkout `git describe --abbrev=0 --tags`
```

然后运行~/.nvm/install.sh将环境变量添加至配置文件，然后source后就能用了
