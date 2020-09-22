<div align="center">

<h1>Вопросы по Javascript: Объекты</h1>

<a href="https://github.com/dollaween/javascript-questions">На главную</a> | <a href="https://github.com/dollaween/javascript-tests">Тесты</a> | <a href="https://github.com/dollaween/javascript-tests">Задачи</a>

</div>

---

##### 1. Что такое затенение свойств (property shadowing)?

<details><summary><b>Ответ</b></summary>
<p>

**Затенение переменных (property shadowing)** — когда переменная, объявленная в определенной области имеет то же имя, что и переменная, объявленная во внешней области.

```javascript
var currency = 'euro'

function showMeTheMoney() {
  var currency = 'ruble'
  console.log(currency)
}

showMeTheMoney()
```

</p>
</details>

---


---
