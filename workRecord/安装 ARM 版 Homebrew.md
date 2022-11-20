## 安装 ARM 版 Homebrew

`ARM`版`Homebrew`需要安装在`/opt/homebrew`路径下，早期的时候需要手动创建目录执行命令，目前使用最新脚本不需要手动操作。

直接执行：

```bash
/bin/bash -c "$(curl -fsSL https://gitee.com/ineo6/homebrew-install/raw/master/install.sh)"
```

然后还需设置环境变量

PS: 终端类型根据执行命令`echo $SHELL`显示的结果：

- `/bin/bash` => `bash` => `.bash_profile`
- `/bin/zsh` => `zsh` => `.zprofile`

**如果遇到环境变量无效问题，建议回过头来查看终端类型，再做正确的设置。**

从`macOS Catalina`(10.15.x) 版开始，`Mac`使用`zsh`作为默认`Shell`，使用`.zprofile`，所以对应命令：

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

如果是`macOS Mojave` 及更低版本，并且没有自己配置过`zsh`，使用`.bash_profile`：

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.bash_profile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

