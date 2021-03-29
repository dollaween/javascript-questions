<div align="center">

# Вопросы по Typescript

[Вопросы](https://github.com/dollaween/javascript-questions)
|
[Тесты](https://github.com/dollaween/javascript-tests)
|
[Задачи](https://github.com/dollaween/javascript-tasks)

</div>

---

##### Какие есть базовые типы?

<details><summary><b>Ответ</b></summary>
<p>

Базовые типы:
* Boolean
* Number
* BigInt
* String
* Symbol
* Array
* Null
* Undefined
* Tuple
* Enum
* Unknown
* Any
* Void
* Never
* Object

```typescript
let bool: boolean = false
let num: number = 25
let big: bigint = 100n
let str: string = 'hello'
let sym: unique symbol = Symbol('key')
let arr: number[] = [1, 2, 3]
let nill: null = null
let und: undefined = undefined
let tuple: [string, number] = ['John', 23]

enum Size {
  S = 42,
  M = 48,
  L = 52
}

// Unknown — можно присваивать любые значения, но нельзя обращаться к свойствам и их вызывать
let unk: unknown = {}
unk = { a: 1 }
unk = () => {}
unk.a = 1                   // Ошибка!

// Any — можно присвоить любое значение
let anyType: any = {}
anyType.a = 1
anyType.a = 'string'
anyType.a()

// Void — используется для обозначения, что функция ничего не возвращает
function returnNothing(): void {}

// Never — тип, обозначающий что значения никогда не будет или что функция никогда не вернет значение.
// Используется для бесконечных циклов, зацикленных функций или прерываемых функций (например, ошибкой)
function error(): never {
  throw new Error()
}

// Object — можно присвоить любые объекты, но нельзя обратиться к свойствам
let obj: object = {}
obj = { a: 1 }
obj.a = 1                   // Ошибка!
obj.a()                     // Ошибка!
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

##### Как работает оператор `typeof`?

<details><summary><b>Ответ</b></summary>
<p>

Оператор `typeof` декларирует тип следующего за ним идентификатора.

`typeof` не захватывает тип, объявленный через `type` и `interface`.

```typescript
let rectangle1 = {
  width: 100,
  height: 50,
  colors: ['black', 'grey'],
  info: {
    created: new Date()
  }
}

let rectangle2: typeof rectangle1

/**
  Теперь rectangle2 будет иметь тип:
  {
    width: number,
    height: number,
    colors: string[],
    info: {
      created: Date
    }
  }
*/ 
```

</p>
</details>

---

##### Как работает оператор `keyof` и `in keyof`?

<details><summary><b>Ответ</b></summary>
<p>

Оператор `keyof` предоставляет доступ ко всем именам свойств в идентификаторе. `keyof` похож на `Object.keys`

```typescript
type Options = {
  url: string,
  token: string,
  hasInfo: boolean
}

let opts: keyof Options

// opts имеет тип "url" | "token" | "hasInfo"
```

Оператор `in keyof` циклически перебирает все свойства в идентификаторе (`T`).

В этом примере мы делаем все свойства `Animal` необязательными
```typescript
interface Animal {
  extinct: boolean;
  race: string;
}

type Optional<T> = { [K in keyof T]?: T[K] };

const animal: Optional<Animal> = {
  extinct: true
};
```

</p>
</details>


---

##### Что такое утиная типизация и как она работает?

<details><summary><b>Ответ</b></summary>
<p>

**Утиная типизация** — объявление переменных без указания типов,
при этом Typescript автоматически проставит тип, основываясь на присваиваемом значении.

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

##### Что такое `declare`?

<details><summary><b>Ответ</b></summary>
<p>

Ключевое слово `declare` используется для объявления типа функции или переменной.

```typescript
// Объявление JQuery
declare function $(selector: string): any

// Объявление стороннего API у которого разработчики еще не написали типы
declare const vkAPI: any
``` 

</p>
</details>

---

##### Для чего нужна библиотека **tslib**?

<details><summary><b>Ответ</b></summary>
<p>

В некоторых случаях компилятор Typescript вставляет вспомогательные функции в сгенерированный Javascript код.
Эти функции эмулируют особенности языка, которые еще не поддерживаются браузерами нативно.

Проблема в том, что вспомогательные функции вставляются в скомпилированный результат для каждого файла, в котором
используются. Это приводит к огромному количеству повторяющегося кода и росту размера бандла.

**tslib**, с установленным флагом `--importHelpers`, решает эту проблему. Теперь все вспомогательные функции
будут браться из библиотеки tslib, а не генерироваться в каждом скомпилированном файле.

[TypeScript: Библиотека tslib](https://habr.com/ru/post/343818/)

</p>
</details>

---
