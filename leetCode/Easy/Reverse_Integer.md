
## Reverse Integer

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
/**
 * @param {number} x
 * @return {number}
 */
const reverse = function(x) {
    const arr = String(x).split('');
    arr.reverse();
    
    const revsArr = [];
    
    if(arr.length == 1){
        return arr[0];
    }
    
    let isZero = false;
    
    arr.forEach(item =>{
        
        if(item != '0'){
            isZero = true;
        }
        
        if(isZero && item != '-'){
            revsArr.push(item);             
            
        }else if(item == '-'){
            revsArr.unshift(item);
        }
    });
    
    return revsArr.join('') <= 2**31 && revsArr.join('') >= -(2**31) ? revsArr.join('') : 0 ;
};

```

#### Number -> String / split 사용하려면 String으로 변환해야한다.
```String(x)```

#### 배열 반대로
```arr.reverse();```

#### 배열 앞에 추가하기
```revsArr.unshift(item);```

#### 배열 하나의 문자열로 바꾸기 / join 안에 구분값 변경 가능
```revsArr.join('');```

#### 숫자 거듭제곱
```2**31```

<hr/>

### :heavy_check_mark: 참고하면 좋은 다른 답안 

Thanks for https://leetcode.com/problems/reverse-integer/discuss/4071/Reverse-Integer-in-JavaScript

```javascript
var reverse = function(x) {
    const reversed =  parseInt(Math.abs(x).toString().split('').reverse().join('')) * Math.sign(x);
    return (reversed <= 0x7fffffff && reversed >= -0x80000000) ? reversed : 0;
};
```

한줄로 요약해서 잘 쓴 답안이다. Math함수를 잘 활용했다.

#### 어떤 수의 절대값 반환
```Math.abs(x)```

#### 어떤 수의 부호를 반환
```Math.sign(x)```

<br/>