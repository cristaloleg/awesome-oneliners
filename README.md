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

# Recursive sed

Basically replaces `to` to `from` in every file in every subdirectory

```
grep -rl from . | xargs sed -i 's/from/to/g'
```
