## dotfiles

*inspired by https://www.atlassian.com/git/tutorials/dotfiles*

Steps to clone:

Prior to the installation make sure you have committed the alias to your .bashrc or .zsh:  
`alias dotfiles='/usr/bin/git --git-dir=$HOME/dotfiles/ --work-tree=$HOME'` 

And that your source repository ignores the folder where you'll clone it, so that you don't create weird recursion problems:  
`echo "dotfiles" >> .gitignore`

Now clone your dotfiles into a bare repository in a "dot" folder of your $HOME:  
`git clone --bare <git-repo-url> $HOME/dotfiles`

Define the alias in the current shell scope:  
`alias dotfiles='/usr/bin/git --git-dir=$HOME/dotfiles/ --work-tree=$HOME'`

Checkout the actual content from the bare repository to your $HOME:  
`dotfiles checkout`
