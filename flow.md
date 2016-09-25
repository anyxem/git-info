# 1. git workflow. (NOT git-flow)

Main branch for work is `master`, but we shouldnt' commit directly there. Some projects can have other branch for develop but futher we assuming that `master` branch is for develop.

Release branch is `release`. There we prepare code to submit to staging or so. Also in this branch we can create tagged commits.

Feature branches are started with `feature/` or `fix/` or whatever you want.

## 2. Start to work with existing project

`git clone <url> `

## 3. Common workflow

1. `git checkout master` - in case of other active branch switch to master
2. `git pull --rebase origin master` - refresh local master branch with remote with key `--rebase` to avoid of unnessecary commits like a `merge xxxx/master with master`

## 4. Create feature branch

1. `git checkout -b feature/my-feature` - create branch and switch to it
2. updating the code
3. `git add -A` - add to index all edited files
4. `git commit -m "feat(main): add main page"` - commit changes according to name standards
5. `git push origin +feature/my-feature` - push commits to remote

repeat items 2-4 if needed. after that push changes again but without `+` sign, as we have already that branch remotely

TRY DO NOT COMMIT DIRECTLY INTO `MASTER` sure IRL we could. :)

## 5. Create pull request

Go to GitHub after pushing commits. Then go `Pull requests`, `New pull request`, in base select `master` in compare select `feature/my-feature`. Then press `Create pull request`. If you pretty often used `--rebase` github will able to merge code automatically, if you you'll know and you should resolve conflicts, and after that push commits again.

When you create `PR` let know your teammates about it and give link to that `PR`. Two of them must leave OK as **comment**, or leave suggestions how to improve you code.

If you see two or more OKs you author can merge branches via GitHub interface. After that author can remove his branch from remote.

![](https://raw.githubusercontent.com/anyxem/git-info/master/img/1.png)

You can see this graph at GitHub `Graphs` -> `Network`.
`Shift + Arrow Right` to see latest commits
