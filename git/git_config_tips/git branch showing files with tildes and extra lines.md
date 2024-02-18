# Problem

My git files starte being shown with tildes and on vim editor. I think it was after instoh-my-bash

## solution

I found the solution on [this stack overflow page](https://stackoverflow.com/questions/50525244/git-command-output-is-in-editor-vim-and-not-directly-to-terminal-output) and it's pretty simple to solve.
As of git 2.16  it's the default behaviour.
the solution lies in changing the pager config. To change for branch, `git config --global pager.branch false` works, but as the pager defaults to true, there must be better solutions.
[Other article on Medium](https://medium.com/pragmatic-programmers/git-config-core-pager-807e17d64243) defaults teaches us how to change this default behaviour. The first alternative is by using `git config --global core.pager ""` where core.pager is set to an empty string. This doesn't say much, but ait works as if the ""="cat" config.
The author also provides one another cool feature that is `git config --global core.pager "less -FX"` or `"less -F`". Here, which will present pagers only when the output is longer than one terminal screen.
