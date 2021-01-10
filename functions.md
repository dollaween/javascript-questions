<div align="center">

<h1>Javascript. Вопросы по функциям</h1>

<a href="https://github.com/dollaween/javascript-questions">На главную</a> | <a href="https://github.com/dollaween/javascript-tests">Тесты</a> | <a href="https://github.com/dollaween/javascript-tasks">Задачи</a>

</div>

---

##### 1. Что такое частичное применение функций?
<details><summary><b>Ответ</b></summary>
<p>

**Частичное применение функций** — предоставление функции с меньшим количеством аргументов, чем она ожидает.

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
