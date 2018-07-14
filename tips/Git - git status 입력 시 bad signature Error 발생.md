
```bash
git status

error: bad signature
fatal: index file corrupt
```

&nbsp;

```bash
rm -f ./git/index
git reset
```

&nbsp;

```bash
git status
# 정상적으로 작동
```
