### 1. 타입 추론

```python
import pandas as pd
df_train = pd.read_csv('../input/train.csv')

#...

df_train = 1

print (df_train)

#출력 : 1
```

이상한 되도않는 값(여기서 1) 넣어봤는데

에러가 나지 않는다.

자바는 컴파일시점에서 걸러주는데

`1` 이 출력되서 당황했다

타입을 자동으로 바꿔버린다고?

`실수해도 계속 모를 수도 있는 상황` 이 올거란 예감이 든다

&nbsp;
&nbsp;

```java
// ex) Java
int[] array = new int[10];
```

`배열`의 경우 자바처럼 미리 공간을 할당을 할 필요가 없어서 좋다.

그래서 아래와 같은 코드가 가능하다

```python
train = pd.read_csv('../input/train.csv')
test = pd.read_csv('../input/test.csv')
full_data = [df_train, df_test]
```

간결하긴 하다
