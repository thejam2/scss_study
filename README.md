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

### Mixins
css를 프로그래밍 언어처럼 사용 가능

```
// _mixins.scss 파일
//@mixin 작명(파라미터) {}

@mixin link($color) {
    text-decoration: none;
    display: block;
    color: $color;
    /**
    조건문도 사용가능
    @if $color == "" {
    } @else {
    }
    */
}
```
```
@import "mixins";
a {
  margin-bottom: 10px;
  &:nth-child(odd) {
    @include link(red);
  }
  &:nth-child(even) {
    @include link(blue);
  }
}
```

### Extends
상속느낌
```
//_buttons.scss 파일

%button {
    font-family: inherit;
    border-radius: 7px;
    font-size: 12px;
    text-transform: uppercase;
    padding: 5px 10px;
    background-color: peru;
    color: white;
    font-weight: 500;
}
```
```
@import "buttons";

a {
  @extend %button;
  text-decoration: none;
}

button {
  @extend %button;
  border: none;
}
```
