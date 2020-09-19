# Javascript. Вопросы по операторам

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

