# branch 생성하기
```
// 참고 https://trustyoo86.github.io/git/2017/11/28/git-remote-branch-create.html

// branch 생성 & 변경
git checkout -b feature-01

// remote branch에도 생성
git push origin feature-01

// loca branch와 remote branch 연동하기
git branch --set-upstream-to origin/feature-1
```

# branch 삭제하기
```
// 참고 https://trustyoo86.github.io/git/2017/11/28/git-remote-branch-create.html

// 다른브랜치로 변경
git checkout 다른브랜치

// 강제로 local branch 삭제
git branch -D feature-01

// remote branch 삭제
git push origin :feature-01
```

# 강제로 pull하기
```
git fetch --all

git reset --hard origin/master

git pull origin master
```
