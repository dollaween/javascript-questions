# Typescript: Вопросы

---

##### 1. Какие есть базовые типы?

<details><summary><b>Ответ</b></summary>
<p>

Базовые типы:
* Boolean
* Number
* BigInt
* String
* Symbol
* Array
* Tuple
* Enum
* Unknown
* Any
* Void
* Null
* Undefined
* Never
* Object

```typescript
let bool: boolean = false
let num: number = 25
let big: bigint = 100n
let str: string = 'hello'
let list: number[] = [1, 2, 3]
let tuple: [string, number]: ['Cassie', 23]
```

</p>
</details>

---

##### Как работает оператор `as`?

<details><summary><b>Ответ</b></summary>
<p>

`as` — assertion operator (утверждение типов), явно указывает, какой тип ожидаем получить.

```typescript
const elem = document.getElementById('root') as HTMLElement
```

</p>
</details>

---

##### Что такое утиная типизация и как она работает?

<details><summary><b>Ответ</b></summary>
<p>

**Утиная типизация** — объявление переменных без указания типов, при этом Typescript автоматически проставит тип, основываясь на присваиваемом значении.

```typescript
let name = 'Liu Kang'

// Объявлению переменной name будет автоматически присвоен тип string
let name: string = 'Liu Kang'
``` 

В примере ниже `fighters` будет иметь два обязательных поля: `name` и `age`
```typescript
let fighters = {
  name: 'Sonya',
  age: 47
}
```

</p>
</details>

---

##### Приведите примеры уже реализованных типов в Typescript

<details><summary><b>Ответ</b></summary>
<p>

Реализованные типы:
* `Partial<T>` — делает все свойства в типе `T` опциональными
* `Readonly<T>` — делает все свойства в типе `T` `readonly`
* `Pick<T, K extends keyof T>` — выбирает из типа `T` указанные свойства `K`
* `Record<K extends string, T>` — переданным свойствам `K` будет присвоен тип `T`

##### Пример `Pick`
```typescript
interface Human {
  id?: number;
  login: string;
  age: number;
  weight: number;
}

type User = Pick<Human, 'id' | 'name'>

// эквивалентно
type User = {
  id? = number;
  name: string
}
```

##### Пример `Record`
```typescript
type ThreeDogProps = Record<'prop1' | 'prop2' | 'prop3', Dog>

// эквивалентно
type ThreeDogProps = {
  prop1: Dog;
  prop2: Dog;
  prop3: Dog
}
```

</p>
</details>

---

##### Как добавить сторонние типы других разработчиков на проект?

<details><summary><b>Ответ</b></summary>
<p>

Типы сторонних разработчиков можно найти здесь:

[https://www.typescriptlang.org/dt/search](https://www.typescriptlang.org/dt/search)

Установить пакет с типами можно так:

`npm add @types/react`

</p>
</details>

---

