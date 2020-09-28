<div align="center">

<h1>Вопросы по Javascript: Дебаггинг</h1>

<a href="https://github.com/dollaween/javascript-questions">На главную</a> | <a href="https://github.com/dollaween/javascript-tests">Тесты</a> | <a href="https://github.com/dollaween/javascript-tests">Задачи</a>

</div>

---

##### 1. Как работает выражение `debugger`?

<details><summary><b>Ответ</b></summary>
<p>

Выражение `debugger` открывает доступ к любому доступному в конкретном окружении отладочному функционалу, например, к установке брейкпоинтов.

В примере ниже, при вызове отладчика, выполнение скрипта приостановится в том месте, где находится выражение `debugger`. В **Chrome Dev Tools** мы можем посмотреть значение аргумента `props`.
```javascript
function buggyFunction(props) {
  debugger
}
buggyFunction()
```

</p>
</details>

---

##### 2. Какие инструменты есть на вкладке "Source" в Chrome Dev Tools?

<details><summary><b>Ответ</b></summary>
<p>

На вкладке "Source" мы можем:
1. Работать с брейкпоинтами: добавлять/удалять, двигаться по ним.
2. Работать с **Event Listeners**.
3. Смотреть **Scope** функции.
4. Смотреть **Call Stack**.
5. Следить за переменными во вкладке **Watch**.

</p>
</details>

---

##### 3. Какие инструменты есть на вкладке "Network" в Chrome Dev Tools?

<details><summary><b>Ответ</b></summary>
<p>

На вкладке "Network" можно:
1. Посмотреть список загруженных данных.
2. Узнать порядок и время загрузки данных.
3. Посмотреть содержание пришедших данных и отправленных запросов.
4. Изменить скорость интернет-соединения для текущей страницы.

</p>
</details>

---

##### 4. Какие у `console` есть методы и как они могут помочь при дебаггинге?

<details><summary><b>Ответ</b></summary>
<p>

У `console` есть несколько методов, которые помогают в дебаге.

`console.dir()` — отображает список свойств указанного объекта или функции.
```javascript
const f = function() {}
f.prototype.add = () => {}

console.dir(f);
```
```javascript
arguments: null
caller: null
length: 0
name: "f"
prototype: {add: ƒ, constructor: ƒ}
__proto__: ƒ ()
[[FunctionLocation]]: app.js:3
[[Scopes]]: Scopes[2]
```

`console.table()` — отображает наборы данных в виде таблицы. Вторым аргументом принимает массив с названиями колонок, которые необходимо отобразить.

```javascript
const arr = [
  { id: 1, name: 'Jon', age: 33, color: 'green' }
];

console.table(arr, ['name', 'age']);
```
```javascript
(index) | name  | age
---------------------
0       | "Jon" | 33
```

`console.time()` — запускает таймер, который можно использовать для определения, сколько времени занимает выполнение той или иной операции.

`console.timeEnd()` — останавливает таймер и выводит результат.

```javascript
console.time()

let arr = []
for (let i = 0; i < 1e6; i++) {
  arr.push(i)
}

console.timeEnd()
```
```javascript
default: 15.090087890625 ms
```

`console.trace()` — показывает стэк трейс до текущей функции.

```javascript
inner
outer
(anonymous)
```

</p>
</details>
