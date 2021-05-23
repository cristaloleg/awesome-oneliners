# awesome-oneliners

One liners or simple functions for your terminal. Feel free to submit a PR.

# git pull every repo in folder

```bash
ls | xargs -P10 -I{} git -C {} pull
```

# Base64 Decode

```bash
b64d () {
  echo "$1" | base64 -d ; echo
}
```

# Base64 Encode

```bash
b64e () {
  echo -n "$1" | base64
}
```

# Clear terminal

```bash
alias cls='printf "\033c"'
```

# Remove merged branches relative to the selected branch 

```bash
grmb () {
  git branch -r --merged $1 | sed 's/ *origin\///' | grep -v "$1$" | xargs -r git branch -d
}
```

# Resolve conflict after merge or rebase into vim

if you prefer vim then you can resolve conflicts with [fugitive](https://github.com/tpope/vim-fugitive)

```bash
alias virc="git diff --name-only --relative -z --diff-filter=U | xargs -0 nvim -f -c 'tab all' -c 'tabd Gvdiff!'"
```

# Git graph log

```bash
git_graph () {
  git log --graph --all --date=relative \
	  --pretty=format:'%Cred%h %Creset%<|(100,trunc)%s %C(bold blue)<%an>%Creset %Cgreen(%cd)%Creset%C(auto)%d'
}
```
