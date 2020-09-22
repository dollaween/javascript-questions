<div align="center">

<h3>Вопросы по Javascript</h3>
<h1>Выражения и операторы</h1>
<br/>

<a href="https://github.com/dollaween/javascript-questions">На главную</a> | <a href="https://github.com/dollaween/javascript-tests">Тесты</a> | <a href="https://github.com/dollaween/javascript-tests">Задачи</a>

</div>

---

##### 1. Как работает оператор `new`?

<details><summary><b>Ответ</b></summary>
<p>

**Оператор `new`** создает экземпляр объекта имеющего конструктор.

При вызове `new User()` (эквивалентно `new User`) происходит следующее:
1. Создается новый объект, наследующий `User.prototype.`.
2. Вызывается конструктор – функция `User` с указанными аргументами и `this`, привязанным к только что созданному объекту.
3. Результатом выражения new становится объект, возвращаемый конструктором. Если конструктор не возвращает объект явно, используется объект из п.1.

```javascript
function User(name, age) {
  this.name = name
  this.age = age
}
let user = new User('John', 33)

console.log(user.name, user.age)      // 'John', 33
```

[Оператор new](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Operators/new)

</p>
</details>

---

##### 2. Как работает оператор `typeof`?

<details><summary><b>Ответ</b></summary>
<p>

Оператор `typeof` возвращает строку, указывающую тип операнда.

`typeof null` — `object`, общепризнанная ошибка в языке, сохраняется для совместимости.

`typeof function() {}` — `function`, хотя функция является подвидом объектов, а не отдельным типом данных.

```javascript
console.log(typeof 'Margarita')
// string

console.log(typeof 18)
// number

console.log(typeof null)
// object
```

</p>
</details>

---

##### 3. Как работает оператор `instanceof`?

<details><summary><b>Ответ</b></summary>
<p>

Оператор `instanceof` проверяет, принадлежит ли объект к определенному классу.

```javascript
function Turtle(name, color) {
  this.name = name
  this.color = color
}

const turle = new Turtle('Leo', 'blue')

console.log(turle instanceof Turtle)
// true

console.log(turle instanceof Object)
// true
```

</p>
</details>

---

##### 4. Как работает ключевое слово `super`?

<details><summary><b>Ответ</b></summary>
<p>

`super` используется для вызова функций, принадлежащих родителю объекта.

```javascript
// Вызов родительского конструктора
super([arguments])

// Вызов функции родительского объекта
super.functionOnParent()
```
</p>
</details>

---

##### 5. Как работает свойство `new.target`?

<details><summary><b>Ответ</b></summary>
<p>

Свойство `new.target` позволяет определить была ли функция или конструктор вызвана с помощью оператора `new`.

```javascript
function Car() {
  if (!new.target) {
    throw new Error('Function must be called with new!')
  }
}

try {
  Car()
} catch(err) {
  console.log(err)
}
```

</p>
</details>

---

##### 6. Как работает оператор `in`?

<details><summary><b>Ответ</b></summary>
<p>

Оператор `in` возвращает `true`, если свойство содержится в объекте или его цепочки прототипов.

```javascript
const colors = {
  red: '#ff0000',
  green: '#00ff00',
  blue: '#0000ff'
}

console.log('red' in colors)
// true

console.log('hasOwnProperty' in colors)
// true

console.log('length' in colors)
// false, у объектов нет свойства length
```

</p>
</details>

---

##### 7. Как работает оператор `for...in`?

<details><summary><b>Ответ</b></summary>
<p>

Оператор `for...in` проходит по всем перечислимым свойствам объекта.

```javascript
const colors = {
  red: '#ff0000',
  green: '#00ff00',
  blue: '#0000ff'
}

for (let prop in colors) {
  console.log(`${prop}: ${colors[prop]}`)
}

/**
 * red: #ff0000
 * green: #00ff00
 * blue: #0000ff
 */
```

У массивов, в качестве свойства, будет взят индекс элемента в массиве.

```javascript
const colors = ['red', 'green', 'blue']

for (let key in colors) {
  console.log(`${key}: ${colors[key]}`);
}

/**
 * 0: red
 * 1: green
 * 2: blue
 */
```

</p>
</details>

---

##### 8. Как работает оператор `for...of`?

<details><summary><b>Ответ</b></summary>
<p>

Оператор `for...of` создает цикл, проходящий по перечислимым объектам (включая Array, Map, Set, arguments).

```javascript
let names = ['Sara', 'Lara', 'Dana'];

for (let name of names) {
  console.log(name);
}

/**
 * Sara
 * Lara
 * Dana
 */
```

</p>
</details>

---
