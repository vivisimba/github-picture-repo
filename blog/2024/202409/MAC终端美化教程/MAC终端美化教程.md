# 1. 安装on-my-zsh
打开终端工具，输入以下命令
```bash
sh -c "$(curl -fsSL https://gitee.com/mirrors/oh-my-zsh/raw/master/tools/install.sh)"
```
安装过程中如果出现了链接超时的错误，不要慌，就再来一次，一次不够来两次~，我是来了三次才下载下来的，安装完毕后，就会看见一个非常大字oh my zsh ，并且停留在“~” 状态下就表示已经安装完成。
![01](https://github.com/vivisimba/github-picture-repo/blob/main/blog/2024/202409/MAC%E7%BB%88%E7%AB%AF%E7%BE%8E%E5%8C%96%E6%95%99%E7%A8%8B/01.png?raw=true)


# 2. 安装主题
在终端中输入以下命令
```bash
vim ~/.zshrc
```
找到ZSH_THEME 这行，并且将后面双引号内文字改成想要套用主题风格，按下i 键进入编辑模式，双引号内改成「agnoster」，最后按下esc 键退出编辑，并输入:wq 就可以保存退出vim 编辑模式。
![02](https://github.com/vivisimba/github-picture-repo/blob/main/blog/2024/202409/MAC%E7%BB%88%E7%AB%AF%E7%BE%8E%E5%8C%96%E6%95%99%E7%A8%8B/02.png?raw=true)
后期如果想要更换主题，可以到Oh My Zsh的官网Wiki Themes页面看效果。然后自行更改即可。

# 3. 开启高亮语法、开启显示行号
在终端中依次输入以下命令
```bash
echo 'syntax on'  >>  ~/.vimrc
echo 'set nu!'  >>  ~/.vimrc
```
![03](https://github.com/vivisimba/github-picture-repo/blob/main/blog/2024/202409/MAC%E7%BB%88%E7%AB%AF%E7%BE%8E%E5%8C%96%E6%95%99%E7%A8%8B/03.png?raw=true)

在终端再次输入设定命令
```bash
source ~/.zshrc
```
最后，输入底下指令能够让zsh 设定实现效果，会发现到终端机出现乱码文字，现在解决它。
![04](https://github.com/vivisimba/github-picture-repo/blob/main/blog/2024/202409/MAC%E7%BB%88%E7%AB%AF%E7%BE%8E%E5%8C%96%E6%95%99%E7%A8%8B/04.png?raw=true)


# 4. 修复终端乱码
### 安装Powerline 字体修正乱码
由于agnoster 主题内夹带有特殊符号，需要另外安装Powerline 字体才能够正常显示，在终端机上输入底下安装Powerline 字体指令即可，在终端依次输入一下三行命令

```bash
cd ~/Downloads && git clone https://github.com/powerline/fonts.git
cd fonts && ./install.sh
cd && rm -rf ~/Downloads/fonts
```
![05](https://github.com/vivisimba/github-picture-repo/blob/main/blog/2024/202409/MAC%E7%BB%88%E7%AB%AF%E7%BE%8E%E5%8C%96%E6%95%99%E7%A8%8B/05.png?raw=true)

按下「⌘,」两个键，会开启终端机偏好设定，切换至「描述档」分页，按下字体底下的「更改•••」按钮。
![06](https://github.com/vivisimba/github-picture-repo/blob/main/blog/2024/202409/MAC%E7%BB%88%E7%AB%AF%E7%BE%8E%E5%8C%96%E6%95%99%E7%A8%8B/06.png?raw=true)

将字体改成最后夹带有Powerline 字体，这里我选择的是Droid Sans Mono Slashed for Powerline 字型，大小可根据自己喜好调整。
![07](https://github.com/vivisimba/github-picture-repo/blob/main/blog/2024/202409/MAC%E7%BB%88%E7%AB%AF%E7%BE%8E%E5%8C%96%E6%95%99%E7%A8%8B/07.png?raw=true)

最后回到终端机内，就可以看见文件目录内的箭头已经可以正常显示，不会再出现乱码情况。
![08](https://github.com/vivisimba/github-picture-repo/blob/main/blog/2024/202409/MAC%E7%BB%88%E7%AB%AF%E7%BE%8E%E5%8C%96%E6%95%99%E7%A8%8B/08.png?raw=true)
在终端的偏好设置里面可自行设置字体颜色和其他的配置，自行点击测试即可
![09](https://github.com/vivisimba/github-picture-repo/blob/main/blog/2024/202409/MAC%E7%BB%88%E7%AB%AF%E7%BE%8E%E5%8C%96%E6%95%99%E7%A8%8B/09.png?raw=true)

# 5. 设置背景图
打开终端爱好设置，选择描述文件菜单，找到图像，然后选取自己的靓照即可，如果终端没有立即更改，重启一下终端即可
![10](https://github.com/vivisimba/github-picture-repo/blob/main/blog/2024/202409/MAC%E7%BB%88%E7%AB%AF%E7%BE%8E%E5%8C%96%E6%95%99%E7%A8%8B/10.png?raw=true)

# 6. 安装命令高亮插件（zsh-syntax-highlighting）

在终端输入以下命令，依然老规矩，如果超时，多试几次，大功毕成~
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

# 7. 安装命令自动补全插件（zsh-autosuggestions）
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
# 8. 配置插件
```bash
vim ~/.zshrc
```
1. 找到plugins=(git)这行，
2. 按下i 键进入编辑模式
3. 修改成这个样子 plugins=(git zsh-syntax-highlighting zsh-autosuggestions)
4. 最后按下esc 键退出编辑，并输入:wq 就可以保存退出vim 编辑模式。
   ![11](https://github.com/vivisimba/github-picture-repo/blob/main/blog/2024/202409/MAC%E7%BB%88%E7%AB%AF%E7%BE%8E%E5%8C%96%E6%95%99%E7%A8%8B/11.png?raw=true)

# 9. 保存刚才的设置
在终端输入以下命令
```bash
source ~/.zshrc
```
完美，你的装逼成就全部已获得~，在终端自己输入一下命令什么的就感受到了这两个插件的作用



最后补充：好多人都想要这张背景图，我也放进来了
![12](https://github.com/vivisimba/github-picture-repo/blob/main/blog/2024/202409/MAC%E7%BB%88%E7%AB%AF%E7%BE%8E%E5%8C%96%E6%95%99%E7%A8%8B/12.png?raw=true)