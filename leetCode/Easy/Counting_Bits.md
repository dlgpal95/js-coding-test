## Counting Bits

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
var countBits = function (n) {
  let result = [];

  for (let i = 0; i <= n; i++) {
    let num = i.toString(2);

    result.push([...num].reduce((acc, curr) => (acc += curr * 1), 0));
  }

  return result;
};
```

2진법으로 바꿔주고 reduce를 이용해서 구했다.

<br/>
