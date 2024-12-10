# Hello Mac Book Pro

## 安装软件

- [Node.js](https://nodejs.org/en/download/)
- [Typora](https://typora.io/)
- [Vscode](https://code.visualstudio.com/)
- [Python 3.9](https://www.python.org/downloads/)
- [PyCharm](https://www.jetbrains.com/pycharm/download/#section=mac)
- [Brew](https://github.com/Homebrew/brew)
- [X mind](https://www.xmind.net/)

## 基本配置

### 配置[brew](https://brew.sh)

[brew官网](https://brew.sh) 介绍一行命令

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

> raw.githubusercontent.com域用于提供存储在GitHub存储库中的文件的未处理版本。如果您浏览到GitHub上的文件，然后单击Raw链接，那么您将到达。查看github内容的方式有两种，"原始"方式和"网页"方式。
>
> raw.githubusercontent.com返回存储在github中的文件的原始内容，因此可以将它们简单地下载到您的计算机中。例如，如果页面代表ruby安装脚本，那么您将获得ruby安装可以理解的ruby安装脚本。
>
> 如果您改为使用github.com链接下载文件，则实际上是在下载包含按钮和注释的网页，并在中间显示您想要的脚本-这就是您想要提供给网络浏览器的功能页面，但对于计算机而言，不是要执行的脚本或可以编译的代码，而是要显示的网页。该网页上有一个名为Raw的按钮，可将您发送到raw.githubusercontent.com上的相应内容。
>
> 要在通常的github界面中查看raw.githubusercontent.com/${repo}/${branch}/${path}的内容：
>
> 您将raw.githubusercontent.com替换为普通的github.com
>
> 然后在回购名称和分支名称之间插入" blob"。
>
> 在这种情况下，分支名称为" master"(这是一个非常常见的分支名称)，因此您将/master/替换为/blob/master/，依此类推
>
> `https://raw.githubusercontent.com/Homebrew/install/master/install`
>
> 变成
>
> `https://github.com/Homebrew/install/blob/master/install`
>
> 这与在Github上找到文件并单击Raw链接相反。

可以安装，但是几次尝试错误后，我则从`https://github.com/Homebrew/install/blob/master/install.sh` 下载该脚本，在本地执行

```shell
/bin/bash install.sh
```

安装成功。不过需手动配置环境变量

```shell
  sudo chmod 755 /etc/paths
  vim /etc/paths
  add `/opt/homebrew/bin`
  
  export PATH=/opt/homebrew/bin:$PATH
```

### 配置[picgo](https://picgo.github.io/PicGo-Core-Doc/zh/guide/commands.html#use)

```shell
npm install picgo -g
picgo install picgo-plugin-gitee
picgo set uploader gitee
```

**About picgo config**

```shell
{
  "picBed": {
    "uploader": "gitee",
    "current": "gitee",
    "transformer": "path",
    "gitee": {
      "owner": "your account",
      "repo": "your repo",
      "path": "images",
      "token": "your token",
      "message": "upload image"
    }
  },
  "picgoPlugins": {
    "picgo-plugin-gitee": true
  }
}
```

### 配置[Typora](https://zhuanlan.zhihu.com/p/340760172)

![image-20210629221520192](https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210629221520192.png)

> there is a issue with picgo u command. 
>
> https://github.com/typora/typora-issues/issues/3464
>
> ![image-20210629222133372](https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210629222133372.png)

Please set the command as below: 

```shell
{which node} {which picgo} picgo u
/usr/local/bin/node /usr/local/bin/picgo u
```

### 配置 [docsify](https://docsify.js.org/#/quickstart)

```she
npm i docsify-cli -g
sudo npm i docsify-cli -g
docsify --help
docsify init Sirius0301.github.io
git clone git@github.com:VagnerDomingues/docsify-example-panels.git
docsify serve
```

### 配置 [ohmyzsh](https://github.com/ohmyzsh)

please follow: https://finquanthub.com/%e7%bb%88%e7%ab%af%e8%ae%be%e7%bd%ae%e6%8c%87%e5%8d%97%ef%bc%8c%e8%ae%a9mac-linux-windows%e7%bb%88%e7%ab%af%e6%9b%b4%e4%b8%8a%e4%b8%80%e5%b1%82%e6%a5%bc/

```shell
  git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
  git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/powerlevel10k
  sudo vi ~/.zshrc
```

![image-20210629224737535](https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210629224737535.png)

---

End
