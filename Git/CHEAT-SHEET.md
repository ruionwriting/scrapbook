# Cheat Sheet

## Rebasing

### Interative Rebase

[Git Rebase Interactive :: A Practical Example](https://www.youtube.com/watch?v=tukOm3Afd8s)

Choose the commit hash prior to the commit(s) you want to change:

```shell
$ git log --oneline
```

Then:

```shell
$ git rebase -i <hash>
```

Just follow the guide provided by git.
