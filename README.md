# 📂 My personal dotfiles  

![image](https://user-images.githubusercontent.com/20686451/160021681-62474e99-daa0-4f40-9f9a-586e783736ca.png)

## 📦 Installation
To install these configuration files you need [chezmoi](https://www.chezmoi.io/install/#one-line-binary-install) installed on your system.  
The following command installs chezmoi and automatically applies the dotfiles:  
```sh
sh -c "$(curl -fsLS chezmoi.io/get)" -- init --apply sparcopt
```

## ⚙️ App configs
This repository manages configurations for the following applications:  

- [zsh](https://www.zsh.org/)
- [oh-my-posh](https://ohmyposh.dev/)
- [neovim](https://neovim.io/)
- [git](https://git-scm.com/)

## 💻 Setup
Follow this steps if you want to customize your CLI like mine:  

1. **[font]** Install FiraCode
   - Download FiraCode.zip from the nerd-font [release page](https://github.com/ryanoasis/nerd-fonts/releases)
   - If you are on Windows, install all the "Windows compatible" files
   - Set the font on your terminal. I'm using ``` FiraCode NF Retina``` 
3. **[shell]** Install zsh  
   - ```sudo apt-get update```  
   - ```sudo apt-get install zsh -y```   
   - ```chsh -s $(which zsh)``` (make it the default shell)   
   - Log out and log back in again to use your new default shell
4. **[prompt]** Install oh-my-posh  
   - I used homebrew but there are other ways to install it (homebrew is recommended as my prompt configuration is linked to homebrew)
   - ```brew tap jandedobbeleer/oh-my-posh```  
   - ```brew install oh-my-posh```  
5. **[icons]** Install LSDeluxe
   - ```sudo dpkg -i lsd_0.21.0_amd64.deb``` from [this release page](https://github.com/Peltoche/lsd/releases) (adjust the package name if needed)
6. **[ls colors]** Install LS_COLORS
   - Download ```lscolors.sh``` from [this repo](https://github.com/trapd00r/LS_COLORS) and place it in your home directory ```~/``` or ```/home/<username>/```
7. **[config]** Apply my configurations
   - ```sh -c "$(curl -fsLS chezmoi.io/get)" -- init --apply sparcopt```
8. Reload your shell
   - ```source ~/.zshrc```  

#### Optional

7. **[editor]** Install neovim
   - ```sudo apt install neovim```  

#### Specific to Windows terminal (that I use)
8. **[terminal]** 
   - Set background opacity to 50% on Settings > Defaults > Transparency
   - Enable acrylic on Settings > Defaults > Transparency
   - Settings > Open JSON file, go to schemes, change the background value of ```One Half Dark``` to ```"background": "#001B26"```
   - Set the color scheme as ```One Half Dark``` in Settings > Appearance

## 🔨 WSL2 fixs
These are changes for WSL2 end users:

- [Fix Windows Subsystem for Linux (WSL) File Permissions](https://www.turek.dev/posts/fix-wsl-file-permissions/)
  - Fixs the weird background color of directories when doing cd completion ```cd <dir>```
- [How to fix Git show all file as modified in WSL](https://momane.com/how-to-fix-git-show-all-file-as-modified-in-wsl)
  - Fixs the WSL/Git issue where most of the files are of the same color because they are tagged as executables
  - You can skip this if you are using my .gitconfig
  - Only necessary if your daily dev setup includes adding/changing files from Windows while using WSL as CLI
- [How to use the Windows clipboard from WSL?](https://github.com/neovim/neovim/wiki/FAQ#how-to-use-the-windows-clipboard-from-wsl)
  - Allows copy/paste from and into neovim
  - You can skip this if you are using my nvim config
