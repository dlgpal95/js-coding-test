## JadenCase 문자열 만들기

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
function solution(s) {
  s = s.toLowerCase();
  let arr = [...s];

  arr = arr.map((e, i) => {
    if (arr[i - 1] == ' ' || arr[i - 1] == null) return (e = e.toUpperCase());
    return e;
  });

  return arr.join('');
}
```

먼저 소문자로 바꿔주고 배열의 전 글자가 공백이거나 null 일때 대문자로 바꿔준다.

<br/>
