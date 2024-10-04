# branch 생성하기
```
// 참고 https://trustyoo86.github.io/git/2017/11/28/git-remote-branch-create.html

// branch 생성 & 변경
git checkout -b {branchName}

// remote branch에도 생성
git push origin {branchName}

// local branch와 remote branch 연동하기
git branch --set-upstream-to origin/{branchName}
```

# branch 삭제하기
```
// 참고 https://trustyoo86.github.io/git/2017/11/28/git-remote-branch-create.html

// 다른브랜치로 변경
git checkout 다른브랜치

// 강제로 local branch 삭제
git branch -D {branchName}

// remote branch 삭제
git push origin :{branchName}
```

# 강제로 pull하기
```
git fetch --all

git reset --hard origin/{branchName}

git pull origin {branchName}
```

# remote branch 삭제하기
```
git branch origin --delete {branchname}
```
