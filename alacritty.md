1. 访问https://ohmyz.sh/#install 安装ohmyzsh

2. 配置.zshrc,(其中在vs code中 PATH 安装一下code 命令)	

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

3. code  .zshrc

打开文件后，删除原有代码

将以下粘贴进去

```
export ZSH="$HOME/.oh-my-zsh"

# git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt" --depth=1
# ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
ZSH_THEME="spaceship"

# git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
# git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

plugins=(
  git
  zsh-autosuggestions
  zsh-syntax-highlighting
  z
)

#https://ohmyz.sh/
source $ZSH/oh-my-zsh.sh
```

4. 依次将4条注释，在终端中运行

5. 最后运行

```
source ~/.zshrc
```

   

