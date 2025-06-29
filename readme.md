# Dev Configuration

## Shell
1. Install ZSH & Oh My ZSH
- On MacOs, ZSH is automatically installed, let's install Oh-My-ZSH
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
source: https://ohmyz.sh/#install

2. Install Autosuggestion (History :v)
Clone this repository into $ZSH_CUSTOM/plugins (by default ~/.oh-my-zsh/custom/plugins)
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
Add the plugin to the list of plugins for Oh My Zsh to load (inside ~/.zshrc):
```
plugins=( 
    # other plugins...
    zsh-autosuggestions
)

```
Source: https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md
3. Custom Themes
I prefer robbyrussell.zsh-theme, but need some custom for better. I just need to add a shell time to this theme
- Go to this path in the shell. This includes a lot of themes.
```
cd ~/.oh-my-zsh/themes
```
- Modify the robbyrussell.zsh-theme to customize this, copy all of these code and paste into the file,
overwrite everything
```
# Prompt: show green arrow if success, red arrow if fail, then time in yellow, then cyan path
PROMPT='%(?:%{$fg_bold[green]%}➜%{$reset_color%} :%{$fg_bold[red]%}➜%{$reset_color%}) '

# Add time in bold yellow
PROMPT+='%{$fg_bold[green]%}%D{%H:%M}%{$reset_color%} '

# Add current directory in cyan
PROMPT+='%{$fg[cyan]%}%c%{$reset_color%}'

# Add git info
PROMPT+=' $(git_prompt_info)'

# Git prompt styles
ZSH_THEME_GIT_PROMPT_PREFIX="%{$fg_bold[blue]%}git:(%{$fg[red]%}"
ZSH_THEME_GIT_PROMPT_SUFFIX="%{$reset_color%} "
ZSH_THEME_GIT_PROMPT_DIRTY="%{$fg[blue]%}) %{$fg[yellow]%}✗"
ZSH_THEME_GIT_PROMPT_CLEAN="%{$fg[blue]%})"
```
Nice! now we completed to set up the shell
