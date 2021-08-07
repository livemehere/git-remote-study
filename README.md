# git의 local 환경과 remote 환경

- 처음으로 협업을하고자 git을 사용하려고하는데 혼자할때는 branch를 하나밖에 쓸일이없어서 git의 동작을 세세히 이해할 필요를 느꼈다

- 고심한과정은 생략하고 결과만을 정리해보겠다

## Push

- push를 한다는 것은 local의 branch를 올린다는 것이다
- remote저장소에 없는 branch라면 새로 생성이되어 저장된다

```bash
git push origin master # 로컬의 master branch를 업로드하겠다!
git push origin develop # 로컬의 develop branch를 업로드하겠다!
```

> 로컬에서 git add와 git commit을 하지 않고 작업한 것들은 중간에 branch를 바꿔도 계속 유지가된다. 즉 commit 하지 않은 파일들은 checkout에 영향을 받지 않는다. 단, 브랜치간에 겹치는 파일이 아닐때만 해당한다. master과 develop에 README.md 파일을 작업한다고 치자. master에서 작성하다가 develop으로 브랜치를 옮겨버리면, 작성한것들이 develop의 것으로 덮어씌워질것이다. 하지만 이를 방지해준다. 알림으로 commit하고 이동하라고 알려준다

## Clone, Pull

- clone과 pull을 한다는 것은 간단하다. 단하나만 알면된다. 브랜치는 가져오지않고, 단지 파일들만 가져오는것이다.
- 그렇기때문에 가져와지는 장소는 설령 remote의 브랜치가 develop 이라도 local 브랜치가 master 이라면 마스터에 담기게된다.
- 그럼 작업을 다하고 push를 하려고하면 어떻게될까? 당연히 나에게는 master 브랜치만이 존재하기때문에, remote의 master에 push가 된다.
- 이를 해결하기 위해서는 2가지가있다
  - 로컬에서 develop브랜치로 checkout 하고, 그 브랜치를 push 하기
  - git checkout -t origin/develop 을하여서, 브랜치와 파일을 같이 가져오는 방법이있다.
