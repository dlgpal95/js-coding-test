
## Roman to Integer

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
/**
 * @param {string} s
 * @return {number}
 */
const romanToInt = function(s) {
    const romaNum = new Map();
    romaNum.set('I',1);
    romaNum.set('V',5);
    romaNum.set('X',10);
    romaNum.set('L',50);
    romaNum.set('C',100);
    romaNum.set('D',500);
    romaNum.set('M',1000);
    
    const sNum = s.split('');
    let result = 0;
    
    for(let i =0 ; i< sNum.length ; i++){
        
        let nowNum = romaNum.get(sNum[i]);
        let nextNum = romaNum.get(sNum[i+1]);
      
        if(nowNum < nextNum){
            result += (nextNum - nowNum);
            i++;
        }else{
            result += romaNum.get(sNum[i]);
         }
    };
    return result;
};
```

map에 담아서 get으로 호출하여서 사용했다. <br/>
예외인경우에는 처리 후 ```i++```으로 순서 뛰어넘었다. < 안뛰어넘어서 계속 고생했다.

<hr/>

### :heavy_check_mark: 참고하면 좋은 다른 답안 

Thanks for https://leetcode.com/problems/roman-to-integer/discuss/326345/Simple-JavaScript-Solution-Easy-Understanding

```javascript
symbols = {
    "I": 1,
    "V": 5,
    "X": 10,
    "L": 50,
    "C": 100,
    "D": 500,
    "M": 1000
};

var romanToInt = function(s) {
    value = 0;
    for(let i = 0; i < s.length; i+=1){
        symbols[s[i]] < symbols[s[i+1]] ? value -= symbols[s[i]]: value += symbols[s[i]]
    }
    return value
};
```

symbols를 사용한 답안이다. <br/>
내가 짠 코드는 ```i++``` 해줘서 넘긴 반면 이 코드는 ```-```를 해줬다.  <br/>
삼항연산자를 이용하여 깔끔하다. 이게 더 좋은방법인거같다. <br/>

<hr/>

### :heavy_check_mark: 참고하면 좋은 다른 답안2

Thanks for https://leetcode.com/problems/roman-to-integer/discuss/801395/JavaScript-Clean-Solution

```javascript
var romanToInt = function(s) {
    const map = { 'I': 1, 'V': 5, 'X': 10, 'L': 50, 'C': 100, 'D': 500, 'M': 1000};
    let num = 0;
    
    for(let i = 0; i < s.length; i++) {
        const curr = map[s[i]], next = map[s[i+1]];
        if(curr < next) num -= curr;
        else num += curr;
    }
    return num;    
};
```

object를 이용한 답안. 내용은 위와 동일하다.

<br/>

