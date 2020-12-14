<div align="center">

<h1>Вопросы по Javascript: Регулярные выражения</h1>

<a href="https://github.com/dollaween/javascript-questions">На главную</a> | <a href="https://github.com/dollaween/javascript-tests">Тесты</a> | <a href="https://github.com/dollaween/javascript-tests">Задачи</a>

</div>

---

##### 1. Выберите только буквы (включая русские)

<details><summary><b>Ответ</b></summary>
<p>

```javascript
/[A-z]+|[А-я]+/
```

</p>
</details>

---

##### 2. Выберите все, кроме букв (включая русские) и цифр

<details><summary><b>Ответ</b></summary>
<p>

```javascript
/[^\wа-яА-Я0-9+]/g
```

</p>
</details>

---

Ссылки:
* [Регулярные выражения](https://learn.javascript.ru/regular-expressions)
