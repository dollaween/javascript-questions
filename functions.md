<div align="center">

<h1>Javascript. Вопросы по функциям</h1>

<a href="https://github.com/dollaween/javascript-questions">На главную</a> | <a href="https://github.com/dollaween/javascript-tests">Тесты</a> | <a href="https://github.com/dollaween/javascript-tasks">Задачи</a>

</div>

---

##### 1. Что такое частичное применение функций?
<details><summary><b>Ответ</b></summary>
<p>

**Частичное применение функций** — предоставление функции меньшего количества аргументов, чем она ожидает.

[Частичное применение функций](https://medium.com/devschacht/functional-reactive-ninja-partial-application-of-functions-99fc21d629ff)

</p>
</details>

---

##### 2. Что такое цепь вызовов (method chaining)?
<details><summary><b>Ответ</b></summary>
<p>

**Цепь вызовов** — конструкция, при которой вызов одного метода следует сразу за вызовом другого.

```js
'Hello'.replace(/Hello/g, 'Bye').concat('!')
```

</p>
</details>

---

##### 3. Что такое рекурсия?
<details><summary><b>Ответ</b></summary>
<p>

**Рекурсия** — это когда функция вызывает саму себя.

Примеры, где используется рекурсия:
* JSON.parse / JSON.stringify (Mozilla's Rhino JsonParser)
* document.getElementById и обход дерева DOM
* Обход объектов

Рецепт написания рекурсии:
1. Написать условие выхода из рекурсии
2. ...какое-либо изменение...
3. Написать вызов функции самой себя

##### Паттерн чистой рекурсии

```js
function recursion(args) {
  // Условие выхода
  return recursion(args--)
}
```

##### Паттерн рекурсивной функции внутри функции-обёртки
Более легкий паттерн, с использованием переменной извне рекурсии.

```js
function wrapper(args) {
  let scope = {}

  function recursion(args) {
    // Пишем условие выхода
    // Изменяем scope
    recursion(args--)
  }

  recursion()

  return scope
}
```

##### Пример
Пример рекурсивной функции, где высчитывается сумма всех чисел от 1 до указанного:
```js
function sumNumbers(num) {
  if (num === 1) return 1

  return num + sumNumbers(num - 1)
}

const result = sumNumbers(5)
console.log(result)
// => 15, так как 1 + 2 + 3 + 4 + 5 === 15
```

</p>
</details>

---

##### 4. Что такое анонимная функция?
<details><summary><b>Ответ</b></summary>
<p>

**Анонимная функция** — это функция, у которой после `function` нет идентификатора.

Примеры анонимных функций:
```js
function() {}
const myFunc1 = function() {}
const myFunc2 = new Function() 
const myObject = {
  methodD(){},
  [property](){}
}
```

Стрелочные функции всегда анонимны.
```js
() => {}
```

Анонимная функция может иметь имя, но при этом все равно являться анонимной:
```js
const myFunc = function() { }
console.log(myFunc.name)        // `myFunc`
```

</p>
</details>

---

##### 5. Что такое "Немедленно вызываемая функция" (IIFE)?
<details><summary><b>Ответ</b></summary>
<p>

**Немедленно вызываемая функция (IIFE)** — это конструкция, позволяющая вызвать функцию сразу после её объявления.

Конструкция состоит из двух частей:
1. Функция, заключенная в оператор группировки `()`. Благодаря этому переменные IIFE замыкаются в его пределах и глобальная область видимости ими не засоряется.
2. Мгновенно выполняющееся функциональное выражение `()`, благодаря которому движок выполняет функцию напрямую.

```js
(function() {
  // code
})()
```

Переменные, внутри функции не могут быть использованы за её пределами:
```js
(function() {
  var name = 'dollaween'
})()
name // throws "Uncaught ReferenceError: name is not defined"
```

Переменная, которой присвоено IIFE, хранит в себе результат выполнения функции, но не саму функцию:
```js
var result = (function () {
  return 'dollaween'
})()
result // 'dollaween'
```

</p>
</details>

---

##### 6. Что такое чистая функция?
<details><summary><b>Ответ</b></summary>
<p>

**Чистая функция** — это функция, которая:
1. Является детерминированной — для одного и того же набора входных значений функция возвращает одинаковый результат.
2. Не обладает побочными эффектами — выполнение функции не изменяет какое-либо состояние за пределами её области видимости и не оказывает видимого воздействия на внешний мир, кроме возвращения значения.

Пример чистой функции:
```js
function add(a, b) {
  return a + b
}
```

Пример не чистой функции:
```js
function getRandom() {
  return Math.random()
}
```

</p>
</details>

---
