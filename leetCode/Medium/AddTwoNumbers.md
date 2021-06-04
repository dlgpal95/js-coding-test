## Add Two Numbers

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var addTwoNumbers = function (l1, l2) {
  let arr1 = [],
    arr2 = [];

  while (l1) {
    arr1.push(l1.val);
    l1 = l1.next;
  }

  while (l2) {
    arr2.push(l2.val);
    l2 = l2.next;
  }

  let num = BigInt(arr1.reverse().join('')) + BigInt(arr2.reverse().join(''));
  let sumArr = [...(num + '')];
  let result;
  for (const i in sumArr) {
    result = new ListNode(sumArr[i], result);
  }
  return result;
};
```

BigInt는 Number 원시 값이 안정적으로 나타낼 수 있는 최대치인 253 - 1보다 큰 정수를 표현할 수 있는 내장 객체이다.
BIgInt를 사용하지않으면 `1e+30` 같은 값이 되어서 num을 구할때 NaN이 나오게된다..

더한 값은 ListNode로 만들고 next값에는 바로전 index까지의 listNode를 넣어준다.

<br/>
