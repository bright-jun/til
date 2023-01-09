# Rebase

# Interactively Rebase

커밋 히스토리를 관리해야할 경우 사용할 수 있는 기능

`git rebase --interactive`, `git rebase -i`

Interactively Rebase 모드에서 사용할 수 있는 명령어들

```
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup <commit> = like "squash", but discard this commit's log message
# x, exec <command> = run command (the rest of the line) using shell
# b, break = stop here (continue rebase later with 'git rebase --continue')
# d, drop <commit> = remove commit
# l, label <label> = label current HEAD with a name
# t, reset <label> = reset HEAD to a label
# m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
# .       create a merge commit using the original merge commit's
# .       message (or the oneline, if no original merge commit was
# .       specified). Use -c <commit> to reword the commit message.
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
```

실행 시 vim으로 수정작업을 할 수 있다. IntelliJ에서는 `Interactively Rebase from Here...`를 통해 해당 기능을 GUI로 제공해주고 있다.

## 주의

`git push --force`

커밋 히스토리 형상을 재구조화해서 푸쉬해야 하므로 force push 를 해서 히스토리 자체를 덮어씌워야 한다. 그렇기에 해당 기능은 협업 개발 중인 main branch에서
사용하는 것은 지양해야 한다.

## [interactively-rebase-from-here-feature-is-disabled](https://youtrack.jetbrains.com/issue/IDEA-203376/interactively-rebase-from-here-feature-is-disabled)

- protected branch 에서는 해당 기능을 사용할 수 없음
- GitHub Setting
    - https://help.github.com/articles/about-protected-branches/
- Intellij Setting
    - Preferences > Version Control > Git > Push > Protected Branches

## 참고

- [git conflict - 알면 기능, 모르면 사고](https://www.youtube.com/watch?v=wVUnsTsRQ3g)
- [7.6 Git Tools - Rewriting History](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)
