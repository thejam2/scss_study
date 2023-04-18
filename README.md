# scss_study

### Variables
css를 변수처럼 사용 가능

_variables.scss 파일 생성 후 ( _있는 파일은 scss위한 파일)
```
$bg: #e7473c;
$title: 32px;
```

사용할 파일에서 import 후 사용
```
@import "_variables";

h2 {
  color: $bg;
}
```


### Nesting

```
.box {
  margin-top: 20px;
  &:hover {
    background-color: green;
  }
  h2 {
    color: blue;
    &:hover {
      color: red;
    }
  }
  button {
    color: red;
  }
}
```
