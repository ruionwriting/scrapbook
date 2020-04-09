# Cheat Sheet

## Managing Repos

[Splitting a subfolder out into a new repository](https://help.github.com/en/articles/splitting-a-subfolder-out-into-a-new-repository)

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

## Manage

[How to prune unwanted git branches](https://gist.github.com/zkiraly/c378a1a43d8be9c9a8f9)

[How to find/identify large commits in git history?](https://stackoverflow.com/questions/10622179/how-to-find-identify-large-commits-in-git-history)
  ```shell
  git rev-list --objects --all \
  | git cat-file --batch-check='%(objecttype) %(objectname) %(objectsize) %(rest)' \
  | sed -n 's/^blob //p' \
  | sort --numeric-sort --key=2 \
  | cut -c 1-12,41- \
  | $(command -v gnumfmt || echo numfmt) --field=2 --to=iec-i --suffix=B --padding=7 --round=nearest
  ```

