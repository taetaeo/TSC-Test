# 07. Null & undefined

<br>

## Undefined & Null 

- In TypeScript, both undefined and null actually have their named undefined and null respectively.
**TypeScript** 에서, **undefined** 와 **null은 실제로 각각 undefined 및 null 이라는 타입을 가진다.** 
- Much like void, they're not extremely useful on their own:void와 마찬가지로, 그 자체로는 그다지 유용하지 않다.
- **둘 다 소문자만 존재한다.**

```ts
// 이 변수들에 할당할 수 있는 것들은 거의 없다.

let u:undefined = undefined;
let n:null=null;
```

## undefined & null are subtypes of all other types.
- 설정을 하지 않으면 그렇습니다.
- number에 null 또는 undefined를 할당할 수 있다는 의미이다.
- 하지만, 컴파일 옵션에서 **'--strictNullChecks'** 사용하면, null과 undefined는 void나 자기 자신들에게만 할당할 수 있다.
  - 이 경우, null과 undefined를 할당할 수 있게 하려면, `union type` 을 이용해야 한다.

```ts
let name:string=null;
let age:number=undefined;

// strictNullChecks => true
// Type 'null' is not assignable to type 'string'/

let name:string = null; // (x)

// null => null || void, undefined => undefined || void
// Type 'null' is not assignable to type 'undefined'

let u : undefined = null; // (x)

let v : void = undefined; // (o)

let union:string | null | undefined = 'str';
```

## null in JavaScript
- null 이라는 값으로 할당된 것을 null이라고 한다.
- 무언가가 있는데, 사용할 준비가 덜 된 상태.
- null이라는 타입은 null이라는 값만 가질 수 있다.
- **런타임에서 typeof 연산자를 이용해서 알아내면, object이다.**

```ts
let n:null=null;
console.log(n); // null
console.log(typeof n); // obeject
```

## undefined in JavaScript

- 값을 할당하지 않은 변수는 undefined 라는 값을 가진다.
- 무언가가 아예 준비가 안된 상태
  - 변수를 선언만 하고 값을 할당하지 않은 상태.
- object의 property가 없을 때도 undefined이다.
- **런타임에서 typeof 연산자를 이용해서 알아내면, undefined이다.**

```ts
let u : undefined = undefined;

console.log(u); // undefined
console.log(typeof u); // undefined
```

<br>