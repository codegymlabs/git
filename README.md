Dockerized git executable
===

Based on Alpine Linux.

Usage
---

```bash
docker run -ti --rm -v ${HOME}:/root -v $(pwd):/git codegymlabs/git <command> <arguments>
```

For example, if you need clone this repository, you can run

```bash
docker run -ti --rm -v ${HOME}:/root -v $(pwd):/git alpine/git clone git@github.com:codegymlabs/git.git
```
    
Make Life Easier
---

Find a way to add this part of bash script into `~/.bashrc` or `~/.profile`:
    
```bash
git () {
    (docker run -ti --rm -v $HOME:/root -v $(pwd):/git codegymlabs/git  "$@")
}
```

... and then use function `git` as normal git executable:

```bash
git clone git@github.com:codegymlabs/git.git
```
