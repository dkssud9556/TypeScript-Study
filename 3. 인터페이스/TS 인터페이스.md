# TypeScript 인터페이스

~~~typescript
function returnName(person: { name: string }) {
    return person.name;
}
let person = { name: 'Daewoong', age: 18 };
returnName(person); // 'Daewoong'
~~~

컴파일러는 returnName 함수의 매개변수가 `{ name: string }`타입에 맞는지 검사한다. `person` 객체는 요구하는 프로퍼티보다 많은 프로퍼티를 가지고 있지만 실행이 잘 된다. 컴파일러는 최소한의 프로퍼티가 있는지와 그 타입이 맞는지만 검사를 한다.

~~~typescript
interface PersonValue {
    name: string;
}
function returnName(person: PersonValue) {
    return person.name;
}
let person = { name: 'Daewoong', age: 18 };
returnName(person); // 'Daewoong'
~~~

이번 예제는 전 예제와 같지만 인터페이스를 사용했다. `PersonValue` 인터페이스는 타입이 `string`인 `name`이라는 프로퍼티가 가져야 한다는 것을 의미한다. 자바같은 경우에는 인터페이스를 명시적으로 구현해서 사용해야 하지만 TypeScript는 형태만 따르면 된다.