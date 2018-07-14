
**상황**

> 커밋 메시지를 잘못 적었다.
아직 push 안했다

ex) `Add 'File.txt'` 라는 커밋메시지를 작성하려고 했는데, 아래와 같이 실수해버렸다면 ?

```bash
git add .
git commit "Add 'File.tx'"
```

당황하지 말고 다음 명령어를 입력한다.

```bash
git commit --amend
```

바꿔주면 끝.

저장하면 아래처럼 뜬다.

```
$ git commit --amend
[master 2482c02] Add 'File.txt'
 Date: Sat Jul 14 21:17:52 2018 +0900
 1 file changed, 9 insertions(+), 1 deletion(-)
```

push 고고
