GNOME 
======
# prerequisites
Before doing anything, we need to install the essential GNOME packages. Therefore, install ```gnome-tweaks``` with the package manager of your distribution (here we are working on Arch Linux) so:
```
sudo pacman -S gnome-tweaks
```
Then you have to install ```extension-manager``` from aur so:
```
yay -S extension-manager
```
After this, update the system once ``` sudo pacman -Syu ```
# Plugins
then enter the [GNOME Shell Extensions](https://extensions.gnome.org/) website and install the following plugins:
### App Icons Taskbar
This allows you to see the running programs in the top panel.
### Blur my Shell
This allows you to make different parts of your Shell transparent or blur.
### Clipboard Indicator
Clipboard plugin. (not mandatory)
### Dash to Dock
Add bottom dock to your desktop.
### GSConnect
Similar to KDE Connect, but for GNOME, it provides the possibility of connecting the phone to the system.
### Iranian Persian Calender
Add Jalali calendar to the panel (optional)
### Logo Menu
Add a menu with your distru's logo (similar to the Windows Start button) in the upper left corner
### Quick Setting Tweaker
It provides the possibility of personalizing quick settings (upper right corner)
### RunCat
A small cat will be added to your top bar to slow down or speed up based on CPU usage
### Top Bar Organizer
It provides the possibility of moving and personalizing the items in the top bar

# 
1. To display the texts correctly, install one of the Nerd family fonts. [suggestion](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.1.1/DroidSansMono.zip)
2. Then go to the [GNOME Look](https://www.gnome-look.org/) site and download the desired theme or icons.
3. Note:
+ After downloading and extracting the theme file, move its folder to this path ```~/.themes``` and the icons folder to the ```./icons``` so that they appear in ```gnome-tweaks```.
+ For my theme, I used the Dracula skin, which can be downloaded from this address.
+ Icons can also be downloaded from this address.
4. Extract the files and copy them to the mentioned folders. Then open ```gnome-tweaks > Appearance``` menu. Change the ```shell``` and ```legacy applications``` to ```Dracula``` and the icons to ```MacMojave-circle-black``` to apply the skins.
# Terminal
For terminal i use ```Black Box``` which can be installed from:
```
yay -S blackbox-terminal
```
You can use any other terminal. I removed the blackbox header, changed the font and made the background a little transparent.
+ For terminal I have used Zash and Starship.
+ install ```zsh``` and ```starship``` 
```
sudo pacman -S zsh zsh-completions starship
```
Then change zsh to default shell using [this guide](https://wiki.archlinux.org/title/zsh#Making_Zsh_your_default_shell) (with chsh).
Then transfer config files inside the ```.config``` to ```~/.config```  so that the changes are applied.

# Oteher
I use various software such as ranger (File Manager), cmus (Music Player), neofatch, etc..., whose configs are also available in the directory. Use if needed.
```
sudo pacman -S ranger cmus neofetch
```
# ZSH Aliases
I have defined several aliases for zsh that you can use.
```
  run='pnpm run'
  c="clear"
  q="exit"
  cleanram="sudo sh -c 'sync; echo 3 > /proc/sys/vm/drop_caches'"
  trim_all="sudo fstrim -va"
  mkgrub='sudo grub-mkconfig -o /boot/grub/grub.cfg'
  mtar='tar -zcvf' # mtar <archive_compress>
  utar='tar -zxvf' # utar <archive_decompress> <file_list>
  z='zip -r' # z <archive_compress> <file_list>
  uz='unzip' # uz <archive_decompress> -d <dir>
  sr='source ~/.config/zsh/env.zsh'
  ..="cd .."
  psg="ps aux | grep -v grep | grep -i -e VSZ -e" 
  mkdir="mkdir -p"
  fm='ranger'
  pacin="pacman -Slq | fzf -m --preview 'cat <(pacman -Si {1}) <(pacman -Fl {1} | awk \"{print \$2}\")' | xargs -ro sudo pacman -S"
  paruin="paru -Slq | fzf -m --preview 'cat <(paru -Si {1}) <(paru -Fl {1} | awk \"{print \$2}\")' | xargs -ro  paru -S"
  pacrem="pacman -Qq | fzf --multi --preview 'pacman -Qi {1}' | xargs -ro sudo pacman -Rns"
  pac="pacman -Q | fzf"
  parucom="paru -Gc"
  parupd="paru -Qua"
  pacupd="pacman -Qu"
  parucheck="paru -Gp"
  cleanpac='sudo pacman -Rns $(pacman -Qtdq); paru -c'
  installed="grep -i installed /var/log/pacman.log"
  ls="exa --color=auto --icons"
  l="ls -l"
  la="ls -a"
  lla="ls -la"
  lt="ls --tree"
  cat="bat --color always --plain"
  grep='grep --color=auto'
  mv='mv -v'
  cp='cp -vr'
  rm='rm -vr'
  commit="git add . && git commit -m"
  push="git push"
  git-rm="git ls-files --deleted -z | xargs -0 git rm"
  g=git
  ga='git add'
  gaa='git add --all'
  gam='git am'
  gama='git am --abort'
  gamc='git am --continue'
  gams='git am --skip'
  gamscp='git am --show-current-patch'
  gap='git apply'
  gapa='git add --patch'
  gapt='git apply --3way'
  gau='git add --update'
  gav='git add --verbose'
  gb='git branch'
  gbD='git branch -D'
  gba='git branch -a'
  gbd='git branch -d'
  gbda='git branch --no-color --merged | command grep -vE "^([+*]|\s*($(git_main_branch)|$(git_develop_branch))\s*$)" | command xargs git branch -d 2>/dev/null'
  gbl='git blame -b -w'
  gbnm='git branch --no-merged'
  gbr='git branch --remote'
  gbs='git bisect'
  gbsb='git bisect bad'
  gbsg='git bisect good'
  gbsr='git bisect reset'
  gbss='git bisect start'
  gc='git commit -v'
  'gc!'='git commit -v --amend'
  gca='git commit -v -a'
  'gca!'='git commit -v -a --amend'
  gcam='git commit -a -m'
  'gcan!'='git commit -v -a --no-edit --amend'
  'gcans!'='git commit -v -a -s --no-edit --amend'
  gcas='git commit -a -s'
  gcasm='git commit -a -s -m'
  gcb='git checkout -b'
  gcd='git checkout $(git_develop_branch)'
  gcf='git config --list'
  gclr='git clone --recurse-submodules'
  gcl='git clone'
  gcld='git clone --depth'
  gclean='git clean -id'
  gcm='git checkout $(git_main_branch)'
  gcmsg='git commit -m'
  'gcn!'='git commit -v --no-edit --amend'
  gco='git checkout'
  gcor='git checkout --recurse-submodules'
  gcount='git shortlog -sn'
  gcp='git cherry-pick'
  gcpa='git cherry-pick --abort'
  gcpc='git cherry-pick --continue'
  gcs='git commit -S'
  gcsm='git commit -s -m'
  gcss='git commit -S -s'
  gcssm='git commit -S -s -m'
  gd='git diff'
  gdca='git diff --cached'
  gdct='git describe --tags $(git rev-list --tags --max-count=1)'
  gdcw='git diff --cached --word-diff'
  gds='git diff --staged'
  gdt='git diff-tree --no-commit-id --name-only -r'
  gdup='git diff @{upstream}'
  gdw='git diff --word-diff'
  gf='git fetch'
  gfa='git fetch --all --prune --jobs=10'
  gfg='git ls-files | grep'
  gfo='git fetch origin'
  gg='git gui citool'
  gga='git gui citool --amend'
  ggpull='git pull origin "$(git_current_branch)"'
  ggpur=ggu
  ggpush='git push origin "$(git_current_branch)"'
  ggsup='git branch --set-upstream-to=origin/$(git_current_branch)'
  ghh='git help'
  gignore='git update-index --assume-unchanged'
  gignored='git ls-files -v | grep "^[[:lower:]]"'
  git-svn-dcommit-push='git svn dcommit && git push github $(git_main_branch):svntrunk'
  gk='\gitk --all --branches &!'
  gke='\gitk --all $(git log -g --pretty=%h) &!'
  gl='git pull'
  glg='git log --stat'
  glgg='git log --graph'
  glgga='git log --graph --decorate --all'
  glgm='git log --graph --max-count=10'
  glgp='git log --stat -p'
  glo='git log --oneline --decorate'
  globurl='noglob urlglobber '
  glod='git log --graph --pretty='\''%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%ad) %C(bold blue)<%an>%Creset'\'
  glods='git log --graph --pretty='\''%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%ad) %C(bold blue)<%an>%Creset'\'' --date=short'
  glog='git log --oneline --decorate --graph'
  gloga='git log --oneline --decorate --graph --all'
  glol='git log --graph --pretty='\''%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%ar) %C(bold blue)<%an>%Creset'\'
  glola='git log --graph --pretty='\''%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%ar) %C(bold blue)<%an>%Creset'\'' --all'
  glols='git log --graph --pretty='\''%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%ar) %C(bold blue)<%an>%Creset'\'' --stat'
  glp=_git_log_prettily
  glum='git pull upstream $(git_main_branch)'
  gm='git merge'
  gma='git merge --abort'
  gmom='git merge origin/$(git_main_branch)'
  gmtl='git mergetool --no-prompt'
  gmtlvim='git mergetool --no-prompt --tool=vimdiff'
  gmum='git merge upstream/$(git_main_branch)'
  gp='git push'
  gpd='git push --dry-run'
  gpf='git push --force-with-lease'
  'gpf!'='git push --force'
  gpoat='git push origin --all && git push origin --tags'
  gpr='git pull --rebase'
  gpristine='git reset --hard && git clean -dffx'
  gpsup='git push --set-upstream origin $(git_current_branch)'
  gpu='git push upstream'
  gpv='git push -v'
  gr='git remote'
  gra='git remote add'
  grb='git rebase'
  grwh='git rm --cached `git ls-files -i -c --exclude-from=.gitignore`'
  grwhx='git ls-files -i -c --exclude-from=.gitignore | xargs git rm --cached'
  grad='git rm -r --cached . && git add .'
  grba='git rebase --abort'
  grbc='git rebase --continue'
  grbd='git rebase $(git_develop_branch)'
  grbi='git rebase -i'
  grbm='git rebase $(git_main_branch)'
  grbo='git rebase --onto'
  grbom='git rebase origin/$(git_main_branch)'
  grbs='git rebase --skip'
  grep='grep --color=auto --exclude-dir={.bzr,CVS,.git,.hg,.svn,.idea,.tox}'
  grev='git revert'
  grh='git reset'
  grhh='git reset --hard'
  grm='git rm'
  grmc='git rm --cached'
  grmv='git remote rename'
  groh='git reset origin/$(git_current_branch) --hard'
  grrm='git remote remove'
  grs='git restore'
  grset='git remote set-url'
  grss='git restore --source'
  grst='git restore --staged'
  grt='cd "$(git rev-parse --show-toplevel || echo .)"'
  gru='git reset --'
  grup='git remote update'
  grv='git remote -v'
  gsb='git status -sb'
  gsd='git svn dcommit'
  gsh='git show'
  gsi='git submodule init'
  gsps='git show --pretty=short --show-signature'
  gsr='git svn rebase'
  gss='git status -s'
  gst='git status'
  gsta='git stash push'
  gstaa='git stash apply'
  gstall='git stash --all'
  gstc='git stash clear'
  gstd='git stash drop'
  gstl='git stash list'
  gstp='git stash pop'
  gsts='git stash show --text'
  gstu='gsta --include-untracked'
  gsu='git submodule update'
  gsw='git switch'
  gswc='git switch -c'
  gswd='git switch $(git_develop_branch)'
  gswm='git switch $(git_main_branch)'
  gtl='gtl(){ git tag --sort=-v:refname -n -l "${1}*" }; noglob gtl'
  gts='git tag -s'
  gtv='git tag | sort -V'
  gunignore='git update-index --no-assume-unchanged'
  gunwip='git log -n 1 | grep -q -c "\-\-wip\-\-" && git reset HEAD~1'
  gup='git pull --rebase'
  gupa='git pull --rebase --autostash'
  gupav='git pull --rebase --autostash -v'
  gupv='git pull --rebase -v'
  gwch='git whatchanged -p --abbrev-commit --pretty=medium'
  gwip='git add -A; git rm $(git ls-files --deleted) 2> /dev/null; git commit --no-verify --no-gpg-sign -m "--wip-- [skip ci]"'
```
