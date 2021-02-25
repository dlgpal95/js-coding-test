
## Palindrome Number

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
/**
 * @param {number} x
 * @return {boolean}
 */
const isPalindrome = function(x) {
    const sNum = String(x).split('');

    if( Math.sign(x) < 0 && sNum[sNum.length-1] == '0'){
        return false;
    }

    return sNum.reverse().join('') == x ? true : false;
};

```

<hr/>

### :heavy_check_mark: 더 좋은 답안 

Thanks for https://leetcode.com/problems/palindrome-number/discuss/387961/No-String-or-Array-conversion-4-Lines-99.66-beat

```javascript
var isPalindrome = function(x) {
  if (x < 0) return false

  let rev = 0
  for(let i = x; i >= 1; i = Math.floor(i/10)) rev = rev*10 + i%10
  return rev === x
};
```

``` if (x < 0) return false``` 를 사용하면 - 걸러지는데 나는 Math.sign()을 이용했다..<br/>
array 사용없이 한 코드이다.  <br/>
속도는 내가 짠거보다 빠르다. 근데 어렵다..



<br/>