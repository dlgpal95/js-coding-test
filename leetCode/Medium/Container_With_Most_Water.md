## Container With Most Water

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
var maxArea = function (height) {
  let result = 0;
  let i = 0,
    j = height.length - 1;

  while (i < j) {
    let num = (j - i) * Math.min(height[i], height[j]);
    if (result < num) result = num;

    height[i] < height[j] ? i++ : j--;
  }
  return result;
};
```

처음에 for문 2개로 모든 경우를 다 구했더니 시간초과가 나왔다..

그래서 시작 0부터 끝 height.length-1 으로 시작해서 점점 줄여서 계산해줬다.

<br/>
