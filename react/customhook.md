### 커스텀 훅의 동작원리

React에서 Hook을 구현하는 핵심 원리는 바로 JavaScript의 클로저(Closure)이다. <br />

```javascript
function useFoo() {
    let foo = 0;

    function getFoo() {
        return foo;
    }

    function setFoo(value) {
        foo = value;
    }

    return [getFoo, setFoo];
}

const [getFoo, setFoo] = useFoo();

console.log(getFoo());  // print 0

setFoo(1);
console.log(getFoo());  // print 1

```

 기본적인 설명을 덧붙이자면 다음과 같다. 일반적으로 함수가 반환하고 나면 그 함수 내에 선언된 지역 변수들은 메모리 상에서 <br />사라지지만, 위 예시에서 foo라는 지역 변수는 useFoo() 함수가 반환하고 나서도 클로저라는 별도의 메모리 공간에 남아있게 <br />된다. 이는 useFoo() 함수가 반환하는 getFoo() 함수와 setFoo() 함수가 그 지역 변수를 사용하기 때문이다. 이러한 경우 foo라는 지역 변수가 getFoo() 함수와 setFoo() 함수에 의해 붙잡혔다고 표현하기도 한다.<br />

 